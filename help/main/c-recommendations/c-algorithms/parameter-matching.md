---
keywords: regras de inclusão;critérios de inclusão;recomendações;promoção;promoções;filtragem dinâmica;dinâmico;correspondência de parâmetros
description: Saiba como filtrar dinamicamente no Adobe [!DNL Target] Recommendations comparando itens (entidades) com um valor na solicitação (API ou mbox).
title: Correspondência de parâmetro
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
TQID: 'https://experienceleague.adobe.com/GTli-O1p4Gm2Fg9J-L0ukQ8dSw2t-da8OatFLP8Ks9g'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 8%
---
# Correspondência de parâmetro {#parameter-matching}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como filtrar recomendações dinamicamente em [!DNL Adobe Target Recommendations] comparando itens (entidades) com um valor na solicitação (API ou mbox).

>[!ENDSHADEBOX]

**[!UICONTROL Correspondência de Parâmetros]** recomenda somente o conteúdo que corresponde aos parâmetros da página ou aos parâmetros do visitante, como dimensões de dispositivo ou localização geográfica. Por exemplo, somente o conteúdo que corresponde ao parâmetro de página do &quot;setor&quot; pode ser recomendado. O processo para criar e usar regras de inclusão para critérios e promoções é semelhante, assim como os casos de uso e exemplos. Para obter mais informações, consulte [Usar regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

Outros exemplos incluem:

* Parâmetros de mbox para largura e altura da tela podem ser usados para direcionar visitantes móveis e recomendar apenas dispositivos móveis e acessórios.
* Uma regra de recomendações pode retornar apenas os telefones celulares mais vendidos que correspondam ou excedam a altura da tela do dispositivo móvel que o visitante usa para exibir a página.
* Os parâmetros de localização geográfica regional podem ser usados para retornar recomendações de ferramentas durante o inverno. Ventiladores de neve e outras ferramentas de redução de neve podem ser recomendadas para visitantes em áreas onde neva, mas não para visitantes em áreas onde não neva.

## Exemplos de correspondência de parâmetros

[!DNL Recommendations] pode corresponder a valores de parâmetros enviados na chamada [!DNL Target]. No exemplo a seguir, o [!DNL Target] detecta que um visitante está usando um dispositivo móvel, com base nos parâmetros de altura e largura da tela enviados na chamada [!DNL Target], e recomenda apenas itens que sejam dispositivos móveis.

Considere o exemplo a seguir [!DNL Target] chamada:

![Chamada do Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

Na página que um visitante está visualizando, os produtos para dispositivos móveis são exibidos.

![Produtos para dispositivos móveis](/help/main/c-recommendations/c-algorithms/assets/phones.png)
