---
keywords: coleção, direcionamento
description: Saiba como usar coleções de produtos ou itens no [!DNL Target Recommendations].
title: Como usar coleções em atividades do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: e62f501b-3521-4456-9ea1-e4b8a2b478c6
source-git-commit: c8bd2bb45ee8ef1a849fd9091554caec77effba0
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 40%

---

# Coleções

Uma coleção é um conjunto de produtos ou itens qualificados para uma recomendação. Uma coleção é definida especificando as condições que devem ser atendidas pelos itens para fazerem parte dela.

Normalmente, uma coleção é um conjunto de itens semelhantes ou relacionados, como uma coleção de um único produto. No entanto, você pode agrupar qualquer item em uma categoria que faça sentido para o seu negócio, como produtos em uma determinada faixa de preço ou cor ou itens que provavelmente serão interessantes em uma área geográfica específica.

Use as coleções para organizar seus produtos em caixas lógicas. Por exemplo, se alguns itens estiverem disponíveis em uma região, mas não em outra, você poderá criar uma coleção que exclui itens que não estão disponíveis na região do visitante. Você também pode usar as coleções para organizar os itens sazonais ou quaisquer outros parâmetros de organização que se aplicam ao seu negócio.

As [recomendações de backup](/help/main/c-recommendations/c-algorithms/backup-recs.md) geradas para cada critério dentro da recomendação também usam essa coleção, para que sejam incluídos na recomendação de backup apenas os itens na coleção. Com as coleções, você pode garantir que apenas os produtos que fazem sentido serão exibidos em um local.

As coleções são recriadas ou atualizadas cada vez que o critério for executado.

Você pode agrupar os produtos em catálogos, em seguida, criar recomendações separadas para cada coleção.

Os critérios de inclusão permitem que você realize ações semelhantes a uma coleção, mas devem ser configurados cada vez que uma atividade for criada. As coleções permitem a criação de um conjunto de itens de uma só vez. Depois disso, é possível usá-lo sempre que for apropriado, sem a necessidade de configurá-lo novamente.

Quando você está criando ou editando uma atividade do [!DNL Recommendations], o nome da coleção aparece ao lado do rótulo [!UICONTROL Criteria] no diagrama da atividade.

>[!NOTE]
>
>As coleções não são aplicadas quando você usa a chave de recomendação [!UICONTROL Recently Viewed Items].

## Crie uma coleção {#task_1256DFF6842141FCAADD9E1428EF7F08}

Crie uma coleção para organizar os produtos ou conteúdo que deseja mostrar em suas recomendações.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** para exibir a lista de coleções existentes.

   ![Lista de coleções](assets/collections_list.png)

   A página [!UICONTROL Collections] exibe uma lista de suas coleções existentes. Crie novas coleções clicando no botão [!UICONTROL Create Collection]. Também é possível editar, copiar e excluir coleções existentes, passando o mouse sobre a coleção desejada e clicando no ícone desejado.

   ![Ícones de flutuação: editar, copiar e excluir](/help/main/c-recommendations/c-products/assets/hover-icons.png)

   O &quot;Número de Itens&quot; relatado para cada coleção na exibição de lista [!UICONTROL Collections] é o número de produtos que correspondem às regras da coleção no [grupo de hosts](/help/main/administrating-target/hosts.md) (ambiente) padrão configurado no Recommendations. Consulte [Configurações](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} para alterar o grupo de hosts padrão.

1. Clique em **[!UICONTROL Create Collection]**.

1. (Condicional) Escolha um ambiente no filtro **[!UICONTROL Environment]** ao criar (ou atualizar) uma coleção para visualizar o conteúdo da coleção no ambiente. Por padrão, os resultados do grupo de hosts padrão são exibidos.

   ![Criar coleção](/help/main/c-recommendations/c-products/assets/CreateCollection.png)

1. Digite um **[!UICONTROL Name]** para a coleção.

   Você também pode inserir um **[!UICONTROL Description]** opcional.

1. Defina as regras usadas para criar a coleção.

   Por exemplo, sua coleção pode ser criada em torno de uma ID de produto ou categoria, margem ou qualquer outro parâmetro na lista.

   Você pode adicionar regras para usar vários parâmetros para definir uma coleção. Várias regras são unidas com um operador AND. Todas as regras especificadas devem ser iguais para que a coleção seja aplicada.

1. Clique em **[!UICONTROL Save]**.

## Criar uma coleção usando a Pesquisa avançada

Você também pode criar coleções usando a Pesquisa Avançada na página [Pesquisa no Catálogo](/help/main/c-recommendations/c-products/catalog-search.md#save-as) ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Salvar como caixa de diálogo](/help/main/c-recommendations/c-products/assets/save-as.png)

Após criar uma pesquisa usando &quot;id > contains&quot; Por exemplo, você pode clicar em [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>A funcionalidade de Pesquisa avançada não faz distinção entre maiúsculas e minúsculas; contudo, os produtos devolvidos no momento da entrega baseiam-se na pesquisa sensível a maiúsculas e minúsculas. Essa não correspondência pode levar à confusão. Certifique-se de considerar a sensibilidade a maiúsculas e minúsculas quando você cria coleções baseadas em resultados usando a funcionalidade Pesquisa avançada. Por exemplo, se você realiza uma busca para &quot;Feriado&quot;, essa busca inicial lista os resultados contendo &quot;Feriado&quot; e &quot;feriado&quot;. Em seguida, se você criar um catálogo com a intenção de encontrar produtos contendo &quot;feriado&quot;, somente os produtos contendo &quot;feriado&quot; serão exibidos. Os produtos contendo &quot;Feriado&quot; não serão exibidos.

## Editar, copiar ou excluir uma coleção

Passe o mouse sobre a coleção desejada na lista, em seguida, clique no ícone apropriado: editar, copiar ou excluir.

![Focalizar ícones para uma coleção](/help/main/c-recommendations/c-products/assets/hover-collections.png)

Você pode copiar uma coleção existente para criar uma coleção duplicada que poderá ser modificada. Isso permite criar uma exclusão semelhante com menos esforço.

Esteja ciente de que as coleções estão disponíveis em toda a conta. Considere isso antes de excluir uma coleção. As coleções excluídas não podem ser recuperadas.

## Usar uma coleção em uma atividade do Recommendations

1. Crie uma coleção usando um dos métodos mencionados acima.

1. Clique em **[!UICONTROL Activities]** e [criar uma nova atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) ou editar uma atividade existente.

1. Após selecionar um critério e um design, a página [!UICONTROL Options] é exibida onde você seleciona a coleção desejada.

   ![Escolher opção de coleção](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. (Condicional) Para alterar uma configuração de coleção existente, na página **[!UICONTROL Experiences]** (etapa 2 do fluxo de trabalho guiado de três etapas), clique em um local onde você inseriu as recomendações, clique em **[!UICONTROL Change Collection]** e selecione a coleção desejada.

   ![Alterar opção de Coleção](/help/main/c-recommendations/c-products/assets/change-collection.png)

## Vídeo de treinamento: criar coleções e exclusões no Recommendations (7:05) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar uma coleção
* Criar uma exclusão

>[!VIDEO](https://video.tv.adobe.com/v/27689)
