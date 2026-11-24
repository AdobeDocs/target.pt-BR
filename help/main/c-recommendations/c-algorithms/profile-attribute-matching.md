---
keywords: regras de inclusão;critérios de inclusão;recomendações;promoção;promoções;filtragem dinâmica;dinâmico;correspondência de atributo de perfil
description: Saiba como filtrar dinamicamente no [!DNL Target Recommendations] comparando itens (entidades) com um valor no perfil do usuário.
title: Correspondência de atributo de perfil
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
TQID: 'https://experienceleague.adobe.com/Gm91Mww5ylvNjUcmzp6KwxIG6LTibvI44LnW67KFzqk'
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
source-wordcount: '503'
ht-degree: 5%
---
# Correspondência de atributo de perfil {#profile-attribute-matching}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como filtrar recomendações dinamicamente em [!DNL Adobe Target Recommendations] comparando itens (entidades) com um valor no perfil do visitante.

>[!ENDSHADEBOX]

Use a **[!UICONTROL Correspondência de atributos de perfil]** para mostrar recomendações que correspondem a um valor armazenado no perfil do visitante, como tamanho ou marca favorita. O processo para criar e usar regras de inclusão para critérios e promoções é semelhante, assim como os casos de uso e exemplos. Para obter mais informações, consulte [Usar regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

Os cenários a seguir mostram como a **[!UICONTROL Correspondência de atributos de perfil]** pode ser usada:

* Uma empresa que vende óculos armazena a cor de quadro favorita de um visitante como &quot;noz&quot;. Para esse visitante, as recomendações são configuradas para retornar apenas quadros de óculos que correspondam à cor &quot;noz&quot;.
* Um parâmetro de perfil pode ser definido para o tamanho da roupa (por exemplo, Pequeno, Medium ou Grande) de um visitante enquanto ele navega no site da empresa. Uma recomendação pode ser configurada para corresponder a esse parâmetro de perfil e retornar apenas os produtos no tamanho de roupa preferido do visitante.

## Exemplos de correspondência do atributo de perfil

**[!UICONTROL Correspondência de atributos de perfil]** recomenda apenas os itens que correspondem a um atributo do perfil do visitante, como nos exemplos a seguir.

### Recomendação de itens da marca favorita do usuário

A opção **[!UICONTROL Correspondência de atributos de perfil]** pode criar uma regra que recomenda itens apenas onde a marca é igual ao valor ou ao texto armazenado em `profile.favoritebrand`. Com essa regra, se um visitante estiver olhando para shorts de corrida de uma marca específica, apenas as recomendações que correspondem à marca favorita desse visitante (o valor armazenado em `profile.favoritebrand` no perfil do visitante) são exibidas.

![Marca favorita](/help/main/c-recommendations/c-algorithms/assets/favorite-brand-new.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Vinculando cargos a candidatos a emprego

Para corresponder cargos a candidatos a emprego, apenas os cargos que estão na mesma cidade do candidato a emprego são recomendados. As regras de inclusão podem corresponder à localização de um candidato a emprego do perfil do visitante a uma lista de trabalhos, como no exemplo a seguir:

![Cidade do usuário](/help/main/c-recommendations/c-algorithms/assets/city-new.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Recomendando itens com base no tamanho

O exemplo a seguir mostra como a correspondência de atributos de perfil afeta as recomendações em um site que vende ventiladores elétricos.

Quando um visitante clica em várias imagens de fãs neste site, cada página define o valor do parâmetro `entity.size` com base no tamanho do ventilador na imagem ser pequeno ou grande. Um script de perfil rastreia e conta o número de vezes que o valor de `entity.size` é definido como pequeno versus grande.

Se o visitante retornar à Página inicial, as recomendações filtradas serão exibidas com base no número de fãs pequenos ou grandes que foram clicados.

Recomendações baseadas na exibição de mais fãs pequenos no site:

![recomendações para fãs pequenos](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recomendações com base na exibição de mais fãs grandes no site:

![recomendações para grandes fãs](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
