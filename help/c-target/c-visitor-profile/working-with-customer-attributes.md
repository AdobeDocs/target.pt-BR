---
keywords: customer record service;crs;crm;mbox3rdpartyid;customer attributes;targeting;csv;crm
description: Informações sobre como usar os dados de clientes corporativos provenientes de um banco de dados de gerenciamento de relacionamento com o cliente (CRM) para o direcionamento de conteúdo no Adobe Target, usando os Atributos do cliente no serviço principal de Perfis e públicos-alvo da Adobe.
title: Atributos do cliente no Adobe Target
subtopic: Getting Started
topic: Standard
uuid: fc3c9a02-30d7-43df-838d-10ce1aa17f16
translation-type: tm+mt
source-git-commit: 7c8705e45b84fb7d49f93e1f3a25392a8d2758a6

---


# Atributos do cliente {#customer-attributes}

Information about using enterprise customer data from a customer relationship management (CRM) databases for content targeting in [!DNL Adobe Target] by using customer attributes in the [!DNL Adobe Enterprise Cloud] core service.

Os dados de clientes corporativos coletados por meio de várias fontes e armazenados em um banco de dados de CRM podem ser usados no [!DNL Target] para entregar estrategicamente o conteúdo mais relevante para os clientes, concentrando-se principalmente em seu retorno. O serviço principal de [!DNL Audiences] (anteriormente chamado de Perfis e Públicos-alvo) unem a coleta e a análise de dados à otimização e realização de testes, o que possibilita a execução de dados e insights.

## Customer attributes overview {#section_B4099971FA4B48598294C56EAE86B45A}

The Audiences core service is part of the [!DNL Adobe Experience Cloud] and provides enterprises a tool to push their customer data to the [!DNL Experience Cloud] platform. Os dados incorporados à [!DNL Experience Cloud] estão disponíveis para todos os fluxos de trabalho da [!DNL Experience Cloud]. [!DNL Target] usa esses dados para direcionar o cliente recorrente com base em atributos. O [!DNL Adobe Analytics] consome esses atributos e eles podem ser usados para análise e segmentação.

![](assets/crs.png)

Considere as seguintes informações ao trabalhar com os atributos do cliente e o [!DNL Target]:

* There are some prerequisite requirements that you must meet before you can use the [!UICONTROL Customer attributes] feature in the [!DNL Audiences] core service. For more information, see &quot;Prerequisites for uploading Customer Attributes&quot; in [Customer attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) in the *Experience Cloud Product documentation*.

   >[!NOTE]
   >
   >[!DNL at.js] (qualquer versão) ou [!DNL mbox.js] versão 58 ou posterior é obrigatório.

* Adobe does not guarantee that 100% of customer attribute (visitor profile) data from CRM databases will be onboarded to the [!DNL Experience Cloud] and, thus, be available for use for targeting in [!DNL Target]. Em nosso design atual, existe a possibilidade de que uma pequena porcentagem de dados não seja incorporada.
* The lifetime of customer attributes data imported from the [!DNL Experience Cloud] to [!DNL Target] depends on the lifetime of the visitor profile, which is 14 days by default. Para obter mais informações, consulte  [Duração do perfil do visitante](../../c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)
* If the `vst.*` parameters are the only thing identifying the visitor, the existing &quot;authenticated&quot; profile will not be fetched as long as `authState` is UNAUTHENTICATED (0). The profile will only come into play if `authState` is changed to AUTHENTICATED (1).

   For example, if the `vst.myDataSource.id` parameter is used to identify the visitor (where `myDataSource` is the data source alias) and there is no MCID or third-party ID, using the parameter `vst.myDataSource.authState=0` won&#39;t fetch the profile that might have been created through a Customer Attributes import. Se o comportamento desejado for buscar o perfil autenticado, o `vst.myDataSource.authState` precisa ter o valor de 1 (AUTENTICADO).

