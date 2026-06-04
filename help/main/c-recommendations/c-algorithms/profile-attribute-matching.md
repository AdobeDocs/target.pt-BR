---
keywords: regras de inclusão;critérios de inclusão;recomendações;promoção;promoções;filtragem dinâmica;dinâmico;correspondência de atributo de perfil
description: Saiba como filtrar dinamicamente no  [!DNL Target Recommendations]  comparando itens (entidades) com um valor no perfil do usuário.
title: Como filtrar por Correspondência de atributos de perfil nas atividades do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
TQID: https://experienceleague.adobe.com/Gm91Mww5ylvNjUcmzp6KwxIG6LTibvI44LnW67KFzqk
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 495
ht-degree: 0%

---

# Correspondência de atributo de perfil

Filtre dinamicamente em [!DNL Adobe Target Recommendations] comparando itens (entidades) com um valor no perfil do usuário.

Use a [!UICONTROL Correspondência de atributos de perfil] quando quiser mostrar recomendações que correspondem a um valor armazenado no perfil do visitante, como tamanho ou marca favorita.

>[!NOTE]
>
>O [processo para criar e usar regras de inclusão](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para critérios e promoções é semelhante, assim como os casos de uso e exemplos.

Os cenários a seguir mostram como usar a [!UICONTROL Correspondência de atributos de perfil]:

* Uma empresa que vende óculos armazena a cor de quadro favorita de um visitante como &quot;noz&quot;. Para esse visitante específico, as recomendações são configuradas para retornar apenas quadros de óculos que correspondam à cor &quot;noz&quot;.
* Um parâmetro de perfil pode ser definido para o tamanho da roupa (por exemplo, Pequeno, Medium ou Grande) de um visitante enquanto ele navega pelo site da empresa. Uma recomendação pode ser configurada para corresponder a esse parâmetro de perfil e devolver produtos específicos somente ao tamanho de roupa preferido do usuário.

## Exemplos de correspondência de atributos de perfil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL A Correspondência de atributos de perfil] permite recomendar apenas os itens que correspondem a um atributo do perfil do visitante, como nos exemplos abaixo.

### Recomendação de itens da marca favorita do usuário

Por exemplo, você pode usar a opção de [!UICONTROL Correspondência de atributos de perfil] para criar uma regra que recomenda itens apenas onde a marca é igual ao valor ou ao texto armazenado em `profile.favoritebrand`. Com essa regra, se um visitante estiver olhando para shorts de corrida de uma marca específica, apenas as recomendações são exibidas de acordo com a marca favorita desse usuário (o valor armazenado em `profile.favoritebrand` no perfil do visitante).

![Marca favorita](/help/main/c-recommendations/c-algorithms/assets/favorite-brand-new.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Vinculando cargos a candidatos a emprego

Suponha que você esteja tentando combinar empregos com candidatos a emprego. Você deseja recomendar apenas os trabalhos que estão na mesma cidade do candidato a emprego.

Você pode usar as regras de inclusão para corresponder a uma localização do candidato a um cargo no perfil do visitante a uma lista de cargos, como no exemplo a seguir:

![Cidade do usuário](/help/main/c-recommendations/c-algorithms/assets/city-new.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Recomendando itens com base no tamanho

Para obter um exemplo visual de como a correspondência de atributos de perfil afeta as recomendações, considere um site que vende ventiladores elétricos.

Quando um visitante clica em várias imagens de fãs neste site, cada página define o valor do parâmetro `entity.size` com base no tamanho do ventilador na imagem ser pequeno ou grande.

Suponha que você tenha criado um script de perfil para rastrear e contar o número de vezes que o valor de `entity.size` foi definido como pequeno versus grande.

Se o visitante retornar à Página inicial, verá recomendações filtradas com base no fato de mais fãs pequenos ou grandes terem sido clicados.

Recomendações baseadas na exibição de mais fãs pequenos no site:

![recomendações para fãs pequenos](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recomendações com base na exibição de mais fãs grandes no site:

![recomendações para grandes fãs](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
