---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;parameter matching
description: Filtre dinamicamente no Adobe Target Recommendations comparando itens (entidades) com um valor na solicitação (API ou mbox).
title: Filtrar por parâmetro Correspondência em regras de inclusão dinâmica no Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: c814215476ef6e40f4f175fe3f9dbb2c26b966eb
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 10%

---


# ![Correspondência ](/help/assets/premium.png) PREMIUMParameter

Filtre dinamicamente comparando itens (entidades) com um valor na solicitação (API ou mbox).

Por exemplo, somente conteúdo recomendado que corresponda ao parâmetro de página &quot;setor&quot; ou outros parâmetros, como dimensões de dispositivo ou localização geográfica, como nos exemplos a seguir.

* Parâmetros de mbox para largura e altura da tela podem ser usados para público alvo de visitantes móveis e recomendamos apenas dispositivos móveis e acessórios.
* Crie uma regra de recomendações que retorne somente os telefones celulares mais vendidos que correspondem ou excedem a altura da tela do dispositivo móvel que o visitante está usando para visualização na página.
* Parâmetros regionais de localização geográfica podem ser usados para retornar recomendações para ferramentas durante o inverno. Os sopradores de neve e outras ferramentas de redução de neve podem ser recomendados para visitantes em áreas onde neva, mas não é recomendado para visitantes em áreas onde não neve.

>[!NOTE]
>
>Se a atividade tiver sido criada antes de 31 de outubro de 2016, seu delivery falhará se ele usar o filtro &quot;Correspondência de parâmetros&quot;. Para resolver este problema:
>
>* Crie uma nova atividade e adicione nela seus critérios.
>* Use um critério que não contenha o filtro &quot;Correspondência de parâmetros&quot;.
>* Remova o filtro &quot;Correspondência de parâmetros&quot; de seus critérios.


## Exemplos de correspondência de parâmetros

[!UICONTROL A ] Correspondência de parâmetros permite que você recomende conteúdo que corresponda aos parâmetros da página ou aos parâmetros do visitante, como dimensões do dispositivo ou localização geográfica, como no exemplo a seguir:

[!DNL Recommendations] pode corresponder aos valores de parâmetro enviados na  [!DNL Target] chamada. Neste caso, [!DNL Target] detecta que um visitante está usando um dispositivo móvel, com base nos parâmetros de altura e largura da tela enviados na chamada [!DNL Target], e recomendará somente itens que sejam dispositivos móveis.

Considere a seguinte chamada de Público alvo de exemplo:

![chamada de público alvo](/help/c-recommendations/c-algorithms/assets/example-target-call-2.png)

Na página que um visitante está visualizando, ele ou ela verá produtos para dispositivos móveis.

![Produtos para dispositivos móveis](/help/c-recommendations/c-algorithms/assets/phones.png)
