---
keywords: recomendações, perguntas frequentes, faq
description: Revise uma lista de perguntas frequentes e suas respostas sobre os designs do Adobe [!DNL Target] Recommendations.
title: Onde posso responder perguntas sobre design para [!DNL Target] Recommendations?
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 85%

---

# ![PREMIUM](/help/assets/premium.png) Perguntas frequentes sobre o design

Lista de perguntas frequentes sobre os designs de recomendações do [!DNL Adobe Target].

## O preço do item recomendado não exibe os dois valores à direita da casa decimal. Como posso exibi-los?

Por padrão, os valores numéricos (como `entity.value`) retornados nos modelos de design não exibem zeros à direita após a casa decimal. Por exemplo, se um item for de $35,00, `entity.value` será igual a 35 e a página exibirá apenas 35 e não $35,00.

Duas opções estão disponíveis para resolver esse problema:

* É possível usar o script do Velocity ou Javascript para aplicar a formatação ao valor retornado.

* Você pode passar o preço do item em dois atributos de entidade separados. O primeiro, `entity.value`, pode ser usado para comparações numéricas (como regras de comparação de preço). O segundo deve ser um atributo personalizado, como `entity.displayValue`, que armazena o valor da entidade como uma string para permitir a renderização correta.

   Por exemplo,

   `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

## Por que a categoria não está sendo exibida no design? Eu estou usando $entity1.categoryId. {#section_073309B8051049C7953D396A93EA0713}

A ID da categoria não pode ser exibida no design. Como várias categorias podem ser armazenadas, o sistema não saberia qual categoria exibir.

## Como devo mudar um design para obter uma atualização instantânea?   {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

A alteração do design que está atualmente em uso leva um tempo para atualizar. Para alterar o design instantaneamente, crie um novo design, selecione-o na atividade e salve a recomendação.

## Como posso capturar as principais informações para exibir no design? Exemplo: se desejarmos exibir a principal categoria do produto, como codificamos esse valor no design da velocidade?   {#section_F08043B14BA24BC8815FEF25F4F84C39}

O parâmetro `$key. *`value`*` captura a maioria das informações do produto para exibir dentro do design. Por exemplo: se você deseja exibir a miniatura dos principais produtos, use `$key.thumbnailURL`.

## Qual versão do Velocity é utilizada? {#section_28F00E15A4A54A768782A3F5BB0CDB21}

A versão 1.7 sem ferramentas adicionais ou bibliotecas incorporadas. O recurso Basic Velocity está disponível.

## O que devo fazer para deixar um valor de entidade existente em branco? Por exemplo: a entity.message de um item precisa ser limpa quando uma promoção termina. {#section_B88F2C2925DC4508974B2F8B13F961CB}

Enviar um espaço sem quebra do JavaScript parece ser suficiente. Peça que os desenvolvedores enviem `\u00A0` como o valor. Exemplo: `entity.message=\u00A0`. Você pode considerar esse como sendo o valor padrão, ao invés de um valor nulo, quando nenhum valor estiver presente.

## Posso usar um script de perfil em um design de recomendações? {#section_6BD55203984A4D80A0C6F241AD7806DF}

Sim. No entanto, você deve adicionar uma barra invertida (\) antes do $ no nome do script de perfil.
