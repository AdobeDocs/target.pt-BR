---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: Usar o Adobe Analytics como fonte de dados comportamental permite que os clientes usem os dados comportamentais baseados em visualizações e/ou compras do Analytics no Adobe Recommendations.
title: Uso do Adobe Analytics com o Público alvo Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: a6cdecbe6acb0b34edb036894c55a2dd2298ee6e
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 2%

---


# Usar Adobe Analytics com Recommendations

Usar [!DNL Adobe Analytics] como a fonte de dados comportamental permite que os clientes usem os dados comportamentais baseados em visualização e/ou compra [!DNL Analytics] nas atividades [!DNL Adobe Target] do Recomendações. Esse recurso é especialmente útil em situações em que a [!DNL Target Recommendations] configuração é nova e [!DNL Analytics] tem muitos dados históricos para aproveitar.

Usar [!DNL Analytics] como fonte de dados comportamental pode agir como uma fonte avançada de informações sobre o comportamento do usuário. Isso pode incluir dados de uma fonte de terceiros ou feed compartilhados somente com [!DNL Analytics].

Ao [criar critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) no Recommendations, há dois botões de opção que permitem escolher qual fonte de dados será usada: [!UICONTROL mboxes] ou [!UICONTROL Analytics].

![Botões de fonte de dados comportamentais](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>Se esses dois botões não forem exibidos em sua conta, entre em contato com o [Atendimento](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)ao cliente.

## Casos de uso

Usar [!DNL Analytics] como fonte de dados comportamental para recomendações também fornece a capacidade de implantar casos de uso específicos sem a necessidade de marcar páginas de entidade com todos os parâmetros de [!DNL Target] entidade. Embora isso exija que certos pré-requisitos estejam em vigor, a disponibilidade de &quot;Variáveis de produto&quot; é a coisa mais importante para que essa funcionalidade funcione perfeitamente. As eVars e props regulares não são suficientes para que esse handshake ocorra automaticamente entre [!DNL Analytics] e [!DNL Target].

Você pode usar [!DNL Analytics] como fonte de dados comportamental para:

* Exiba recomendações em um site de varejo para usuários em uma página PDP, com base no que outros usuários compraram da mesma categoria no mês passado, usando dados do Analytics.
* Exiba o conteúdo na tela inicial de um site de mídia para o conteúdo mais popular em uma categoria específica que está com tendência no momento, com base em [!DNL Analytics] dados.

## Implementação no Analytics

As seções a seguir ajudarão a implementar esse recurso no [!DNL Analytics] lado.

### Pré-requisitos: variáveis de produto no Analytics

É necessário implementar variáveis de produto com [!DNL Analytics] os atributos necessários para [!DNL Target Recommendations].

Um formato de feed de [!DNL Target Recommendations] amostra atuará como um guia no qual todos os atributos precisam ser definidos nas variáveis do produto. Posteriormente, esses valores devem ser &quot;mapeados&quot; na [!DNL Target] interface do usuário para os respectivos valores de [!DNL Target] entidade.

>[!NOTE]
>
>Se for um site de conteúdo, as respectivas partes de conteúdo deverão ser tratadas como &quot;produtos&quot; e os atributos associados a esse conteúdo (por exemplo: nome do autor, data de publicação, título do conteúdo, mês de lançamento etc.) deve ser passado como atributos. A granularidade do nível de categoria ou tipos de categoria deve ser decidida pela empresa com base nos requisitos de caso de uso.

Para obter mais detalhes sobre como configurar variáveis de produto, consulte [produtos](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/products.html) no Guia *de implementação do* Analytics. Algumas das notas dessa documentação precisam ser discretas para a equipe que a está implantando (por exemplo: Categoria). É sempre aconselhável consultar o Adobe antes de fazer esta atividade.

### Considerações

[!DNL Analytics] os dados são enviados por meio de um feed diário. Os resultados comportamentais levarão até 24 horas para serem refletidos nos resultados das recomendações no site. Como em todas as configurações de [!DNL Recommendations] critérios, essa fonte de dados pode e deve ser testada.

Para uma tomada de decisão rápida sobre qual fonte de dados deve ser usada, se houver muitos dados orgânicos gerados todos os dias pelos usuários, e não muita dependência necessária aos dados históricos, então usar uma [!DNL Target] mbox como fonte de dados comportamental pode ser uma boa opção. Em casos de menos disponibilidade de dados orgânicos gerados recentemente, se você quiser basear-se em [!DNL Analytics] dados, então o uso [!DNL Analytics] como fonte de dados comportamental é um bom ajuste.

### Etapas para implantar

Supondo que todos os pré-requisitos estejam no lugar, execute as seguintes tarefas:

1. Em [!DNL Target], clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]** para adquirir seu código [!DNL Target] de cliente.

   ![Código de cliente](/help/c-recommendations/c-algorithms/assets/client-code.png)

