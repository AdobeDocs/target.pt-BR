---
keywords: Testes multivariados;url de atividade
description: Saiba como especificar a URL de atividade que determina a página que é usada no teste e que é aberta quando a atividade de [!UICONTROL Teste multivariado] é criada usando  [!DNL Adobe Target].
title: Qual é o URL de atividade em uma atividade de [!UICONTROL Teste multivariado] (MVT)?
feature: Multivariate Tests
exl-id: 336169ae-7c8b-4fd5-9b1c-0bd3e9524425
TQID: https://experienceleague.adobe.com/oQKwrlZ95XKEKSJIUiWqXXo9AJJzCb20gfS1rtwGImM
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 38%

---

# URL da atividade

A URL da atividade determina a página que é usada no [!UICONTROL Teste Multivariado] (MVT) e que é aberta quando o teste é criado no [!DNL Adobe Target].

1. Quando solicitado durante a [criação da atividade](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), especifique o URL da atividade. Digite a URL completa (incluindo `https://`) e clique em **[!UICONTROL Criar]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] e [!DNL `http://www.adobe.com`] são correspondentes.

   Por padrão, o [!UICONTROL Visual Experience Composer] (VEC) abre a página especificada nas suas [configurações do Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.

1. (Condicional) Para exibir uma página diferente após a abertura do VEC, clique no ícone **[!UICONTROL Configurar]** e selecione **[!UICONTROL Entrega de página]**. Em seguida, especifique a URL.

1. (Condicional) Clique em **[!UICONTROL Adicionar regra]** para adicionar mais páginas ou seções à atividade.

   Regras adicionais podem ser baseadas em qualquer um dos seguintes:

   * [!UICONTROL  URL]
   * [!UICONTROL Domínio]
   * [!UICONTROL Caminho]
   * [!UICONTROL Fragmento de hash (#)]
   * [!UICONTROL Consulta]
   * [!UICONTROL Personalizado]

   Regras adicionais podem ser unidas ao URL da atividade com AND ou OR. Todas as regras adicionadas são avaliadas entre si com AND.

   Clique em **[!UICONTROL Salvar]** quando tiver concluído.

>[!NOTE]
>
>Se você tiver inserido uma URL para um site que não inclui o código JavaScript [!DNL Target], não será possível selecionar elementos de página.
>
>Por padrão, o VEC não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar a opção **[!UICONTROL Renderizar usando JavaScript]** se quiser alterar esses elementos usando o [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.
