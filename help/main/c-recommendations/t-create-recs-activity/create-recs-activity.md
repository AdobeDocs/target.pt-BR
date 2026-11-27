---
keywords: criar recomendações, atividade do recommendations, novas recomendações, visão geral do recommendations
description: Saiba como usar o [!DNL Target] [!UICONTROL Visual Experience Composer] (VEC) para criar uma atividade [!DNL Recommendations].
title: Criar uma atividade [!DNL Recommendations]
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: c83073d5-f852-4f09-8343-e4658fbf6f43
TQID: 'https://experienceleague.adobe.com/rb9any1dsbk-E-ELV56A2D6X5f0z0cTziscrajmbYDA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1169'
ht-degree: 3%
---
# Criar uma atividade [!DNL Recommendations] {#create-recs-activity}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como criar uma atividade do [!DNL Recommendations] no [!DNL Target] **[!UICONTROL Visual Experience Composer]** (VEC), desde selecionar o local até configurar a atividade.

>[!ENDSHADEBOX]

Uma atividade [!DNL Recommendations] exibe itens recomendados em uma página. A criação da atividade no [!DNL Target] **[!UICONTROL Visual Experience Composer]** (VEC) permite que as recomendações sejam colocadas diretamente em uma página habilitada para [!DNL Target], no local exato em que os visitantes devem vê-las.

## Crie a atividade e selecione o local {#create-activity}

O URL da atividade e o local definem a página e a área dessa página onde as recomendações são exibidas.

1. No menu **[!UICONTROL Atividades]**, clique em **[!UICONTROL Criar Atividade]** > **[!UICONTROL Recomendações]**.

   ![A página Todas as Atividades com o menu Criar Atividade aberto e a opção Recomendações realçada](../assets/create_reco_1.png)

1. Selecione **[!UICONTROL Visual]**, se necessário.

   Para usar o **[!UICONTROL Experience Composer baseado em formulário]**, selecione **[!UICONTROL Formulário]**. Consulte [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md). Para obter uma comparação dos compositores, incluindo o VEC **[!UICONTROL Aplicativo de página única]**, consulte [Experiências e ofertas](/help/main/c-experiences/experiences.md). Para problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Escolha um [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique o URL da atividade e clique em **[!UICONTROL Criar]**.

   O URL da atividade é a página onde as recomendações são exibidas. [!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]), portanto `http://www.adobe.com/br` e `https://www.adobe.com/br` são correspondentes.

   O VEC é aberto e mostra a página.

