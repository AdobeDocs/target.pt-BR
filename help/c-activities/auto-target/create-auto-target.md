---
keywords: Criar direcionamento automático, teste A/B, atividade de direcionamento automático, nova atividade a/b, direcionamento automático, direcionamento automático para experiências personalizadas, personalizadas, otimização
description: Saiba como usar o Visual Experience Composer (VEC) no Adobe Target para criar sua atividade de Teste A/B de Direcionamento automático diretamente em uma página habilitada para o Target.
title: Como criar uma atividade de direcionamento automático?
feature: Auto-Target
exl-id: 5521740c-eee2-4ba2-8931-cf56d56a4561
translation-type: tm+mt
source-git-commit: 73053526e68e08136ab66b9d4c1aa17958cfc76e
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 49%

---

# ![](/help/assets/premium.png) PREMIUMCriar uma atividade de Direcionamento automático

Use o [!UICONTROL Visual Experience Composer] (VEC) em [!DNL Adobe Target] para criar sua atividade de [!UICONTROL Direcionamento automático] [!UICONTROL Teste A/B] diretamente em uma página [!DNL Target] habilitada e modificar partes da página em [!DNL Target].

>[!NOTE]
>
>O [!UICONTROL Direcionamento automático] está disponível como parte da solução do [!DNL Target Premium]. Este recurso não está disponível no [!DNL Target Standard] sem uma licença do [!DNL Target Premium]. Para obter mais informações sobre os recursos avançados fornecidos por esta licença, consulte [Target Premium](/help/c-intro/intro.md).
>
>Além da atividade [!UICONTROL Direcionamento automático] [!UICONTROL Teste A/B] (discutida neste artigo), [!DNL Target] fornece dois outros tipos de atividades [!UICONTROL Teste A/B]: [!UICONTROL Manual (Padrão)] e [!UICONTROL Alocação automática].
>
>Consulte [Tipos de atividades de Teste A/B](/help/c-activities/t-test-ab/test-ab.md#types) em *Visão geral do Teste A/B*.

Para criar uma atividade de [!UICONTROL Direcionamento automático]:

1. Na lista **[!UICONTROL Atividades]**, clique em **[!UICONTROL Criar atividade]** > **[!UICONTROL Teste A/B]**.

   ![Lista suspensa Criar atividade](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Os tipos de atividades disponíveis dependem da sua conta do [!DNL Target]. Alguns tipos de atividades podem não aparecer na lista. Por exemplo, [!UICONTROL Direcionamento automático] e [!UICONTROL Recommendations] são [recursos do Target Premium](/help/c-intro/intro.md#premium).
   >
   >Para obter informações sobre os vários tipos de atividades, consulte [Atividades](/help/c-activities/activities.md) e o [Guia de atividades do Target](/help/c-activities/target-activities-guide.md).

1. Selecione **[!UICONTROL Visual (Padrão)]**, se necessário.

   ![Criar atividade de teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   Se preferir usar o [!UICONTROL Experience Composer baseado em formulário], selecione [!UICONTROL Formulário]. Consulte [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Experience Composer baseado em formulário], [!DNL Target] oferece o VEC de aplicativos de página única. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/c-experiences/experiences.md).
   >
   >Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >A opção [[!UICONTROL Escolher local de trabalho]](/help/administrating-target/c-user-management/property-channel/property-channel.md) na ilustração anterior é um recurso do [Target Premium](/help/c-intro/intro.md). Sua organização tem uma licença do [!UICONTROL Target Standard] se você não vir essa opção.

1. Escolha um [espaço de trabalho](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique o [URL da atividade](/help/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) e clique em **[!UICONTROL Próximo]**.

   Se sua conta foi configurada com um URL padrão, esse URL aparece por padrão. Você pode trocar o URL padrão por outro URL.

   O [!UICONTROL Visual Experience Composer] é aberto, mostrando a página especificada no URL.

   ![VEC](/help/c-activities/t-test-ab/t-test-create-ab/assets/vec-new.png)

1. Digite um nome para a atividade no espaço fornecido.

   ![Campo nome](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_newname-new.png)

   O nome da atividade não pode começar com nenhum dos seguintes caracteres:

   | Caractere | Descrição |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Plus |
   | `-` | menos |
   | `@` | Sinal de arroba |

1. Crie quaisquer experiências alterando os elementos na página.

   O [!UICONTROL Visual Experience Composer] exibe duas guias do lado esquerdo depois que você cria uma atividade: Experiência A e Experiência B. A Experiência A é a experiência de controle. Seu foco é na guia Experiência B, que pode ser modificada conforme desejado. A Experiência B é a experiência alternativa que você pode adicionar ao seu teste. Você pode adicionar várias experiências ao teste. Você também podem excluir a Experiência A da atividade se não quiser incluir uma experiência de site padrão como opção.

   Para mais informações sobre adicionar ou modificar experiências no [!UICONTROL Visual Experience Composer], consulte  [Adicionar experiência](/help/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Para modificar a Experiência B, comece com a etapa 3.

1. Clique em **[!UICONTROL Direcionamento]** na parte superior do [!UICONTROL Visual Experience Composer] para ir até a próxima etapa do fluxo de trabalho guiado de três etapas.

   O diagrama do fluxo é aberto.

   ![Etapa de direcionamento de Teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   O diagrama do fluxo guia você pelas etapas da escolha do público-alvo para a atividade e da configuração das experiências.

1. Na caixa [!UICONTROL Audience], clique no ícone de edição (três elipses verticais), clique em **[!UICONTROL Substituir público]**, em seguida em [selecione o público](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) para sua atividade.

   Por padrão, o público-alvo é definido como [!UICONTROL All Visitors].

1. Escolha a porcentagem de visitantes qualificados que você deseja inserir na atividade.

   ![Porcentagem de público-alvo](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

1. Defina sua alocação de tráfego.

   Você pode mostrar várias experiências no mesmo público-alvo. Um diagrama é exibido mostrando um público-alvo selecionado e as experiências que você incluiu na atividade.

   Escolha o método de alocação de tráfego desejado. Para criar uma atividade de [!UICONTROL Direcionamento automático], selecione **[!UICONTROL Direcionamento automático para experiências personalizadas]**.

   Os três tipos de alocação de tráfego são descritos abaixo:

   * **[!UICONTROL Manual]**: especifique a porcentagem de participantes que deseja visualizar cada experiência. Você pode dividir os percentuais igualmente entre todas as experiências ou especificar percentuais maiores ou menores para cada experiência. O total de experiências deve ser igual a 100%. Para obter mais informações, consulte [Criar um teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Alocação automática para a melhor experiência]**: A maioria dos participantes da atividade é direcionada automaticamente para experiências de maior desempenho. Alguns visitantes são alocados em todas experiências, para manter a exploração de experiências e reconhecer alterações em tendências de desempenho. Para obter mais informações, consulte [Visão geral da alocação automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

   * **[!UICONTROL Direcionamento automático para experiências]** personalizadas:  [!DNL Target] O usa aprendizagem de máquina avançada para personalizar o conteúdo e gerar conversões, identificando várias experiências de alto desempenho definidas pelo profissional de marketing e depois apresentando a experiência mais personalizada para visitantes com base em seus perfis de clientes individuais e nos comportamentos passados de visitantes semelhantes.
   Você também pode clicar em **[!UICONTROL Adicionar]** para adicionar outra experiência à atividade.

1. Quando estiver satisfeito com suas opções de público-alvo, experiência e alocação de tráfego, clique em **[!UICONTROL Avançar]** para ir para a terceira etapa do fluxo de trabalho guiado de três etapas.

1. Especifique as [metas e configurações](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) da atividade.

   ![Configurações de atividade A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

   >[!NOTE]
   >
   >Se quiser usar [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) com essa atividade, consulte informações importantes em [Suporte A4T para atividades de Alocação automática e Direcionamento automático](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Clique em **[!UICONTROL Salvar e fechar]** ou **[!UICONTROL Salvar]**.

Após criar a atividade, a guia [!UICONTROL Visão geral] mostra informações sobre a atividade, incluindo um diagrama da atividade.

## Vídeo de treinamento: Criação de testes A/B (8:36) ![Selo tutorial](/help/assets/tutorial.png)

Este vídeo mostra como criar um teste A/B usando fluxo de trabalho orientado de três etapas do [!DNL Target].

* Crie uma atividade [!UICONTROL Teste A/B] em [!DNL Adobe Target]
* Aloque o tráfego usando uma divisão manual ou automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)
