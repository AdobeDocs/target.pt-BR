---
keywords: gerenciamento de relacionamento com o cliente;serviço de registro do cliente;crs;crm;mbox3rdpartyid;atributos do cliente;direcionamento;csv;crm;pessoas da adobe experience cloud
description: Saiba como usar os dados de clientes corporativos de um banco de dados de gerenciamento de relacionamento com o cliente (CRM) para o direcionamento de conteúdo no  [!DNL Adobe Target].
title: O que são atributos do cliente e como usá-los?
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 31%

---

# Atributos do cliente

Informações sobre o uso de dados de clientes corporativos dos bancos de dados de Gerenciamento de Relacionamento com o Cliente (CRM) para o direcionamento de conteúdo no [!DNL Adobe Target] usando atributos do cliente no serviço [!DNL Adobe Enterprise Cloud People].

Os dados de clientes corporativos coletados por meio de várias fontes e armazenados em bancos de dados de CRM podem ser usados no [!DNL Target] para fornecer estrategicamente o conteúdo mais relevante para os clientes, concentrando-se principalmente em seu retorno. Os públicos-alvo e atributos do cliente no serviço [!DNL People] (anteriormente chamado de Perfis e Públicos-alvo) unem a coleta e a análise de dados à otimização e realização de testes, o que possibilita a execução de dados e insights.

## Visão geral dos atributos do cliente {#section_B4099971FA4B48598294C56EAE86B45A}

Os [Atributos do Cliente](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html) no serviço [!DNL People] fazem parte do [!DNL Adobe Experience Cloud] e fornecem às empresas uma ferramenta para enviar os dados dos clientes para a plataforma [!DNL Experience Cloud].

Os dados incorporados à [!DNL Experience Cloud] estão disponíveis para todos os fluxos de trabalho da [!DNL Experience Cloud]. [!DNL Target] usa esses dados para direcionar o cliente de retorno com base nos atributos. O [!DNL Adobe Analytics] consome esses atributos e eles podem ser usados para análise e segmentação.

![exemplo de crs](/help/main/c-target/c-visitor-profile/assets/crs.png)

Considere as informações a seguir ao trabalhar com os atributos do cliente e o [!DNL Target]:

* Você precisa atender alguns pré-requisitos para usar o recurso [!UICONTROL Customer attributes] no serviço [!DNL People]. Para obter mais informações, consulte &quot;Pré-requisitos para o upload de atributos do cliente&quot; em [Atributos do cliente](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) na *documentação de Serviços e administração do Experience Cloud*.
* Esteja ciente das limitações relacionadas aos uploads de arquivo, conforme documentado em [Sobre arquivo de dados e fonte de dados para atributos do cliente](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=pt-BR) no *Guia de Componentes da Interface Central do Experience Cloud*. Como prática recomendada:

   * Carregar arquivos grandes únicos (dentro dos [limites especificados](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=pt-BR)). Arquivos grandes únicos são preferidos sobre vários arquivos menores.
   * Se você precisar dividir o upload em vários arquivos, verifique se os arquivos estão totalmente processados antes de enviar novos arquivos. Certifique-se de que cada arquivo em um lote seja totalmente processado antes de submeter o próximo arquivo no lote.

