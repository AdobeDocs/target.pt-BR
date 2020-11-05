---
keywords: Create auto-target;A/B test;auto-target activity;new a/b activity;auto target;auto-target for personalized experiences;personalized
description: Use o Visual Experience Composer no Adobe Target para criar sua atividade de teste A/B de autoalocação diretamente em uma página ativada pelo Público alvo e para modificar partes da página no Público alvo.
title: Criar uma atividade de Público alvo automático
feature: ab
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
translation-type: tm+mt
source-git-commit: fb4f43eef067a24f58ab8b53a7c8aa9c09392c9e
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 59%

---


# ![PREMIUM](/help/assets/premium.png) Criar uma atividade de Público alvo automático

Use o [!UICONTROL Visual Experience Composer] (VEC) em [!DNL Adobe Target] para criar a atividade de teste [!UICONTROL A/B de Público alvo] automático [!UICONTROL diretamente em uma página] -ativada e modificar partes da página dentro [!DNL Target][!DNL Target].

>[!NOTE]
>
>Além da atividade de teste [!UICONTROL A/B do Público alvo] automático [!UICONTROL (discutida neste artigo),] fornece dois tipos adicionais de atividades de teste [!DNL Target]  A/B: [!UICONTROL Manual (padrão)] e [!UICONTROL Autoalocação].
>
>Consulte [Tipos de atividades](/help/c-activities/t-test-ab/test-ab.md#types) de teste A/B na visão geral *do teste* A/B.

Para criar uma atividade de Público alvo [!UICONTROL automático] :

1. Na lista **[!UICONTROL Atividades]**, clique em **[!UICONTROL Criar atividade]** > **[!UICONTROL Teste A/B]**.

   ![Lista suspensa Criar atividade](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Os tipos de atividades disponíveis dependem da sua conta do [!DNL Target]. Alguns tipos de atividades podem não aparecer na lista. Por exemplo, Público alvo  automático e [!UICONTROL Recommendations] são recursos [do](/help/c-intro/intro.md#premium)Público alvo Premium.
   >
   >Para obter informações sobre os vários tipos de atividades, consulte [Atividades](/help/c-activities/activities.md) e o [Guia de atividades do Target](/help/c-activities/target-activities-guide.md).

1. Selecione **[!UICONTROL Visual (Padrão)]**, se necessário.

   ![Criar Atividade de teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   If you prefer to use the [!UICONTROL Form-Based Experience Composer], select [!UICONTROL Form]. Consulte [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do Criador de experiências baseado em [!UICONTROL forma], [!DNL Target] oferta a VEC do aplicativo de página única. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/c-experiences/experiences.md).
   >
   >Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >A opção [[!UICONTROL Escolher local de trabalho]](/help/administrating-target/c-user-management/property-channel/property-channel.md) na ilustração anterior é um recurso do [Target Premium](/help/c-intro/intro.md). Your organization has a [!UICONTROL Target Standard] license if you do not see this option.

1. Escolha um [espaço de trabalho](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique o [URL da atividade](/help/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) e clique em **[!UICONTROL Próximo]**.

   Se sua conta foi configurada com um URL padrão, esse URL aparece por padrão. Você pode trocar o URL padrão por outro URL.

   O [!UICONTROL Visual Experience Composer] é aberto, mostrando a página especificada no URL.

   ![VEC](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Digite um nome para a atividade no espaço fornecido.

   ![Campo nome](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   Os seguintes caracteres não são permitidos em um nome de atividade:

   | Caractere | Descrição |
   |--- |--- |
   | `/` | Barra |
   | `?` | Ponto de interrogação |
   | `#` | Sinal numérico |
   | `:` | Dois-pontos |
   | `=` | Igual a |
   | `+` | Plus |
   | `-` | menos |
   | `@` | Sinal de arroba |

1. Crie quaisquer novas experiências alterando os elementos na página.

   O [!UICONTROL Visual Experience Composer] exibe duas guias do lado esquerdo após você criar uma nova atividade: Experiência A e Experiência B. A Experiência A é a experiência de controle. Seu foco será na guia Experiência B, que você pode modificar como quiser. A Experiência B é a experiência alternativa que você pode adicionar ao seu teste. Você pode adicionar várias experiências ao teste. Você também podem excluir a Experiência A da atividade se não quiser incluir uma experiência de site padrão como opção.

   Para mais informações sobre adicionar ou modificar experiências no [!UICONTROL Visual Experience Composer], consulte  [Adicionar experiência](/help/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Para modificar a Experiência B, comece com a etapa 3.

1. Clique em **[!UICONTROL Direcionamento]** na parte superior do [!UICONTROL Visual Experience Composer] para ir até a próxima etapa do fluxo de trabalho guiado de três etapas.

   O diagrama do fluxo é aberto.

   ![Etapa de direcionamento de Teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   O diagrama do fluxo guia você pelas etapas da escolha do público-alvo para a atividade e da configuração das experiências.

1. Na caixa [!UICONTROL Audiência] , clique no ícone de edição (três elipses verticais), clique em **[!UICONTROL Substituir Audiência]** e [selecione a audiência](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) para a atividade.

   By default, the audience is set to [!UICONTROL All Visitors].

1. Escolha a porcentagem de visitantes qualificados que você deseja inserir na atividade.

   ![Porcentagem de público-alvo](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

1. Defina sua alocação de tráfego.

   Você pode mostrar várias experiências no mesmo público-alvo. Um diagrama é exibido mostrando um público-alvo selecionado e as experiências que você incluiu na atividade.

   Escolha o método de alocação de tráfego desejado. Para criar uma atividade de Público alvo  automático, selecione público alvo **[!UICONTROL automático para experiências]** personalizadas.

   Os três tipos de alocação de tráfego são descritos a seguir:

   * **[!UICONTROL Manual]**: especifique a porcentagem de participantes que deseja visualizar cada experiência. Você pode dividir os percentuais igualmente entre todas as experiências ou especificar percentuais maiores ou menores para cada experiência. O total de experiências deve ser igual a 100%. For more information, see [Create an A/B Test](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Alocar automaticamente para a melhor experiência]**: a maioria dos participantes da atividade é direcionada automaticamente para as experiências de maior desempenho. Alguns visitantes são alocados em todas experiências, para manter a exploração de experiências e reconhecer alterações em tendências de desempenho. For more information, see [Auto-Allocate overview](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL Público alvo automático para experiências]** personalizadas: [!DNL Target] O usa o aprendizado de máquina avançado para personalizar o conteúdo e gerar conversões, identificando várias experiências de alto desempenho definidas pelo profissional de marketing e, em seguida, servindo a experiência mais personalizada para visitantes com base em seus perfis individuais de clientes e comportamentos passados de visitantes semelhantes.
   You can also click **[!UICONTROL Add]** to add another experience to the activity.

1. When you are satisfied with your audience, experience choices, and traffic allocation choices, click **[!UICONTROL Next]** to move to the third step of the three-step guided workflow.

1. Especifique as [metas e configurações](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) da atividade.

   ![Configurações de atividade A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. Clique em **[!UICONTROL Salvar e fechar]** ou em **[!UICONTROL Salvar]**.

After you create the activity, the [!UICONTROL Overview] tab shows information about the activity, including a diagram of your activity.

## Training video: Creating A/B Tests (8:36) ![Tutorial badge](/help/assets/tutorial.png)

Este vídeo mostra como criar um teste A/B usando fluxo de trabalho orientado de três etapas do [!DNL Target].

* Criar uma atividade de teste  A/B em [!DNL Adobe Target]
* Aloque o tráfego usando uma divisão manual ou automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)