1. Adquira seu conjunto de [!DNL Analytics] relatórios.

   Use seu conjunto de relatórios do site [!DNL Analytics] de produção. Este é o conjunto de relatórios que rastreia o site no qual você [!DNL Recommendations] implantou.

1. Em [!DNL Analytics], clique em **[!UICONTROL Admin]** > Feeds **[!UICONTROL de dados]**.

   ![Configuração > Feeds de dados](/help/c-recommendations/c-algorithms/assets/data-feed.png)

1. Click **[!UICONTROL Add]** to create a new feed.

   ![Adicionar feed](/help/c-recommendations/c-algorithms/assets/add-feed.png)

1. Preencha as informações do feed:

   * **Nome**: Feed de Prod Recs
   * **Conjunto** de relatórios: Seu conjunto de relatórios predeterminado
   * **Email**: Especifique qualquer endereço apropriado para um usuário administrador
   * **Intervalo** do feed: Selecionar o intervalo desejado
   * **Atraso no processamento**: Sem atraso.
   * **Datas** de start e término: Alimentação contínua

   ![Seção de informações do feed](/help/c-recommendations/c-algorithms/assets/feed-information.png)

1. Fill in the details in the **[!UICONTROL Destination]** section:

   >[!NOTE]
   > 
   >Consulte a [!DNL Adobe Analytics] equipe antes de executar esta etapa.

   * **Tipo**: FTP
   * **Host**: `xxx.yyy.com`
   * **Caminho**: Seu código [!DNL Target] de cliente
   * **Nome de usuário**: Especifique seu nome de usuário
   * **Senha**: Especifique sua senha

   A captura de tela é apenas para fins de referência. Sua implantação terá credenciais diferentes. Consulte a [!DNL Adobe Analytics] equipe ou o Atendimento ao cliente ao executar esta etapa.

   ![Seção de destino](/help/c-recommendations/c-algorithms/assets/destination.png)

1. Preencha as definições da Coluna **[!UICONTROL de]** dados:

   * **Formato** de compactação: Gzip
   * **Tipo** de empacotamento:  Arquivo único
   * **Manifesto:** Concluir arquivo

      ![Configurações de Formato de compactação, Tipo de empacotamento e Manifesto](/help/c-recommendations/c-algorithms/assets/compression.png)

   * **Colunas incluídas**:

      >[!IMPORTANT]
      >
      >As colunas devem ser adicionadas na mesma ordem documentada aqui. Selecione as colunas na seguinte ordem e clique em **[!UICONTROL Adicionar]** para cada coluna.

      * hit_time_gmt
      * visid_high
      * visid_low
      * event_list
      * product_list
      * visit_num

1. Clique em **[!UICONTROL Salvar]**.

   ![Seção Definições da coluna de dados](/help/c-recommendations/c-algorithms/assets/data-column-definitions.png)

Com isso, a configuração no [!DNL Analytics] lado está concluída. Agora é hora de mapear essas variáveis de [!DNL Target] lado para o fornecimento contínuo de dados comportamentais.

## Implementação no Público alvo

1. No Público alvo, clique em **[!UICONTROL Recommendations]** e, em seguida, clique na guia **[!UICONTROL Feeds]** .

   ![Feeds](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Clique em **[!UICONTROL Criar feed]**.

1. Selecione Classificações **[!UICONTROL do]** Analytics e especifique o conjunto de relatórios.

   ![Opção Classificações do Analytics](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Clique em **[!UICONTROL Mapeamento]** e mapeie os cabeçalhos da coluna de campo para os nomes de campo apropriados do [!UICONTROL Recommendations] .

   ![Seção de mapeamento](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Clique em **[!UICONTROL Salvar]**.