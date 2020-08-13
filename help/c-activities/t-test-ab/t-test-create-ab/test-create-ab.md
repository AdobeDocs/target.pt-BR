---
keywords: Create A/B;A/B test;A/B activity;new a/b activity
description: Use o Visual Experience Composer no Target para criar o teste diretamente em uma página habilitada para o Target e modificar partes da página no Target.
title: Criar um teste A/B
feature: ab
topic: Advanced,Standard,Classic
uuid: 2a255cf9-91c7-4710-bfd7-a4d8797ef24c
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 99%

---


# Criar um teste A/B{#create-an-a-b-test}

Use o Visual Experience Composer no Target para criar o teste diretamente em uma página habilitada para o Target e modificar partes da página no Target.

1. Na lista [!UICONTROL Atividades], clique em **[!UICONTROL Criar atividade]** > **[!UICONTROL Teste A/B]**.

   ![Lista suspensa Criar atividade](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Os tipos de atividades disponíveis dependem da sua conta do [!DNL Target]. Alguns tipos de atividades podem não aparecer na lista. Por exemplo, o [!UICONTROL Recommendations] é um [recurso do Target Premium](/help/c-intro/intro.md#premium).
   >
   >Para obter informações sobre os vários tipos de atividades, consulte [Atividades](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) e o [Guia de atividades do Target](/help/c-activities/target-activities-guide.md).

   ![Criar atividade de Teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

1. Selecione **[!UICONTROL Visual (Padrão)]**, se necessário.

   Se preferir usar o Experience Composer baseado em formulário, selecione [!UICONTROL Formulário]. Consulte [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do Experience Composer baseado em formulário, o Target oferece o VEC para aplicativo de página única e o VEC para aplicativos móveis. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/c-experiences/experiences.md).
   >
   >Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >A opção [!UICONTROL [Escolher local de trabalho](/help/administrating-target/c-user-management/property-channel/property-channel.md) na ilustração anterior é um recurso do [Target Premium](/help/c-intro/intro.md). Caso não veja essa opção, a licença da organização é do Target Standard.]

1. (Condicional) Se você for um [cliente do Target Premium](/help/c-intro/intro.md#premium), escolha um [espaço de trabalho](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique o [URL da atividade](../../../c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90) e clique em **[!UICONTROL Próximo]**.

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

   Para mais informações sobre adicionar ou modificar experiências no [!UICONTROL Visual Experience Composer], consulte  [Adicionar experiência](../../../c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Para modificar a Experiência B, comece com a etapa 3.

1. Clique em **[!UICONTROL Direcionamento]** na parte superior do [!UICONTROL Visual Experience Composer] para ir até a próxima etapa do fluxo de trabalho guiado de três etapas.

   O diagrama do fluxo é aberto.

   ![Etapa de direcionamento de Teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   O diagrama do fluxo guia você pelas etapas da escolha do público-alvo para a atividade e da configuração das experiências.
1. Na caixa [!UICONTROL Público-alvo], clique no ícone de edição e [selecione o público-alvo](../../../c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087) para a atividade.

   Por padrão, o público-alvo é definido como Todos visitantes.

1. Escolha a porcentagem de visitantes qualificados que você deseja inserir na atividade.

   ![Porcentagem de público-alvo](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

1. Defina sua alocação de tráfego.

   Você pode mostrar várias experiências no mesmo público-alvo. Um diagrama é exibido mostrando um público-alvo selecionado e as experiências que você incluiu na atividade.

   Escolha o método de alocação de tráfego desejado:

   * **[!UICONTROL Manual]**: especifique a porcentagem de participantes que deseja visualizar cada experiência. Você pode dividir os percentuais igualmente entre todas as experiências ou especificar percentuais maiores ou menores para cada experiência. O total de experiências deve ser igual a 100%.

   * **[!UICONTROL Alocar automaticamente para a melhor experiência]**: a maioria dos participantes da atividade é direcionada automaticamente para as experiências de maior desempenho. Alguns visitantes são alocados em todas experiências, para manter a exploração de experiências e reconhecer alterações em tendências de desempenho. Consulte [Alocação de tráfego automatizada](../../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Direcionamento automático para experiências personalizadas]**: o Target usa algoritmos avançados de aprendizado de máquina para direcionar os visitantes automaticamente para a melhor experiência, maximizando suas metas. Para obter mais informações, consulte [Direcionamento automático para otimizar](../../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).
   Você também pode clicar em **[!UICONTROL Adicionar experiência]** para adicionar uma outra experiência à atividade.

1. Quando estiver satisfeito com suas opções de público-alvo e experiência, clique em **[!UICONTROL Próximo]** para ir até a terceira etapa do fluxo de trabalho guiado em três etapas.

1. Especifique as [metas e configurações](../../../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) da atividade.

   ![Configurações de atividade A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. Clique em **[!UICONTROL Salvar]**.

Após criar a atividade, a guia Visão geral mostra informações sobre a atividade, incluindo um diagrama da atividade.

## Vídeo de treinamento: Criar testes A/B (8:36) ![Crachá do tutorial](/help/assets/tutorial.png)

Este vídeo mostra como criar um teste A/B usando fluxo de trabalho orientado de três etapas do [!DNL Target].

* Criar uma atividade A/B no Adobe Target
* Aloque o tráfego usando uma divisão manual ou automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)