* A [!DNL Adobe] não garante que 100% dos dados do atributo do cliente (perfil do visitante) dos bancos de dados do CRM sejam incorporados à [!DNL Experience Cloud] e, portanto, estejam disponíveis para uso de direcionamento em [!DNL Target]. No design atual, há a possibilidade de uma pequena porcentagem de dados (até 0,1% de grandes lotes de produção) não ser integrada.
* O tempo de vida dos dados de atributos do cliente importados de [!DNL Experience Cloud] para [!DNL Target] depende do tempo de vida do perfil do visitante, que é de 14 dias por padrão. Para obter mais informações, consulte [Duração do Perfil do Visitante](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* Se os parâmetros `vst.*` forem a única coisa que identifica o visitante, o perfil &quot;autenticado&quot; existente não será recuperado, desde que `authState` seja UNAUTHENTICATED (0). O perfil entra em ação somente se `authState` for alterado para AUTENTICADO (1).

  Por exemplo, se o parâmetro `vst.myDataSource.id` for usado para identificar o visitante (onde `myDataSource` é o alias da fonte de dados) e não há MCID ou ID de terceiros, o uso do parâmetro `vst.myDataSource.authState=0` não buscará o perfil, que pode ter sido criado por meio de uma importação dos Atributos do cliente. Se o comportamento desejado for buscar o perfil autenticado, `vst.myDataSource.authState` deve ter o valor de 1 (AUTENTICADO).

* Não é possível enviar os seguintes caracteres em `mbox3rdPartyID`: sinal de adição (+) e barra invertida (/).

## Acessar Atributos do cliente no serviço People

1. No [!DNL Adobe Experience Cloud], clique no ícone de menu ( ![ícone de menu](/help/main/c-target/c-visitor-profile/assets/menu-icon.png) ) e clique em **[!UICONTROL People]**.

   ![Pessoas](/help/main/c-target/c-visitor-profile/assets/people.png)

1. Clique na guia **[!UICONTROL Customer Attributes]**.

   ![guia Atributos do cliente](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Fluxo de trabalho do atributo do cliente para [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Conclua as etapas a seguir para usar os dados do CRM no [!DNL Target], conforme ilustrado abaixo:

![fluxo de trabalho do crm](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

As instruções detalhadas para concluir cada uma das seguintes tarefas podem ser encontradas em [Criar uma fonte de atributo do cliente e carregar o arquivo de dados](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html) na *documentação dos Serviços e Administração do Experience Cloud*.

1. Criar um arquivo de dados.

   Exporte os dados do cliente do formato CRM para o para criar um arquivo .csv. Como alternativa, um arquivo zip ou gzip pode ser criado para o upload. Certifique-se de que a primeira linha do arquivo CSV seja o cabeçalho e que todas as linhas (dados do cliente) tenham o mesmo número de entradas.

   A ilustração a seguir mostra um exemplo de arquivo de dados de clientes corporativos:

   ![amostra de crs](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   A ilustração a seguir mostra um exemplo de arquivo .csv de cliente corporativo:

   ![amostra do csv](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. Criar a fonte de atributo e fazer upload do arquivo de dados.

   Especifique um Nome e uma Descrição da fonte de dados e a ID do alias. A ID do alias é um identificador exclusivo que deve ser usado em seu código de Atributo do Cliente no `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >O nome da fonte de dados e o nome do atributo não podem conter ponto.

   Seu arquivo de dados deve estar em conformidade com os requisitos de upload de arquivo e não deve exceder 100 MB. Se o arquivo for muito grande ou se você tiver dados que precisam ser carregados de forma recorrente, é possível transferir os arquivos para o FTP.

   * **HTTPS:** Você pode arrastar e soltar o arquivo de dados .csv ou clicar em **[!UICONTROL Browse]** para carregar do seu sistema de arquivos.
   * **FTP:** clique no link do FTP para [carregar o arquivo por meio do FTP](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). O primeiro passo é fornecer uma senha para o servidor de FTP fornecido pela Adobe. Especifique a senha e clique em **[!UICONTROL Done]**.

   Agora transfira o arquivo CSV/ZIP/GZIP para o servidor FTP. Após a transferência ser bem-sucedida, crie um arquivo com o mesmo nome e a extensão `.fin`. Transfira este arquivo vazio para o servidor. Isso indica um Fim de Transferência e o [!DNL Experience Cloud] começa a processar o arquivo de dados.

1. Validar o esquema.

   O processo de validação permite mapear os nomes de exibição e as descrições aos atributos carregados (sequências, números inteiros, números e assim por diante). Mapeie cada atributo para seu tipo de dados, nome de exibição e descrição corretos.

   Clique em **[!UICONTROL Save]** após a conclusão da validação do esquema. O tempo de upload do arquivo varia dependendo do tamanho.

   ![Validar esquema](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![Carregar esquema](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. Configurar assinaturas e ativar a fonte de atributo.

   Clique em **[!UICONTROL Add Subscription]** e selecione a solução para inscrever esses atributos. [Configurar assinaturas](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) define o fluxo de dados entre o [!DNL Experience Cloud] e as soluções. Ativar a fonte de atributo permite que os dados fluam para as soluções assinadas. Os registros do cliente carregados são combinados com sinais de ID vindos do seu site ou aplicativo.

   ![Configurar solução](/help/main/c-target/c-visitor-profile/assets/solution.png)

   ![Ativar](/help/main/c-target/c-visitor-profile/assets/activate.png)

   Ao executar esta etapa, esteja ciente das seguintes limitações:

   * O tamanho máximo de arquivo para cada upload usando o método de HTTP é de 100 MB.
   * O tamanho máximo de arquivo para cada upload usando o método de FTP é de 4 GB.
   * O número de atributos permitidos para a inscrição: 5 para o [!DNL Target Standard] e 200 para o [!DNL Target Premium].

## Usar os atributos do cliente em [!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}

Você pode usar os atributos do cliente no [!DNL Target] das seguintes maneiras:

### Criação de públicos-alvo de direcionamento

No [!DNL Target], você pode selecionar um atributo do cliente na seção [!UICONTROL Visitor Profile] ao criar um público-alvo. Todos os atributos do cliente têm o prefixo &lt; data_source_name > na lista. Combine esses atributos como necessário a outros atributos de dados para construir públicos-alvo.

![Público-alvo](/help/main/c-target/c-visitor-profile/assets/TargetAudience.png)

### Criação de scripts de perfil usando tokens

Os atributos de cliente podem ser referenciados nos scripts de perfil, usando o formato `crs.get('<Datasource Name>.<Attribute name>')`.

Esse script de perfil pode ser usado diretamente nas ofertas para entrega de atributos que pertencem ao visitante atual.

### Uso de mbox3rdPartyID no seu site para uma implementação e uso bem-sucedidos

Passe `mbox3rdPartyId` como parâmetro para a mbox global dentro do método `targetPageParams()`. O valor de `mbox3rdPartyId` deve ser definido para a ID do cliente que estava presente no arquivo de dados CSV.

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Uso do serviço de Experience Cloud ID.

Se você estiver usando o serviço da Experience Cloud ID, é necessário definir uma ID do cliente e um Estado de autenticação para usar os atributos do cliente no direcionamento. Para obter mais informações, consulte [IDs do cliente e estado de autenticação](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) na *Ajuda do serviço de ID de Experience Cloud*.

Para obter mais informações sobre o uso de atributos do cliente no [!DNL Target], consulte os recursos a seguir:

* [Crie uma fonte de atributo do cliente e carregue o arquivo de dados](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) na *documentação de Serviços e Administração do Experience Cloud*

## Problemas encontrados com frequência pelos clientes {#section_BE0F70E563F64294B17087DE2BC1E74C}

Você pode encontrar os seguintes problemas ao trabalhar com atributos do cliente e [!DNL Target].

>[!NOTE]
>
>Os problemas 1 e 2 causam aproximadamente 60% dos problemas nessa área. O problema 3 causa aproximadamente 30% dos problemas. O problema 4 causa aproximadamente 5% dos problemas. Os 5% restantes são devido a diversos problemas.

### Problema 1: os atributos do cliente são removidos porque o perfil é muito grande

Não há limite de caracteres em um campo específico do perfil do usuário, mas se o perfil for maior que 64 K, ele será truncado, removendo os atributos mais antigos até que o perfil fique abaixo de 64 K novamente.

### Problema 2: Atributos não listados na Biblioteca de público-alvo em [!DNL Target], mesmo depois de vários dias

Isso geralmente é um problema de conexão do pipeline. Como solução, solicite que a equipe dos Atributos do Cliente republique o feed.

### Problema 3: A entrega não está funcionando com base no atributo

O perfil ainda não foi atualizado na borda. Como solução, solicite que a equipe dos Atributos do Cliente republique o feed.

### Problema 4: Problemas de implementação

Esteja ciente dos seguintes problemas de implementação:

* A ID do visitante não foi passada corretamente. ID passada em `mboxMCGVID` em vez de `setCustomerId`.
* A ID do visitante foi passada corretamente, mas o estado de AUTENTICAÇÃO não foi definido como autenticado.
* `mbox3rdPartyId` não foi transmitido corretamente.

### Problema 5: `mboxUpdate` não foi executado corretamente

`mboxUpdate` não foi executado adequadamente com `mbox3rdPartyId`.

### Problema 6: os atributos do cliente não estão sendo importados para o [!DNL Target]

Se você não puder encontrar os dados dos Atributos do Cliente no Destino, verifique se a importação ocorreu nos últimos *x* dias, onde *x* é o valor [Duração do Perfil do Visitante](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) do Destino (14 dias por padrão).

## Vídeo de treinamento: Carregar dados offline usando atributos do cliente ![Selo do tutorial](/help/main/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

Este vídeo mostra como importar CRM offline, suporte técnico, ponto de venda e outros dados de marketing para o serviço [!DNL Experience Cloud People] e como associá-los a visitantes que usam suas IDs conhecidas.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
