---
keywords: regras de inclusão;critérios de inclusão;recomendações;promoção;promoções;filtragem dinâmica;dinâmico;correspondência de atributo de perfil
description: Saiba como filtrar dinamicamente no Adobe [!DNL Target] Recommendations comparando itens (entidades) com um valor no perfil do usuário.
title: Como filtrar por Correspondência de atributos de perfil nas atividades do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 6%
---
# Correspondência de atributo de perfil

Filtre dinamicamente em [!DNL Adobe Target] [!DNL Recommendations] comparando itens (entidades) com um valor no perfil do usuário.

Use a [!UICONTROL Correspondência de atributos de perfil] quando quiser mostrar recomendações que correspondem a um valor armazenado no perfil do visitante, como tamanho ou marca favorita.

>[!NOTE]
>
>O [processo para criar e usar regras de inclusão](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para critérios e promoções é semelhante, assim como os casos de uso e exemplos.

Os cenários a seguir mostram como usar a [!UICONTROL Correspondência de atributos de perfil]:

* Uma empresa que vende óculos armazena a cor de quadro favorita de um visitante como &quot;noz&quot;. Para esse visitante específico, as recomendações são configuradas para retornar apenas quadros de óculos que correspondam à cor &quot;noz&quot;.
* Um parâmetro de perfil pode ser definido para o tamanho da roupa (por exemplo, Pequeno, Medium ou Grande) de um visitante enquanto ele navega pelo site da empresa. Uma recomendação pode ser configurada para corresponder a esse parâmetro de perfil e devolver produtos específicos somente ao tamanho de roupa preferido do usuário.

## Exemplos de correspondência de atributos de perfil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL A Correspondência de atributos de perfil] permite que você recomende somente os itens que correspondam a um atributo do perfil do visitante, como nos exemplos abaixo.

### Recomendação de itens da marca favorita do usuário

Por exemplo, você pode usar a opção de [!UICONTROL Correspondência de atributos de perfil] para criar uma regra que recomenda itens apenas onde a marca é igual ao valor ou ao texto armazenado em `profile.favoritebrand`. Com essa regra, se um visitante estiver olhando para shorts de corrida de uma marca específica, apenas as recomendações exibirão a correspondência dessa marca favorita do usuário (o valor armazenado em `profile.favoritebrand` no perfil do visitante).

![Marca favorita](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Vinculando cargos a candidatos a emprego

Suponha que você esteja tentando combinar empregos com candidatos a emprego. Você deseja recomendar apenas os trabalhos que estão na mesma cidade do candidato a emprego.

Você pode usar as regras de inclusão para corresponder a uma localização do candidato a emprego no perfil do visitante a uma lista de empregos, como no exemplo a seguir:

![Cidade do usuário](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Recomendando itens com base no tamanho

Para obter um exemplo visual de como a correspondência de atributos de perfil afeta as recomendações, considere um site que vende ventiladores elétricos.

Quando um visitante clica em várias imagens de fãs neste site, cada página define o valor do parâmetro `entity.size` com base no tamanho do ventilador na imagem ser pequeno ou grande.

Suponha que você tenha criado um script de perfil para rastrear e contar o número de vezes que o valor de `entity.size` foi definido como pequeno vs. grande.

Se o visitante retornar à Página inicial, verá recomendações filtradas com base no fato de mais fãs pequenos ou grandes terem sido clicados.

Recomendações baseadas na exibição de mais fãs pequenos no site:

![recomendações para fãs pequenos](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recomendações com base na exibição de mais fãs grandes no site:

![recomendações para grandes fãs](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
