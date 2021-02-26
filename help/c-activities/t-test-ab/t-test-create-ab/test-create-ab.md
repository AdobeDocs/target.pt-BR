---
keywords: Criar teste A/B;teste A/B;atividade A/B;nova atividade a/b;criar a/b
description: Saiba como usar o Visual Experience Composer (VEC) no Adobe Target para criar sua atividade de teste A/B diretamente em uma página ativada pelo Público alvo.
title: Como crio um teste A/B?
feature: Testes A/B
translation-type: tm+mt
source-git-commit: e87786f2df104d66d97cacd83921875dacd78afe
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 61%

---


# Criar um teste A/B

Use o [!UICONTROL Visual Experience Composer] (VEC) em [!DNL Adobe Target] para criar sua atividade [!UICONTROL Teste A/B] diretamente em uma página ativada por [!DNL Target] e modificar partes da página em [!DNL Target].

>[!NOTE]
>
>Além da atividade Manual (Padrão) [!UICONTROL Teste A/B] (discutida nesta seção), [!DNL Target] fornece dois tipos adicionais de atividades [!UICONTROL Teste A/B]: [!UICONTROL Alocar automaticamente] e [!UICONTROL Público alvo automático].
>
>Consulte [Tipos de atividades de teste A/B](/help/c-activities/t-test-ab/test-ab.md#types) em *Visão geral do teste A/B*.

Para criar uma atividade manual [!UICONTROL Teste A/B]:

1. Na lista **[!UICONTROL Atividades]**, clique em **[!UICONTROL Criar atividade]** > **[!UICONTROL Teste A/B]**.

   ![Lista suspensa Criar atividade](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_select-new.png)

   >[!NOTE]
   >
   >Os tipos de atividades disponíveis dependem da sua conta do [!DNL Target]. Alguns tipos de atividades podem não aparecer na lista. Por exemplo, o [!UICONTROL Recommendations] é um [recurso do Target Premium](/help/c-intro/intro.md#premium).
   >
   >Para obter informações sobre os vários tipos de atividades, consulte [Atividades](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) e o [Guia de atividades do Target](/help/c-activities/target-activities-guide.md).

1. Selecione **[!UICONTROL Visual (Padrão)]**, se necessário.

   ![Criar Atividade de teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/create-ab.png)

   Se preferir usar o [!UICONTROL Criador de experiências baseado em forma], selecione [!UICONTROL Formulário]. Consulte [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Criador de experiências baseado em forma], o [!DNL Target] oferta o aplicativo de página única VEC. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/c-experiences/experiences.md).
   >
   >Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >A opção [[!UICONTROL Escolher local de trabalho]](/help/administrating-target/c-user-management/property-channel/property-channel.md) na ilustração anterior é um recurso do [Target Premium](/help/c-intro/intro.md). Sua organização tem uma licença [!UICONTROL Target Standard] se você não visualizar essa opção.

1. (Condicional) Se você for um [cliente do Target Premium](/help/c-intro/intro.md#premium), escolha um [espaço de trabalho](/help/administrating-target/c-user-management/property-channel/property-channel.md).

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

1. Crie quaisquer novas experiências alterando os elementos na página.

   O [!UICONTROL Visual Experience Composer] exibe duas guias do lado esquerdo após você criar uma nova atividade: Experiência A e Experiência B. A Experiência A é a experiência de controle. Seu foco será na guia Experiência B, que você pode modificar como quiser. A Experiência B é a experiência alternativa que você pode adicionar ao seu teste. Você pode adicionar várias experiências ao teste. Você também podem excluir a Experiência A da atividade se não quiser incluir uma experiência de site padrão como opção.

   Para mais informações sobre adicionar ou modificar experiências no [!UICONTROL Visual Experience Composer], consulte  [Adicionar experiência](/help/c-activities/t-test-ab/t-test-create-ab/ab-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00). Para modificar a Experiência B, comece com a etapa 3.

1. Clique em **[!UICONTROL Direcionamento]** na parte superior do [!UICONTROL Visual Experience Composer] para ir até a próxima etapa do fluxo de trabalho guiado de três etapas.

   O diagrama do fluxo é aberto.

   ![Etapa de direcionamento de Teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new.png)

   O diagrama do fluxo guia você pelas etapas da escolha do público-alvo para a atividade e da configuração das experiências.

1. Na caixa [!UICONTROL Audiência], clique no ícone de edição (três elipses verticais), clique em **[!UICONTROL Substituir Audiência]** e [selecione a audiência](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) para a sua atividade.

   Por padrão, a audiência está definida como [!UICONTROL Todos os Visitantes].

1. Escolha a porcentagem de visitantes qualificados que você deseja inserir na atividade.

   ![Porcentagem de público-alvo](/help/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

1. Defina sua alocação de tráfego.

   Você pode mostrar várias experiências no mesmo público-alvo. Um diagrama é exibido mostrando um público-alvo selecionado e as experiências que você incluiu na atividade.

   Escolha o método de alocação de tráfego desejado:

   * **[!UICONTROL Manual]**: especifique a porcentagem de participantes que deseja visualizar cada experiência. Você pode dividir os percentuais igualmente entre todas as experiências ou especificar percentuais maiores ou menores para cada experiência. O total de experiências deve ser igual a 100%.

   * **[!UICONTROL Alocar automaticamente para a melhor experiência]**: a maioria dos participantes da atividade é direcionada automaticamente para as experiências de maior desempenho. Alguns visitantes são alocados em todas experiências, para manter a exploração de experiências e reconhecer alterações em tendências de desempenho. Consulte [Alocação de tráfego automatizada](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Público alvo automático para experiências]** personalizadas:  [!DNL Target] O usa o aprendizado de máquina avançado para personalizar o conteúdo e gerar conversões, identificando várias experiências de alto desempenho definidas pelo profissional de marketing e, em seguida, servindo a experiência mais personalizada para visitantes com base em seus perfis individuais de clientes e comportamentos passados de visitantes semelhantes. Para obter mais informações, consulte [Público alvo automático](/help/c-activities/auto-target/auto-target-to-optimize.md).
   Você também pode clicar em **[!UICONTROL Adicionar]** para adicionar outra experiência à atividade.

1. Quando estiver satisfeito com sua audiência, suas opções de experiência e suas opções de alocação de tráfego, clique em **[!UICONTROL Próximo]** para ir para a terceira etapa do fluxo de trabalho guiado em três etapas.

1. Especifique as [metas e configurações](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md) da atividade.

   ![Configurações de atividade A/B](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

1. Clique em **[!UICONTROL Salvar e fechar]** ou **[!UICONTROL Salvar]**.

Depois de criar a atividade, a guia [!UICONTROL Visão geral] mostra informações sobre a atividade, incluindo um diagrama da atividade.

## Vídeo de treinamento: Criando testes A/B (8:36) ![Etiqueta do tutorial](/help/assets/tutorial.png)

Este vídeo mostra como criar um teste A/B usando fluxo de trabalho orientado de três etapas do [!DNL Target].

* Criar uma atividade [!UICONTROL Teste A/B] em [!DNL Adobe Target]
* Aloque o tráfego usando uma divisão manual ou automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)
