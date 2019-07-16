---
description: Use o Visual Experience Composer (VEC) do Target para criar uma atividade do Recommendations diretamente em uma página habilitada para o Target e modificar partes da página no Target.
keywords: criar recomendações, atividade do recommendations, novas recomendações, visão geral do recommendations
seo-description: Use o Visual Experience Composer (VEC) do Target para criar uma atividade do Recommendations diretamente em uma página habilitada para o Target e modificar partes da página no Target.
seo-title: Criar uma atividade do Recommendations
solution: Target
title: Criar uma atividade do Recommendations
title-outputclass: premium
topic: Premium
uuid: c3f22cce-204a-4509-92c4-8fec43fbaebe
badge: premium
translation-type: tm+mt
source-git-commit: 1f3b3be385cad4e7e87f27b566fc1266eef649b8

---


# ![PREMIUM](/help/assets/premium.png) Criar uma atividade do Recommendations{#create-a-recommendations-activity}

Use o Visual Experience Composer (VEC) do Target para criar uma atividade do Recommendations diretamente em uma página habilitada para o Target e modificar partes da página no Target.

1. Clique em **[!UICONTROL Criar atividade]** &gt; **[!UICONTROL Recommendations]**.

   ![Atividade Criar recomendações](/help/c-recommendations/t-create-recs-activity/assets/Menu_CreateActivity.png)

1. Select **[!UICONTROL Visual (Default)]**, if necessary.

   ![Caixa de diálogo Criar atividade do Recommendations](/help/c-recommendations/t-create-recs-activity/assets/DB_NewRecAct.png)

   Se preferir usar o Experience Composer baseado em formulário, selecione [!UICONTROL Formulário]. See [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md) for more information.

   >[!NOTE]
   >
   >Além do VEC e do Criador de experiências baseado em forma, o Target oferece o VEC do aplicativo de página única e o VEC para aplicativos móveis. For more information about the various composers, see [Experiences and Offers](/help/c-experiences/experiences.md).
   >
   >Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >The [!UICONTROL [Choose Workplace](/help/administrating-target/c-user-management/property-channel/property-channel.md) option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. Sua organização tem uma licença do Target Standard caso não veja essa opção.]

