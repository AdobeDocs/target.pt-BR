---
keywords: criar recomendações, atividade do recommendations, novas recomendações, visão geral do recommendations
description: Saiba como usar o Adobe [!DNL Target] Visual Experience Composer (VEC) para criar uma atividade do Recommendations diretamente em um [!DNL Target]página ativada.
title: Como criar uma atividade do Recommendations?
feature: Recommendations
exl-id: c83073d5-f852-4f09-8343-e4658fbf6f43
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 76%

---

# ![PREMIUM](/help/main/assets/premium.png) Criar uma atividade do Recommendations

Use o Visual Experience Composer (VEC) do Target para criar uma atividade do Recommendations diretamente em uma página habilitada para o Target e modificar partes da página no Target.

1. Clique em **[!UICONTROL Criar atividade]** > **[!UICONTROL Recomendações]**.

   ![Criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_CreateActivity.png)

1. Selecione **[!UICONTROL Visual (Padrão)]**, se necessário.

   ![Caixa de diálogo Criar atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/DB_NewRecAct.png)

   Se preferir usar o Experience Composer baseado em formulário, selecione [!UICONTROL Formulário]. Consulte [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do Experience Composer baseado em formulário, o Target oferece o VEC para aplicativo de página única e o VEC para aplicativos móveis. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/main/c-experiences/experiences.md).
   >
   >Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >O [!UICONTROL [Escolher local de trabalho]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) na ilustração anterior é uma opção [Target Premium](/help/main/c-intro/intro.md) recurso. Caso não veja essa opção, a licença da organização é do Target Standard.

1. (Condicional) Se você for um [cliente do Target Premium](/help/main/c-intro/intro.md#premium), escolha um [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique um URL de atividade e, em seguida, clique em **[!UICONTROL Avançar]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://wwww.adobe.com`] têm correspondência.

   O URL de atividade é a página onde as recomendações serão exibidas.

   Ao clicar em [!UICONTROL Avançar], o VEC será aberto e irá exibir sua página. Você pode substituir um elemento atual com recomendações ou inseri-las.

1. Clique em um elemento na página e, em seguida, se as recomendações estiverem disponíveis no local onde esse elemento está localizado, clique em **[!UICONTROL Substituir por Recommendations]**, **[!UICONTROL Inserir o Recommendations antes de]** ou **[!UICONTROL Inserir o Recommendations depois de]**.

   Os visitantes do seu site verão o conteúdo recomendado somente se se qualificarem para a recomendação. Os visitantes que não se qualificarem para a recomendação verão o conteúdo padrão.

   ![Opções do Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_Replace-Insert.png)

   * **[!UICONTROL Substituir por Recommendations]**: Substituir um elemento por recomendações exclui o conteúdo atual e o substitui por suas recomendações. Quando os visitantes visitam seu site e se qualificam para a recomendação, eles verão os itens recomendados na área especificada em vez do conteúdo existente.
   * **[!UICONTROL Inserir o Recommendations antes de]**: Inserir recomendações antes do elemento selecionado coloca o conteúdo recomendado antes desse elemento. Dependendo da construção da sua página, a recomendação é exibida acima ou à esquerda do elemento selecionado.
   * **[!UICONTROL Inserir o Recommendations depois de]**: Inserir recomendações depois do elemento selecionado coloca o conteúdo recomendado após esse elemento. Dependendo da construção da sua página, a recomendação é exibida abaixo ou à direita do elemento selecionado.

   O **[!UICONTROL Expandir seleção]** permite expandir o local selecionado (contêiner pai) para ajudar você a identificar e incluir facilmente os elementos de página desejados com mais facilidade.

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

   ![Selecionar opções de Tipo de página](/help/main/c-recommendations/t-create-recs-activity/assets/Menu_PageType.png)

1. Selecione um ou mais [critérios](/help/main/c-recommendations/c-algorithms/algorithms.md).

   Os critérios são exibidos como cartões que mostram as informações sobre cada um dos critérios. Por padrão, a variável [!UICONTROL Selecionar critérios] exibe critérios compatíveis com seu negócio vertical e o tipo de página selecionado na etapa anterior. Você pode alterar essas opções para exibir outros critérios.

   >[!NOTE]
   >
   >Nem todos os critérios serão executados corretamente em cada página. A página ou mbox precisam passar pela `entity.id` ou `entity.categoryId` para as recomendações do item atual/categoria atual para serem compatíveis. Em geral, é melhor mostrar apenas critérios compatíveis. No entanto, se você desejar que critérios incompatíveis estejam disponíveis para a atividade, desmarque a caixa de seleção **[!UICONTROL Compatível]**. A opção [!UICONTROL Compatível] talvez não seja exibida, dependendo de suas configurações do Recommendations (**[!UICONTROL Recommendations]** > **[!UICONTROL Configurações]** > **[!UICONTROL Filtro critérios incompatíveis]**). Para obter mais informações, consulte [Configurações](https://developer.adobe.com/target/implement/recommendations/).

   ![Caixa de diálogo Selecionar critérios](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_SelectCriteria2.png)

   Se você selecionar vários critérios, o tráfego será dividido igualmente entre eles. Por exemplo, se você tiver selecionado dois critérios, e sua atividade for projetada para exibir conteúdo padrão para 20% dos participantes da atividade, então 40% dos participantes da atividade verão as recomendações controladas por cada critério. Não há opções para alterar as porcentagens de cada critério.

   * Para pesquisar um critério existente (por exemplo, se forem exibidos muitos cartões de critério), digite no campo de pesquisa até que os critérios desejados sejam exibidos, selecione o critério e clique em **[!UICONTROL Próximo]**.

      Alguns critérios são fornecidos com o [!DNL Recommendations]. Você e sua equipe também podem criar seus próprios critérios personalizados.

   * Para criar um novo critério, clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar critérios]**, em seguida, preencha as informações para o novo critério. Para obter informações sobre como criar novos critérios, consulte [Criação de critérios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).
   * Você também pode agrupar critérios em sequências. Para criar uma nova sequência de critérios, clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar sequência de critérios]**. Consulte [Criar sequência de critérios](/help/main/c-recommendations/c-algorithms/create-criteria-sequence.md) para obter mais informações.

