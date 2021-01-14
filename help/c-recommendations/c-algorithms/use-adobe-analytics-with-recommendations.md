---
keywords: behavioral data source;analytics;recommendations;criteria;product variables
description: Usar o Adobe Analytics como fonte de dados comportamental permite que os clientes usem os dados comportamentais baseados em visualizações e/ou compras do Analytics no Adobe Recommendations.
title: Uso do Adobe Analytics com o Público alvo Recommendations
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 3%

---


# Usar Adobe Analytics com Recommendations

Usar [!DNL Adobe Analytics] como fonte de dados comportamental permite que os clientes usem os dados comportamentais baseados em visualizações e/ou compras de [!DNL Analytics] nas atividades de recomendações [!DNL Adobe Target]. Este recurso é especialmente útil em situações em que a configuração [!DNL Target Recommendations] é nova e [!DNL Analytics] tem muitos dados históricos a serem aproveitados.

Usar [!DNL Analytics] como fonte de dados comportamental pode agir como uma fonte avançada de informações sobre o comportamento do usuário. Isso pode incluir dados de uma fonte de terceiros ou feed compartilhados somente com [!DNL Analytics].

Enquanto [criar critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) no Recommendations, há dois botões de opção que permitem escolher qual fonte de dados será usada: [!UICONTROL mboxes] ou [!UICONTROL Analytics].

