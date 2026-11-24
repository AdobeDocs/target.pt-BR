---
keywords: recomendações;perguntas frequentes;faq
description: Perguntas frequentes e suas respostas sobre [!DNL Target Recommendations] designs.
title: Perguntas e respostas sobre design
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
TQID: 'https://experienceleague.adobe.com/xRu0XEnc8wX8PZngba7CO67mFdja7HALL-1OSnhAmuY'
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
source-git-commit: d5030abcda38bbc6d33b88ce3bb5d64f69e4e492
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 19%
---
# Perguntas e respostas sobre design {#design-faq}

>[!BEGINSHADEBOX]

**Nesta página:** encontre respostas para perguntas frequentes sobre [!DNL Adobe Target] [!DNL Recommendations] designs.

>[!ENDSHADEBOX]

+++ Como o preço de um item recomendado pode exibir ambos os dígitos à direita da casa decimal?

Por padrão, os valores numéricos (como `entity.value`) retornados em designs não exibem zeros à direita após a casa decimal. Por exemplo, se um item custa USD$ 35,00, `entity.value` é igual a 35 e a página exibirá apenas 35 e não USD$ 35,00.

Duas opções estão disponíveis para resolver esse problema:

* O script do Velocity ou JavaScript pode aplicar formatação ao valor retornado.

* O preço do item pode ser passado para dois atributos de entidade separados. O primeiro, `entity.value`, pode ser usado para comparações numéricas (como regras de comparação de preço). O segundo deve ser um atributo personalizado, como `entity.displayValue`, que armazena o valor da entidade como uma cadeia de caracteres para permitir a renderização correta.

  Por exemplo,

  `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

+++

+++ Por que a categoria não é exibida no design quando $entity1.categoryId é usada?

A ID da categoria não pode ser exibida em um design. Várias categorias podem ser armazenadas, de modo que o sistema não sabe qual categoria exibir.

+++

+++ Como um design pode ser alterado para obter uma atualização instantânea?

A alteração do design que está atualmente em uso leva um tempo para atualizar. Para alterar o design instantaneamente, crie um novo design, selecione-o na atividade e salve a recomendação.

+++

+++ Como as principais informações, como a categoria do produto principal, podem ser exibidas em um design do?

Os parâmetros `$key` capturam a maioria das informações do produto principal para exibição dentro do design. Por exemplo, para exibir a miniatura do produto principal, use `$key.thumbnailURL`.

+++

+++ Qual versão do Velocity é utilizada?

Versão 1.7, sem ferramentas ou bibliotecas adicionais. O recurso Basic Velocity está disponível.

+++

+++ Como um valor de entidade existente pode ser substituído por um em branco, por exemplo, quando entity.message de um item deve ser limpo no final de uma promoção?

Enviar um espaço sem quebra do JavaScript parece permitir. Os desenvolvedores enviam `\u00A0` como valor, por exemplo `entity.message=\u00A0`. Também pode ser considerado usar esse valor como o padrão quando nenhum valor estiver presente, em vez de um nulo.

+++

+++ Um script de perfil pode ser usado em um design de [!DNL Recommendations]?

Sim. Para usar um script de perfil em um design do [!DNL Recommendations], insira `\${...}` ao redor do nome. Por exemplo, se o script de perfil for nomeado como `user.basket`, utilize-o como `\${user.basket}` no design. A barra invertida implica que o script de perfil não é renderizado pelo Velocity, portanto, nenhuma operação pode ser executada no script de perfil em um modelo do Velocity. O valor é impresso diretamente na página.

+++
