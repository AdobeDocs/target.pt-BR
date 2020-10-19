---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;parameter matching
description: Filtre dinamicamente no Adobe Target Recommendations comparando itens (entidades) com um valor na solicitação (API ou mbox).
title: Filtrar por parâmetro Correspondência em regras de inclusão dinâmica no Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 27%

---


# ![Correspondência de parâmetros PREMIUM](/help/assets/premium.png)

Filtre dinamicamente comparando itens (entidades) com um valor na solicitação (API ou mbox).

Por exemplo, somente conteúdo recomendado que corresponda ao parâmetro de página &quot;setor&quot; ou outros parâmetros, como dimensões de dispositivo ou localização geográfica, como nos exemplos a seguir.

* Parâmetros de mbox para largura e altura da tela podem ser usados para público alvo de visitantes móveis e recomendamos apenas dispositivos móveis e acessórios.
* Parâmetros regionais de localização geográfica podem ser usados para retornar recomendações para ferramentas durante o inverno. Os sopradores de neve e outras ferramentas de redução de neve podem ser recomendados para visitantes em áreas onde neva, mas não é recomendado para visitantes em áreas onde não neve.

>[!NOTE]
>
>Se a atividade tiver sido criada antes de 31 de outubro de 2016, seu delivery falhará se ele usar o filtro &quot;Correspondência de parâmetros&quot;. Para resolver este problema:
>
>* Crie uma nova atividade e adicione nela seus critérios.
>* Use um critério que não contenha o filtro &quot;Correspondência de parâmetros&quot;.
>* Remova o filtro &quot;Correspondência de parâmetros&quot; de seus critérios.


Operadores disponíveis:

* é igual a
* não é igual
* contém
* não contém
* começa com
* termina com
* é maior que ou igual a
* é menor que ou igual a
* está entre