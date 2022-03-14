---
keywords: regras de inclusão, critérios de inclusão, recomendações, promoção, promoções, filtragem dinâmica, dinâmica, correspondência de parâmetros
description: Saiba como filtrar dinamicamente no Adobe [!DNL Target] Recommendations, comparando itens (entidades) com um valor na solicitação (API ou mbox).
title: Como faço para filtrar por correspondência de parâmetros nas atividades do Recommendations?
feature: Recommendations
exl-id: 9ec161b9-1b37-4475-b508-af676126c817
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 10%

---

# ![PREMIUM](/help/main/assets/premium.png) Correspondência de parâmetros

Filtre dinamicamente comparando itens (entidades) com um valor na solicitação (API ou mbox).

Por exemplo, recomende somente o conteúdo que corresponda ao parâmetro de página do &quot;setor&quot; ou outros parâmetros, como dimensões de dispositivo ou localização geográfica, como nos exemplos a seguir.

* Parâmetros de mbox para largura e altura da tela podem ser usados para direcionar visitantes móveis e recomendar somente dispositivos móveis e acessórios.
* Crie uma regra de recomendações que retorne somente os telefones celulares mais vendidos que correspondam ou excedam a altura da tela do dispositivo móvel que o visitante está usando para visualizar a página.
* Parâmetros de localização geográfica regionais podem ser usados para retornar recomendações de ferramentas durante o inverno. Os sopradores de neve e outras ferramentas de redução de neve podem ser recomendados para visitantes em áreas em que neva, mas não é recomendado para visitantes em áreas em que não neve.

>[!NOTE]
>
>Se a atividade foi criada antes de 31 de outubro de 2016, ocorrerá falha na sua entrega se o filtro &quot;Correspondência de parâmetros&quot; for usado. Para resolver este problema:
>
>* Crie uma nova atividade e adicione nela seus critérios.
>* Use um critério que não contenha o filtro &quot;Correspondência de parâmetros&quot;.
>* Remova o filtro &quot;Correspondência de parâmetros&quot; de seus critérios.


## Exemplos de correspondência de parâmetros

[!UICONTROL Correspondência de parâmetros] O permite recomendar o conteúdo que corresponda aos parâmetros da página ou aos parâmetros do visitante, como dimensões de dispositivo ou localização geográfica, como no exemplo a seguir:

[!DNL Recommendations] pode corresponder aos valores de parâmetro enviados no [!DNL Target] chame. Nesse caso, [!DNL Target] O detecta que um visitante está usando um dispositivo móvel, com base nos parâmetros de altura e largura da tela enviados na variável [!DNL Target] e recomendará somente itens que sejam dispositivos móveis.

Considere o exemplo de chamada do Target a seguir:

![Chamada do Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call-2.png)

Na página que um visitante está visualizando, ele verá produtos de dispositivos móveis.

![Produtos para dispositivos móveis](/help/main/c-recommendations/c-algorithms/assets/phones.png)
