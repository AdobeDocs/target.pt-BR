---
keywords: personalização automatizada;oferta;relatórios;grupo;grupo de relatórios;automated personalization;offer;reporting;group;reporting group;ap
description: Saiba como usar grupos de relatórios de ofertas em atividades do  [!DNL Adobe Target] [!UICONTROL Automated Personalization].
title: Posso Usar Grupos de Relatórios de Oferta em Atividades do [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
TQID: https://experienceleague.adobe.com/VW3zVGXb3IuQMDaRyidbkjsbUrojvwFsvwP3yRVeHp4
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 875
ht-degree: 20%

---

# Oferecer grupos de relatório no [!UICONTROL Automated Personalization]

Informações sobre o uso de grupos de relatórios em atividades de [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP).

Os grupos de relatórios executam duas funções-chave:

* Os grupos de relatórios permitem que você veja suas ofertas agrupadas nos relatórios de atividades de AP.
* Os grupos de relatórios desempenham uma função importante no funcionamento dos modelos de personalização do [!DNL Target].

Quando você usa grupos de relatórios, o [!DNL Target] cria um modelo de personalização para cada grupo de relatórios usando os dados de todas as ofertas desse grupo. Sem grupos de relatórios, o [!DNL Target] cria um modelo de personalização para cada oferta na atividade de AP.

Se a configuração da atividade não tiver dados suficientes para criar um modelo de personalização por oferta, os grupos de relatórios ajudarão a reduzir os requisitos de dados para usar o [!UICONTROL Automated Personalization]. Os grupos de relatórios também podem ajudar a resolver o problema de &quot;inicialização imediata&quot; para novas ofertas, agrupando ofertas semelhantes para que cada modelo receba mais dados para treinar. Os grupos de modelagem também podem ser usados para atividades em que novas ofertas são introduzidas regularmente na atividade de AP.

Essa abordagem funciona bem se os visitantes responderem da mesma maneira a todas as ofertas de um grupo. A prática recomendada é agrupar as ofertas nas quais grupos semelhantes de visitantes respondem de maneira similar. Ou seja, agrupe ofertas com taxas de conversão semelhantes. Você nunca deve colocar todas as ofertas em um único grupo de relatórios. Agrupar todas as ofertas ou agrupar ofertas com taxas de conversão diferentes provavelmente reduz a eficácia dos modelos de personalização [!DNL Target].

>[!NOTE]
>
>Se uma oferta for removida ou substituída de um determinado grupo de modelagem, o tráfego antigo que visualizou essa oferta específica também será excluído do grupo de modelagem. Em outras palavras, as ofertas excluídas não contribuem para quais dados são usados para que os modelos de personalização do [!DNL Target] aprendam.

## Configurar grupos de relatórios

1. Na página **[!UICONTROL Experiências]** de uma atividade de AP, clique no ícone **[!UICONTROL Gerenciar conteúdo]** ( ![Ícone Gerenciar conteúdo](/help/main/assets/icons/Experience.svg) )
1. Clique na guia **[!UICONTROL Ofertas]** na parte superior da caixa de diálogo [!UICONTROL Gerenciar conteúdo].
1. (Condicional) Adicione experiências específicas a um grupo de relatórios, clicando no ícone [!UICONTROL Mais Ações] ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmall.svg) ) da oferta desejada e clicando em **[!UICONTROL Grupo de Relatórios]**.

1. (Condicional) Adicione experiências em lote a um grupo de relatórios, marcando as caixas de seleção das experiências relevantes e clicando em **[!UICONTROL Grupo de relatórios]** na parte inferior da caixa de diálogo.

1. Para atribuir a oferta selecionada a um grupo de relatórios existente, selecione **[!UICONTROL Existente]**, selecione o grupo de relatórios desejado na lista suspensa e clique em **[!UICONTROL Confirmar]**.

   Ou

   Para criar um grupo de relatórios para atribuir a oferta selecionada, selecione **[!UICONTROL Novo]**, nomeie o novo grupo de relatórios e clique em **[!UICONTROL Confirmar]**.

Você pode usar a lista [!UICONTROL Local] para filtrar ofertas por local. Use a lista [!UICONTROL Grupos de relatórios] para filtrar ofertas a grupos de relatórios. Você também pode usar a lista [!UICONTROL Grupo de relatórios] para filtrar [!UICONTROL Ofertas não atribuídas], de modo que possa atribuir um grupo de relatórios a uma oferta que não está atualmente atribuída a qualquer grupo de relatórios.

Para obter informações sobre como direcionar uma oferta para públicos específicos, consulte [Ofertas do [!UICONTROL Automated Personalization] do Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## Avisos

* É importante entender que os grupos de relatórios afetam como o [!DNL Target] cria seus modelos. Como resultado, o [!DNL Adobe] recomenda que você use grupos de relatórios somente se planeja substituir ou adicionar novas ofertas enquanto uma atividade estiver ativa. Se uma nova oferta for introduzida em uma atividade ativa, colocar a nova oferta em um grupo com ofertas semelhantes existentes permitirá que a máquina use os dados já coletados para as outras ofertas em seu grupo para saber mais sobre a nova oferta. Você nunca deve colocar todas as ofertas em um único grupo de relatórios.

* As atividades de AP têm combinações de localização+oferta (rótulos de modelo). Quando [!DNL Target] registra dados em relatórios, [!DNL Target] considera essas combinações de modo que fique claro de qual evento (exibição, clique, etc.) a oferta veio.

  Por exemplo, uma atividade pode ter vários locais e várias ofertas, que podem se sobrepor. Se um visitante visualizar mais de uma dessas ofertas em locais diferentes, [!DNL Target] registrará dados somente para essas ofertas. Se o mesmo visitante clicar em uma oferta posteriormente, [!DNL Target] registrará um evento somente dessa combinação (não para todas as combinações).

  Da mesma forma, se o clique vem de um local diferente, que está presente em uma métrica, mas não exibe uma oferta, esse evento será registrado na atividade, mas não para nenhuma combinação de oferta+local. Como resultado, essa oferta não aparece no grupo de relatórios de oferta.

  Esse comportamento ocorre porque o clique pode ser feito de uma mbox diferente, e não da mbox que serviu a oferta. Por esse motivo, a métrica é associada à atividade, mas não à oferta.

## Exibir ofertas em um grupo de relatórios

1. Clique em **[!UICONTROL Atividades]**, clique na atividade [!UICONTROL Automated Personalization] desejada da lista e na guia **[!UICONTROL Relatórios]** para exibir o relatório [Nível da oferta](/help/main/c-reports/personalization-reports/reports-ap.md).

   Se você tem muitas atividades, clique no ícone [!UICONTROL Mostrar filtros] (funnel) e marque a caixa de seleção [!UICONTROL Automated Personalization] para filtrar a lista e exibir apenas [!UICONTROL atividades do Automated Personalization].

1. Clique em **[!UICONTROL Controle]** ou **[!UICONTROL Direcionado]** na tabela para exibir as ofertas desagrupadas dentro dos grupos de relatórios.

   ![Grupos de ofertas: controle e direcionado](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

Para obter informações sobre como usar os relatórios do [!UICONTROL Automated Personalization] (incluindo o relatório do [!UICONTROL Nível de Oferta]), consulte os [relatórios de Resumo do Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).
