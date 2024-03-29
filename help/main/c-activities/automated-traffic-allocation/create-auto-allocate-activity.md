---
keywords: criar alocação automática;teste A/B;atividade de alocação automática;nova atividade a/b;alocação automática;alocar automaticamente para a melhor experiência;alocar;alocar automaticamente
description: Saiba como usar o [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] para criar um [!UICONTROL Alocação automática] Atividade de Teste A/B.
title: Como criar um [!UICONTROL Alocação automática] Atividade?
feature: Auto-Allocate
exl-id: 30bc95e0-4f5e-4d1f-bad2-7b20b8f3c7d2
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 49%

---

# Criar um [!UICONTROL Alocação automática] atividade

Use o [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] para criar o [!UICONTROL Alocação automática] [!UICONTROL Teste A/B] atividade diretamente em um [!DNL Target]página habilitada para e modificar partes da página no [!DNL Target].

Além do [!UICONTROL Alocação automática] [!UICONTROL Teste A/B] atividade (discutida neste artigo), [!DNL Target] O fornece dois tipos adicionais de [!UICONTROL Teste A/B] atividades: [!UICONTROL Manual (Padrão)] e [!UICONTROL Direcionamento automático]. Consulte [Tipos de atividades de teste A/B](/help/main/c-activities/t-test-ab/test-ab.md#types) in *Visão geral do teste A/B*.

Para criar uma [!UICONTROL Alocação automática] atividade:

1. Na lista **[!UICONTROL Atividades]**, clique em **[!UICONTROL Criar atividade]** > **[!UICONTROL Teste A/B]**.

   ![Lista suspensa Criar atividade](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   Os tipos de atividades disponíveis dependem da sua conta do [!DNL Target]. Alguns tipos de atividades podem não aparecer na lista. Por exemplo, o [!UICONTROL Recommendations] é um [recurso do Target Premium](/help/main/c-intro/intro.md#premium). Para obter informações sobre os vários tipos de atividades, consulte [Atividades](/help/main/c-activities/activities.md) e o [Guia de atividades do Target](/help/main/c-activities/target-activities-guide.md).

1. No **[!UICONTROL Criar atividade de teste A/B]** caixa de diálogo, selecione **[!UICONTROL Visual]**, se necessário.

   Se preferir usar a variável [!UICONTROL Experience Composer baseado em formulário], selecione [!UICONTROL Formulário]. Consulte [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Experience Composer baseado em formulário], [!DNL Target] O oferece o VEC para aplicativos de página única. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/main/c-experiences/experiences.md).
   >
   >Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) Se você for um [cliente do Target Premium](/help/main/c-intro/intro.md#premium), escolha um [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique o [URL da atividade](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md) e clique em **[!UICONTROL Criar]**.

   Se sua conta foi configurada com um URL padrão, esse URL aparece por padrão. Você pode alterar o URL padrão para outro, se necessário.

   O [!UICONTROL Visual Experience Composer] é aberto, mostrando a página especificada no URL.

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

   O [!UICONTROL Visual Experience Composer] exibe duas guias do lado esquerdo após você criar uma nova atividade: Experiência A e Experiência B. A Experiência A é a experiência de controle. Seu foco está na guia Experiência B, que pode ser modificada conforme desejado. A Experiência B é a experiência alternativa que você pode adicionar ao seu teste. Você pode adicionar várias experiências ao teste. Você também podem excluir a Experiência A da atividade se não quiser incluir uma experiência de site padrão como opção.

   Para mais informações sobre adicionar ou modificar experiências no [!UICONTROL Visual Experience Composer], consulte  [Adicionar experiência](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md). Para modificar a Experiência B, comece com a etapa 2.

1. Clique em **[!UICONTROL Direcionamento]** na parte superior do [!UICONTROL Visual Experience Composer] para ir até a próxima etapa do fluxo de trabalho guiado de três etapas.

   O diagrama do fluxo é aberto.

   ![Etapa de direcionamento de Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   O diagrama do fluxo guia você pelas etapas da escolha do público-alvo para a atividade e da configuração das experiências.

1. No [!UICONTROL Público] clique no ícone editar (as reticências verticais), clique em **[!UICONTROL Substituir público-alvo]**, depois [selecionar o público](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) para a sua atividade.

   Por padrão, o público-alvo é definido como [!UICONTROL Todos os visitantes].

1. Escolha a porcentagem de visitantes qualificados que você deseja inserir na atividade.

   ![Porcentagem de público-alvo](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

1. Configure seu método de alocação de tráfego.

   Você pode mostrar várias experiências no mesmo público-alvo. Um diagrama é exibido mostrando o público-alvo selecionado e as experiências adicionadas à atividade.

   Escolha o método de alocação de tráfego desejado. Para criar uma [!UICONTROL Alocação automática] atividade, selecione **[!UICONTROL Alocar automaticamente para a melhor experiência]**.

   Os três tipos de alocação de tráfego são descritos abaixo:

   * **[!UICONTROL Manual (Padrão)]**: especifique a porcentagem de participantes que deseja visualizar cada experiência. Você pode dividir os percentuais igualmente entre todas as experiências ou especificar percentuais maiores ou menores para cada experiência. O total de experiências deve ser igual a 100%. Para obter mais informações, consulte [Criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

   * **[!UICONTROL Alocar automaticamente para a melhor experiência]**: a maioria dos participantes da atividade é direcionada automaticamente para as experiências de maior desempenho. Alguns visitantes são alocados em todas experiências, para manter a exploração de experiências e reconhecer alterações em tendências de desempenho.

   * **[!UICONTROL Direcionamento automático para experiências personalizadas]**: [!DNL Target] O usa aprendizagem de máquina avançada para personalizar conteúdo e gerar conversões, identificando várias experiências de alto desempenho definidas pelo profissional de marketing e, em seguida, apresentando a experiência mais personalizada para visitantes com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfil semelhantes. Para obter mais informações, consulte [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   Você também pode clicar em **[!UICONTROL Adicionar]** para adicionar outra experiência à atividade.

1. Quando estiver satisfeito com suas opções de público-alvo, experiência e alocação de tráfego, clique em **[!UICONTROL Próxima]** para ir até a terceira etapa do fluxo de trabalho guiado em três etapas.

1. Especifique as [metas e configurações](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) da atividade.

   >[!NOTE]
   >
   >Se quiser usar [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) com esta atividade, consulte informações importantes no [Suporte do A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

1. Clique em **[!UICONTROL Salvar e fechar]** ou **[!UICONTROL Salvar]**.

Depois de criar a atividade, a variável [!UICONTROL Visão geral] A guia mostra informações sobre a atividade, incluindo um diagrama da atividade.

## Vídeo de treinamento: Criar testes A/B (8:36)

Este vídeo mostra como criar um teste A/B usando fluxo de trabalho orientado de três etapas do [!DNL Target].

* Criar um [!UICONTROL Teste A/B] atividade no [!DNL Adobe Target]
* Aloque o tráfego usando uma divisão manual ou automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)