* Não é possível enviar os seguintes caracteres em `mbox3rdPartyID`: sinal de adição (+) e barra invertida (/).

## Customer attribute workflow for Target {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Conclua as etapas a seguir para usar os dados do CRM no [!DNL Target], conforme ilustrado abaixo:

![](assets/crm_workflow.png)

Detailed instructions for completing each of the following tasks can be found in [Create a customer attribute source and upload the data file](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html) in the *Experience Cloud Product Documentation*.

1. Criar um arquivo de dados.

   Exporte os dados do cliente do formato CRM para o CSV para criar um arquivo .csv. Como alternativa, um arquivo zip ou gzip pode ser criado para o upload. Verifique se a primeira linha do arquivo CSV é o cabeçalho e se todas as linhas (dados do cliente) têm o mesmo número de entradas.

   ![](assets/CRS_sample.png)

   ![](assets/CRS_CSV_sample.png)

1. Criar a fonte de atributo e fazer upload do arquivo de dados.

   Especifique um Nome e uma Descrição da fonte de dados e a ID do alias. A ID do alias é uma ID exclusiva para ser usada no código do atributo do cliente em `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >O nome da fonte de dados e o nome do atributo não podem conter ponto.

   Os arquivos de dados de até 100 MB podem ser enviados usando o método de HTTP. Arquivos maiores que 100 MB, até 4 GB, podem ser carregados por FTP.

   * **HTTPS:** Você pode arrastar e soltar o arquivo de dados .csv ou clicar em **[!UICONTROL Procurar]** para fazer upload do seu sistema de arquivos.
   * **FTP:** Clique no link FTP para [carregar o arquivo por FTP](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). O primeiro passo é fornecer uma senha para o servidor de FTP fornecido pela Adobe. Specify the password, then click **[!UICONTROL Done]**.

      Agora transfira o arquivo CSV/ZIP/GZIP para o servidor FTP. Depois que a transferência de arquivos for bem-sucedida, crie um novo arquivo com o mesmo nome e extensão .fin. Transfira este arquivo vazio para o servidor. This indicates a End Of Transfer and the [!DNL Experience Cloud] starts to process the data file.

1. Validar o esquema.

   O processo de validação permite mapear os nomes de exibição e as descrições aos atributos carregados (sequências, números inteiros, números e assim por diante). Mapeie cada atributo para seu tipo de dados, nome de exibição e descrição corretos.

   Click **[!UICONTROL Save]** after the schema validation is complete. O tempo de upload do arquivo varia dependendo do tamanho.

   ![](assets/SchemaValidate.png)

   ![](assets/upload1.png)

1. Configurar assinaturas e ativar a fonte de atributo.

   Clique em **[!UICONTROL Adicionar assinatura]**, em seguida, selecione a solução para inscrever esses atributos. [Configurar assinaturas](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html) configura o fluxo de dados entre as soluções [!DNL Experience Cloud] e. Ativar a fonte de atributo permite que os dados fluam para as soluções assinadas. Os registros do cliente carregados são combinados com sinais de ID vindos do seu site ou aplicativo.

   ![](assets/solution.png)

   ![](assets/activate.PNG)

   Ao executar esta etapa, esteja ciente das seguintes limitações:

   * O tamanho máximo de arquivo para cada upload usando o método de HTTP é de 100 MB.
   * O tamanho máximo de arquivo para cada upload usando o método de FTP é de 4 GB.
   * O número de atributos permitidos para a inscrição: 5 para o [!DNL Target Standard] e 200 para o [!DNL Target Premium].

## Usar os atributos do cliente no Target {#section_107E3A0F0EC7478E82E6DBD17B30B756}

Você pode usar os atributos do cliente no [!DNL Target] das seguintes maneiras:

### Criação de públicos-alvo de direcionamento

No [!DNL Target], você pode selecionar um atributo do cliente na seção Perfil do visitante ao criar um público-alvo.  Todos os atributos do cliente têm o prefixo &lt; data_source_name > na lista. Combine esses atributos como necessário a outros atributos de dados para construir públicos-alvo.

![Público-alvo](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### Criação de scripts de perfil usando tokens

Os atributos de cliente podem ser referenciados nos scripts de perfil, usando o formato `crs.get('<Datasource Name>.<Attribute name>')`.

Esse script de perfil pode ser usado diretamente nas ofertas para entrega de atributos que pertencem ao visitante atual.

### Uso de mbox3rdPartyID no seu site para uma implementação e uso bem-sucedidos

Pass `mbox3rdPartyId` as a parameter to the global mbox inside the `targetPageParams()` method. The value of `mbox3rdPartyId` should be set to the customer ID that was present in the CSV data file.

```
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Uso do serviço de Experience Cloud ID.

