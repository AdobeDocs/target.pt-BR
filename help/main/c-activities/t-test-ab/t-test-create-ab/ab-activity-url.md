---
keywords: url da atividade;url;url diferente
description: Descubra como definir a [!UICONTROL URL da atividade] em uma atividade A/B, de Direcionamento de experiência ou de Teste multivariado para definir páginas de teste e garantir um design de teste preciso.
title: Qual é o URL da atividade em uma atividade A/B, de Direcionamento de experiência ou de Teste multivariado?
feature: A/B Tests
exl-id: 7f1b8364-790d-4767-bff3-4217ced1a77b
reason: republish
TQID: 'https://experienceleague.adobe.com/arQWsSfBKYtrayq9AI8ejU1T-Uor-oL5j2Sp2JKKXZE'
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
source-git-commit: aad553690f1f399177214c94a2276d038f46d9cb
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 25%
---
# URL da atividade {#ab-activity-url}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como especificar a URL de atividade de uma atividade A/B, de Direcionamento de experiência (XT) ou de Teste multivariado (MVT), como exibir uma página diferente e como adicionar regras para mais páginas ou seções.

>[!ENDSHADEBOX]

A [!UICONTROL URL da Atividade] determina a página que é usada na atividade. Esta é a página que é aberta no [!UICONTROL Visual Experience Composer] (VEC) ou no [!UICONTROL Experience Composer baseado em formulário] quando a atividade é criada no [!DNL Adobe Target].

## Especifique o URL da atividade {#specify-url}

Quando solicitado durante a criação da atividade, especifique o URL da atividade. Digite a URL completa (incluindo `https://`) e clique em **[!UICONTROL Criar]**.

>[!NOTE]
>
>[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com/br`] e [!DNL `https://www.adobe.com/br`] são correspondentes.

Se você especificar uma URL para um site que não inclui a biblioteca de JavaScript [!DNL Target] [at.js ou [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html?lang=pt-BR){target=_blank}, não será possível selecionar elementos de página.

## Exibir uma página diferente {#different-page}

Por padrão, o VEC ou o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) abre a página especificada nas suas [configurações do Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.

Para exibir uma página diferente após a abertura do VEC:

1. Na página **[!UICONTROL Experiências]**, clique em **[!UICONTROL Configurar]** na parte superior da página e selecione **[!UICONTROL Entrega de página]**.

1. Especifique a URL no campo **[!UICONTROL URL]**.

1. Clique em **[!UICONTROL Salvar]** quando tiver concluído.

Por padrão, o VEC não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar a opção **[!UICONTROL Renderizar usando o JavaScript]** se quiser alterar esses elementos usando o VEC.

>[!NOTE]
>
>Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.

## Adicionar regras para mais páginas ou seções {#add-rules}

Para adicionar mais páginas ou seções à atividade, clique em **[!UICONTROL Adicionar regra]** nas configurações de **[!UICONTROL Entrega de página]** e em **[!UICONTROL Salvar]** quando terminar.

Regras adicionais podem ser baseadas em qualquer um dos seguintes:

* URL
* Domínio
* Caminho
* Fragmento em hash (#)
* Consulta
* Parâmetro da mbox
* Personalizado

Regras adicionais podem ser unidas ao URL da atividade com AND ou OR. Todas regras que você adicionar são avaliadas contra si próprias com AND.
