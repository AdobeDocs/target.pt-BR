---
keywords: customer relationship management;customer record service;crs;crm;mbox3rdpartyid;customer attributes;targeting;csv;crm;adobe experience cloud people
description: Informações sobre o uso de dados de clientes corporativos em bancos de dados de gerenciamento de relacionamento com o cliente (CRM) para direcionamento de conteúdo no Adobe Target usando Atributos do cliente no serviço principal do Adobe Experience Cloud People.
title: Atributos do cliente no Adobe Target
feature: visitor profiles
subtopic: Getting Started
topic: Standard
uuid: fc3c9a02-30d7-43df-838d-10ce1aa17f16
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '1508'
ht-degree: 40%

---


# Atributos do cliente {#customer-attributes}

Information about using enterprise customer data from Customer Relationship Management (CRM) databases for content targeting in [!DNL Adobe Target] by using customer attributes in the [!DNL Adobe Enterprise Cloud People] core service.

Enterprise customer data collected through multiple sources and stored inside CRM databases can be used in [!DNL Target] to strategically deliver the most relevant content to customers, specifically focusing on returning customers. Audiences and customer attributes in the [!DNL People] core service (formerly Profiles and Audiences) brings together data collection and analysis with testing and optimization, making data and insights actionable.

## Customer attributes overview {#section_B4099971FA4B48598294C56EAE86B45A}

[Os Atributos](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) do cliente no serviço [!DNL People] principal fazem parte do [!DNL Adobe Experience Cloud] e fornecem às empresas uma ferramenta para encaminhar os dados do cliente para a [!DNL Experience Cloud] plataforma.

Os dados incorporados à [!DNL Experience Cloud] estão disponíveis para todos os fluxos de trabalho da [!DNL Experience Cloud]. [!DNL Target] usa esses dados para direcionar o cliente recorrente com base em atributos. O [!DNL Adobe Analytics] consome esses atributos e eles podem ser usados para análise e segmentação.

![exemplo de crs](/help/c-target/c-visitor-profile/assets/crs.png)

Considere as seguintes informações ao trabalhar com os atributos do cliente e o [!DNL Target]:

* There are some prerequisite requirements that you must meet before you can use the [!UICONTROL Customer attributes] feature in the [!DNL People] core service. For more information, see &quot;Prerequisites for uploading Customer Attributes&quot; in [Customer attributes](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) in the *Experience Cloud and Core Services Product documentation*.

   >[!NOTE]
   >
   >[!DNL at.js] (qualquer versão) ou [!DNL mbox.js] versão 58 ou posterior é obrigatório.

* [!DNL Adobe] não garante que 100% dos dados do atributo do cliente (perfil do visitante) dos bancos de dados do CRM serão integrados ao [!DNL Experience Cloud] e, portanto, estarão disponíveis para uso na definição de metas no [!DNL Target]. Em nosso projeto atual, há a possibilidade de uma pequena porcentagem de dados (até 0,1% dos grandes lotes de produção) não ser integrada.
* The lifetime of customer attributes data imported from the [!DNL Experience Cloud] to [!DNL Target] depends on the lifetime of the visitor profile, which is 14 days by default. Para obter mais informações, consulte  [Duração do perfil do visitante](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD)
* If the `vst.*` parameters are the only thing identifying the visitor, the existing &quot;authenticated&quot; profile will not be fetched as long as `authState` is UNAUTHENTICATED (0). The profile will come into play only if `authState` is changed to AUTHENTICATED (1).

   For example, if the `vst.myDataSource.id` parameter is used to identify the visitor (where `myDataSource` is the data source alias) and there is no MCID or third-party ID, using the parameter `vst.myDataSource.authState=0` won&#39;t fetch the profile that might have been created through a Customer Attributes import. If the desired behavior is to fetch the authenticated profile, the `vst.myDataSource.authState` must have the value of 1 (AUTHENTICATED).

* Não é possível enviar os seguintes caracteres em `mbox3rdPartyID`: sinal de adição (+) e barra invertida (/).

## Acessar atributos do cliente no serviço principal de Pessoas

1. No [!DNL Adobe Experience Cloud], clique no ícone de menu ( ícone ![de](/help/c-target/c-visitor-profile/assets/menu-icon.png) menu ) e clique em **[!UICONTROL Pessoas]**.

   ![Pessoas](/help/c-target/c-visitor-profile/assets/people.png)

