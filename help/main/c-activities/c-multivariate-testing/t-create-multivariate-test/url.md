---
keywords: Testes multivariados;url de atividade
description: Saiba como especificar a URL de atividade que determina a página que é usada no teste e que é aberta quando a atividade [!UICONTROL Multivariate Test] é criada usando  [!DNL Adobe Target].
title: Qual é a URL de atividade em uma atividade [!UICONTROL Multivariate Test] (MVT)?
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
source-git-commit: 7853d8c5934e40d1026e067dfa413f520ecba931
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 34%

---

# URL da atividade

A URL da atividade determina a página que é usada no [!UICONTROL Multivariate Test] (MVT) e que é aberta quando o teste é criado no [!DNL Adobe Target].

Quando solicitado durante a [criação da atividade](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), especifique o URL da atividade. Digite a URL completa (incluindo `https://`) e clique em **[!UICONTROL Next]**.

>[!NOTE]
>
>[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] e [!DNL `http://www.adobe.com`] são correspondentes.

Por padrão, o [!UICONTROL Visual Experience Composer] (VEC) abre a página especificada nas suas [configurações do Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.

Para exibir uma página diferente após a abertura do VEC, clique no ícone **[!UICONTROL Configure]** e selecione **[!UICONTROL Page Delivery]** e, em seguida, especifique a URL.

![Caixa de diálogo Entrega de página](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Clique em **[!UICONTROL Add Template Rule]** para adicionar mais páginas ou seções à atividade.

Regras adicionais podem ser baseadas em qualquer um dos seguintes:

* URL
* Domínio
* Caminho
* Fragmento em hash (#)
* Consulta
* Parâmetro

Regras adicionais podem ser unidas ao URL da atividade com AND ou OR. Todas as regras adicionadas são avaliadas entre si com AND.

Clique em **[!UICONTROL Save]** quando terminar.

>[!NOTE]
>
>Se você tiver inserido uma URL para um site que não inclui o código JavaScript [!DNL Target], não será possível selecionar elementos de página.

Por padrão, o VEC não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar **[!UICONTROL Render using JavaScript]** se quiser alterar esses elementos usando o [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.
