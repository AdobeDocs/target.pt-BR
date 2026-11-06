---
source-git-commit: 87c0d2aa67d54dcbc2963be63d2d7ad9c02b6aa9
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 5%
---
# Trechos

## Recursos do Target Premium {#premium-note}

>[!NOTE]
>
>Essa funcionalidade está disponível como parte da licença do [Target Premium](/help/main/c-intro/intro.md#premium). Essa funcionalidade não está disponível no [!DNL Target Standard].

## Atualização de permissões do Target {#permissions-update}

>[!IMPORTANT]
>
>[!DNL Target] usuários com direitos de [!UICONTROL Administrador do Produto] e [!UICONTROL Administrador do Sistema] podem editar todas as configurações nas páginas [!UICONTROL Administração], independentemente de sua função no [!DNL Target]. Os usuários sem essas permissões têm acesso somente leitura a essas configurações.

## Interface do usuário do Target atualizada {#updated-ui}

>[!NOTE]
>
>Novo em 2025, o [!DNL Target] introduziu uma interface de usuário atualizada e o [!UICONTROL Visual Experience Composer] (VEC). Clique nos links a seguir para saber mais:
>
>* Notas de versão do [[!DNL Target Standard/Premium] 25.2.1 (17 de fevereiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para [!UICONTROL Atividades], [!UICONTROL Recomendações] e o [!UICONTROL Visual Experience Composer] (VEC).
>
>* Notas de versão do [[!DNL Target Standard/Premium] 25.1.1 (9 de janeiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para a [!UICONTROL Biblioteca de Ofertas].
>
>* [Compreender a [!DNL Target] Interface](/help/main/c-intro/understand-the-target-ui.md): fornece uma breve visão geral para ajudá-lo a se familiarizar com o [!DNL Target] e fornece links para informações mais detalhadas e instruções passo a passo.
>
>* [[!UICONTROL Alterações do Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): a versão [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de fevereiro de 2015) apresenta um [!UICONTROL Visual Experience Composer] (VEC) atualizado. Este artigo explica as diferenças entre as versões herdadas e atualizadas do VEC.
>
>* [[!UICONTROL Opções do Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): este artigo explica a interface do usuário do VEC atualizada e suas opções.
>
>* [[!DNL Target] Perguntas frequentes sobre atualização da interface do usuário](/help/main/c-intro/updated-ui-faq.md): estas perguntas frequentes abordam perguntas comuns sobre a nova interface do usuário do [!DNL Target] e do [!UICONTROL Visual Experience Composer] (VEC), incluindo alterações de navegação, locais de recursos e a desativação da opção de versão temporária da interface do usuário. Seja você um profissional de marketing, desenvolvedor ou administrador, essas Perguntas frequentes ajudarão a fazer a transição descomplicada e a aproveitar ao máximo a interface atualizada.

## Regras de nome de atividade {#activity-name-rules}

O nome da atividade não pode começar com `=`, `+`, `-` ou `@`. O nome da atividade também não pode conter nenhuma das sequências de caracteres a seguir: `;=`, `;+`, `;-`, `;@`, `,=`, `,+`, `,-`, `,@`, `["` ou `"]`.

## Selecione um público na etapa de Direcionamento {#audience-selection-steps}

1. Para alterar o público-alvo, clique no ícone **[!UICONTROL Substituir]** ( ![Ícone Substituir](/help/main/assets/icons/Retweet.svg) ) no quadro direito.

1. Na caixa de diálogo **[!UICONTROL Adicionar público-alvo]**, [selecione o público-alvo desejado](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) e clique em **[!UICONTROL Atribuir público-alvo]**.

   Para criar um público-alvo que combine vários públicos-alvo, clique em **[!UICONTROL Combinar públicos-alvo]**. Para obter detalhes, consulte [Combinar vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md).

   Para criar um novo público-alvo que ainda não esteja na [!UICONTROL Biblioteca de Público-alvo], clique em **[!UICONTROL Criar Público-alvo]**. No [fluxo de trabalho create-audience](/help/main/c-target/c-audiences/audiences.md), escolha uma das seguintes opções:

   * **[!UICONTROL Biblioteca de público-alvo]**: crie um público-alvo sob demanda que seja salvo na [!UICONTROL Biblioteca de público-alvo] e possa ser reutilizado em outras atividades.
   * **[!UICONTROL Somente esta atividade]**: crie um [público-alvo específico da atividade](/help/main/c-target/creating-activity-only-audience.md) que não esteja salvo na [!UICONTROL Biblioteca de Público-alvo] e possa ser usado somente na atividade atual.

1. Clique em **[!UICONTROL Porcentagem de visitantes]** no quadro direito e escolha a porcentagem de visitantes qualificados que você deseja inserir na atividade.


