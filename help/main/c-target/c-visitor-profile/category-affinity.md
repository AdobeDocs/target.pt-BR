---
keywords: afinidade, afinidade de categorias
description: Saiba mais sobre a afinidade de categorias no  [!DNL Adobe Target]  que captura automaticamente as categorias visitadas por um usuário e calcula a afinidade de categoria do usuário para que possa ser direcionado e segmentado.
title: O Que É Afinidade De Categorias?
feature: Audiences
exl-id: 9478a7fb-e4b5-46d9-be73-b72cb99c3e5e
source-git-commit: 80481a149d436f13bd510c4c4287d447799afbb4
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 56%

---

# Afinidade de categorias

O recurso de afinidade de categorias no [!DNL Adobe Target] captura automaticamente as categorias no site que um usuário visita e calcula a afinidade de cada categoria do usuário para que possa ser direcionado e segmentado. A afinidade de categorias ajuda a garantir que o conteúdo seja direcionado para visitantes com maior probabilidade de agir de acordo com essas informações.

## Transmitindo informações de afinidade de categoria para [!DNL Target] {#section_B0C8E46EEBAC4549AD90352A47787D04}

Sempre que um usuário visitar o site, parâmetros do perfil específicos do visitante serão gravados no banco de dados do [!DNL Target]. Os dados são vinculados ao cookie do usuário. Um parâmetro útil é `user.categoryId`, um parâmetro de mbox atribuído em uma página de produto. Conforme o visitante continua a navegação, ou retorna para outra sessão, as categorias de produtos que um usuário específico visualiza podem ser registradas. Você também pode registrar informações de categoria passando-as como parâmetro de mbox `user.categoryId` em qualquer mbox (incluindo uma mbox aninhada), como um parâmetro de URL `user.categoryId`, ou em parâmetros de página [!DNL Target] com uma mbox global. Consulte seu representante de conta para obter mais detalhes.

Separe as categorias com uma vírgula para incluir um item em várias categorias. Por exemplo:

* `user.categoryId=clothing,shoes,nike,running,nike clothing,nike shoes,nike running shoes`

Com base na frequência e recenticidade das visitas às categorias de seu produto, a afinidade de categoria (se houver) de um usuário será registrada. A Afinidade de categorias pode ser utilizada para definir populações para as suas atividades.