1. (Conditional) If you are a [Target Premium customer](/help/c-intro/intro.md#premium), choose a [workspace](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique um URL de atividade e, em seguida, clique em **[!UICONTROL Avançar]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://wwww.adobe.com`] são correspondentes.

   O URL de atividade é a página onde as recomendações serão exibidas.

   Ao clicar em [!UICONTROL Avançar], o VEC será aberto e irá exibir sua página. Você pode substituir um elemento atual com recomendações ou inseri-las.

1. Click an element on your page, then if recommendations are available where that element is located, click **[!UICONTROL Replace w/ Recommendations]**, **[!UICONTROL Insert Recommendations Before]**, or **[!UICONTROL Insert Recommendations After]**.

   ![Opções do Recommendations](/help/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   Substituir um elemento com recomendações exclui o conteúdo atual e o substituiu com as suas recomendações.

1. Selecione um tipo de página.

   Os tipos de página podem incluir:

   * Página de carrinho
   * Página de categoria
   * Página inicial
   * Página de aterrissagem
   * Página do produto
   * Página de resultados da pesquisa
   * Página de agradecimento
   * Outras
   ![Selecionar opções de Tipo de página](/help/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. Select one or more [criteria](/help/c-recommendations/c-algorithms/algorithms.md).

   Os critérios são exibidos como cartões que mostram as informações sobre cada um dos critérios. Por padrão, a tela [!UICONTROL Selecionar critério] mostra critérios que são compatíveis com seu negócio vertical e o tipo de página que você selecionou. Você pode alterar essas opções para exibir outros critérios.

   >[!NOTE]
   >
   >Nem todos os critérios serão executados corretamente em cada página. A página ou mbox precisam passar pela `entity.id` ou `entity.categoryId` para as recomendações do item atual/categoria atual para serem compatíveis. Em geral, é melhor mostrar apenas critérios compatíveis. No entanto, se você desejar que critérios incompatíveis estejam disponíveis para a atividade, desmarque a caixa de seleção **[!UICONTROL Compatível]**. A opção [!UICONTROL Compatível] talvez não seja exibida, dependendo de suas configurações do Recommendations (**[!UICONTROL Recommendations]** &gt; **[!UICONTROL Configurações]** &gt; **[!UICONTROL Filtrar critérios incompatíveis]**). Para obter mais informações, consulte [Configurações](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84).

   ![Caixa de diálogo Selecionar critérios](/help/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   Se você selecionar vários critérios, o tráfego será dividido igualmente entre eles. Por exemplo, se você tiver selecionado dois critérios, e sua atividade for projetada para exibir conteúdo padrão para 20% dos participantes da atividade, então 40% dos participantes da atividade verão as recomendações controladas por cada critério. Não há opções para alterar as porcentagens de cada critério.

   * To search for an existing criteria (for example, if a large number of criteria cards are displayed), type in the search field until the desired criteria appears, then select the criteria and click **[!UICONTROL Next]**.

      Alguns critérios são fornecidos com o [!DNL Recommendations]. Você e sua equipe também podem criar seus próprios critérios personalizados.

   * To create a new criteria, click **[!UICONTROL Create Criteria]** &gt; **[!UICONTROL Create Criteria]**, then fill in the information for the new criteria. Para obter informações sobre como criar novos critérios, consulte [Criação de critérios](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).
   * Você também pode agrupar critérios em sequências. To create a new criteria sequence, click **[!UICONTROL Create Criteria]** &gt; **[!UICONTROL Create Criteria Sequence]**. Consulte [Criando sequências de critérios](../../c-recommendations/c-algorithms/create-criteria-sequence.md#task_8A9CB465F28D44899F69F38AD27352FE) para obter mais informações.

1. Clique em **[!UICONTROL Avançar]**.
1. Select a [design](/help/c-recommendations/c-design-overview/design-overview.md).

   Um design é um modelo que determina a aparência dos locais em sua página. [!DNL Target]O inclui vários designs pré-configurados. Também é possível criar designs personalizados. Para obter mais informações, consulte [Criar um design](../../c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14) e [Personalizar um design](../../c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59).

   ![Caixa de diálogo Selecionar design](/help/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   Cada design exibe uma representação gráfica de como será sua aparência e ícones que mostram quantas de suas atividades inicializadas e inativas atualmente usam aquele design.

   * To select one or more existing designs, click the designs, then click **[!UICONTROL Next]**.

      Se você selecionou vários critérios, é possível selecionar apenas um design.

   * To create a custom design, click **[!UICONTROL Create Design]**, then fill in the name and code for the new design. Clique em **[!UICONTROL Avançar]**, selecione ou faça o upload de uma imagem e clique em **[!UICONTROL Concluído]** &gt; **[!UICONTROL Concluído]**. Para obter informações sobre como criar um novo design, consulte [Criar um design](../../c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Clique em **[!UICONTROL Avançar]**.

   Você tem a opção de adicionar promoções para suas recomendações. Para mais informações sobre adicionar promoções frente e atrás, consulte [Adição de promoções](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14).
1. Clique em **[!UICONTROL Salvar]**.

   A tela do VEC exibe o design da recomendação na sua página.

1. (Opcional) Clique em **[!UICONTROL Visualizar]** para ver como a atividade irá aparecer para os visitantes.

   O modo [!UICONTROL Visualizar] permite que você interaja com suas recomendações, como um visitante faria.

   Quando tiver terminado de visualizar suas recomendações, clique em **[!UICONTROL Compor]**.

1. Examine sua recomendação no VEC e clique em **[!UICONTROL Avançar]**.

1. Analise sua atividade do [!DNL Recommendations] no diagrama de fluxo e faça as alterações necessárias.

   ![Diagrama de fluxo do Recommendations](/help/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   O diagrama do fluxo guia você pelas etapas da escolha do público-alvo para a atividade, configurando as experiências e especificando as métricas de sucesso.

   No diagrama de fluxo, você pode fazer o seguinte:

   * Alterar o público-alvo que verá as recomendações

      >[!NOTE]
      >
      >Além de selecionar um público existente, você pode [criar um público somente atividade](../../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) ou [combinar vários públicos para criar públicos](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) combinados ad hoc em vez de criar um novo público.

      Por padrão, todos os usuários visualizam as recomendações. No entanto, você pode direcionar a recomendação para um público-alvo específico.

      Para uma atividade do [!DNL Recommendations], o grupo de controle visualiza a página sem nenhuma recomendação.

   * Visualize os critérios
   * Altere a coleção (ao lado da etiqueta [!UICONTROL Critérios])
   * Altere a porcentagem dos participantes que visualizam a experiência de controle
   * Visualize o código do design
   * Altere ou remova um design

1. Clique em **[!UICONTROL Avançar]** ao concluir.
1. Especifique suas configurações de atividade.

   Por exemplo, digite um nome (obrigatório) e objetivo (opcional) para a atividade. Para obter informações sobre as configurações, consulte [Configurações da atividade do Recommendations](../../c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB).

   >[!NOTE]
   >
   >Se você especificar um nome de atividade do [!DNL Recommendation] que já existe para outra atividade no [!DNL Recommendations Classic], a nova atividade será ressincronizada com um novo nome. O novo nome é o nome original anexado com um carimbo de data e hora que o torna exclusivo. O novo nome é exibido no [!DNL Target Standard/Premium] e no [!DNL Recommendations Classic].

1. When finished, click **[!UICONTROL Save &amp; Close]**.

   Uma visão geral da sua atividade é exibida.

   Na página de [!UICONTROL visão geral] é possível:

   * Ativar a atividade
   * Editar a atividade
   * Colocar a atividade no quadro da Experience Cloud
   * Visualizar seus URLs da experiência
   * Baixar os dados
   * Alterar a porcentagem dos participantes da atividade que visualizam a experiência de controle
   * Mostrar ou ocultar detalhes
   * Visualizar o código dos seus designs.

1. (Opcional) Abra a guia [!UICONTROL Relatórios] para visualizar o relatório que mostra o desempenho de sua atividade do [!DNL Recommendations].
1. (Opcional) Abra a guia [!UICONTROL Conflitos] para visualizar qualquer [conflito de atividade](https://marketing.adobe.com/resources/help/en_US/target/target/c_activity_collisions.html) que possa ocorrer.

   Conflitos de atividade ocorrem quando várias atividades estão definidas para entregar conteúdo na mesma página e podem fazer com que conteúdo inesperado seja exibido.
