---
keywords: personalização automatizada;oferta;relatórios;grupo;grupo de relatórios;automated personalization;offer;reporting;group;reporting group;ap
description: Saiba como usar grupos de relatórios de ofertas em atividades do [!DNL Adobe Target] [!UICONTROL Automated Personalization].
title: Posso Usar Grupos de Relatórios de Oferta em Atividades do [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
TQID: 'https://experienceleague.adobe.com/VW3zVGXb3IuQMDaRyidbkjsbUrojvwFsvwP3yRVeHp4'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: e8a43148-398f-56c7-9433-6564f96999c2
    internal-label: Reports
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 3%
---
# Oferecer grupos de relatório no [!UICONTROL Automated Personalization] {#offer-reporting-groups}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como os grupos de relatórios de ofertas funcionam nas atividades do **[!UICONTROL Automated Personalization]**, como configurá-los e como exibi-los nos relatórios.

>[!ENDSHADEBOX]

Os grupos de relatórios permitem organizar as ofertas de uma atividade do [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) em grupos. Os grupos de relatórios executam duas funções-chave:

* Eles permitem ver suas ofertas agrupadas em relatórios de atividade AP.
* Eles desempenham uma função importante em como os modelos de personalização do [!DNL Target] funcionam.

Quando você usa grupos de relatórios, o [!DNL Target] cria um modelo de personalização para cada grupo de relatórios, usando os dados de todas as ofertas desse grupo. Sem grupos de relatórios, o [!DNL Target] cria um modelo de personalização para cada oferta na atividade de AP.

Os grupos de relatórios também reduzem os requisitos de dados para usar o **[!UICONTROL Automated Personalization]** quando a configuração da atividade não tiver dados suficientes para criar um modelo de personalização por oferta. Eles ajudam com o problema de &quot;inicialização imediata&quot; de novas ofertas, que são agrupadas com ofertas semelhantes para que cada modelo tenha mais dados para treinar.

Essa abordagem funciona bem quando os visitantes respondem da mesma maneira a todas as ofertas em um grupo, portanto, agrupe ofertas com taxas de conversão semelhantes. Nunca agrupe todas as ofertas em um único grupo de relatórios e não agrupe ofertas com taxas de conversão diferentes, pois ambas as opções provavelmente reduzirão a eficácia dos modelos de personalização do [!DNL Target].

>[!NOTE]
>
>Se uma oferta for removida ou substituída em um grupo de relatórios, o tráfego histórico que viu essa oferta também será excluído do grupo, portanto, as ofertas excluídas não contribuem para os dados que os modelos de personalização do [!DNL Target] usam para aprender.


## Considerações

### Usar grupos de relatórios para atividades online

Os grupos de relatórios afetam como o [!DNL Target] cria seus modelos. Como resultado, o [!DNL Adobe] recomenda que você use grupos de relatórios somente se planeja substituir ou adicionar ofertas enquanto uma atividade estiver ativa. Se uma nova oferta for introduzida em uma atividade ativa, colocar a nova oferta em um grupo com ofertas semelhantes existentes permitirá que o [!DNL Target] use os dados já coletados para as outras ofertas do grupo para saber mais sobre a nova oferta.

### Como os dados são registrados para ofertas e locais

As atividades de AP têm combinações de localização e oferta (rótulos de modelo). Quando [!DNL Target] registra dados em relatórios, ele considera essas combinações, de modo que fica claro de qual evento (exibição, clique, etc.) a oferta veio.

Por exemplo, uma atividade pode ter vários locais e várias ofertas, que podem se sobrepor. Se um visitante visualizar mais de uma dessas ofertas em locais diferentes, [!DNL Target] registrará dados somente para essas ofertas. Se o mesmo visitante clicar em uma oferta posteriormente, [!DNL Target] registrará um evento somente dessa combinação (não para todas as combinações).

Da mesma forma, se o clique vier de um local diferente que esteja presente em uma métrica, mas não exibir uma oferta, o evento será registrado na atividade, mas não para qualquer combinação de oferta e local. Como resultado, essa oferta não aparece no grupo de relatórios de oferta. Esse comportamento ocorre porque o clique pode ser feito de uma mbox diferente daquela que forneceu a oferta. Nesse caso, a métrica está associada à atividade, mas não à oferta.

## Configurar grupos de relatórios

A atribuição de ofertas a grupos de relatórios determina como o [!DNL Target] cria seus modelos de personalização e como as ofertas são exibidas nos relatórios de atividades. Configure os grupos enquanto cria a atividade ou, posteriormente, se adicionar novas ofertas a uma atividade ativa.

1. Na página **[!UICONTROL Experiências]** de uma atividade de AP, clique no ícone **[!UICONTROL Gerenciar conteúdo]** ( ![Ícone Gerenciar conteúdo](/help/main/assets/icons/Experience.svg) ).

1. Clique na guia **[!UICONTROL Ofertas]** na parte superior da caixa de diálogo **[!UICONTROL Gerenciar conteúdo]**.

   ![Ícone Configurar](../assets/ap-offers-2.png)

1. (Condicional) Escolha as ofertas a serem adicionadas a um grupo de relatórios.

   * Para adicionar uma única oferta, clique no ícone **[!UICONTROL Mais Ações]** ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmall.svg) ) da oferta e clique em **[!UICONTROL Grupo de Relatórios]**.
   * Para adicionar várias ofertas de uma só vez, marque as caixas de seleção das ofertas e clique em **[!UICONTROL Grupo de Relatórios]** na parte inferior da caixa de diálogo.

