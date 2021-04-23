---
keywords: fonte de dados comportamentais, analytics, recommendations, critérios, variáveis de produto
description: Saiba como usar o Adobe Analytics como a fonte de dados comportamentais para usar os dados comportamentais baseados em visualização e/ou compras do Analytics em [!DNL Target] Recommendations.
title: Como uso o Adobe Analytics com  [!DNL Target] Recommendations?
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 1%

---

# Usar o Adobe Analytics com Recommendations

Usar [!DNL Adobe Analytics] como fonte de dados comportamentais permite que os clientes usem os dados comportamentais baseados em visualização e/ou compra de [!DNL Analytics] nas atividades de [!DNL Adobe Target] recomendações. Esse recurso é especialmente útil em situações em que a configuração [!DNL Target Recommendations] é nova e [!DNL Analytics] tem muitos dados históricos para serem aproveitados.

Usar [!DNL Analytics] como fonte de dados comportamentais pode agir como uma fonte avançada de informações sobre o comportamento do usuário. Isso pode incluir dados de uma fonte de terceiros ou feed que é compartilhado somente com [!DNL Analytics].

Enquanto [criar critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) no Recommendations, há dois botões de opção que permitem escolher qual fonte de dados deve ser usada: [!UICONTROL mboxes] ou [!UICONTROL Analytics].

![Botões de fonte de dados comportamentais](/help/c-recommendations/c-algorithms/assets/behavioral-data-source.png)

>[!NOTE]
>
>Se esses dois botões não forem exibidos em sua conta, entre em contato com o [Atendimento ao cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Casos de uso para dados do Analytics no Target

Usar [!DNL Analytics] como fonte de dados comportamentais para recomendações também fornece a capacidade de implantar casos de uso específicos sem o requisito de marcar páginas de entidade com todos os parâmetros de entidade [!DNL Target]. Embora isso exija que determinados pré-requisitos estejam em vigor, a disponibilidade de &quot;Variáveis de produto&quot; é a coisa mais importante para que essa funcionalidade funcione perfeitamente. eVars e Props regulares não são suficientes para que esse handshake ocorra automaticamente entre [!DNL Analytics] e [!DNL Target].

Você pode usar [!DNL Analytics] como a fonte de dados comportamentais para:

* Exiba recomendações em um site de varejo para usuários em uma página PDP, com base no que outros usuários compraram da mesma categoria no último mês, usando dados do Analytics.
* Exiba o conteúdo na tela inicial de um site de mídia para o conteúdo mais popular em uma categoria específica que está com tendência no momento, com base nos dados [!DNL Analytics] .

## Implementação no Analytics

As seções a seguir ajudarão você a implementar esse recurso no lado [!DNL Analytics].

### Pré-requisitos: configurar variáveis de produto no Analytics

Você deve implementar variáveis de produto em [!DNL Analytics] com os atributos necessários que são necessários para [!DNL Target Recommendations].

Um [!DNL Target Recommendations] formato de feed de amostra atuará como um guia no qual todos os atributos precisam ser definidos nas variáveis do produto. Posteriormente, esses valores devem ser &quot;mapeados&quot; na interface do usuário [!DNL Target] para os respectivos valores de entidade [!DNL Target].

>[!NOTE]
>
>Se for um site de conteúdo, as respectivas partes de conteúdo deverão ser tratadas como &quot;produtos&quot; e atributos associados sobre esse conteúdo (por exemplo: nome do autor, data de publicação, título do conteúdo, mês de lançamento, etc.) deve ser passado como atributos. A granularidade do nível da categoria, ou tipos de categoria, deve ser decidida pela empresa com base nos requisitos do caso de uso.

Para obter mais detalhes sobre como configurar variáveis de produto, consulte [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) no *Guia de implementação do Analytics*. Algumas observações nessa documentação precisam ser discricionárias da equipe que a está implantando (exemplo: Categoria). Recomenda-se sempre consultar o Adobe antes de realizar esta atividade.

### Considerações

[!DNL Analytics] os dados são enviados por um feed diário. Os resultados comportamentais levarão até 24 horas para serem refletidos nos resultados das recomendações no site. Assim como em todas as configurações de critérios [!DNL Recommendations] , essa fonte de dados pode e deve ser testada.

Para uma tomada de decisão rápida sobre qual fonte de dados deve ser usada, se houver muitos dados orgânicos gerados todos os dias pelos usuários, e não muita dependência exigida nos dados históricos, então usar uma mbox [!DNL Target] como fonte de dados comportamentais pode ser um bom ajuste. Em casos de menos disponibilidade de dados orgânicos gerados recentemente, se você quiser basear-se em [!DNL Analytics] dados, o uso de [!DNL Analytics] como fonte de dados comportamentais será um bom ajuste.

Agora é hora de mapear essas variáveis no lado [!DNL Target] para o fornecimento contínuo de dados comportamentais.

## Implementar no Target

1. No Target, clique em **[!UICONTROL Recommendations]** e, em seguida, clique na guia **[!UICONTROL Feeds]**.

   ![Feeds](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Clique em **[!UICONTROL Criar feed]**.

1. Selecione **[!UICONTROL Classificações do Analytics]** e especifique o conjunto de relatórios.

   ![Opção Classificações do Analytics](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Clique em **[!UICONTROL Mapping]** e mapeie os cabeçalhos da coluna de campo para os nomes de campo [!UICONTROL Recommendations] apropriados.

   ![Seção Mapeamento](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Clique em **[!UICONTROL Salvar]**.

## Perguntas frequentes

Considere as seguintes perguntas frequentes ao usar [!DNL Analytics] com [!DNL Target]:

### Os valores `entity.id` e `entity.categoryId` precisam ser passados dentro da chamada da mbox [!DNL Target]?

Sim, esses dois valores ainda são necessários. O restante dos atributos pode ser transmitido por meio de um feed [!DNL Analytics], conforme discutido neste documento.

### Posso usar regras de inclusão dinâmica, como parâmetro de entidade que corresponde atributos de perfil usando a abordagem de feed [!DNL Analytics]?

Sim, você pode. O método é semelhante ao usar [!DNL Target] autônomo. No entanto, neste caso, é necessário ter presente o fator de tempo. As variáveis de entidade que devem corresponder às variáveis de perfil dependem da camada de dados que pode aparecer muito mais tarde na página.
