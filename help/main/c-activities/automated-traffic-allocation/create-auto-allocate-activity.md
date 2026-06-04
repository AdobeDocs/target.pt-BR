---
keywords: criar alocação automática;teste A/B;atividade de alocação automática;nova atividade a/b;alocação automática;alocar automaticamente para a melhor experiência;alocar;alocar automaticamente
description: Saiba como usar o [!UICONTROL Visual Experience Composer] (VEC) para criar atividades de Teste A/B de [!UICONTROL Alocação automática].
title: Como criar uma atividade de [!UICONTROL Alocação automática]?
feature: Auto-Allocate
exl-id: 30bc95e0-4f5e-4d1f-bad2-7b20b8f3c7d2
TQID: https://experienceleague.adobe.com/dInypDH72qyoj5UygbEt-BWpq1gZkbxJiSXSheNPO54
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1060
ht-degree: 14%

---

# Criar uma atividade de [!UICONTROL Alocação automática]

Use o [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] para criar sua atividade de [!UICONTROL Alocação automática] e [!UICONTROL Teste A/B] diretamente em uma página habilitada para [!DNL Target] e modificar partes da página no [!DNL Target].

Além da atividade [!UICONTROL Alocação automática] [!UICONTROL Teste A/B] (discutida neste artigo), o [!DNL Target] fornece dois tipos adicionais de atividades [!UICONTROL Teste A/B]: [!UICONTROL Manual (Padrão)] e [!UICONTROL Direcionamento automático]. Consulte [Tipos de atividades de teste A/B](/help/main/c-activities/t-test-ab/test-ab.md#types) na *Visão geral do teste A/B*.

Para criar uma atividade de [!UICONTROL Alocação automática]:

1. Na lista **[!UICONTROL Atividades]**, clique em **[!UICONTROL Criar atividade]** > **[!UICONTROL Teste A/B]**.

1. Na caixa de diálogo [!UICONTROL Criar atividade de teste A/B], selecione **[!UICONTROL Visual]**, se necessário.

   Se preferir usar o [!UICONTROL Experience Composer baseado em formulário], selecione [!UICONTROL Formulário]. Consulte [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Experience Composer baseado em formulário], o [!DNL Target] oferece o VEC [!UICONTROL Aplicativo de página única]. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Se você for um [cliente do Target Premium](/help/main/c-intro/intro.md#premium), na lista suspensa **[!UICONTROL Escolher Workspace]**, escolha um [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   A opção [[!UICONTROL Escolher Local de Trabalho]](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) é um recurso do [Target Premium](/help/main/c-intro/intro.md) e talvez não seja exibida se sua organização tiver uma licença do [!UICONTROL Target Standard].

1. Na caixa **[!UICONTROL Inserir URL da atividade]**, especifique sua [URL da atividade](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Se sua conta foi [configurada com um URL padrão](/help/main/administrating-target/visual-experience-composer-set-up.md), esse URL aparece por padrão. Você pode alterar o URL padrão para outro, se necessário.

1. Clique em **[!UICONTROL Criar]**.

   O [!UICONTROL Visual Experience Composer] é aberto, mostrando a página especificada no URL.

1. Para nomear a atividade, clique no ícone **[!UICONTROL Editar]** ( ![Ícone Editar](/help/main/assets/icons/Edit.svg) ) ao lado de &quot;[!UICONTROL Atividade sem título]&quot;, especifique um nome descritivo para a atividade e clique em **[!UICONTROL Salvar]**.

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
   | ,- | Vírgula, menos |
   | ,@ | Vírgula, No sinal |
   | `[`&quot; | Colchete de abertura, aspas duplas |
   | &quot;`]` | Aspas duplas, colchete de fechamento |

1. Crie novas experiências alterando os elementos na página.

   O [!UICONTROL Visual Experience Composer] exibe duas guias no lado esquerdo depois que você cria uma nova atividade: [!UICONTROL Experiência A] e [!UICONTROL Experiência B]. A [!UICONTROL Experiência A] é a experiência de controle. Seu foco está na guia [!UICONTROL Experiência B], que você pode modificar conforme desejado. [!UICONTROL Experiência B] é a experiência alternativa que você pode adicionar ao seu teste. Você pode adicionar várias experiências ao teste clicando no ícone [!UICONTROL Adicionar] ( ![Ícone Adicionar](/help/main/assets/icons/Add.svg) ) na parte superior do painel [!UICONTROL Experiências]. Você também podem excluir a Experiência A da atividade se não quiser incluir uma experiência de site padrão como opção.

   Para obter mais informações sobre como adicionar ou modificar experiências no [!UICONTROL Visual Experience Composer], consulte [Adicionar experiência](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Para modificar a [!UICONTROL Experiência B], comece com a Etapa 2.

1. Clique em **[!UICONTROL Direcionamento]** na parte superior do [!UICONTROL Visual Experience Composer] para ir até a próxima etapa do fluxo de trabalho guiado de três etapas.

   O diagrama do fluxo é aberto.

   ![Etapa de direcionamento de Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

   O diagrama do fluxo guia você pelas etapas da atribuição de um público-alvo e sua porcentagem de tráfego, selecionando o método de alocação de tráfego e especificando a alocação de tráfego para cada experiência na atividade.

1. (Condicional) Clique no controle **[!UICONTROL Todos os visitantes]** para selecionar outro público-alvo para a atividade.

   O público-alvo [!UICONTROL Todos os visitantes] está definido como padrão. Se você selecionar outro público-alvo, o nome dele será exibido no controle mais à esquerda.

   O quadro direito é exibido, permitindo adicionar ou excluir um público-alvo e atribuir a porcentagem de visitante à atividade.

   1. Para alterar o público-alvo, clique no ícone **[!UICONTROL Substituir]** ( ![Ícone Substituir](/help/main/assets/icons/Retweet.svg) ) no quadro direito.
   1. Na caixa de diálogo [!UICONTROL Adicionar público-alvo], [selecione o público-alvo desejado](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) e clique em **[!UICONTROL Atribuir público-alvo]**.

      Você pode clicar em **Combinar Públicos-alvo** para [criar um público-alvo que combine vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md).

      Se precisar criar um novo público-alvo que ainda não esteja na [!UICONTROL Biblioteca de Público-Alvo], clique em **Criar Público**. Durante o [fluxo de trabalho de criação de público-alvo](/help/main/c-target/c-audiences/audiences.md), você pode escolher entre as seguintes opções:

      * **[!UICONTROL Biblioteca de público-alvo]**: crie um público-alvo sob demanda que seja salvo na [!UICONTROL Biblioteca de público-alvo] e que possa ser reutilizado em outras atividades
      * **Somente esta atividade**: crie um [público-alvo específico da atividade](/help/main/c-target/creating-activity-only-audience.md) que não esteja salvo na [!UICONTROL Biblioteca de Público-Alvo] e possa ser usado somente na atividade atual

   1. Clique em **[!UICONTROL Porcentagem de visitantes]** no quadro direito e escolha a porcentagem de visitantes qualificados que você deseja inserir na atividade.

   Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

1. Clique no controle **[!UICONTROL Alocação de tráfego]** e escolha o método de alocação de tráfego desejado no painel direito. Neste cenário, clique em **[!UICONTROL Alocar automaticamente para a melhor experiência]**.

   ![Configurações do Método de Alocação de Tráfego](/help/main/c-activities/automated-traffic-allocation/assets/auto-allocate-to-best-exp.png)

   Os seguintes métodos de alocação de tráfego estão disponíveis:

   * **[!UICONTROL Manual (Padrão)]**: especifique a porcentagem de participantes que deseja visualizar cada experiência. Você pode dividir os percentuais igualmente entre todas as experiências ou especificar percentuais maiores ou menores para cada experiência. O total de experiências deve ser igual a 100%.

   * **[!UICONTROL Alocar automaticamente na melhor experiência]**: a maioria dos participantes da atividade é direcionada automaticamente para experiências de maior desempenho. Alguns visitantes são alocados em todas experiências, para manter a exploração de experiências e reconhecer alterações em tendências de desempenho. Para obter mais informações, consulte [[!UICONTROL Visão geral da Alocação automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Direcionamento automático para experiências personalizadas]**: [!DNL Target] usa aprendizagem de máquina avançada para personalizar conteúdo e gerar conversões, identificando várias experiências definidas pelo profissional de marketing com desempenho elevado e apresentando a experiência mais personalizada para os visitantes com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfil similares. Para obter mais informações, consulte [visão geral do Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

1. Clique em **[!UICONTROL Experiências]** no painel direito e especifique a alocação de tráfego desejada para cada experiência.

1. Quando estiver satisfeito com suas opções de público-alvo, experiência e alocação de tráfego, clique em **[!UICONTROL Avançar]** para ir até a terceira etapa do fluxo de trabalho guiado em três etapas.

1. Especifique as [metas e configurações](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) da atividade.

   >[!NOTE]
   >
   >Se você quiser usar o [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) com esta atividade, consulte informações importantes no [Suporte do A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Clique em **[!UICONTROL Salvar e fechar]** ou **[!UICONTROL Salvar]**.

Após criar a atividade, a guia [!UICONTROL Visão geral] mostra informações sobre a atividade, incluindo um diagrama da atividade.
