---
keywords: url da atividade;url;url diferente
description: Descubra como configurar o [!UICONTROL Activity URL] para definir páginas de teste e garantir um design de teste preciso.
title: Qual é o URL da atividade em uma atividade A/B?
feature: A/B Tests
hide: true
hidefromtoc: true
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
source-git-commit: d92c09b905b10c6d0175a5de137d573f8cd475d7
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 32%

---

# URL da atividade

A URL da atividade determina a página que é usada no teste e que é aberta quando o teste é criado usando [!DNL Adobe Target].

Quando solicitado durante a criação da atividade, especifique o URL da atividade. Digite a URL completa (incluindo `https://`) e clique em **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://www.adobe.com`] são correspondentes.

## Especificar um URL diferente

Por padrão, o [!UICONTROL Visual Experience Composer] abre a página especificada nas suas [configurações do Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.

1. (Condicional) Para exibir uma página diferente após a abertura de [!UICONTROL Visual Experience Composer], na página **[!UICONTROL Experiences]**, clique em **[!UICONTROL Configure]** na parte superior da página e selecione **[!UICONTROL Page Delivery]**.

1. Especifique a URL no campo **[!UICONTROL URL]**.

1. (Condicional) Clique em **[!UICONTROL Add Rule]** para adicionar mais páginas ou seções à atividade.

   Regras adicionais podem ser baseadas em qualquer um dos seguintes:

   * URL
   * Domínio
   * Caminho
   * Fragmento em hash (#)
   * Consulta
   * Parâmetro da mbox
   * Personalizado

   Regras adicionais podem ser unidas ao URL da atividade com AND ou OR. Todas regras que você adicionar são avaliadas contra si próprias com AND.

1. Clique em **[!UICONTROL Save]** quando terminar.

   Se você tiver inserido uma URL para um site que não inclui o código JavaScript [!DNL Target]s, não será possível selecionar elementos de página.

   Por padrão, o [!UICONTROL Visual Experience Composer] não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar **[!UICONTROL Render using JavaScript]** se quiser alterar esses elementos usando o [!UICONTROL Visual Experience Composer].—>

>[!NOTE]
>
>Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.
