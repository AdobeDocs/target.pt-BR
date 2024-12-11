---
keywords: criar alocação automática;teste A/B;atividade de alocação automática;nova atividade a/b;alocação automática;alocar automaticamente para a melhor experiência;alocar;alocar automaticamente
description: Saiba como usar o [!UICONTROL Visual Experience Composer] (VEC) para criar [!UICONTROL Auto-Allocate] atividades de Teste A/B.
title: Como criar uma atividade [!UICONTROL Auto-Allocate]?
feature: Auto-Allocate
hide: true
hidefromtoc: true
exl-id: 1bfa311a-cbd9-48be-9b28-840be55b1118
source-git-commit: 8bfad2fe6804c241deec6c8ea70e2f8e7d79d8c6
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 15%

---

# Criar uma atividade [!UICONTROL Auto-Allocate]

Use o [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] para criar sua atividade do [!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] diretamente em uma página habilitada para [!DNL Target] e modificar partes da página no [!DNL Target].

Além da atividade [!UICONTROL Auto-Allocate] [!UICONTROL A/B Test] (discutida neste artigo), [!DNL Target] fornece dois tipos adicionais de atividades [!UICONTROL A/B Test]: [!UICONTROL Manual (Default)] e [!UICONTROL Auto-Target]. Consulte [Tipos de atividades de teste A/B](/help/main/c-activities/t-test-ab/test-ab.md#types) na *Visão geral do teste A/B*.

Para criar uma atividade [!UICONTROL Auto-Allocate]:

1. Na lista **[!UICONTROL Activities]**, clique em **[!UICONTROL Create Activity]** > **[!UICONTROL A/B Test]**.

1. Na caixa de diálogo [!UICONTROL Create A/B Test Activity], selecione **[!UICONTROL Visual]**, se necessário.

   Se preferir usar o [!UICONTROL Form-Based Experience Composer], selecione [!UICONTROL Form]. Consulte [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Form-Based Experience Composer], o [!DNL Target] oferece o VEC [!UICONTROL Single Page Application]. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Se você for um [cliente do Target Premium](/help/main/c-intro/intro.md#premium), na lista suspensa **[!UICONTROL Choose Workspace]**, escolha um [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   A opção [[!UICONTROL Choose Workplace]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) é um recurso do [Target Premium](/help/main/c-intro/intro.md) e talvez não seja exibida se sua organização tiver uma licença do [!UICONTROL Target Standard].

1. Na caixa **[!UICONTROL Enter Activity URL]**, especifique sua [URL de atividade](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Se sua conta foi [configurada com um URL padrão](/help/main/administrating-target/visual-experience-composer-set-up.md), esse URL aparece por padrão. Você pode alterar o URL padrão para outro, se necessário.

1. Clique em **[!UICONTROL Create]**.

   A [!UICONTROL Visual Experience Composer] é aberta, mostrando a página especificada na URL.

1. Clique no ícone **[!UICONTROL Rename]** ( ![Ícone Renomear](/help/main/assets/icons/MoreSmallListVert.svg) ), clique em **[!UICONTROL Rename]**, especifique um nome para a atividade e clique em **[!UICONTROL Save]**.

   O nome da atividade não pode começar com nenhum dos seguintes caracteres:

   | Caractere | Descrição |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Plus |
   | `-` | menos |
   | `@` | Sinal de arroba |

   O nome da atividade não pode conter nenhuma das sequências de caracteres a seguir:

   | Sequência de caracteres | Descrição |
   |--- |--- |
   | ;= | Ponto e vírgula, Igual a |
   | ;+ | Ponto-e-vírgula, Mais |
   | ;- | Ponto e vírgula, sinal de subtração |
   | ;@ | Ponto e vírgula, no sinal |
   | ,= | Vírgula, Igual a |
   | ,+ | Vírgula, Mais |
   | - | Vírgula, menos |
   | ,@ | Vírgula, No sinal |
   | `[`&quot; | Colchete de abertura, aspas duplas |
   | &quot;`]` | Aspas duplas, colchete de fechamento |

1. Crie novas experiências alterando os elementos na página.

   O [!UICONTROL Visual Experience Composer] exibe duas guias no lado esquerdo depois que você cria uma nova atividade: [!UICONTROL Experience A] e [!UICONTROL Experience B]. [!UICONTROL Experience A] é a experiência de controle. Seu foco está na guia [!UICONTROL Experience B], que pode ser modificada conforme desejado. [!UICONTROL Experience B] é a experiência alternativa que você pode adicionar ao seu teste. Você pode adicionar várias experiências ao teste clicando no ícone [!UICONTROL Add] ( ![Ícone Adicionar](/help/main/assets/icons/Add.svg) ) na parte superior do painel [!UICONTROL Experiences]. Você também podem excluir a Experiência A da atividade se não quiser incluir uma experiência de site padrão como opção.

   Para obter mais informações sobre como adicionar ou modificar experiências no [!UICONTROL Visual Experience Composer], consulte [Adicionar experiência](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Para modificar [!UICONTROL Experience B], comece com a Etapa 2.

1. Clique em **[!UICONTROL Targeting]** na parte superior de [!UICONTROL Visual Experience Composer] para ir até a próxima etapa do fluxo de trabalho guiado em três etapas.

   O diagrama do fluxo é aberto.

   ![Etapa de direcionamento de Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   O diagrama do fluxo guia você pelas etapas da atribuição de um público-alvo e sua porcentagem de tráfego, selecionando o método de alocação de tráfego e especificando a alocação de tráfego para cada experiência na atividade.

1. (Condicional) Clique no controle **[!UICONTROL All Visitors]** para selecionar outro público-alvo para a atividade.

   O público-alvo [!UICONTROL All Visitors] está definido como padrão. Se você selecionar outro público-alvo, o nome dele será exibido no controle mais à esquerda.

   O quadro direito é exibido, permitindo adicionar ou excluir um público-alvo e atribuir a porcentagem de visitante à atividade.

   1. Para alterar o público-alvo, clique no ícone **[!UICONTROL Replace]** ( ![Ícone Substituir](/help/main/assets/icons/Retweet.svg) ) no quadro direito.
   1. Na caixa de diálogo [!UICONTROL Add Audience], [selecione o público desejado](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) e clique em **[!UICONTROL Assign Audience]**.

      Você pode clicar em **Combinar Públicos-alvo** para [criar um público-alvo que combine vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md).

      Se você precisar criar um novo público-alvo que ainda não esteja no [!UICONTROL Audience Library], clique em **Criar público-alvo**. Durante o [fluxo de trabalho de criação de público-alvo](/help/main/c-target/c-audiences/audiences.md), você pode escolher entre as seguintes opções:

      * **[!UICONTROL Audience Library]**: Crie um público-alvo sob demanda que seja salvo no [!UICONTROL Audience Library] que possa ser reutilizado em outras atividades
      * **Somente esta atividade**: crie um [público-alvo específico da atividade](/help/main/c-target/creating-activity-only-audience.md) que não seja salvo no [!UICONTROL Audience Library] e possa ser usado somente na atividade atual

   1. Clique em **[!UICONTROL Visitor Percentage]** no quadro direito e escolha a porcentagem de visitantes qualificados que você deseja inserir na atividade.

   Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

1. Clique no controle **[!UICONTROL Traffic Allocation]** e escolha o método de alocação de tráfego desejado no painel direito. Neste cenário, clique em **[!UICONTROL Auto-Allocate to best experience]**.

   ![Configurações do Método de Alocação de Tráfego](/help/main/c-activities/automated-traffic-allocation/assets/auto-allocate-to-best-exp.png)

   Os seguintes métodos de alocação de tráfego estão disponíveis:

   * **[!UICONTROL Manual (Default)]**: especifique a porcentagem de participantes que deseja visualizar cada experiência. Você pode dividir os percentuais igualmente entre todas as experiências ou especificar percentuais maiores ou menores para cada experiência. O total de experiências deve ser igual a 100%.

   * **[!UICONTROL Auto-Allocate to best experience]**: a maioria dos participantes da atividade é direcionada automaticamente para experiências de maior desempenho. Alguns visitantes são alocados em todas experiências, para manter a exploração de experiências e reconhecer alterações em tendências de desempenho. Para obter mais informações, consulte [[!UICONTROL Auto-Allocate] visão geral](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Auto-Target for personalized experiences]**: [!DNL Target] usa aprendizagem de máquina avançada para personalizar conteúdo e gerar conversões identificando várias experiências de alto desempenho definidas pelo profissional de marketing e depois apresentando a experiência mais personalizada para os visitantes com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfil similares. Para obter mais informações, consulte [visão geral do Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

1. Clique em **[!UICONTROL Experiences]** no painel direito e especifique a alocação de tráfego desejada para cada experiência.

1. Quando estiver satisfeito com suas opções de público-alvo, experiência e alocação de tráfego, clique em **[!UICONTROL Next]** para ir até a terceira etapa do fluxo de trabalho guiado em três etapas.

1. Especifique as [metas e configurações](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) da atividade.

   >[!NOTE]
   >
   >Se você quiser usar o [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) com esta atividade, consulte informações importantes no [Suporte do A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Clique em **[!UICONTROL Save & Close]** ou **[!UICONTROL Save]**.

Após criar a atividade, a guia [!UICONTROL Overview] mostra informações sobre a atividade, incluindo um diagrama da atividade.
