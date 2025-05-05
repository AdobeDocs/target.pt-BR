---
keywords: fonte de dados comportamentais;análises;recomendações;critérios;variáveis do produto
description: Saiba como usar o  [!DNL Adobe Analytics]  como a fonte de dados comportamentais no  [!DNL Target Recommendations].
title: Como usar [!DNL Adobe Analytics] com [!DNL Target Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 0%

---

# Usar [!DNL Adobe Analytics] com [!DNL Recommendations]

Usar [!DNL Adobe Analytics] como a fonte de dados comportamentais permite que os clientes usem os dados comportamentais baseados em visualização e em compra de [!DNL Analytics] em [!DNL Adobe Target Recommendations] atividades. Este recurso é especialmente útil em situações em que a configuração do [!DNL Target Recommendations] é nova e o [!DNL Analytics] tem muitos dados históricos para usar.

Usar [!DNL Analytics] como fonte de dados comportamentais pode atuar como uma fonte rica de informações sobre o comportamento do usuário. Essas informações podem incluir dados de uma fonte de terceiros ou feed que são compartilhados somente com [!DNL Analytics].

Ao [criar o critério](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) em [!DNL Recommendations], há dois botões de opção que permitem escolher qual fonte de dados deve ser usada: [!UICONTROL mboxes] ou [!UICONTROL Analytics]. Para criar um critério, clique em [!UICONTROL Recommendations] > [!UICONTROL Criteria] > [!UICONTROL Create Criteria] > [!UICONTROL Create Criteria]. Para obter mais informações, consulte [Criar critérios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

>[!NOTE]
>
>Se esses dois botões não forem exibidos na sua conta, entre em contato com o [Atendimento ao cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Casos de uso para dados [!DNL Analytics] em [!DNL Target]

Usar [!DNL Analytics] como a fonte de dados comportamentais para recomendações também permite implantar casos de uso específicos sem o requisito de marcar páginas de entidade com todos os parâmetros de entidade [!DNL Target]. Embora isso exija que determinados pré-requisitos estejam em vigor, a disponibilidade de &quot;Variáveis de produto&quot; é a coisa mais importante para que essa funcionalidade funcione perfeitamente. eVars e Props comuns não são suficientes para que esse handshake ocorra automaticamente entre [!DNL Analytics] e [!DNL Target].

Você pode usar [!DNL Analytics] como fonte de dados comportamentais para:

* Exibir recomendações em um site de varejo para usuários em uma página de detalhes do produto, com base no que outros usuários compraram da mesma categoria no mês passado, usando dados do [!DNL Analytics].
* Exiba conteúdo na tela inicial de um site de mídia para o conteúdo mais popular de uma determinada categoria que está em tendência no momento, com base nos dados [!DNL Analytics].

## Implementação em [!DNL Analytics]

As seções a seguir ajudam a implementar esse recurso no lado do [!DNL Analytics].

### Pré-requisitos: configurar variáveis de produto no [!DNL Analytics]

Implemente variáveis de produto em [!DNL Analytics] com os atributos necessários que são necessários para [!DNL Target Recommendations].

Um exemplo de formato de feed do [!DNL Target Recommendations] atua como guia no qual todos os atributos devem ser definidos nas variáveis do produto. Posteriormente, esses valores devem ser &quot;mapeados&quot; na interface do usuário [!DNL Target] para os respectivos valores de entidade [!DNL Target].

>[!NOTE]
>
>Se for um site de conteúdo, as respectivas partes de conteúdo deverão ser tratadas como &quot;produtos&quot; e os atributos associados sobre esse conteúdo deverão ser passados como atributos. Esses atributos podem incluir nome do autor, data de publicação, título do conteúdo, mês de lançamento e assim por diante. A granularidade do nível de categoria ou dos tipos de categoria deve ser decidida pela empresa com base nos requisitos do caso de uso.

Para obter mais detalhes sobre como configurar variáveis de produto, consulte [produtos](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html?lang=pt-BR) no guia *Implementar o Adobe Analytics*. Algumas das notas nessa documentação exigem a discrição da equipe que está implantando (exemplo : Categoria). É sempre aconselhável consultar [!DNL Adobe] antes de realizar esta atividade.

### Considerações

Os dados de [!DNL Analytics] são enviados por meio de um feed diário. Os resultados comportamentais podem levar até 24 horas para serem refletidos nos resultados das recomendações do site. Como em todas as configurações de critérios de [!DNL Recommendations], essa fonte de dados pode e deve ser testada.

Para tomar decisões rápidas sobre qual fonte de dados deve ser usada, se houver muitos dados orgânicos gerados diariamente pelos usuários e pouca dependência necessária dos dados históricos, usar uma mbox [!DNL Target] como fonte de dados comportamentais pode ser uma boa opção. Em casos de menor disponibilidade de dados orgânicos gerados recentemente, se você quiser se basear em dados de [!DNL Analytics], o uso de [!DNL Analytics] como fonte de dados comportamentais será um bom ajuste.

Agora é hora de mapear essas variáveis no lado [!DNL Target] para o fornecimento contínuo de dados comportamentais.

## Implementar em [!DNL Target]

1. Em [!DNL Target], clique em **[!UICONTROL Recommendations]** e, em seguida, clique na guia **[!UICONTROL Feeds]**.

1. Clique em **[!UICONTROL Create Feed]**.

1. Selecione **[!UICONTROL Analytics Classifications]** e especifique o conjunto de relatórios.

1. Clique em **[!UICONTROL Next]** para avançar para as configurações de **[!UICONTROL Schedule]** e selecione um período de frequência para o feed:

   * [!UICONTROL Daily]
   * [!UICONTROL Weekly]
   * [!UICONTROL Every 2 weeks]
   * [!UICONTROL Never]

   Você também pode selecionar a hora do dia em que o feed será processado.

1. Clique em **[!UICONTROL Next]** para avançar para as configurações de **[!UICONTROL Mapping]** e mapear os cabeçalhos de coluna de campo para os nomes de campo [!UICONTROL Recommendations] apropriados.

1. Clique em **[!UICONTROL Save]**.

## Perguntas frequentes

Considere as seguintes perguntas frequentes ao usar [!DNL Analytics] com [!DNL Target]:

### Os valores `entity.id` e `entity.categoryId` precisam ser passados na chamada de mbox [!DNL Target]?

Sim, esses dois valores ainda são obrigatórios. O restante dos atributos pode ser passado por meio de um feed [!DNL Analytics], conforme discutido neste documento.

### Posso usar regras de inclusão dinâmica, como correspondência de parâmetros de entidade e atributos de perfil usando a abordagem de feed [!DNL Analytics]?

Sim, você pode. O método é semelhante ao usar [!DNL Target] independente. Nesse caso, no entanto, você deve estar atento ao fator tempo. As variáveis de entidade que devem corresponder às variáveis de perfil dependem da camada de dados que pode aparecer muito mais tarde na página.