Você pode usar `user.categoryAffinities[]` em um script de perfil para retornar uma matriz das afinidades que um visitante preencheu. Para obter mais informações, consulte [user.categoryAffinities em Objetos e métodos nos atributos de perfil](/help/main/c-target/c-visitor-profile/profile-parameters.md#objects).

>[!IMPORTANT]
>
>O atributo `user.categoryId` usado para o algoritmo de afinidade de categorias é diferente do atributo `entity.categoryId` usado nas recomendações de produto e conteúdo de [!DNL Adobe Target Recommendations]. O `user.categoryId` é necessário rastrear a categoria favorita de um usuário. O `entity.categoryId` é necessário para basear as recomendações na categoria da página ou do item atual. Passe ambos os valores para [!DNL Target] se quiser usar ambos os recursos.

## Caso de negócios para afinidade de categoria {#section_D6FF913E88E6486B8FBCE117CA8B253B}

A atividade de um visitante em uma sessão, como a categoria que ele visualiza com mais frequência, pode ser usada para direcionamento em visitas subsequentes. Cada página de categoria visualizada por um visitante durante uma sessão é capturada e a categoria &quot;favorita&quot; dele ou dela será calculada com base no recenticidade e modelo de frequência. Desta forma, cada vez que o visitante volta para a página inicial, a área da imagem principal pode ser direcionada para exibir conteúdo relacionado à categoria favorita daquele usuário.

## Exemplo de uso de afinidade de categorias {#section_A4AC0CA550924CB4875F4F4047554C18}

Suponha que você venda instrumentos musicais online e queira direcionar as promoções de vendas de baixos para visitantes que já tenham expressado interesse em instrumentos no passado. Utilizando a afinidade de categorias, você pode criar ofertas que sejam exibidas somente para os visitantes que tenham essa afinidade de categorias.

## Algoritmo de afinidade de categorias {#section_8B86C7FF50294208866ABF16F07D5EB9}

O algoritmo de afinidade de categoria funciona da seguinte maneira:

* Dez pontos para primeira visualização de categoria
* Cinco pontos para cada categoria clicada após a primeira
* Quando uma nova categoria é clicada, 1 é subtraído de todas as categorias clicadas anteriormente
* Se uma categoria já tiver sido clicada (vista), clicar novamente nela não subtrai 1 de todas as outras categorias
* Se uma sexta nova categoria for clicada, a categoria com menor pontuação entre as primeiras cinco será removida do cálculo
* No fim da sessão, divida todos os valores por 2

>[!NOTE]
>
>Quando várias categorias são passadas em uma única chamada de mbox, a ordem das categorias em `categoryAffinities` não é garantida. Uma categoria arbitrária é registrada primeiro e recebe uma pontuação de 10.

### Exemplo: algoritmo de afinidade de categoria

Por exemplo, visualizar a categoria `mens-clothing`, em seguida, `accessories`, `jewelry`, e `accessories` novamente em uma sessão resulta em afinidades de:

* `accessories`: 9 (+5 – 1 + 5)

* `mens-clothing`: 8 (+10 – 1 – 1)

* `jewelry`: 5 (+5)

Quando a sessão for encerrada e o usuário voltar posteriormente para o site, as pontuações serão reduzidas:

* `accessories`: 4,5 (9/2)

* `mens-clothing`: 4 (8/2)

* `jewelry`: 2,5 (5/2)

Considerando que o usuário então visualize, em ordem `jewelry`, `accessories`, `beauty`, `shoes` e `womens-clothing`:

* `accessories`: 6,5 (4.5 + 5 – 1 – 1 - 1)

* `womens-clothing`: 5 (+5)

* `jewelry`: 4,5 (2,5 + 5 – 1 – 1 - 1)

* `shoes`: 4 (+5 – 1)

* `beauty`: 3 (+5 – 1 - 1)

* `mens-clothing` é descartada depois do clique final de `womens-clothing`, como a categoria de pontuação mais baixa com uma pontuação de 1 (4 – 1 – 1 - 1)

Quando a sessão for encerrada e o usuário voltar posteriormente para o site, as pontuações serão reduzidas:

* `accessories`: 3,3 (6,5/2)

* `womens-clothing`: 2,5 (5/2)

* `jewelry`: 2,3 (4,5/2)

* `shoes`: 2 (4/2)

* `beauty`: 1,5 (3/2)

## Usar afinidade de categorias para direcionamento {#concept_5750C9E6C97A40F8B062A5C16F2B5FFC}

As seções a seguir contêm informações para ajudar você a usar um público-alvo de afinidade de categorias para o direcionamento em uma atividade.

### Criar um público-alvo para usar a afinidade de categorias {#section_A27C600BBA664FE7A74F8FE076B78F40}

1. Na lista **[!UICONTROL Audiences]**, clique em **[!UICONTROL Create Audience]**.

   Ou

   Para copiar um público-alvo existente, na lista de Públicos-alvo, passe com o mouse sobre o público-alvo desejado e clique no ícone Copiar. Você pode editar o público-alvo para criar um público-alvo semelhante.

1. Digite um nome de público-alvo descritivo.
1. Clique em **[!UICONTROL + Add Rule]** > **[!UICONTROL Visitor Profile]**.
1. Na lista suspensa **[!UICONTROL Visitor Profile]**, selecione **[!UICONTROL Category Affinity]**.

   ![Perfil do visitante > Afinidade de categorias](assets/affinity.png)

1. Selecione a categoria desejada:

   ![Afinidade de categorias > Categoria](assets/affinity-category.png)

   As categorias incluem:

   * Categoria favorita
   * Primeira categoria
   * Segunda categoria
   * Terceira categoria
   * Quarta categoria
   * Quinta categoria

   As opções &quot;Categoria favorita&quot; e &quot;Primeira categoria&quot; são equivalentes.

1. Escolha o avaliador:

   * Contém (não diferencia maiúsculas de minúsculas)
   * Não contém (não diferencia maiúsculas de minúsculas)
   * Igual

1. Especifique cada novo valor em uma linha separada (por exemplo, &quot;sapatos&quot;).
1. Clique em **[!UICONTROL Save]**.

### Usar o público-alvo da afinidade de categorias em uma atividade {#section_91526B942D1B4AEBB8FCDF4EBFF931CF}

Você pode usar públicos-alvo de afinidade de categorias em qualquer atividade. Durante o fluxo de trabalho guiado de três etapas, na etapa [!UICONTROL Target], escolha o público-alvo desejado.
