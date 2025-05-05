---
keywords: recommendations feed;feed;SAINT;ftp;csv;classificações;análises classificações
description: Saiba como os feeds importam entidades para o  [!DNL Adobe Target] [!DNL Recommendations] usando arquivos CSV, o formato de feed  [!DNL Google Product Search] e as [!DNL Analytics] classificações de produto.
title: Como usar [!UICONTROL Feeds] no  [!DNL Target Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 7b336a9e-23f4-4b09-9c8f-b9cb68162b1b
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '2417'
ht-degree: 38%

---

# Feeds

Use os feeds para importar entidades em [!DNL Adobe Target] [!DNL Recommendations]. As entidades podem ser enviadas usando arquivos CSV, o formato de feed [!DNL Google Product Search] e as classificações de produto [!DNL Adobe Analytics].

## Visão geral dos feeds {#concept_D1E9C7347C5D4583AA69B02E79607890}

Os feeds permitem passar [Entidades](/help/main/c-recommendations/c-products/products.md) ou aumentar seus dados de mbox com informações que ou não estão disponíveis na página, ou não são seguras para serem enviadas diretamente da página. Por exemplo, margem, Custo de Mercadorias Vendidas (COGS) e assim por diante.

Os feeds também permitem passar informações detalhadas do item para [!DNL Recommendations], como ID do produto, categoria, nome, mensagem e outros atributos.

Você pode escolher quais colunas do seu arquivo de classificações do produto [!DNL Target] ou do arquivo [!DNL Google Product Search] você deseja enviar para o servidor [!DNL Recommendations].

Esses dados sobre cada item podem ser usados para:

* Exibir valores em designs
* Definir regras de inclusão de critérios
* Classificar itens em diferentes coleções
* Aplicar exclusões às recomendações

As descrições de item podem ser passadas para [!DNL Target] usando feeds ou mboxes. Se [!DNL Target] coletar dados usando um feed de entidade e uma mbox, os dados mais recentes prevalecerão. Normalmente, os dados mais recentes vêm de uma mbox, porque ela é vista com mais frequência. Se, por coincidência, dados do feed de entidade e da mbox cheguem ao mesmo tempo, os dados da mbox serão usados.

A lista [!UICONTROL Feeds] ( **[!UICONTROL Recommendations]** > **[!UICONTROL Feeds]**) fornece informações sobre os feeds criados.

A página [!UICONTROL Feeds] contém as seguintes colunas:

* **Nome**: o nome do feed especificado durante a criação. Para editar o nome de um feed, edite o próprio feed. Quando você salva o feed com o novo nome, ele é atualizado.
* **Status**: o [status](/help/main/c-recommendations/c-products/feeds.md#concept_E475986720D1400999868B3DFD14A7A0) atual do feed.
* **Tipo**: os tipos incluem [CSV](/help/main/c-recommendations/c-products/feeds.md#section_65CC1148C7DD448FB213FDF499D35FCA), [[!DNL Google Product Feed]](/help/main/c-recommendations/c-products/feeds.md#section_8EFA98B5BC064140B3F74534AA93AFFF) e [Classificações do Analytics](/help/main/c-recommendations/c-products/feeds.md#section_79E430D2C75443BEBC9AA0916A337E0A).
* **Itens**: exibe o número de itens no feed.
* **Agenda**: exibe a agenda de atualização do feed: [!UICONTROL Daily], [!UICONTROL Weekly], [!DNL Every 2 Weeks] ou [!UICONTROL Never].
* **Última atualização**: exibe a data e a hora em que o feed foi atualizado pela última vez e o nome da pessoa que atualizou o feed.

Clique no ícone [!UICONTROL Customize Table] ( ![Ícone Personalizar tabela](/help/main/assets/icons/ColumnSetting.svg) ) para selecionar ou desmarcar as colunas que deseja exibir.

Clique no ícone [!UICONTROL Information] ( ![Ícone de informações](/help/main/assets/icons/InfoOutline.svg) ) para exibir um cartão com a data do último carregamento e a URL do feed.

Clique no ícone [!UICONTROL More Actions] ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmallList.svg) ) para acessar as seguintes ações: [!UICONTROL Deactivate], [!DNL Edit], [!UICONTROL Copy] e [!UICONTROL Delete].

>[!IMPORTANT]
>
>As entidades e os atributos de entidade carregados expiram após 61 dias. Isso significa o seguinte:
>
>* O feed deve ser executado pelo menos uma vez por mês para garantir que o conteúdo do catálogo não expire.
>* Remover um item do seu arquivo de feed não remove esse item do catálogo. Para remover o item do catálogo, exclua manualmente o item por meio da interface ou da API [!DNL Target]. Ou modifique os atributos do item (como inventário) para garantir que o item seja excluído da consideração.

## Tipos de Source

As entidades podem ser enviadas usando arquivos CSV, o formato de feed [!DNL Google Product Search] e as classificações de produto [!DNL Adobe Analytics].

### CSV {#section_65CC1148C7DD448FB213FDF499D35FCA}

Você pode criar um arquivo .csv usando o formato de upload CSV proprietário do [!DNL Adobe]. O arquivo contém as informações de exibição sobre os atributos reservados e personalizados para os seus produtos. Para fazer o upload dos atributos específicos à sua implementação, substitua `CustomN` na linha de cabeçalho pelo nome do atributo que deseja usar. No exemplo abaixo, `entity.Custom1` foi substituído por: `entity.availability`. Em seguida, você pode fazer o upload em massa do arquivo para o servidor [!DNL Recommendations].

O uso do formato .csv tem as seguintes vantagens em relação ao formato de feed [!DNL Google]:

* O formato .csv não requer mapeamentos de campo.
* O formato .csv suporta atributos de vários valores (veja o exemplo abaixo).
* O formato .csv suporta até 100 atributos personalizados. Se você precisar de mais de 100 atributos personalizados, pode criar um segundo arquivo de feed com um conjunto diferentes de atributos personalizados.

Use o método de upload em massa para enviar informações de exibição se não houver mboxes na página ou se desejar complementar as informações de exibição com itens que não estejam disponíveis no site. Por exemplo, talvez você queira enviar informações sobre o inventário que podem não estar publicadas no seu site.

Qualquer dado carregado por meio do arquivo .csv, feed de produto do Google ou feed de classificação de produto do [!DNL Analytics] substitui o valor do atributo da entidade existente no banco de dados. Se você enviar informações de preço via solicitações de mbox e depois enviar valores de preço diferentes no arquivo, os valores no arquivo substituem os valores enviados na solicitação de mbox. Uma exceção a essa regra é o atributo de entidade `categoryId` no qual os valores de categoria são anexados em vez de substituídos até o limite de 250 caracteres.

>[!IMPORTANT]
>
>Não coloque os valores entre aspas duplas ( &quot; ) no arquivo .csv, a menos que seja intencional. Se colocar os valores entre aspas duplas, você poderá removê-los ao incluí-los em outro conjunto de aspas duplas. As aspas duplas que não forem removidas evitarão que o feed do Recommendations carregue corretamente.

Por exemplo, a sintaxe a seguir está incorreta:

```
"Apples "Bananas" Grapes"",
```

A sintaxe a seguir está correta:

```
"Apples ""Bananas"" Grapes""",
```

>[!NOTE]
>
>Não é possível substituir um valor existente por um valor em branco. Passe outro valor em seu lugar para substituir o valor existente. No caso de um preço de venda, uma solução comum é transmitir uma mensagem &quot;NULA&quot; real ou alguma outra mensagem. Você poderá escrever uma regra do modelo para excluir itens com esse valor.

O produto estará disponível na interface de Admin aproximadamente duas horas depois de ter carregado a entidade com sucesso.

A seguir, encontra-se um código de exemplo para um arquivo .csv:

```
## RECSRecommendations Upload File 
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines. 
## RECS 
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left. 
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'. 
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations. 
## RECSentity.id,entity.name,entity.categoryId,entity.message,entity.thumbnailUrl,entity.value,entity.pageUrl,entity.inventory,entity.margin,entity.last_updated_by,entity.multi_english,entity.availability,entity.tax_country,entity.tax_region,entity.tax_rate,entity.product_type,entity.item_group_id,entity.color,entity.size,entity.brand,entity.gtin 
na3456,RipCurl Watch with Titanium Dial,Watches & Sport,Cutting edge titanium with round case,https://example.com/s7/na3456_Viewer,425,https://example.com/shop/en-us/na3456_RipCurl,24,0.25,csv,"[""New"",""Web"",""Sales"",""[1,2,34,5]""]",in stock,US,CA,9.25,Shop by Category > Watches,dz1,Titanium,44mm,RipCurl,"075380 01050 5" 
na3457,RipCurl Watch with Black Dial,Watches & Sport,Cutting edge matte black with round case,https://example.com/s7/na3457_Viewer,275,https://example.com/shop/en-us/na3457_RipCurl,24,0.27,csv,"[""New"",""Web"",""Sales"",""[1,2,34,5]""]",in stock,US,CA,9.25,Shop by Category > Watches,dz1,Black,44mm,RipCurl,"075340 01060 7"
```

### [!DNL Google] {#section_8EFA98B5BC064140B3F74534AA93AFFF}

O tipo de feed [!DNL Google Product Search] usa o formato [!DNL Google]. Isso é diferente do formato de upload CSV proprietário do [!DNL Adobe].

Se você tiver um [!DNL Google Product Feed] existente, poderá usá-lo como seu arquivo de importação.

>[!NOTE]
>
>Não é necessário usar dados de [!DNL Google]. [!DNL Recommendations] usa o mesmo formato que [!DNL Google]. Você pode usar este método para atualizar qualquer dado que possua e usar os recursos de programação disponíveis. No entanto, você deve manter os nomes de atributo predefinidos [!DNL Google] ao configurar o arquivo.

A maioria dos varejistas carrega produtos para [!DNL Google]; portanto, quando um visitante usa a pesquisa de produto [!DNL Google], seus produtos são exibidos. [!DNL Recommendations] segue a especificação [!DNL Google] exatamente para feeds de entidade. Os feeds de entidade podem ser enviados para [!DNL Recommendations] via .xml, .txt ou .tsv e podem usar os [atributos definidos pelo Google](https://support.google.com/merchants/answer/188494?hl=en&amp;topic=2473824&amp;ctx=topic#US). Os resultados podem ser pesquisados nas [[!DNL Google] páginas de compra](https://www.google.com/prdhp).

>[!NOTE]
>
>O método POST deve ser permitido no servidor que está hospedando o conteúdo do feed [!DNL Google].

Como [!DNL Recommendations] usuários já configuram feeds .xml ou .txt para enviar a [!DNL Google] via URL ou FTP, os feeds de entidade aceitam esses dados do produto e os usam para criar o catálogo de recomendações. Especifique onde esse feed existe, e o servidor de recomendações recuperará os dados.

Se você usar [!DNL Google Product Search] para o carregamento do feed de entidade, ainda deverá ter uma mbox de página de produto na página se quiser mostrar recomendações ou rastrear exibições de produto para entrega de algoritmo com base nas exibições.

Os feeds [!DNL Google] não dão suporte a vários valores para um atributo personalizado.

O feed é executado no momento em que você o salva e ativa. Ela é executada no momento em que você salva o feed e, em seguida, todos os dias uma hora depois.

Este é um exemplo de código para um arquivo .xml de feed [!DNL Google Product Search]:

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?> 
<feed xmlns="https://www.w3.org/2005/Atom" xmlns:ns2="https://base.google.com/ns/1.0" xmlns:ns3="https://base.google.com/cns/1.0"> 
    <title>Product Feed</title> 
    <link href="https://example.com"/> 
    <updated>2017-12-13T08:45:04.918-08:00</updated> 
    <author> 
        <name>Product Feed Author</name> 
    </author> 
    <id>https://example.com</id> 
    <entry> 
        <title>RipCurl Watch with Titanium Dial</title> 
        <description>Cutting edge Titanium with Round case</description> 
        <ns2:id>na3452</ns2:id> 
        <ns2:link>https://example.com/shop/en-us/na3452_RipCurl</ns2:link> 
        <ns2:availability>in stock</ns2:availability> 
        <ns2:condition>NEW</ns2:condition> 
        <ns2:google_product_category>Watches &amp; Sport</ns2:google_product_category> 
        <ns2:gtin>075380 01050 5</ns2:gtin> 
        <ns2:image_link>https://example.com/s7/na3452_Viewer</ns2:image_link> 
        <ns2:mobile_link>https://m.example.com/s7/na3452_Viewer</ns2:mobile_link> 
        <ns2:mpn>71050</ns2:mpn> 
        <ns2:price>425</ns2:price> 
        <ns2:product_review_average>5.0</ns2:product_review_average> 
        <ns2:product_review_count>30</ns2:product_review_count> 
        <ns2:product_type>Shop by Category > Watches </ns2:product_type> 
        <ns2:brand>RipCurl</ns2:brand> 
        <ns2:sale_price>375</ns2:sale_price> 
        <ns2:tax> 
          <ns2:country>US</ns2:country> 
          <ns2:region>CA</ns2:region> 
          <ns2:rate>9.25</ns2:rate> 
          <ns2:tax_ship>y</ns2:tax_ship> 
        </ns2:tax> 
        <ns2:is_bundle>N</ns2:is_bundle> 
    </entry> 
    <entry> 
        <title>RipCurl Watch with Black Dial</title> 
        <description>Cutting edge matte black with Round case</description> 
        <ns2:id>na3453</ns2:id> 
        <ns2:link>https://example.com/shop/en-us/na3453_RipCurl</ns2:link> 
        <ns2:availability>in stock</ns2:availability> 
        <ns2:condition>NEW</ns2:condition> 
        <ns2:google_product_category>Watches &amp; Sport</ns2:google_product_category> 
        <ns2:gtin>075380 013450 5</ns2:gtin> 
        <ns2:image_link>https://example.com/s7/na3453_Viewer</ns2:image_link> 
        <ns2:mobile_link>https://m.example.com/s7/na3453_Viewer</ns2:mobile_link> 
        <ns2:mpn>71050</ns2:mpn> 
        <ns2:price>275</ns2:price> 
        <ns2:product_review_average>4.8</ns2:product_review_average> 
        <ns2:product_review_count>23</ns2:product_review_count> 
        <ns2:product_type>Shop by Category > Watches </ns2:product_type> 
        <ns2:brand>RipCurl</ns2:brand> 
        <ns2:sale_price>249</ns2:sale_price> 
        <ns2:tax> 
          <ns2:country>US</ns2:country> 
          <ns2:region>CA</ns2:region> 
          <ns2:rate>9.25</ns2:rate> 
          <ns2:tax_ship>y</ns2:tax_ship> 
        </ns2:tax> 
        <ns2:is_bundle>N</ns2:is_bundle> 
    </entry> 
</feed> 
```

Este é um exemplo de código para um arquivo .tsv de feed [!DNL Google Product Search]:

```
id    title    description    link    price    condition    availability    image_link    tax    shipping_weight    shipping    google_product_category    product_type    item_group_id    color    size    gender    age_group    pattern    brand    gtin    mpn 
na3454    RipCurl Watch with Titanium Dial    Cutting edge titanium with round case    https://example.com/shop/en-us/na3454_RipCurl    425    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075380 01050 5    DZ1437 
na3455    RipCurl Watch with Black Dial    Cutting edge matte black with round case    https://example.com/shop/en-us/na3455_RipCurl    275    new    in stock    https://example.com/s7/na3452_Viewer    US:CA:9.25:y    1.5 oz    US:::0.00 USD    Watches & Sport    Shop by Category > Watches    dz1    Black    44mm    male    adult    Solid    RipCurl    075340 01060 7    DZ1446
```

### Classificações de produto de [!DNL Analytics] {#section_79E430D2C75443BEBC9AA0916A337E0A}

A classificação do Produto [!DNL Adobe Analytics] é a única classificação disponível para recomendações. Para obter mais informações sobre esse arquivo de classificação, consulte [Sobre classificações](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=pt-BR) no guia *Componentes do Analytics*. É possível que nem todas as informações que você precisa para as recomendações estejam disponíveis em sua implementação atual do, portanto, siga este guia do usuário se desejar adicioná-las ao arquivo de classificações.

>[!IMPORTANT]
>
>Antes de importar dados de entidade para [!DNL Recommendations] usando [!DNL Analytics] classificações de produto, esteja ciente de que este não é o método preferido.
>
> Esteja ciente dos seguintes avisos:
>
>* As atualizações para os atributos da entidade têm um atraso adicional de até 24 horas.
>* [!DNL Target] dá suporte somente a [!UICONTROL Product Classifications]. O SKU do produto [!DNL Analytics] deve mapear no mesmo nível que o [!DNL Recommendations] `entity.id`. Classificações personalizadas [!DNL Analytics] podem ser criadas usando [!UICONTROL Adobe Consulting Services]. Entre em contato com o Gerente de contas se tiver dúvidas.

## Criar feed {#steps}

Crie um feed para inserir informações sobre os produtos ou serviços no [!DNL Recommendations].

1. Na interface [!DNL Target], clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Feeds]** > **[!UICONTROL Create Feed]**.

1. Especifique um nome descritivo para o feed.
1. Selecione um **[!UICONTROL Source Type]**.

   * [!UICONTROL CSV]
   * [!UICONTROL Google Product Feed]
   * [!UICONTROL Analytics Classifications]

   Para obter informações sobre os tipos de feed [!UICONTROL CSV] e [!UICONTROL Google Product Feed], consulte [Visão Geral dos Feeds](/help/main/c-recommendations/c-products/feeds.md#concept_D1E9C7347C5D4583AA69B02E79607890). Você também pode [baixar um guia CSV de modelo](/help/main/c-recommendations/c-products/assets/EntityFileUploadTemplate.csv) para ajudar a formatar o feed corretamente.

1. (Condicional) Se você selecionou **[!UICONTROL CSV]** ou **[!UICONTROL Google Product Feed]**, especifique o local em que o feed pode ser acessado.

   * **FTP**: se você selecionar FTP, forneça as informações do servidor FTP, as credenciais de logon, o nome do arquivo e o diretório do FTP. Você pode usar o FTP com SSL (FTPS) para uploads mais seguros.

     Configurações compatíveis do servidor FTP:

      * FTP e FTPS devem ser definidos para usar FTP passivo.
      * Para FTPS, configure o servidor para aceitar as conexões FTPS explícitas.
      * SFTP não é compatível.
      * Você pode especificar manualmente uma porta em que a conexão será iniciada (por exemplo, `ftp://ftp.yoursite.com:2121`). Se você não especificar uma porta, a porta FTP ou FTPS padrão será usada.

   * **URL**: se você selecionar [!UICONTROL URL], especifique a URL.

1. (Condicional) Se você selecionou **[!UICONTROL Analytics Classifications]**, escolha o conjunto de relatórios na lista suspensa.

1. Clique na seta **[!UICONTROL Next]** para exibir as opções de [!UICONTROL Schedule].

1. Selecione uma opção de atualização:

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 Weeks]
   * [!UICONTROL Never]: Não agendar uma atualização. Escolha essa opção se você não quiser que esse feed seja executado.

1. Especifique o tempo em que deseja que o feed seja executado.

   Essa opção é baseada no fuso horário usado no seu navegador. Se desejar usar uma hora em um fuso horário diferente, deve calcular esse tempo de acordo com o seu fuso horário.

1. Clique na seta **[!UICONTROL Next]** para exibir as opções de [!UICONTROL Mapping] e especifique como deseja mapear seus dados para as definições de [!DNL Target].

1. (Opcional) se você deseja que o feed pertença a um ambiente (grupo de hosts), selecione o grupo de hosts.

   Por padrão, o feed pertence a todos os grupos de hosts. Isso garante que esses itens neste feed estejam disponíveis em qualquer ambiente. Para obter mais informações, consulte [Hosts](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

1. Clique em **[!UICONTROL Save]**.

Depois de criar ou editar um feed, ele é executado imediatamente. O feed é atualizado de acordo com os parâmetros definidos. Leva algum tempo para as informações estarem disponíveis. Em primeiro lugar, o feed deve sincronizar, em seguida, ele deve ser processado e indexados antes que possa ser publicado e disponibilizado. O status atual aparece em [Status do Feed](/help/main/c-recommendations/c-products/feeds.md#status) na lista [!UICONTROL Feeds]. Você pode fechar o [!DNL Target] antes que o processo esteja completo e o mesmo continuará.

Enquanto a indexação estiver em andamento, os produtos e cabeçalhos de feed serão exibidos antes que os valores individuais sejam indexados. Isso permite pesquisar e visualizar produtos para que você possa criar coleções, exclusões, designs e atividades antes da conclusão da indexação.

Quando o Status apresentar a mensagem de &quot;Sucesso&quot;, isso significa que o arquivo foi encontrado e analisado corretamente. A informação não está disponível para o uso no [!DNL Recommendations] até que o arquivo seja indexado, o que pode levar algum tempo, dependendo do tamanho do seu arquivo. Se o processo falhar, significa que o arquivo não foi encontrado. Por exemplo, você usou um URL incorreto, suas informações de FTP estavam incorretas ou havia um erro de análise.

## Status do feed e indicadores  {#concept_E475986720D1400999868B3DFD14A7A0}

Informações sobre os status possíveis do feed e seus indicadores.

### Status do feed {#status}

A seguir, estão os possíveis status de um feed:

| Status | Descrição |
|--- |--- |
| [!UICONTROL Syncing] | Os detalhes de configuração do feed estão sendo salvos em [!DNL Target]. |
| [!UICONTROL Sync Failed] | Os detalhes de configuração do feed não puderam ser salvos em [!DNL Target]. Tente novamente. |
| [!UICONTROL No Feed Run] | Você criou um feed, mas ele não foi agendado (a frequência está definida como Nunca). |
| Agendado na *data e hora* | O feed não foi executado, mas está agendado para execução na data e hora especificada. |
| [!UICONTROL Waiting for Download] | [!DNL Target] está se preparando para baixar o arquivo de feed. |
| [!UICONTROL Downloading Feed File] | [!DNL Target] está baixando o arquivo de feed. |
| [!UICONTROL Importing Items] | [!DNL Target] está importando itens do arquivo de feed. |
| Feed importado com êxito no *momento* | [!DNL Target] importou o arquivo de feed para o sistema de entrega de conteúdo. Os atributos do item foram alterados no sistema de entrega de conteúdo e serão refletidos em breve nas recomendações entregues. Se você não vir as alterações esperadas, tente novamente e atualize a página que contém as recomendações.<br>Notas:<ul><li>Se as alterações nos atributos de um item resultarem na exclusão de um item das recomendações, a exclusão será refletida imediatamente. Se um item for recém-adicionado ou se as alterações nos atributos resultarem na exclusão de um item *não mais* das recomendações, isso não será refletido até a atualização do próximo algoritmo, que ocorre em 24 horas.</li><li>Quando esse status é exibido, as atualizações podem ainda não ser refletidas na interface do usuário do [!UICONTROL Catalog Search]. Um status separado está listado em [!UICONTROL Catalog Search], indicando a última vez que o catálogo pesquisável foi atualizado.</li></ul> |
| [!UICONTROL Failed to Index] | Ocorreu uma falha na operação de índice. Tente novamente. |
| [!UICONTROL Server Not Found] | Locais de FTP ou URL inválidos ou não acessíveis. |

Para atualizar um feed (por exemplo, para fazer alterações na sua configuração de feed ou arquivo de feed), abra o feed, faça qualquer alteração desejada e clique em **[!UICONTROL Save]**.

>[!IMPORTANT]
>
>As entidades carregadas expiram após 61 dias. Isso significa que o seu arquivo de feed deve ser carregado pelo menos a cada 60 dias para evitar uma interrupção nas atividades de recomendações. Se um item não estiver incluído em um arquivo de feed (ou em outro método de atualização de entidade) pelo menos uma vez a cada 60 dias, [!DNL Target] deduzirá que o item não é mais relevante e o removerá do catálogo.

### Indicadores de status do feed {#section_3C8A236C5CB84C769A9E9E36B8BFABA4}

Os seguintes indicadores de status do feed são exibidos na coluna [!UICONTROL Status]:

| Indicador de status | Descrição |
|--- |--- |
| Indicador de status verde | Quando um feed acaba de indexar de modo bem-sucedido, um ponto de status verde indica que o feed está em um estado bem-sucedido. |
| Indicador de status amarelo | Quando um feed ou índice de feed é atrasado em 25% da frequência de feed, um ponto de status amarelo é exibido. Por exemplo, um ponto amarelo é exibido para um feed definido para execução diária, se o índice ainda não concluiu seis horas após o tempo agendado. Observação: assim que o status do feed for &quot;Aguardando para fila de índice&quot;, os novos valores atualizados estarão disponíveis no processamento de entrega e critérios. |
| Indicador de status branco | Quando um feed não está agendado, um ponto de status branco indica que o feed ainda não foi executado. |
| Indicador de status vermelho | Se o feed não carregar dados no servidor, um indicador de status vermelho será mostrado. |

Considere os exemplos a seguir:

**Exemplo 1:**

* Primeiro dia: o feed é processado diariamente às 9h PST.
* Dia dois: são 15:30 e o feed aina não executou desde 9h.

O status deve ser amarelo, pois o índice deveria ter sido executado há aproximadamente 6,5 horas. 6,5 horas +24 é 127% da janela de feed.

**Exemplo 2:**

* 1 de janeiro: o feed mensal é processado às 9:00 PST.
* 3 de fevereiro: são 10h e o feed não é executado há um mês, um dia e uma hora.

O status deve ser amarelo, pois o índice deveria ter sido executado há aproximadamente um dia e uma hora. Embora isso seja somente (31+(1/25))/30 = 1,03% da configuração de frequência, ultrapassou o máximo de atraso de um dia.

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Noções básicas sobre feeds no Recommendations (3:01) ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo contém as seguintes informações:

* Entender a finalidade dos feeds
* Entender o valor dos feeds

>[!VIDEO](https://video.tv.adobe.com/v/27695)

### Criar um feed (6:44) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Configurar um feed
* Saber qual tipo de feed usar

>[!VIDEO](https://video.tv.adobe.com/v/27696)
