---
keywords: atividades;atividade;tipos de atividade;editar atividade;editar;copiar;activities;activity;activity;activity types;edit activity;copy
description: Saiba mais sobre as diferentes maneiras de editar uma atividade existente.
title: Como editar uma atividade?
feature: Activities
exl-id: 5f2a930a-9950-430e-a898-50af1f917ec1
source-git-commit: 34633032385f848dcc87fe1bc8cd025e42bcc3e9
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 24%

---

# Editar uma atividade

Saiba como editar atividades existentes no [!DNL Adobe Target]. Este artigo aborda os diferentes métodos disponíveis na interface do [!DNL Target] para modificar atividades. Esteja você atualizando experiências, ajustando regras de direcionamento ou configurando metas, o [!DNL Target] garante que suas alterações sejam salvas com segurança antes da ativação.

O [!DNL Target] fornece vários locais na interface do usuário onde você pode editar atividades existentes. O processo varia dependendo do método escolhido.

## Edite uma atividade usando o ícone de passar o mouse [!UICONTROL More Actions] na página Atividades {#section_29EE2ECA6B88473A8F9AC5600FFBB174}

1. Na página **[!UICONTROL Activities]**, clique no ícone **[!UICONTROL More Actions]** ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmall.svg) ) ao lado da atividade que você deseja editar e clique em [!UICONTROL **Editar**].

   O Target abre a atividade no [!UICONTROL Visual Experience Composer] (VEC) e você visualiza a página [!UICONTROL Experiences] (a primeira etapa do fluxo de trabalho guiado três etapas).

1. Edite a atividade conforme desejado usando as [opções de VEC](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

1. Clique em **[!UICONTROL Next]** para avançar para a próxima etapa e, em seguida, faça as edições necessárias.

1. Ao acessar a página **Metas e Configurações**, você terá as seguintes opções:

   * **[!UICONTROL Save & Close]:** Clique em **[!UICONTROL Save and Close]** para salvar suas alterações e exibir a página [!UICONTROL Overview] da atividade.
   * **Salvar:** Clique no ícone **[!UICONTROL More Actions]** ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmallListVert.svg) ) e selecione **[!UICONTROL Save]** para salvar suas alterações e permanecer no VEC, onde você pode continuar a fazer alterações. Aguarde a conclusão do salvamento para fazer novas alterações. O VEC é recarregado com as alterações atualizadas depois da conclusão do salvamento.

## Edite uma atividade clicando no seu nome na página [!UICONTROL Activities] {#section_176180DAD17E40CEA441903F39E0AA1C}

1. Para evitar a necessidade de percorrer todo o fluxo de trabalho, clique na atividade desejada na página [!UICONTROL Activities] para abri-la, selecione uma opção na lista suspensa **[!UICONTROL Edit Activity]** e selecione a opção desejada.

   * **Editar Experiências:** Leva você diretamente à página [!UICONTROL Experiences] (a primeira etapa do fluxo de trabalho guiado de três etapas).
   * **Editar Direcionamento**: Leva você diretamente à página [!UICONTROL Targeting] (a segunda etapa do fluxo de trabalho guiado de três etapas).
   * **[!UICONTROL Goals & Settings]**: Leva você diretamente à página [!UICONTROL Goals & Settings] (a terceira etapa do fluxo de trabalho guiado de três etapas).

1. Faça as alterações desejadas e salve a atividade.

   * **[!UICONTROL Save & Close]:** Clique em **[!UICONTROL Save and Close]** para salvar suas alterações e exibir a página [!UICONTROL Overview] da atividade.
   * **Salvar:** Clique no ícone **[!UICONTROL More Actions]** ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmallListVert.svg) ) e selecione **[!UICONTROL Save]** para salvar suas alterações e permanecer no VEC, onde você pode continuar a fazer alterações. Aguarde a conclusão do salvamento para fazer novas alterações. O VEC é recarregado com as alterações atualizadas depois da conclusão do salvamento.

## Trabalhar com as atividades herdadas criadas em [!DNL Recommendations Classic] {#classic}

As atividades de exibição da lista [!UICONTROL Activities] criadas em várias fontes, incluindo [!DNL Recommendations Classic]. As seguintes ações estão disponíveis ao trabalhar com as atividades herdadas criadas em [!DNL Recommendations Classic]:

* [!UICONTROL Activate]
* [!UICONTROL Deactivate]
* [!UICONTROL Archive]
* [!UICONTROL Copy]
* [!UICONTROL Delete]

