---
keywords: regras de inclusão;critérios de inclusão;recomendações;promoção;promoções;filtragem dinâmica;vinculação de atributo dinâmico;perfil
description: Filtre dinamicamente no Adobe Target Recommendations comparando itens (entidades) com um valor no perfil do usuário.
title: Filtrar por correspondência de atributo de Perfil nas regras de inclusão dinâmica nas Recomendações de Público alvo v
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 7%

---


# ![Correspondência de atributos ](/help/assets/premium.png) PREMIUMProfile

Filtre dinamicamente em [!DNL Adobe Target] [!DNL Recommendations] comparando itens (entidades) com um valor no perfil do usuário.

Use [!UICONTROL Correspondência de atributos do Perfil] quando quiser mostrar recomendações que correspondem a um valor armazenado no perfil do visitante, como tamanho ou marca favorita.

>[!NOTE]
>
>O processo [para criar e usar regras de inclusão](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para critérios e promoções é semelhante, assim como os casos de uso e exemplos.

Os seguintes cenários mostram como você pode usar [!UICONTROL Correspondência de Atributo de Perfil]:

* Uma empresa que vende óculos armazena uma cor de quadro favorita dos visitantes como &quot;noz&quot;. Para esse visitante específico, as recomendações são configuradas para retornar apenas quadros de óculos que correspondem a &quot;noz&quot; em cores.
* Um parâmetro de perfil pode ser definido para o tamanho da roupa (por exemplo, Pequeno, Médio ou Grande) de um visitante à medida que eles navegam pelo site da empresa. Uma recomendação pode ser configurada para corresponder a esse parâmetro de perfil e retornar produtos específicos somente para o tamanho de vestuário preferencial do usuário.

## Exemplos de Correspondência de Atributo de perfil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL A ] Correspondência de atributos de perfil permite que você recomende somente os itens que correspondem a um atributo do perfil do visitante, como nos exemplos abaixo.

### Recomendar itens da marca favorita do usuário

Por exemplo, você pode usar a opção [!UICONTROL Correspondência de atributos do Perfil] para criar uma regra que recomenda itens somente quando a marca for igual ao valor ou texto armazenado em `profile.favoritebrand`. Com essa regra, se um visitante estiver olhando para shorts de corrida de uma marca específica, apenas as recomendações exibirão a correspondência dessa marca favorita do usuário (o valor armazenado em `profile.favoritebrand` no perfil do visitante).

![Marca favorita](/help/c-recommendations/c-algorithms/assets/favorite-brand.png)

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Correspondência de empregos a candidatos a emprego

Suponha que você esteja tentando combinar empregos com candidatos a emprego. Você deseja recomendar somente trabalhos que estejam na mesma cidade que o candidato a emprego.

Você pode usar as regras de inclusão para corresponder a localização de um visitante de trabalho de seu perfil a uma lista de trabalhos, como no exemplo a seguir:

![Cidade do usuário](/help/c-recommendations/c-algorithms/assets/city.png)

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

### Recomendar itens com base no tamanho

Para obter um exemplo visual de como a correspondência de atributos de perfil afeta as recomendações, considere um site que vende fãs elétricos.

Quando um visitante clica em várias imagens de fãs neste site, cada página define o valor do parâmetro `entity.size` com base no tamanho do ventilador na imagem que é pequeno ou grande.

Suponha que você criou um script de perfil para rastrear e contar o número de vezes que o valor de `entity.size` está definido como pequeno vs. grande.

Se o visitante retornar ao Home page, ele ou ela verá recomendações filtradas com base no clique em mais fãs pequenos ou fãs grandes.

Recommendations baseado na exibição de mais fãs pequenos no site:

![recomendações para pequenos ventiladores](/help/c-recommendations/c-algorithms/assets/small-fans.png)

Recommendations baseado na exibição de fãs maiores no site:

![recomendações para grandes ventiladores](/help/c-recommendations/c-algorithms/assets/large-fans.png)