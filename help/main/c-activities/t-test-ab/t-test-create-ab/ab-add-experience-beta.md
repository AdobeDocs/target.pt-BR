---
keywords: Definição de metas; experiência; adicionar experiência; adicionar experiência
description: Use o [!UICONTROL Visual Experience Composer] (VEC) para adicionar experiências às atividades.
title: Como adicionar experiências em uma atividade A/B?
feature: A/B Tests
hide: true
hidefromtoc: true
exl-id: 4b2d6cc6-f280-4d65-8153-53e9cd61d15a
source-git-commit: d5bd3b0d7cdf6eb06175a6365da6b8173f76800f
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 28%

---

# Adicionar experiência

O [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) do fornece uma interface visual para adicionar e editar as experiências na sua página.

Para obter mais detalhes sobre experiências, consulte [Experiências](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. Na página **[!UICONTROL Experiences]** do VEC, clique no ícone [!UICONTROL Add] ( ![Ícone Adicionar](/help/main/assets/icons/Add.svg) ) na parte superior do painel [!UICONTROL Experiences].

   O VEC exibe duas guias no lado esquerdo depois que você cria uma nova atividade: Experiência A e Experiência B. A Experiência A é a experiência de controle. Você pode adicionar várias experiências ao teste.

1. Selecione os elementos que deseja alterar e faça as alterações desejadas.

   À medida que você passa o mouse sobre os elementos na página, eles são realçados. Qualquer elemento destacado pode ser alterado usando o VEC.

   Se você criou uma solicitação [!DNL Target] na página usando [!DNL Target Classic] (antigo [!DNL Test&Target]), essa solicitação [!DNL Target] aparece como um elemento que mostra o nome da solicitação e pode ser modificada como qualquer outro elemento.

   Para ver uma lista de ações que podem ser executadas em um elemento de uma página exibida para alterar a experiência, consulte [Opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Se você apresentar uma imagem de uma fonte diferente da sua página principal (como uma imagem hospedada em `akamai.net` e disponibilizada em `example.com`), ela não será exibida na miniatura da página mostrada no diagrama de fluxo.

1. Clique em **[!UICONTROL Next]** quando terminar de criar a experiência.

## Renomear experiência

1. Clique no ícone **[!UICONTROL Rename Experience]** ( ![Ícone Renomear](/help/main/assets/icons/Rename.svg) ) ao lado de uma experiência para dar um novo nome a ela.

2. Especifique um novo nome e clique em **[!UICONTROL Save]**.

   Ao nomear ou renomear uma experiência, os seguintes caracteres não são permitidos:

   | Caractere | Descrição |
   |--- |--- |
   | / | Barra |
   | ? | Ponto de interrogação |
   | # | Sinal numérico |
   | : | Dois-pontos |
   | = | Igual a |
   | + | Plus |
   | - | Menos |
   | @ | Sinal de arroba |

## Redirecionar para URL

1. No painel **[!UICONTROL Experiences]**, clique no ícone **[!UICONTROL More]** ( ![ícone Mais](/help/main/assets/icons/MoreSmall.svg) ) ao lado de uma experiência e clique em **[!UICONTROL Redirect to URL]**.

   Para obter mais informações, consulte [Redirecionar para URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

1. Especifique o URL para o qual deseja redirecionar a experiência.

1. (Condicional) Marque a caixa de seleção **[!UICONTROL Include Current Query Parameters]**.

1. Clique em **[!UICONTROL Save]**.

## Duplicar uma experiência

Você pode copiar uma experiência em um [!UICONTROL A/B Test] para fazer pequenas alterações nele sem ter que recriar a experiência.

1. No painel **[!UICONTROL Experiences]**, clique no ícone **[!UICONTROL More]** ( ![ícone Mais](/help/main/assets/icons/MoreSmall.svg) ) ao lado de uma experiência e clique em **[!UICONTROL Duplicate]**.

## Excluir uma experiência

1. No painel **[!UICONTROL Experiences]**, clique no ícone **[!UICONTROL More]** ( ![Ícone de mais](/help/main/assets/icons/MoreSmall.svg) ) ao lado de uma experiência, clique em **[!UICONTROL Delete]** e em **[!UICONTROL Delete]** para confirmar a ação.
