---
keywords: criar alocação automática;teste A/B;atividade de alocação automática;nova atividade a/b;alocação automática;alocar automaticamente para a melhor experiência;alocar;alocar automaticamente
description: Saiba como usar o [!UICONTROL Visual Experience Composer] (VEC) no  [!DNL Adobe Target] para criar uma atividade de Teste A/B do [!UICONTROL Auto-Allocate].
title: Como criar uma atividade [!UICONTROL Auto-Allocate]?
feature: Auto-Allocate
exl-id: 30bc95e0-4f5e-4d1f-bad2-7b20b8f3c7d2
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 37%

---

# Criar uma atividade [!UICONTROL Auto-Allocate]

Use o [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] para criar sua atividade do [!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] diretamente em uma página habilitada para [!DNL Target] e modificar partes da página no [!DNL Target].

Além da atividade [!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] (discutida neste artigo), [!DNL Target] fornece dois tipos adicionais de atividades [!UICONTROL A/B Test]: [!UICONTROL Manual (Default)] e [!UICONTROL Auto-Target]. Consulte [Tipos de atividades de teste A/B](/help/main/c-activities/t-test-ab/test-ab.md#types) na *Visão geral do teste A/B*.

Para criar uma atividade [!UICONTROL Auto-Allocate]:

1. Na lista **[!UICONTROL Activities]**, clique em **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**.

   ![Lista suspensa Criar atividade](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   Os tipos de atividades disponíveis dependem da sua conta do [!DNL Target]. Alguns tipos de atividades podem não aparecer na lista. Por exemplo, [!UICONTROL Recommendations] é um [recurso do Target Premium](/help/main/c-intro/intro.md#premium). Para obter informações sobre os vários tipos de atividades, consulte [Atividades](/help/main/c-activities/activities.md) e o [Guia de atividades do Target](/help/main/c-activities/target-activities-guide.md).

1. Na caixa de diálogo **[!UICONTROL Create A/B Test Activity]**, selecione **[!UICONTROL Visual]**, se necessário.

   Se preferir usar o [!UICONTROL Form-Based Experience Composer], selecione [!UICONTROL Form]. Consulte [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Form-Based Experience Composer], o [!DNL Target] oferece o VEC para Aplicativos de Página Única. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/main/c-experiences/experiences.md).
   >
   >Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Se você for um [cliente do Target Premium](/help/main/c-intro/intro.md#premium), escolha um [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique o [URL da atividade](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) e clique em **[!UICONTROL Create]**.

   Se sua conta foi configurada com um URL padrão, esse URL aparece por padrão. Você pode alterar o URL padrão para outro, se necessário.

   A [!UICONTROL Visual Experience Composer] é aberta, mostrando a página especificada na URL.

   ![VEC](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Digite um nome para a atividade no espaço fornecido.

   ![Campo nome](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   O nome da atividade não pode começar com nenhum dos seguintes caracteres:

   | Caractere | Descrição |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Plus |
   | `-` | menos |
   | `@` | Sinal de arroba |

1. Crie quaisquer experiências alterando os elementos na página.

   O [!UICONTROL Visual Experience Composer] exibe duas guias no lado esquerdo depois que você cria uma nova atividade: Experiência A e Experiência B. A Experiência A é a experiência de controle. Seu foco está na guia Experiência B, que pode ser modificada conforme desejado. A Experiência B é a experiência alternativa que você pode adicionar ao seu teste. Você pode adicionar várias experiências ao teste. Você também podem excluir a Experiência A da atividade se não quiser incluir uma experiência de site padrão como opção.

   Para obter mais informações sobre como adicionar ou modificar experiências no [!UICONTROL Visual Experience Composer], consulte [Adicionar experiência](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Para modificar a Experiência B, comece com a etapa 2.

1. Clique em **[!UICONTROL Targeting]** na parte superior de [!UICONTROL Visual Experience Composer] para ir até a próxima etapa do fluxo de trabalho guiado em três etapas.

   O diagrama do fluxo é aberto.

   ![Etapa de direcionamento de Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   O diagrama do fluxo guia você pelas etapas da escolha do público-alvo para a atividade e da configuração das experiências.

1. Na caixa [!UICONTROL Audience], clique no ícone de edição (as reticências verticais), clique em **[!UICONTROL Replace Audience]** e [selecione o público-alvo](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) para a sua atividade.

   Por padrão, o público-alvo está definido como [!UICONTROL All Visitors].

1. Escolha a porcentagem de visitantes qualificados que você deseja inserir na atividade.

   ![Porcentagem de público-alvo](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

1. Configure seu método de alocação de tráfego.

   Você pode mostrar várias experiências no mesmo público-alvo. Um diagrama é exibido mostrando o público-alvo selecionado e as experiências adicionadas à atividade.

   Escolha o método de alocação de tráfego desejado. Para criar uma atividade [!UICONTROL Auto-Allocate], selecione **[!UICONTROL Auto-Allocate to best experience]**.

   Os três tipos de alocação de tráfego são descritos abaixo:

   * **[!UICONTROL Manual (Default)]**: especifique a porcentagem de participantes que deseja visualizar cada experiência. Você pode dividir os percentuais igualmente entre todas as experiências ou especificar percentuais maiores ou menores para cada experiência. O total de experiências deve ser igual a 100%. Para obter mais informações, consulte [Criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Auto-allocate to best experience]**: a maioria dos participantes da atividade é direcionada automaticamente para experiências de maior desempenho. Alguns visitantes são alocados em todas experiências, para manter a exploração de experiências e reconhecer alterações em tendências de desempenho.

   * **[!UICONTROL Auto-target for personalized experiences]**: [!DNL Target] usa aprendizagem de máquina avançada para personalizar conteúdo e gerar conversões identificando várias experiências de alto desempenho definidas pelo profissional de marketing e depois apresentando a experiência mais personalizada para os visitantes com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfil similares. Para obter mais informações, consulte [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   Você também pode clicar em **[!UICONTROL Add]** para adicionar outra experiência à atividade.

1. Quando estiver satisfeito com suas opções de público-alvo, experiência e alocação de tráfego, clique em **[!UICONTROL Next]** para ir até a terceira etapa do fluxo de trabalho guiado em três etapas.

1. Especifique as [metas e configurações](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) da atividade.

   >[!NOTE]
   >
   >Se você quiser usar o [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) com esta atividade, consulte informações importantes no [Suporte do A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Clique em **[!UICONTROL Save & Close]** ou **[!UICONTROL Save]**.

Após criar a atividade, a guia [!UICONTROL Overview] mostra informações sobre a atividade, incluindo um diagrama da atividade.

## Vídeo de treinamento: Criação de Testes A/B (8:36)

Este vídeo mostra como criar um teste A/B usando fluxo de trabalho orientado de três etapas do [!DNL Target].

* Criar uma atividade [!UICONTROL A/B Test] em [!DNL Adobe Target]
* Aloque o tráfego usando uma divisão manual ou automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)
