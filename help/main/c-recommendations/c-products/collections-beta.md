---
keywords: coleção, direcionamento
description: Saiba como usar coleções de produtos ou itens no [!DNL Target Recommendations].
title: Como usar coleções em atividades do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: b6eaf89ef71ea3448584dcdadc926c45dba77504
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 29%

---

# Coleções

Uma coleção é um conjunto de produtos ou itens qualificados para uma recomendação. Uma coleção é definida especificando as condições que devem ser atendidas pelos itens para fazerem parte dela.

Normalmente, uma coleção é um conjunto de itens semelhantes ou relacionados, como uma coleção de um único produto. No entanto, você pode agrupar qualquer item em uma categoria que faça sentido para o seu negócio, como produtos em uma determinada faixa de preço ou cor ou itens que provavelmente serão interessantes em uma área geográfica específica.

Use as coleções para organizar seus produtos em caixas lógicas. Por exemplo, se alguns itens estiverem disponíveis em uma região, mas não em outra, você poderá criar uma coleção que exclui itens que não estão disponíveis na região do visitante. Você também pode usar as coleções para organizar os itens sazonais ou quaisquer outros parâmetros de organização que se aplicam ao seu negócio.

[Recomendações de backup](/help/main/c-recommendations/c-algorithms/backup-recs.md) gerado para cada critério dentro da recomendação também usa essa coleção, para que sejam incluídos na recomendação de backup apenas os itens na coleção. Com as coleções, você pode garantir que apenas os produtos que fazem sentido serão exibidos em um local.

As coleções são recriadas ou atualizadas cada vez que o critério for executado.

Você pode agrupar os produtos em catálogos, em seguida, criar recomendações separadas para cada coleção.

Os critérios de inclusão permitem que você realize ações semelhantes a uma coleção, mas devem ser configurados cada vez que uma atividade for criada. As coleções permitem criar um conjunto de itens uma vez e, em seguida, usá-lo sempre que apropriado, sem precisar configurá-lo novamente.

Ao criar ou editar um [!DNL Recommendations] atividade, o nome da coleção aparece ao lado da variável [!UICONTROL Criteria] no diagrama de atividades.

>[!NOTE]
>
>As coleções não são aplicadas ao usar o [!UICONTROL Recently Viewed Items] chave de recomendação.

## Crie uma coleção {#task_1256DFF6842141FCAADD9E1428EF7F08}

Crie uma coleção para organizar os produtos ou conteúdo que deseja mostrar em suas recomendações.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Collections]** para exibir a lista de coleções existentes.

   ![Lista de coleções](assets/collections-list.png)

   A variável [!UICONTROL Collections] exibe uma lista de suas coleções existentes. Crie novas coleções clicando no ícone [!UICONTROL Create Collection] botão. Também é possível editar, copiar e excluir coleções existentes clicando no ícone de reticências ao lado da coleção desejada e clicando na opção desejada.

   O &quot;Número de itens&quot; reportado para cada coleção no [!UICONTROL Collections] exibição de lista é o número de produtos que correspondem às regras da coleção no Recommendations padrão configurado [grupo de hosts](/help/main/administrating-target/hosts.md) (ambiente). Consulte [Configurações](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} para alterar o grupo de hosts padrão.

1. Clique em **[!UICONTROL Create Collection]**.

   ![Criar coleção](/help/main/c-recommendations/c-products/assets/create-collection.png)

1. Digite a **[!UICONTROL Name]** para a coleção.

   Você também pode inserir um **[!UICONTROL Description]**.

1. (Condicional) Escolha um [ambiente](/help/main/administrating-target/environments.md) do **[!UICONTROL Environment]** ao criar (ou atualizar) uma coleção para visualizar o conteúdo da coleção nesse ambiente. Por padrão, os resultados do grupo de hosts padrão são exibidos.

1. Defina as regras usadas para criar a coleção.

   Por exemplo, sua coleção pode ser criada em torno de uma ID de produto ou categoria, margem ou qualquer outro parâmetro na lista.

   Você pode adicionar regras para usar vários parâmetros para definir uma coleção. Várias regras são unidas com um operador AND. Todas as regras especificadas devem ser iguais para que a coleção seja aplicada.

1. Clique em **[!UICONTROL Create]**.

## Crie uma coleção usando [!UICONTROL Advanced Search]

Também é possível criar coleções usando [!UICONTROL Advanced Search] no [Pesquisa no catálogo](/help/main/c-recommendations/c-products/catalog-search.md#save-as) página ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Caixa de diálogo Salvar como](/help/main/c-recommendations/c-products/assets/save-as.png)

Após criar uma pesquisa usando &quot;id > contains&quot; Por exemplo, você pode clicar em [!UICONTROL Save As] > [!UICONTROL Collection].

>[!IMPORTANT]
>
>A variável [!UICONTROL Advanced Search] A funcionalidade não diferencia maiúsculas de minúsculas; no entanto, os produtos retornados no momento do delivery baseiam-se na pesquisa sensível a maiúsculas e minúsculas. Essa não correspondência pode levar à confusão. Considere a diferenciação entre maiúsculas e minúsculas ao criar coleções com base nos resultados usando o [!UICONTROL Advanced Search] funcionalidade. Por exemplo, se você realiza uma busca para &quot;Feriado&quot;, essa busca inicial lista os resultados contendo &quot;Feriado&quot; e &quot;feriado&quot;. Em seguida, se você criar um catálogo com a intenção de encontrar produtos contendo &quot;feriado&quot;, somente os produtos contendo &quot;feriado&quot; serão exibidos. Os produtos contendo &quot;Feriado&quot; não serão exibidos.

## Editar, copiar ou excluir uma coleção

Clique em **reticências** ícone ao lado da coleção desejada na lista, em seguida, clique no ícone apropriado: editar, copiar ou excluir.

![Ícones de flutuação: editar, copiar e excluir](/help/main/c-recommendations/c-products/assets/hover-icons-new.png)

Você pode copiar uma coleção existente para criar uma coleção duplicada que poderá ser modificada. Isso permite criar uma coleção semelhante com menos esforço.

Esteja ciente de que as coleções estão disponíveis em toda a conta. Considere isso antes de excluir uma coleção. As coleções excluídas não podem ser recuperadas.

## Usar uma coleção em uma [!DNL Recommendations] atividade

1. Crie uma coleção usando um dos métodos mencionados acima.

1. Clique em **[!UICONTROL Activities]** e [criar uma nova Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md) atividade ou edite uma atividade existente.

1. Depois de selecionar um critério e criar, a variável [!UICONTROL Options] é exibida onde você seleciona a coleção desejada.

   ![Escolher opção de coleção](/help/main/c-recommendations/c-products/assets/choose-collection.png)

1. (Condicional) Para alterar uma configuração de coleta existente, no campo **[!UICONTROL Experiences]** (etapa 2 do fluxo de trabalho guiado de três partes), clique em um local onde você fez as recomendações, clique em **[!UICONTROL Change Collection]** e selecione a coleção desejada.

   ![Opção Alterar coleção](/help/main/c-recommendations/c-products/assets/change-collection.png)

## Vídeo de treinamento: criar coleções e exclusões no Recommendations (7:05) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar uma coleção
* Criar uma exclusão

>[!VIDEO](https://video.tv.adobe.com/v/27689)