![Botões de fonte de dados comportamentais](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>Se esses dois botões não forem exibidos em sua conta, entre em contato com [Atendimento ao cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Casos de uso para dados do Analytics no Público alvo

Usar [!DNL Analytics] como fonte de dados comportamental para recomendações também oferece a capacidade de implantar casos de uso específicos sem a necessidade de marcar páginas de entidades com todos os parâmetros de entidade [!DNL Target]. Embora isso exija que certos pré-requisitos estejam em vigor, a disponibilidade de &quot;Variáveis de produto&quot; é a coisa mais importante para que essa funcionalidade funcione perfeitamente. As eVars e props regulares não são suficientes para que esse handshake ocorra automaticamente entre [!DNL Analytics] e [!DNL Target].

Você pode usar [!DNL Analytics] como a fonte de dados comportamental para:

* Exiba recomendações em um site de varejo para usuários em uma página PDP, com base no que outros usuários compraram da mesma categoria no mês passado, usando dados do Analytics.
* Exiba o conteúdo na tela inicial de um site de mídia para o conteúdo mais popular em uma categoria específica que está com tendência no momento, com base nos dados [!DNL Analytics].

## Implementação no Analytics

As seções a seguir ajudarão a implementar esse recurso no lado [!DNL Analytics].

### Pré-requisitos: configurar variáveis de produto no Analytics

Você deve implementar variáveis de produto em [!DNL Analytics] com os atributos necessários necessários para [!DNL Target Recommendations].

Um formato de feed de amostra [!DNL Target Recommendations] atuará como guia no qual todos os atributos precisam ser definidos nas variáveis do produto. Posteriormente, esses valores devem ser &quot;mapeados&quot; na interface [!DNL Target] para os respectivos valores de entidade [!DNL Target].

>[!NOTE]
>
>Se for um site de conteúdo, as respectivas partes de conteúdo deverão ser tratadas como &quot;produtos&quot; e os atributos associados a esse conteúdo (por exemplo: nome do autor, data de publicação, título do conteúdo, mês de lançamento etc.) deve ser passado como atributos. A granularidade do nível de categoria ou tipos de categoria deve ser decidida pela empresa com base nos requisitos de caso de uso.

Para obter mais detalhes sobre como configurar variáveis de produto, consulte [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) no *Guia de implementação do Analytics*. Algumas das notas dessa documentação precisam ser discretas para a equipe que a está implantando (por exemplo: Categoria). É sempre aconselhável consultar o Adobe antes de fazer esta atividade.

### Considerações

[!DNL Analytics] os dados são enviados por meio de um feed diário. Os resultados comportamentais levarão até 24 horas para serem refletidos nos resultados das recomendações no site. Assim como com todas as configurações de critérios [!DNL Recommendations], essa fonte de dados pode e deve ser testada.

Para uma tomada de decisão rápida sobre qual fonte de dados será usada, se houver muitos dados orgânicos gerados todos os dias pelos usuários, e não houver muita dependência necessária aos dados históricos, então usar uma mbox [!DNL Target] como fonte de dados comportamental pode ser uma boa opção. Em casos de menos disponibilidade de dados orgânicos gerados recentemente, se você quiser se basear em [!DNL Analytics] dados, o uso de [!DNL Analytics] como fonte de dados comportamental é um bom ajuste.

### Etapas para implantar

Supondo que todos os pré-requisitos estejam em vigor, as seguintes tarefas devem ser executadas pela equipe [!DNL Adobe Target Recommendations]:

>[!IMPORTANT]
>
>As etapas abaixo são apenas para fins ilustrativos. No momento, um membro da equipe [!DNL Recommendations] deve executar essas etapas. [Para obter mais infirmações, em contato com o Atendimento ao cliente da ](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)

1. Em [!DNL Target], clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]** para adquirir o código de cliente [!DNL Target].

   ![Código de cliente](/help/c-recommendations/c-algorithms/assets/client-code.png)

1. Adquira seu conjunto de relatórios [!DNL Analytics].

   Use seu conjunto de relatórios de [!DNL Analytics] site de produção. Este é o conjunto de relatórios que rastreia o site no qual você [!DNL Recommendations] implantou.

1. Em [!DNL Analytics], clique em **[!UICONTROL Admin]** > **[!UICONTROL Feeds de dados]**.

   ![Configuração > Feeds de dados](/help/c-recommendations/c-algorithms/assets/data-feed.png)

1. Clique em **[!UICONTROL Adicionar]** para criar um novo feed.

   ![Adicionar feed](/help/c-recommendations/c-algorithms/assets/add-feed.png)

1. Preencha as informações do feed:

   * **Nome**: Feed de Prod Recs
   * **Conjunto** de relatórios: Seu conjunto de relatórios predeterminado
   * **Email**: Especifique qualquer endereço apropriado para um usuário administrador
   * **Intervalo** do feed: Selecionar o intervalo desejado
   * **Atraso no processamento**: Sem atraso.
   * **Datas** de start e término: Alimentação contínua

   ![Seção de informações do feed](/help/c-recommendations/c-algorithms/assets/feed-information.png)

1. Preencha os detalhes na seção **[!UICONTROL Destino]**:

   >[!NOTE]
   > 
   >Consulte a equipe [!DNL Adobe Analytics] antes de executar esta etapa.

   * **Tipo**: FTP
   * **Host**: `xxx.yyy.com`
   * **Caminho**: Seu código  [!DNL Target] de cliente
   * **Nome de usuário**: Especifique seu nome de usuário
   * **Senha**: Especifique sua senha

   A captura de tela é apenas para fins de referência. Sua implantação terá credenciais diferentes. Consulte a equipe [!DNL Adobe Analytics] ou o Atendimento ao cliente ao executar esta etapa.

   ![Seção de destino](/help/c-recommendations/c-algorithms/assets/destination.png)

1. Preencha as definições **[!UICONTROL Coluna de Dados]**:

   * **Formato** de compactação: Gzip
   * **Tipo** de empacotamento: Arquivo único
   * **Manifesto:Arquivo** De Conclusão

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

Com isso, a configuração no lado [!DNL Analytics] é concluída. Agora é hora de mapear essas variáveis no lado [!DNL Target] para o fornecimento contínuo de dados comportamentais.

## Implementação no Público alvo

1. No Público alvo, clique em **[!UICONTROL Recommendations]** e, em seguida, clique na guia **[!UICONTROL Feeds]**.

   ![Feeds](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Clique em **[!UICONTROL Criar feed]**.

1. Selecione **[!UICONTROL Classificações do Analytics]** e especifique o conjunto de relatórios.

   ![Opção Classificações do Analytics](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Clique em **[!UICONTROL Mapeamento]** e mapeie os cabeçalhos da coluna de campo para os nomes de campo [!UICONTROL Recommendations] apropriados.

   ![Seção de mapeamento](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Clique em **[!UICONTROL Salvar]**.

## Perguntas frequentes

Considere as seguintes perguntas frequentes ao usar [!DNL Analytics] com [!DNL Target]:

### Os valores `entity.id` e `entity.categoryId` precisam ser transmitidos dentro da chamada de mbox [!DNL Target]?

Sim, esses dois valores ainda são necessários. O restante dos atributos pode ser transmitido por meio de um feed [!DNL Analytics], conforme discutido neste documento.

### É possível usar regras de inclusão dinâmica, como parâmetro de entidade corresponde atributos de perfil usando a abordagem de feed [!DNL Analytics]?

Sim, você pode. O método é semelhante ao usar [!DNL Target] independente. Neste caso, porém, devem estar atentos ao fator de tempo. As variáveis de entidade que devem corresponder às variáveis de perfil dependem da camada de dados que pode aparecer muito mais tarde na página.

