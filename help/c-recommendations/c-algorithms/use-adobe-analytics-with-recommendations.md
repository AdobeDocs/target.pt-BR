---
keywords: fonte de dados comportamentais, analytics, recommendations, critérios, variáveis de produto
description: Saiba como usar o Adobe Analytics como a fonte de dados comportamentais para usar os dados comportamentais baseados em visualização e/ou compras do Analytics em [!DNL Target] Recommendations.
title: Como uso o Adobe Analytics com [!DNL Target] Recommendations?
feature: Recommendations
exl-id: d2b7e840-9546-4a8e-bec4-1ebea5a79672
source-git-commit: 2a4cae206bf634bf3fbec65c5c4b289aadefede1
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 1%

---

# Usar o Adobe Analytics com o Recommendations

Usando [!DNL Adobe Analytics] já que a fonte de dados comportamentais permite que os clientes usem os dados comportamentais baseados em visualização e/ou compra do [!DNL Analytics] em [!DNL Adobe Target] atividades do recommendations. Esse recurso é especialmente útil em situações em que a variável [!DNL Target Recommendations] a configuração é nova e [!DNL Analytics] O tem muitos dados históricos para aproveitar.

Usando [!DNL Analytics] já que a fonte de dados comportamentais pode agir como uma fonte avançada de informações sobre o comportamento do usuário. Isso pode incluir dados de uma fonte de terceiros ou feed compartilhado somente com a [!DNL Analytics].

Ao [criação de critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) no Recommendations, há dois botões de opção que permitem escolher qual fonte de dados deve ser usada: [!UICONTROL mboxes] ou [!UICONTROL Analytics].

![Botões de fonte de dados comportamentais](assets/behavioral-data-source.png)

>[!NOTE]
>
>Se esses dois botões não forem exibidos em sua conta, entre em contato com [Atendimento ao cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

## Casos de uso para dados do Analytics no Target

Usando [!DNL Analytics] já que a fonte de dados comportamentais do recommendations também oferece a capacidade de implantar casos de uso específicos sem a necessidade de marcar páginas de entidade com todos os [!DNL Target] parâmetros de entidade. Embora isso exija que determinados pré-requisitos estejam em vigor, a disponibilidade de &quot;Variáveis de produto&quot; é a coisa mais importante para que essa funcionalidade funcione perfeitamente. eVars regulares e Props não são suficientes para que esse handshake ocorra automaticamente entre [!DNL Analytics] e [!DNL Target].

Você pode usar [!DNL Analytics] como fonte de dados comportamentais para:

* Exiba recomendações em um site de varejo para usuários em uma página PDP, com base no que outros usuários compraram da mesma categoria no último mês, usando dados do Analytics.
* Exiba o conteúdo na tela inicial de um site de mídia para o conteúdo mais popular em uma categoria específica que está com tendência no momento, com base em [!DNL Analytics] dados.

## Implementação no Analytics

As seções a seguir ajudarão você a implementar esse recurso no [!DNL Analytics] lado.

### Pré-requisitos: configurar variáveis de produto no Analytics

Você deve implementar variáveis de produto em [!DNL Analytics] com os atributos necessários que são necessários para [!DNL Target Recommendations].

A [!DNL Target Recommendations] o formato de feed de exemplo atuará como um guia no qual todos os atributos precisam ser definidos nas variáveis do produto. Posteriormente, esses valores devem ser &quot;mapeados&quot; no [!DNL Target] Interface do usuário para os respectivos [!DNL Target] valores de entidade.

>[!NOTE]
>
>Se for um site de conteúdo, as respectivas partes de conteúdo deverão ser tratadas como &quot;produtos&quot; e atributos associados sobre esse conteúdo (por exemplo: nome do autor, data de publicação, título do conteúdo, mês de lançamento, etc.) deve ser passado como atributos. A granularidade do nível da categoria, ou tipos de categoria, deve ser decidida pela empresa com base nos requisitos do caso de uso.

Para obter mais detalhes sobre como configurar variáveis de produto, consulte [products](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/products.html) no *Guia de implementação do Analytics*. Algumas observações nessa documentação precisam ser discricionárias da equipe que a está implantando (exemplo: Categoria). Recomenda-se sempre consultar o Adobe antes de realizar esta atividade.

### Considerações

[!DNL Analytics] os dados são enviados por um feed diário. Os resultados comportamentais levarão até 24 horas para serem refletidos nos resultados das recomendações no site. Como com todos [!DNL Recommendations] configurações de critérios, essa fonte de dados pode e deve ser testada.

Para uma tomada de decisão rápida sobre qual fonte de dados deve ser usada, se houver muitos dados orgânicos gerados todos os dias pelos usuários, e não muita dependência necessária aos dados históricos, então usando uma [!DNL Target] mbox como a fonte de dados comportamentais pode ser um bom ajuste. Em casos de menos disponibilidade de dados orgânicos gerados recentemente, se você quiser basear-se em [!DNL Analytics] , em seguida, usar [!DNL Analytics] já que a fonte de dados comportamentais é uma boa opção.

Agora é hora de mapear essas variáveis em [!DNL Target] para o fornecimento contínuo de dados comportamentais.

## Implementar no Target

1. No Target, clique em **[!UICONTROL Recommendations]**, em seguida, clique no botão **[!UICONTROL Feeds]** guia .

   ![Feeds](/help/c-recommendations/c-algorithms/assets/feeds-tab.png)

1. Clique em **[!UICONTROL Criar feed]**.

1. Selecionar **[!UICONTROL Classificações do Analytics]**, em seguida, especifique o conjunto de relatórios.

   ![Opção Classificações do Analytics](/help/c-recommendations/c-algorithms/assets/analytics-classifications.png)

1. Clique em **[!UICONTROL Mapeamento]**, em seguida, mapeie os cabeçalhos da coluna de campo para o [!UICONTROL Recommendations] nomes de campo.

   ![Seção Mapeamento](/help/c-recommendations/c-algorithms/assets/mapping.png)

1. Clique em **[!UICONTROL Salvar]**.

## Perguntas frequentes

Considere as seguintes perguntas frequentes ao usar [!DNL Analytics] com [!DNL Target]:

### São as `entity.id` e `entity.categoryId` valores necessários para serem transmitidos no [!DNL Target] chamada de mbox?

Sim, esses dois valores ainda são necessários. O restante dos atributos pode ser passado por um [!DNL Analytics] feed, conforme discutido neste documento.

### Posso usar regras de inclusão dinâmica, como parâmetro de entidade que corresponde atributos de perfil usando o [!DNL Analytics] abordagem de feed?

Sim, você pode. O método é semelhante ao usar [!DNL Target] independente. No entanto, neste caso, é necessário ter presente o fator de tempo. As variáveis de entidade que devem corresponder às variáveis de perfil dependem da camada de dados que pode aparecer muito mais tarde na página.