1. Clique em **[!UICONTROL Avançar]**.
1. Selecione um [design](/help/main/c-recommendations/c-design-overview/design-overview.md).

   Um design é um modelo que determina a aparência dos locais em sua página. [!DNL Target] O inclui vários designs pré-configurados. Também é possível criar designs personalizados. Para obter mais informações, consulte [Criar um design](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14) e [Personalizar um design](/help/main/c-recommendations/c-design-overview/customizing-a-template.md#concept_94F1554C3F2E4CDB9A2C3D78F10EDA59).

   ![Caixa de diálogo Selecionar design](/help/main/c-recommendations/t-create-recs-activity/assets/Card_SelectDesign.png)

   Cada design exibe uma representação gráfica de como será sua aparência e ícones que mostram quantas de suas atividades inicializadas e inativas atualmente usam aquele design.

   * Para selecionar um ou mais designs existentes, clique nos designs e depois em **[!UICONTROL Próximo]**.

      Se você selecionou vários critérios, é possível selecionar apenas um design.

   * Para criar um design personalizado, clique em **[!UICONTROL Criar design]** e, em seguida, preencha o nome e o código do novo design. Clique em **[!UICONTROL Avançar]**, selecione ou faça o upload de uma imagem e clique em **[!UICONTROL Concluído]** > **[!UICONTROL Concluído]**. Para obter informações sobre como criar um novo design, consulte [Criar um design](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Clique em **[!UICONTROL Avançar]**.

   Você tem a opção de adicionar promoções para suas recomendações. Para mais informações sobre adicionar promoções frente e atrás, consulte  [Adição de promoções](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14).

1. Clique em **[!UICONTROL Salvar]**.

   A tela do VEC exibe o design da recomendação na sua página.

1. (Opcional) Clique em **[!UICONTROL Visualizar]** para ver como a atividade irá aparecer para os visitantes.

   O modo [!UICONTROL Visualizar] permite que você interaja com suas recomendações, como um visitante faria.

   Quando tiver terminado de visualizar suas recomendações, clique em **[!UICONTROL Compor]**.

1. Examine sua recomendação no VEC e clique em **[!UICONTROL Avançar]**.

1. Analise sua atividade do [!DNL Recommendations] no diagrama de fluxo e faça as alterações necessárias.

   ![Diagrama de fluxo do Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/SCRN_Workflow.png)

   O diagrama do fluxo guia você pelas etapas da escolha do público-alvo para a atividade, configurando as experiências e especificando as métricas de sucesso.

   No diagrama de fluxo, você pode fazer o seguinte:

   * Alterar o público-alvo que verá as recomendações

      >[!NOTE]
      >
      >Além de selecionar um público existente, você pode [criar um público somente atividade](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) ou [combinar vários públicos para criar públicos](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) combinados ad hoc em vez de criar um novo público.

      Por padrão, todos os usuários visualizam as recomendações. No entanto, você pode direcionar a recomendação para um público-alvo específico.

      Para uma atividade do [!DNL Recommendations], o grupo de controle visualiza a página sem nenhuma recomendação.

   * Visualize os critérios
   * Altere a coleção (ao lado da etiqueta [!UICONTROL Critérios])
   * Altere a porcentagem dos participantes que visualizam a experiência de controle
   * Visualize o código do design
   * Altere ou remova um design

1. Clique em **[!UICONTROL Avançar]** ao concluir.
1. Especifique suas configurações de atividade.

   Por exemplo, digite um nome (obrigatório) e objetivo (opcional) para a atividade. Para obter informações sobre as configurações, consulte [Configurações da atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB).

   >[!NOTE]
   >
   >Se você especificar um nome de atividade do [!DNL Recommendation] que já existe para outra atividade no [!DNL Recommendations Classic], a nova atividade será ressincronizada com um novo nome. O novo nome é o nome original anexado com um carimbo de data e hora que o torna exclusivo. O novo nome é exibido no [!DNL Target Standard/Premium] e no [!DNL Recommendations Classic].

1. Ao finalizar, clique em **[!UICONTROL Salvar e fechar]**.

   Uma visão geral da sua atividade é exibida.

   Na página de [!UICONTROL visão geral] é possível:

   * Ativar a atividade
   * Editar a atividade
   * Compartilhe a atividade no feed do Experience Cloud
   * Controle de qualidade da atividade
   * Visualizar seus URLs da experiência
   * Baixar os dados
   * Alterar a porcentagem dos participantes da atividade que visualizam a experiência de controle
   * Mostrar ou ocultar detalhes
   * Visualizar o código dos seus designs

1. (Opcional) Abra a guia [!UICONTROL Relatórios] para visualizar o relatório que mostra o desempenho de sua atividade do [!DNL Recommendations].

1. (Opcional) Abra a guia [!UICONTROL Conflitos] para visualizar qualquer [conflito de atividade](/help/main/c-experiences/c-visual-experience-composer/activity-collisions.md) que possa ocorrer.

   Conflitos de atividade ocorrem quando várias atividades estão definidas para entregar conteúdo na mesma página e podem fazer com que conteúdo inesperado seja exibido.

## Vídeo de treinamento: criar uma atividade do Recommendations (7:15) ![Selo do tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/27688)
