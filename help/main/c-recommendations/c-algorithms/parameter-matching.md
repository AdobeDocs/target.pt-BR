---
keywords: regras de inclusão;critérios de inclusão;recomendações;promoção;promoções;filtragem dinâmica;dinâmico;correspondência de parâmetros
description: Saiba como filtrar dinamicamente no Adobe [!DNL Target] Recommendations comparando itens (entidades) com um valor na solicitação (API ou mbox).
title: Como filtrar por correspondência de parâmetros em atividades do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 10%

---

# Correspondência de parâmetros

Filtre dinamicamente comparando itens (entidades) com um valor na solicitação (API ou mbox).

Por exemplo, recomende somente o conteúdo que corresponda ao parâmetro de página do &quot;setor&quot; ou outros parâmetros, como dimensões de dispositivos ou localização geográfica, como nos exemplos a seguir.

* Parâmetros de mbox para largura e altura da tela podem ser usados para direcionar visitantes móveis e recomendar apenas dispositivos móveis e acessórios.
* Crie uma regra de recomendações que retorne apenas os telefones celulares mais vendidos que correspondem ou excedem a altura da tela do dispositivo móvel que o visitante está usando para exibir a página.
* Os parâmetros de localização geográfica regional podem ser usados para retornar recomendações de ferramentas durante o inverno. Ventiladores de neve e outras ferramentas de redução de neve podem ser recomendadas para visitantes em áreas onde neva, mas não são recomendadas para visitantes em áreas onde não neva.

>[!NOTE]
>
>Se a atividade foi criada antes de 31 de outubro de 2016, ocorrerá falha na sua entrega se o filtro &quot;Correspondência de parâmetros&quot; for usado. Para resolver este problema:
>
>* Crie uma nova atividade e adicione nela seus critérios.
>* Use um critério que não contenha o filtro &quot;Correspondência de parâmetros&quot;.
>* Remova o filtro &quot;Correspondência de parâmetros&quot; de seus critérios.

## Exemplos de Correspondência de Parâmetros

[!UICONTROL Parameter Matching] permite que você recomende um conteúdo que corresponda aos parâmetros da página ou aos parâmetros do visitante, como dimensões de dispositivo ou localização geográfica, como no exemplo a seguir:

[!DNL Recommendations] pode corresponder a valores de parâmetros enviados na chamada [!DNL Target]. Nesta instância, o [!DNL Target] detecta que um visitante está usando um dispositivo móvel, com base nos parâmetros de altura e largura da tela enviados na chamada do [!DNL Target], e recomendará somente itens que sejam dispositivos móveis.

Considere o exemplo de chamada do Target a seguir:

![Chamada do Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

Na página que um visitante está visualizando, ele verá os produtos para dispositivos móveis.

![Produtos para dispositivos móveis](/help/main/c-recommendations/c-algorithms/assets/phones.png)