Não é possível editar uma [!DNL Recommendations] atividade diretamente. Se você quiser editar a atividade, crie uma cópia da atividade usando [!DNL Target Premium] e depois salve a atividade recém-criada. Essa atividade recém-criada pode ser editada conforme necessário.

## Salvar uma atividade no formato de rascunho {#section_968CD7A63027432EBD8FAE3A0F7404C3}

O recurso Salvar como rascunho não está mais disponível. Para obter mais informações, consulte *[!UICONTROL Status]* em [Aplicar filtros à lista de Atividades](/help/main/c-activities/activities.md#filters).

## Copiar/editar uma atividade ao usar espaços de trabalho {#section_45A92E1DD3934523B07E71EF90C4F8B6}

Um espaço de trabalho permite que uma organização atribua um conjunto específico de usuários a um conjunto específico de propriedades. De muitas formas, um espaço de trabalho é semelhante a um conjunto de relatórios no [!DNL Adobe Analytics].

>[!NOTE]
>
>Os espaços de trabalho são parte da funcionalidade [!UICONTROL Properties and Permissions] disponível como parte da solução [!DNL Target Premium]. Não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

Se você fizer parte de uma organização multinacional, poderá ter um espaço de trabalho para suas páginas da Web, propriedades ou sites na Europa e outro espaço de trabalho para suas páginas, propriedades ou sites da Web nos EUA. Se fizer parte de uma organização multimarcas, poderá ter um espaço de trabalho separado para cada uma de suas marcas.

Para obter mais informações sobre espaços de trabalho e a funcionalidade Permissões de Usuário de Empresa, consulte [Permissões de Usuário de Empresa](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838).

Se você tiver o [!UICONTROL Enterprise User Permissions] habilitado em seu ambiente, poderá copiar atividades para o mesmo espaço de trabalho ou para outro espaço de trabalho. Atualmente, não é possível mover uma atividade de um espaço de trabalho para outro. Para copiar uma atividade para outro espaço de trabalho, na página [!UICONTROL Activities], clique no ícone **[!UICONTROL More Actions]** ( ![ícone de Mais Ações](/help/main/assets/icons/MoreSmall.svg) ) ao lado da atividade que você deseja copiar e clique em [!UICONTROL **Copiar**].

Leve em consideração as seguintes informações ao usar a funcionalidade de copiar/editar com espaços de trabalho:

* Se você copiar uma atividade no mesmo espaço de trabalho ou do espaço de trabalho padrão para um espaço de trabalho não padrão, o Assistente de atividade será aberto automaticamente. Em cópias entre espaços de trabalho, talvez você só precise atualizar as propriedades da atividade.
* Quando uma atividade é copiada de um espaço de trabalho não padrão para outro espaço de trabalho (seja padrão ou não padrão), o Assistente de atividade é aberto e alguma entrada manual é necessária para concluir a configuração:
   * **[!UICONTROL Properties]**: as propriedades podem diferir entre os espaços de trabalho. Essa situação pode acionar um aviso:

      * No [!UICONTROL Form-Based Experience Composer], os avisos são exibidos diretamente na interface do usuário para visibilidade imediata.

        ![Aviso de espaço de trabalho baseado em formulário](/help/main/c-activities/assets/form-based-warning.png)

      * No VEC, os avisos ficam visíveis ao clicar em [!UICONTROL Configure] > [!UICONTROL Properties].

        ![vec-warning](/help/main/c-activities/assets/vec-warning.png)

        Para resolver esse problema, clique em [!UICONTROL Add/Remove] para que somente as propriedades disponíveis no espaço de trabalho de destino sejam exibidas para seleção.

   * **Públicos-alvo e ofertas**: todos os públicos-alvo e ofertas do espaço de trabalho original devem ser substituídos. Como alternativa, você pode copiá-los das páginas [!UICONTROL Audiences] ou [!UICONTROL Offers] e selecionar os itens apropriados na lista correspondente na atividade.

   * **Alterações manuais necessárias**: todas as alterações manuais necessárias estão resumidas na etapa final ([!UICONTROL Save & Close]). Um pop-up exibe uma lista de entidades que exigem atualizações, ajudando a garantir que todos os ajustes necessários sejam feitos antes de concluir a configuração da atividade.

     ![aviso de validação do Workspace](/help/main/c-activities/assets/work-space-validation.png)

Se o ambiente não tiver a funcionalidade [!UICONTROL Enterprise User Permissions] habilitada, todas as atividades serão abertas no modo de edição antes da cópia.