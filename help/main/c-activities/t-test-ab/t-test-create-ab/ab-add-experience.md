---
keywords: Direcionamento; experiência; adicionar experiência; adicionar experiência
description: Use o [!UICONTROL Visual Experience Composer] (VEC) para adicionar experiências às atividades.
title: Como adicionar experiências em uma atividade A/B?
feature: A/B Tests
exl-id: c0f1b5a7-07b0-46c2-97f3-95dcc0fcbe3d
TQID: 'https://experienceleague.adobe.com/7qEiUXkfMbPmtB2eMio0LztOYM3naHxG-WRQZOyMmlU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 9f1aaf5c0b172b4bbe89266800708881306e4592
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 25%
---
# Adicionar experiência {#ab-add-experience}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como adicionar e criar uma experiência em uma atividade A/B e como renomeá-la, redirecioná-la, duplicá-la ou excluí-la.

>[!ENDSHADEBOX]

O [!DNL Adobe Target] **[!UICONTROL Visual Experience Composer]** (VEC) fornece uma interface visual para adicionar e editar as experiências na sua página. Para obter mais detalhes sobre experiências, consulte [Experiências](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

## Adicionar e projetar uma experiência {#add-experience}

Para adicionar uma experiência e alterar a página dessa experiência:

1. Na página **[!UICONTROL Experiências]** do VEC, clique no ícone **[!UICONTROL Adicionar]** ( ![Ícone Adicionar](/help/main/assets/icons/Add.svg) ) na parte superior do painel **[!UICONTROL Experiências]**.

   Depois de criar uma nova atividade, o VEC exibe duas guias no lado esquerdo: Experiência A e Experiência B. A Experiência A é a experiência de controle. Você pode adicionar várias experiências ao teste.

1. Selecione os elementos que deseja alterar e faça as alterações desejadas.

   À medida que você passa o mouse sobre os elementos na página, eles são realçados. Qualquer elemento destacado pode ser alterado usando o VEC. Se você criou uma solicitação [!DNL Target] na página usando [!DNL Target Classic] (antigo [!DNL Test&Target]), essa solicitação [!DNL Target] aparece como um elemento que mostra o nome da solicitação e pode ser modificada como qualquer outro elemento.

   Para ver uma lista de ações que podem ser executadas em um elemento de uma página exibida para alterar a experiência, consulte [Opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

1. Clique em **[!UICONTROL Avançar]** quando terminar de criar a experiência.

>[!NOTE]
>
>Se você apresentar uma imagem de uma fonte diferente da sua página principal (como uma imagem hospedada em `akamai.net` e disponibilizada em `example.com`), ela não será exibida na miniatura da página mostrada no diagrama de fluxo.

## Renomear uma experiência {#rename-experience}

Para dar um novo nome a uma experiência:

1. Clique no ícone **[!UICONTROL Renomear Experiência]** ( ![Ícone Renomear](/help/main/assets/icons/Rename.svg) ) ao lado da experiência.

1. Especifique um novo nome e clique em **[!UICONTROL Salvar]**.

Ao nomear ou renomear uma experiência, os seguintes caracteres não são permitidos:

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

## Redirecionar uma experiência para um URL {#redirect-to-url}

Para enviar visitantes de uma experiência para outra URL, consulte também [Redirecionar para a URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md):

1. No painel **[!UICONTROL Experiências]**, clique no ícone **[!UICONTROL Mais]** ( ![ícone Mais](/help/main/assets/icons/MoreSmall.svg) ) ao lado da experiência e clique em **[!UICONTROL Redirecionar para a URL]**.

1. Especifique o URL para o qual deseja redirecionar a experiência.

1. (Condicional) Marque a caixa de seleção **[!UICONTROL Incluir parâmetros de consulta atuais]**.

1. Clique em **[!UICONTROL Salvar]**.

## Duplicar uma experiência {#duplicate-experience}

Você pode copiar uma experiência em um teste A/B para fazer pequenas alterações nela sem precisar recriar a experiência. No painel **[!UICONTROL Experiências]**, clique no ícone **[!UICONTROL Mais]** ( ![ícone Mais](/help/main/assets/icons/MoreSmall.svg) ) ao lado da experiência e clique em **[!UICONTROL Duplicar]**.

## Excluir uma experiência {#delete-experience}

No painel **[!UICONTROL Experiências]**, clique no ícone **[!UICONTROL Mais]** ( ![ícone Mais](/help/main/assets/icons/MoreSmall.svg) ) ao lado da experiência, clique em **[!UICONTROL Excluir]** e em **[!UICONTROL Excluir]** para confirmar a ação.
