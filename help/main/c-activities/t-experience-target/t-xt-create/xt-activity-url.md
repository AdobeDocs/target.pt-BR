---
keywords: Direcionamento de experiência;xt;url de atividade;url
description: Saiba como especificar a [!UICONTROL Activity URL] que determina a página que é usada no teste e que é aberta quando a atividade [!UICONTROL Experience Targeting] é criada usando  [!DNL Adobe Target].
title: O que é o [!UICONTROL Activity URL] em uma atividade [!UICONTROL Experience Targeting] (XT)?
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 24513d8cb39d38dcfbc74bf40961d5517cc90a4b
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 39%

---

# URL da atividade em [!UICONTROL Experience Targeting] (XT) atividades

O [!UICONTROL Activity URL] determina a página que é usada em uma atividade [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT). Esta é a página que abre no [!UICONTROL Visual Experience Composer] (VEC) ou [!UICONTROL Form-Based Experience Composer] quando a atividade é criada.

1. Quando solicitado ao [criar uma atividade de XT](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), especifique o URL da atividade. Digite a URL completa (incluindo `https://`) e clique em **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] e [!DNL `http://www.adobe.com`] são correspondentes.
   >
   >Por padrão, o VEC ou o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) abre a página especificada nas suas [configurações do Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.
   >
   >Se você especificar uma URL para um site que não inclui uma biblioteca de JavaScript [[!DNL Target] at.js ou [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html){target=_blank}, não será possível selecionar elementos da página.

1. (Condicional) Para exibir uma página diferente após a abertura do VEC, clique em **[!UICONTROL Configure]**, selecione **[!UICONTROL Page Delivery]** e especifique a URL no campo [!UICONTROL URL].

   ![Caixa de diálogo Entrega de página](/help/main/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.

1. (Condicional) Clique em **[!UICONTROL Add Template Rule]** para adicionar mais páginas ou seções à atividade.

   Regras adicionais podem ser baseadas em qualquer um dos seguintes:

   * URL
   * Domínio
   * Caminho
   * Fragmento em hash (#)
   * Consulta
   * Parâmetro da mbox

   Regras adicionais podem ser unidas no URL da atividade com AND ou OR. Todas regras que você adicionar são avaliadas contra si próprias com AND.

1. Clique em **[!UICONTROL Save]** quando terminar.
