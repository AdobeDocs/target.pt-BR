---
keywords: mvt;teste multivariado;ofertas;combinações
description: Saiba como usar o [!UICONTROL Visual Experience Composer] (VEC) no Adobe [!DNL Target] para criar as ofertas que você deseja incluir em seu [!UICONTROL Teste multivariado] (MVT).
title: Como criar combinações em um [!UICONTROL Teste multivariado] (MVT)?
feature: Multivariate Tests
exl-id: 8b5883de-de76-403d-ae20-c933a8665555
TQID: 'https://experienceleague.adobe.com/3vxuP07ZViE1etmmvBdYVHIOrtZqRZfL3nE5RMHo9rU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 29%
---
# Criar combinações {#create-combinations}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como criar a imagem e as ofertas do HTML que compõem as combinações de um **[!UICONTROL Teste Multivariado]**.

>[!ENDSHADEBOX]

Em um **[!UICONTROL Teste multivariado]** (MVT), cada local contém várias ofertas, e cada combinação de ofertas entre os locais é uma experiência. Use o **[!UICONTROL Visual Experience Composer]** (VEC) no [!DNL Adobe Target] para criar as ofertas que deseja incluir no teste.

Para obter mais informações sobre como usar o VEC para criar e editar ofertas, consulte [Opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

>[!NOTE]
>
>Você pode clicar em **[!UICONTROL Expandir seleção]** ao selecionar objetos na página para selecionar o elemento pai, além do elemento selecionado originalmente. Ao selecionar qualquer elemento pai, todos os filhos desse elemento serão selecionados automaticamente. Você pode expandir a seleção várias vezes.
>
>Você também pode usar o [caminho DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) para navegar pelos elementos.

## Ofertas de imagem {#image-offers}

Teste várias ofertas de imagem dentro de um local para determinar qual imagem é mais bem sucedida.

1. Clique em uma imagem na sua página e selecione **[!UICONTROL Alterar Oferta de Imagem]**.

   ![Alterar menu de Oferta de Imagem](../assets/multivariate-1.png)

1. Na caixa de diálogo **[!UICONTROL Oferta de imagem]**, selecione todas as imagens que deseja incluir no teste e clique em **[!UICONTROL Adicionar]**.

   ![Alterar menu de Oferta de Imagem](../assets/multivariate-3.png)

Cada imagem se torna uma experiência separada nesse local.

## Ofertas do HTML {#html-offers}

Teste várias ofertas HTML de um local para determinar qual é mais bem sucedida.

1. Clique em uma oferta do HTML na sua página e em **[!UICONTROL Alterar oferta do HTML]**.

   ![Alterar menu Oferta do HTML](../assets/multivariate-2.png)

1. Escolha sua oferta do HTML e clique em **[!UICONTROL Criar oferta]** e depois em **[!UICONTROL HTML Offer]**.

   ![Alterar menu Oferta do HTML](../assets/multivariate-4.png)

1. Nomeie a oferta, digite ou cole o código para a oferta do HTML e clique em **[!UICONTROL Criar]**.

   Repita o procedimento para qualquer oferta adicional do HTML que desejar incluir.

1. Clique em **[!UICONTROL Salvar]**.

Cada oferta em HTML se torna uma experiência separada nesse local.

Para obter recomendações sobre quantas combinações devem ser incluídas e como analisá-las antes de iniciar o teste, consulte [Práticas recomendadas para testes multivariados](/help/main/c-activities/c-multivariate-testing/best-practices.md#create).
