---
keywords: regras de inclusão, critérios de inclusão, recomendações, promoção, promoções, filtragem dinâmica, dinâmica, correspondência de atributos de perfil
description: Saiba como filtrar dinamicamente no Adobe [!DNL Target] Recommendations, comparando itens (entidades) com um valor no perfil do usuário.
title: Como faço para filtrar por correspondência de atributos de perfil nas atividades do Recommendations?
feature: Recommendations
exl-id: d4b837af-771b-41b4-982b-f9f08e4753f2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 6%

---

# ![PREMIUM](/help/main/assets/premium.png) Correspondência de atributos de perfil

Filtrar dinamicamente em [!DNL Adobe Target] [!DNL Recommendations] comparando itens (entidades) com um valor no perfil do usuário.

Use [!UICONTROL Correspondência de atributos de perfil] quando quiser mostrar recomendações que correspondem a um valor armazenado no perfil do visitante, como tamanho ou marca favorita.

>[!NOTE]
>
>O [processo para criar e usar regras de inclusão](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para critérios e promoções é semelhante, assim como os casos de uso e exemplos.

Os seguintes cenários mostram como você pode usar [!UICONTROL Correspondência de atributos de perfil]:

* Uma empresa que vende óculos armazena a cor de quadro favorita de um visitante como &quot;noz&quot;. Para esse visitante específico, as recomendações são configuradas para retornar apenas os quadros de óculos que correspondem a &quot;noz&quot; em cor.
* Um parâmetro de perfil pode ser definido para o tamanho da roupa (por exemplo, Pequena, Média ou Grande) de um visitante enquanto ele navega pelo site de sua empresa. Uma recomendação pode ser configurada para corresponder a esse parâmetro de perfil e retornar produtos específicos somente ao tamanho de roupas preferencial do usuário.

## Exemplos de Correspondência de atributos de perfil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL Correspondência de atributos de perfil] O permite recomendar somente os itens que correspondem a um atributo do perfil do visitante, como nos exemplos abaixo.

### Recomendando itens da marca favorita do usuário

Por exemplo, você pode usar a variável [!UICONTROL Correspondência de atributos de perfil] opção para criar uma regra que recomenda itens somente onde a marca é igual ao valor ou ao texto armazenado em `profile.favoritebrand`. Com essa regra, se um visitante estiver olhando para shorts de corrida de uma marca específica, apenas as recomendações exibirão a correspondência dessa marca favorita do usuário (o valor armazenado em `profile.favoritebrand` no perfil do visitante).

![Marca favorita](/help/main/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Combinação de empregos com candidatos a emprego

Suponha que você está tentando adequar os empregos aos candidatos a emprego. Você deseja recomendar somente trabalhos que estejam na mesma cidade do candidato a emprego.

Você pode usar regras de inclusão para corresponder a localização de um candidato a emprego do perfil do visitante a uma lista de tarefas, como no exemplo a seguir:

![Cidade do usuário](/help/main/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Recomendar itens com base no tamanho

Para obter um exemplo visual de como a correspondência de atributos de perfil afeta as recomendações, considere um site que vende fãs elétricos.

Quando um visitante clica em várias imagens de fãs neste site, cada página define o valor da variável `entity.size` com base no tamanho do ventilador na imagem ser pequeno ou grande.

Suponha que você tenha criado um script de perfil para rastrear e contar o número de vezes que o valor de `entity.size` é definida como pequena vs. grande.

Se o visitante retornar à Página inicial, ele verá recomendações filtradas com base no clique de mais fãs pequenos ou fãs grandes.

Recommendations baseado na exibição de mais fãs pequenos no site:

![recomendações para pequenos fãs](/help/main/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations baseado na exibição de fãs maiores no site:

![recomendações de grandes fãs](/help/main/c-recommendations/c-algorithms/assets/large-fans.png)