1. Atribuir as ofertas selecionadas a um grupo de relatórios.

   * Para atribuir as ofertas a um grupo de relatórios existente, selecione **[!UICONTROL Existente]**, selecione o grupo de relatórios na lista suspensa e clique em **[!UICONTROL Confirmar]**.
   * Para criar um grupo de relatórios para as ofertas, selecione **[!UICONTROL Novo]**, nomeie o novo grupo de relatórios e clique em **[!UICONTROL Confirmar]**.

Para restringir a lista de ofertas, filtre-a por local com a lista **[!UICONTROL Local]** ou por grupo de relatórios com a lista **[!UICONTROL Grupo de Relatórios]**. A lista **[!UICONTROL Grupo de Relatórios]** também oferece a opção **[!UICONTROL Ofertas Não Atribuídas]**, que exibe as ofertas que ainda não pertencem a nenhum grupo de relatórios, para que você possa atribuí-las a um grupo.

Para obter informações sobre como direcionar uma oferta para públicos específicos, consulte [Ofertas do **[!UICONTROL Automated Personalization]** do Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#set-up-targeting-rules).

## Exibir ofertas em um grupo de relatórios

O relatório **[!UICONTROL Nível de oferta]** mostra como as ofertas de uma atividade são executadas, agrupadas por grupo de relatórios, para que você possa comparar os grupos e as ofertas individuais.

1. Clique em **[!UICONTROL Atividades]**, clique na atividade **[!UICONTROL Automated Personalization]** da lista e na guia **[!UICONTROL Relatórios]** para exibir o relatório [Nível da oferta](/help/main/c-reports/personalization-reports/reports-ap.md).

   Se você tem muitas atividades, clique no ícone **[!UICONTROL Mostrar Filtros]** (funnel) e marque a caixa de seleção **[!UICONTROL Automated Personalization]** para exibir apenas as atividades do **[!UICONTROL Automated Personalization]**.

1. Clique em **[!UICONTROL Controle]** ou **[!UICONTROL Direcionado]** na tabela para exibir as ofertas desagrupadas e as ofertas dentro dos grupos de relatórios.

   ![Grupos de ofertas: controle e direcionado](/help/main/c-reports/assets/offer-groups.png)

Para obter informações sobre como usar os relatórios do **[!UICONTROL Automated Personalization]** (incluindo o relatório do **[!UICONTROL Nível de Oferta]**), consulte os [relatórios de Resumo do Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).
