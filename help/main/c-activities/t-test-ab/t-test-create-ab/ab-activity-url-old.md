---
keywords: url da atividade;url;url diferente
description: Saiba como especificar a URL da atividade que determina a página que é usada no teste e que é aberta quando o teste é criado usando  [!DNL Adobe Target].
title: Qual é o URL da atividade em uma atividade A/B?
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 44%

---

# URL da atividade

O URL da atividade determina a página que é usada no teste e que é aberta quando o teste é criado usando o Adobe Target.

Quando solicitado durante a criação da atividade, especifique o URL da atividade. Digite a URL completa (incluindo `https://`) e clique em **[!UICONTROL Create]**.

>[!NOTE]
>
>[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://www.adobe.com`] são correspondentes.

## Especificar um URL diferente

Por padrão, o [!UICONTROL Visual Experience Composer] abre a página especificada nas suas [configurações do Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.

1. Para exibir uma página diferente depois da abertura de [!UICONTROL Visual Experience Composer], na página **[!UICONTROL Experiences]**, clique no ícone de engrenagem **[!UICONTROL Configure]** e selecione **[!UICONTROL Page Delivery]**.

1. Especifique a URL no campo **[!UICONTROL URL]**.

   ![Caixa de diálogo Entrega de página](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

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

Se você tiver inserido um URL para um site que não inclui o código JavaScript do [!DNL Target] Standard, não será possível selecionar elementos de página.

Por padrão, o [!UICONTROL Visual Experience Composer] não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar **[!UICONTROL Render using JavaScript]** se quiser alterar esses elementos usando o [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.