1. Clique na guia Atributos **[!UICONTROL do]** cliente.

   ![Guia Atributos do cliente](/help/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Customer attribute workflow for Target {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Conclua as etapas a seguir para usar os dados do CRM no [!DNL Target], conforme ilustrado abaixo:

![fluxo de trabalho do crm](/help/c-target/c-visitor-profile/assets/crm_workflow.png)

Detailed instructions for completing each of the following tasks can be found in [Create a customer attribute source and upload the data file](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html) in the *Experience Cloud and Core Services Product Documentation*.

1. Criar um arquivo de dados.

   Exporte os dados do cliente do formato CRM para o CSV para criar um arquivo .csv. Como alternativa, um arquivo zip ou gzip pode ser criado para o upload. Verifique se a primeira linha do arquivo CSV é o cabeçalho e se todas as linhas (dados do cliente) têm o mesmo número de entradas.

   A ilustração a seguir mostra um exemplo de arquivo de dados do cliente empresarial:

   ![amostra de crs](/help/c-target/c-visitor-profile/assets/CRS_sample.png)

   A ilustração a seguir mostra um exemplo de arquivo .csv de cliente empresarial:

   ![amostra csv](/help/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. Criar a fonte de atributo e fazer upload do arquivo de dados.

   Especifique um Nome e uma Descrição da fonte de dados e a ID do alias. A ID do alias é uma ID exclusiva para ser usada no código do atributo do cliente em `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >O nome da fonte de dados e o nome do atributo não podem conter ponto.

   Seu arquivo de dados deve estar em conformidade com os requisitos de upload do arquivo e não deve exceder 100 MB. Se o arquivo for muito grande ou se você tiver dados que precisarão ser carregados de forma recorrente, é possível fazer o FTP dos arquivos.

   * **HTTPS:** Você pode arrastar e soltar o arquivo de dados .csv ou clicar em **[!UICONTROL Procurar]** para fazer upload do seu sistema de arquivos.
   * **FTP:** Clique no link FTP para [carregar o arquivo por FTP](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). O primeiro passo é fornecer uma senha para o servidor de FTP fornecido pela Adobe. Specify the password, then click **[!UICONTROL Done]**.

   Agora transfira o arquivo CSV/ZIP/GZIP para o servidor FTP. Depois que a transferência de arquivos for bem-sucedida, crie um novo arquivo com o mesmo nome e extensão .fin. Transfira este arquivo vazio para o servidor. This indicates a End Of Transfer and the [!DNL Experience Cloud] starts to process the data file.

1. Validar o esquema.

   O processo de validação permite mapear os nomes de exibição e as descrições aos atributos carregados (sequências, números inteiros, números e assim por diante). Mapeie cada atributo para seu tipo de dados, nome de exibição e descrição corretos.

   Click **[!UICONTROL Save]** after the schema validation is complete. O tempo de upload do arquivo varia dependendo do tamanho.

   ![Validar schema](/help/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![Carregar schema](/help/c-target/c-visitor-profile/assets/upload1.png)

1. Configurar assinaturas e ativar a fonte de atributo.

   Clique em **[!UICONTROL Adicionar assinatura]**, em seguida, selecione a solução para inscrever esses atributos. [Configure o subscrição](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/subscription.html) para configurar o fluxo de dados entre as soluções [!DNL Experience Cloud] e. Ativar a fonte de atributo permite que os dados fluam para as soluções assinadas. Os registros do cliente carregados são combinados com sinais de ID vindos do seu site ou aplicativo.

   ![Configurar solução](/help/c-target/c-visitor-profile/assets/solution.png)

   ![Ativar](/help/c-target/c-visitor-profile/assets/activate.png)

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

* [Crie uma fonte de atributo do cliente e faça upload do arquivo](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/t-crs-usecase.html) de dados na Documentação do produto do *Experience Cloud*
* [Atributos do cliente: quanto mais você souber, melhor se conectará](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/) no *Blog de Marketing digital*

## Issues frequently encountered by customers {#section_BE0F70E563F64294B17087DE2BC1E74C}

Você pode encontrar os seguintes problemas ao trabalhar com atributos do cliente e o [!DNL Target].

>[!NOTE]
>
>Os problemas 1 e 2 causam aproximadamente 60% dos problemas nessa área. O problema 3 causa aproximadamente 30% dos problemas. O problema 4 causa aproximadamente 5% dos problemas. Os 5% restantes são devido a diversos problemas.

### Problema 1: Os atributos do cliente são removidos porque o perfil é muito grande

Não há limite de caracteres em um campo específico do perfil do usuário, mas se o perfil for maior que 64 K, ele será truncado, removendo os atributos mais antigos até que o perfil fique abaixo de 64 KB novamente.

### Issue 2: Attributes not listing in the Audience Library in [!DNL Target], even after several days

Isso geralmente é um problema de conexão do pipeline. Como solução, solicite que a equipe dos Atributos do Cliente republique o feed.

### Problema 3: Delivery que não funciona com base no atributo

O perfil ainda não foi atualizado na borda. Como solução, solicite que a equipe dos Atributos do Cliente republique o feed.

### Problema 4: Questões de implementação

Esteja ciente dos seguintes problemas de implementação:

* A ID do visitante não foi passada corretamente. The ID was passed in `mboxMCGVID` instead of `setCustomerId`.
* A ID do visitante foi passada corretamente, mas o estado de AUTENTICAÇÃO não foi definido como autenticado.
* `mbox3rdPartyId` não foi transmitido corretamente.

### Problema 5: `mboxUpdate` não executado corretamente

`mboxUpdate`O não foi executado adequadamente com `mbox3rdPartyId`.

### Issue 6: Customer attributes are not being imported into [!DNL Target]

If you cannot find Customer Attributes data in Target, ensure that the import occurred within the last *x* days where *x* is the Target [Visitor Profile Lifetime](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) value (14 days by default).

## Training video: Upload Offline Data using Customer Attributes ![Tutorial badge](/help/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

This video shows you how to import offline CRM, help desk, point-of-sale, and other marketing data into the [!DNL Experience Cloud People] service and associate it with visitors using their known IDs.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