Se você estiver usando o serviço de Experience Cloud ID, será necessário definir uma ID do cliente e um Estado de autenticação para usar os atributos do cliente no direcionamento. For more information, see [Customer IDs and Authentication State](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html) in the *Experience Cloud Identity Service Help*.

Para obter mais informações sobre o uso de atributos do cliente no [!DNL Target], consulte os recursos a seguir:

* [Crie uma fonte de atributo do cliente e faça upload do arquivo](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html) de dados na Documentação do produto da *Experience Cloud*
* [Atributos do cliente: quanto mais você souber, melhor se conectará](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/) no *Blog de Marketing digital*

## Issues frequently encountered by customers {#section_BE0F70E563F64294B17087DE2BC1E74C}

Você pode encontrar os seguintes problemas ao trabalhar com atributos do cliente e o [!DNL Target]:

| Problema | Detalhes |
|--- |--- |
| Os atributos do cliente são removidos, pois o perfil é muito grande | Não há limite de caracteres em um campo específico do perfil do usuário, mas se o perfil for maior que 64 K, ele será truncado, removendo os atributos mais antigos até que o perfil fique abaixo de 64 KB novamente. |
| Atributos não listados na Biblioteca de público-alvo no [!DNL Target], mesmo depois de vários dias | Isso geralmente é um problema de conexão do pipeline. Como solução, solicite que a equipe dos Atributos do Cliente republique o feed. |
| A entrega não funciona com base no atributo | O perfil ainda não foi atualizado na borda. Como solução, solicite que a equipe dos Atributos do Cliente republique o feed. |
| Problemas de implementação | Esteja ciente dos seguintes problemas de implementação:<ul><li>A ID do visitante não foi passada corretamente. The ID was passed in `mboxMCGVID` instead of `setCustomerId`.</li><li>A ID do visitante foi passada corretamente, mas o estado de AUTENTICAÇÃO não foi definido como autenticado.</li><li>`mbox3rdPartyId` não foi transmitido corretamente.</li> |
| `mboxUpdate` não foi executado adequadamente | `mboxUpdate`O não foi executado adequadamente com `mbox3rdPartyId`. |
| Os atributos do cliente não estão sendo importados para o Target | If you cannot find Customer Attributes data in Target, ensure that the import occurred within the last *x* days where *x* is the Target [Visitor Profile Lifetime](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) value (14 days by default). |

Os problemas nas linhas 1 e 2 acima causam aproximadamente 60% dos problemas nessa área. Os problemas na linha 3 causam aproximadamente 30% dos problemas. O problema na linha 4 causa aproximadamente 5% dos problemas. Os 5% restantes são devido a diversos problemas.

## Vídeo de treinamento: Fazer upload de dados offline usando atributos do cliente {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8} Etiqueta ![do tutorial](/help/assets/tutorial.png)

Este vídeo mostra como importar CRM offline, help desk, ponto de venda e outros dados de marketing para o serviço de Pessoas da Experience Cloud e associá-los aos visitantes usando suas IDs conhecidas.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
