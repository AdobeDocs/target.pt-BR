---
keywords: url da atividade;url;url diferente
description: Descubra como definir a [!UICONTROL URL de atividade] para definir páginas de teste e garantir um design de teste preciso.
title: Qual é o URL da atividade em uma atividade A/B?
feature: A/B Tests
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
reason: republish
TQID: https://experienceleague.adobe.com/arQWsSfBKYtrayq9AI8ejU1T-Uor-oL5j2Sp2JKKXZE
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 305
ht-degree: 38%

---

# URL da atividade

A URL da atividade determina a página que é usada no teste e que é aberta quando o teste é criado usando [!DNL Adobe Target].

Quando solicitado durante a criação da atividade, especifique o URL da atividade. Digite a URL completa (incluindo `https://`) e clique em **[!UICONTROL Criar]**.

>[!NOTE]
>
>[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://www.adobe.com`] são correspondentes.

## Especificar um URL diferente

Por padrão, o [!UICONTROL Visual Experience Composer] abre a página especificada nas suas [configurações do Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.

1. (Condicional) Para exibir uma página diferente depois que o [!UICONTROL Visual Experience Composer] for aberto, na página **[!UICONTROL Experiências]**, clique em **[!UICONTROL Configurar]** na parte superior da página e selecione **[!UICONTROL Entrega de página]**.

1. Especifique a URL no campo **[!UICONTROL URL]**.

1. (Condicional) Clique em **[!UICONTROL Adicionar regra]** para adicionar mais páginas ou seções à atividade.

   Regras adicionais podem ser baseadas em qualquer um dos seguintes:

   * URL
   * Domínio
   * Caminho
   * Fragmento em hash (#)
   * Consulta
   * Parâmetro da mbox
   * Personalizado

   Regras adicionais podem ser unidas ao URL da atividade com AND ou OR. Todas regras que você adicionar são avaliadas contra si próprias com AND.

1. Clique em **[!UICONTROL Salvar]** quando tiver concluído.

   Se você tiver inserido uma URL para um site que não inclui o código JavaScript [!DNL Target]s, não será possível selecionar elementos de página.

   Por padrão, o [!UICONTROL Visual Experience Composer] não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar a opção **[!UICONTROL Renderizar usando o JavaScript]** se quiser alterar esses elementos usando o [!UICONTROL Visual Experience Composer].—>

>[!NOTE]
>
>Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.