1. Clique no elemento onde as recomendações devem ser exibidas e selecione **[!UICONTROL Substituir conteúdo]** > **[!UICONTROL Recomendação]**.

   <!--
   * **[!UICONTROL Replace w/ Recommendations]**: Deletes the current content of the element and replaces it with the recommendations.
   * **[!UICONTROL Insert Recommendations Before]**: Places the recommendations before the element, above or to the left of it, depending on the page construction.
   * **[!UICONTROL Insert Recommendations After]**: Places the recommendations after the element, below or to the right of it, depending on the page construction.

   ![Visual Experience Composer with a selected container and the menu options Replace w/ Recommendations, Insert Recommendations Before, Insert Recommendations After, and Expand Selection](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   Use **[!UICONTROL Expand Selection]** to expand the selection to the parent container, so that it includes the desired page elements.
   -->

   Os visitantes qualificados para a recomendação veem os itens recomendados na área especificada. Os visitantes que não se qualificarem verão o conteúdo padrão.

   >[!NOTE]
   >
   >**[!UICONTROL As atividades do Recommendations]** oferecem suporte a apenas uma modificação ou recomendação por vez. Para exibir várias recomendações, crie várias atividades [!DNL Recommendations] ou use o teste A/B ou XT.

   ![Visual Experience Composer com uma imagem selecionada na página e a opção Recomendação exibida no menu](../assets/create_reco_2.png)

<!--
1. Select a page type: Cart Page, Category Page, Home Page, Landing Page, Product Page, Search Results Page, Thank You Page, or Other.

   ![Select Page Type dialog box with the list of page types open](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

   The page type determines which criteria are suggested in the next section.
-->

1. Acesse o menu **[!UICONTROL Mostrar propriedades]** e clique em **[!UICONTROL Selecionar uma recomendação]**.

   ![Painel de recomendação do Visual Experience Composer com o botão Selecionar uma recomendação](../assets/create_reco_3.png)

## Selecione os critérios {#select-criteria}

Os critérios determinam quais itens são recomendados e como são escolhidos para cada visitante.

1. Marque a caixa de seleção de um ou mais [critérios](/help/main/c-recommendations/c-algorithms/algorithms.md).

   ![Caixa de diálogo Selecionar Critérios com o campo de pesquisa, o ícone de filtro, o botão Criar critérios e a lista de critérios com um critério selecionado](../assets/create_reco_4.png)

   Quando vários critérios são selecionados, o tráfego é dividido igualmente entre eles e as porcentagens não podem ser alteradas para cada critério. Por exemplo, se dois critérios forem selecionados e a atividade exibir conteúdo padrão para 20% dos participantes, 40% deles verão as recomendações de cada critério.

   >[!NOTE]
   >
   >Nem todos os critérios são executados corretamente em cada página. Para que as recomendações do item atual ou da categoria atual sejam compatíveis, a página ou mbox deve passar em `entity.id` ou `entity.categoryId`. É melhor mostrar apenas critérios compatíveis. Para disponibilizar critérios incompatíveis para a atividade, desmarque a caixa de seleção **[!UICONTROL Compatível]**. Esta caixa de seleção pode não ser exibida, dependendo da configuração **[!UICONTROL Administração]** > **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios de Filtro Incompatíveis]**. Para obter mais informações, consulte [Configurações](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=pt-BR){target=_blank}.

1. Opcionalmente, localize ou crie critérios:

   * Para pesquisar um critério existente quando a lista for longa, digite no campo de pesquisa até que os critérios desejados sejam exibidos. Alguns critérios são fornecidos com [!DNL Recommendations], e a equipe também pode criar critérios personalizados.
   * Para criar um novo critério, clique em **[!UICONTROL Criar critério]** e insira as informações para o novo critério. Consulte [Criar critérios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).
   * Para agrupar critérios em uma sequência, crie uma sequência de critérios. Consulte [Criar sequências de critérios](/help/main/c-recommendations/c-algorithms/create-criteria-sequence.md).

1. Clique em **[!UICONTROL Avançar]**.

## Selecionar o design e as promoções {#select-design}

Um design é um modelo que determina a aparência das recomendações no local selecionado, e uma coleção determina quais itens podem aparecer. Como opção, as promoções podem ser adicionadas às recomendações.

1. Selecione um [design](/help/main/c-recommendations/c-design-overview/design-overview.md).

   ![Caixa de diálogo Selecionar Design com o botão Criar design e a lista de designs com o Design 2 x 4 selecionado](../assets/create_reco_5.png)

   * Para usar designs existentes, marque a caixa de seleção de um ou mais designs e clique em **[!UICONTROL Avançar]**. Somente um design pode ser selecionado quando vários critérios são selecionados.
   * Para criar um design personalizado, clique em **[!UICONTROL Criar design]** e insira o nome e o código do novo design. Clique em **[!UICONTROL Avançar]**, selecione ou carregue uma imagem e clique em **[!UICONTROL Concluído]** > **[!UICONTROL Concluído]**.

   [!DNL Target] inclui vários designs pré-configurados. Para obter mais informações sobre designs personalizados, consulte [Criar um design](/help/main/c-recommendations/c-design-overview/create-design.md#create-design) e [Personalizar um design usando o Velocity](/help/main/c-recommendations/c-design-overview/customizing-a-template.md#customize-design).

1. Clique em **[!UICONTROL Avançar]**.

1. Na página **[!UICONTROL Opções]**, selecione a coleção.

   A coleção determina quais itens estão qualificados para serem exibidos nas recomendações. Para obter mais informações, incluindo como criar uma coleção, consulte [Usar uma coleção em uma atividade](/help/main/c-recommendations/c-products/collections.md#use-collection).

1. (Opcional) Adicione promoções frente e atrás às recomendações. Consulte [Adicionar promoções](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#add-promotions).

1. Clique em **[!UICONTROL Salvar]**.

   A tela do VEC exibe o design da recomendação na página.

## Revisar e concluir a atividade {#complete-activity}

Analisar as recomendações e o fluxo de atividade antes de salvar ajuda a confirmar se o público-alvo, os critérios e o design corretos estão em vigor.

1. (Opcional) Clique em **[!UICONTROL Visualizar]** para ver como a atividade aparece para os visitantes. Esse modo permite a interação com as recomendações, pois um visitante interagiria com elas. Clique em **[!UICONTROL Compor]** para retornar ao VEC.

1. Examine a recomendação no VEC e clique em **[!UICONTROL Avançar]**.

1. Revise a atividade no diagrama de fluxo e faça as alterações necessárias. Clique em **[!UICONTROL Avançar]** quando terminar.

   ![Diagrama de fluxo do Recommendations com Todos os visitantes dividido em um grupo de controle de 10% e um grupo de 90% que leva à coleção Todas as coleções, aos critérios selecionados e ao Design 2 x 4](../assets/create_reco_6.png)

   O diagrama do fluxo aborda o público-alvo da atividade, as experiências e as métricas de sucesso. No diagrama, as seguintes alterações podem ser feitas:

   * **Público-alvo**: todos os visitantes veem as recomendações por padrão, mas um público-alvo existente pode ser selecionado. Como alternativa para criar um novo público-alvo, um [público-alvo somente atividade](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) pode ser criado ou [vários públicos-alvo podem ser combinados](/help/main/c-target/combining-multiple-audiences.md#section_2F1CE9434CC04174B4BA2BFC89B85D77) para criar um público-alvo ad hoc.
   * **Critério**: exibir os critérios ou alterar a coleção (ao lado do rótulo **[!UICONTROL Critério]**).
   * **Grupo de controle**: altere a porcentagem de participantes que visualizam a experiência de controle. Em uma atividade [!DNL Recommendations], o grupo de controle visualiza a página sem nenhuma recomendação.
   * **Design**: exibir o código de design, alterar ou remover o design.

1. Especifique as configurações de atividade, por exemplo, um nome (obrigatório) e um objetivo (opcional). Para as configurações, incluindo as regras para o nome da atividade, consulte [Configurações de atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#recs-activity-settings).

1. Clique em **[!UICONTROL Salvar e fechar]**.

## Gerenciar a atividade {#manage-activity}

Depois que a atividade é salva, a página **[!UICONTROL Visão geral]** exibe um resumo da atividade. Nessa página, as seguintes ações estão disponíveis:

* Ative, edite ou faça o QA da atividade.
* Compartilhe a atividade no feed da Experience Cloud.
* Visualize os URLs da experiência e baixe os dados.
* Alterar a porcentagem dos participantes da atividade que visualizam a experiência de controle.
* Mostrar ou ocultar os detalhes dos critérios e exibir o código dos designs.

Duas páginas adicionais estão disponíveis na atividade:

* **[!UICONTROL Relatórios]**: mostra o relatório sobre o desempenho da atividade [!DNL Recommendations].
* **[!UICONTROL Conflitos]**: mostra qualquer [conflito de atividade](/help/main/c-experiences/c-visual-experience-composer/activity-collisions.md) que possa ocorrer. Conflitos ocorrem quando várias atividades entregam conteúdo na mesma página e podem fazer com que conteúdo inesperado seja exibido.

## Vídeo de treinamento: criar uma atividade do Recommendations (7:15) ![Selo do tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/33964?captions=por_br)
