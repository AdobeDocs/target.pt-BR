---
keywords: collection;Targeting
description: Uma coleção é um conjunto de produtos ou itens no Adobe Target que são qualificados para uma recomendação.
title: Coleções no Adobe Target
feature: entities
uuid: aa1afdcf-e51c-4e44-a229-3c21fc9d0514
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 99%

---


# ![PREMIUM](/help/assets/premium.png) Coleções {#collections}

Uma coleção é um conjunto de produtos ou itens que são qualificados para uma recomendação.

Normalmente, uma coleção é um conjunto de itens semelhantes ou relacionados, como uma coleção de um único produto. No entanto, você pode agrupar qualquer item em uma categoria que faça sentido para o seu negócio, como produtos em uma determinada faixa de preço ou cor, ou itens que possam ser interessantes em uma área geográfica específica.

Use as coleções para organizar seus produtos em caixas lógicas. Por exemplo, se alguns itens estão disponíveis em uma região, mas não em outra, você pode criar uma coleção que exclui os itens que não estão disponíveis na região do visitante. Você também pode usar as coleções para organizar os itens sazonais ou quaisquer outros parâmetros de organização que se aplicam ao seu negócio.

As [recomendações de backup](/help/c-recommendations/c-algorithms/backup-recs.md) geradas para cada critério dentro da recomendação também usam essa coleção, para que sejam incluídos na recomendação de backup apenas os itens na coleção. Com as coleções, você pode garantir que apenas os produtos que fazem sentido serão exibidos em um local.

As coleções são recriadas ou atualizadas cada vez que o critério for executado.

Você pode agrupar os produtos em catálogos, em seguida, criar recomendações separadas para cada coleção.

Os critérios de inclusão permitem que você realize ações semelhantes a uma coleção, mas devem ser configurados cada vez que uma atividade for criada. As coleções permitem a criação de um conjunto de itens de uma só vez. Depois disso, é possível usá-lo sempre que for apropriado, sem a necessidade de configurá-lo novamente.

Quando você está criando ou editando uma atividade do [!DNL Recommendations], o nome da coleção aparece ao lado da etiqueta de [!UICONTROL Critérios] no diagrama da atividade.

>[!NOTE]
>
>As coleções não são aplicadas quando você usa a chave de recomendação [!UICONTROL Itens recentemente visualizados].

## Crie uma coleta {#task_1256DFF6842141FCAADD9E1428EF7F08}

Crie uma coleta para organizar os produtos que deseja mostrar nas recomendações.

1.  Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Coleções]** para exibir a lista de coleções existentes. 

   ![Lista de coleções](assets/collections_list.png)

   O “Número de itens” relatado para cada coleção na exibição de lista das [!UICONTROL Coleções] é o número de produtos que correspondem às regras da coleção no [grupo de hosts](/help/administrating-target/hosts.md) (ambiente) padrão configurado no Recommendations. Consulte [Configurações](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) para alterar o grupo de hosts padrão.

1. Clique em **[!UICONTROL Criar coleção]**.

1. (Condicional) Escolha um ambiente no filtro **[!UICONTROL Ambiente]** ao criar (ou atualizar) uma coleção para visualizar o conteúdo da coleção no ambiente. Por padrão, os resultados do grupo de hosts padrão são exibidos.

   ![Criar coleção](/help/c-recommendations/c-products/assets/CreateCollection.png)

1. Digite um **[!UICONTROL Nome]** para a coleção.

   Você também pode inserir uma **[!UICONTROL Descrição opcional]**.

1. Defina as regras usadas para criar a coleção.

   Por exemplo, sua coleção pode ser criada em torno de uma ID de produto ou categoria, margem ou qualquer outro parâmetro na lista.

   Você pode adicionar regras para usar vários parâmetros para definir uma coleção. Várias regras são unidas por um E. Todas as regras especificadas devem ser iguais para que a coleção seja aplicada.

1. Clique em **[!UICONTROL Salvar]**.

## Criar uma coleção usando a Pesquisa avançada

Você também pode criar coleções usando a Pesquisa avançada na página [Pesquisa no catálogo](/help/c-recommendations/c-products/catalog-search.md) ([!UICONTROL Recommendations] > [!UICONTROL Pesquisa no catálogo] > [!UICONTROL Pesquisa avançada]).

![Caixa de diálogo Salvar como](/help/c-recommendations/c-products/assets/save-as-dialog.png)

Após criar uma pesquisa usando &quot;id > contains&quot; por exemplo, você pode clicar em [!UICONTROL Salvar como] > [!UICONTROL Coleção].

>[!IMPORTANT]
>
>A funcionalidade de Pesquisa avançada não faz distinção entre maiúsculas e minúsculas; contudo, os produtos devolvidos no momento da entrega baseiam-se na pesquisa sensível a maiúsculas e minúsculas. Essa não correspondência pode levar à confusão. Certifique-se de considerar a sensibilidade a maiúsculas e minúsculas quando você cria coleções baseadas em resultados usando a funcionalidade Pesquisa avançada. Por exemplo, se você realiza uma busca para &quot;Feriado&quot;, essa busca inicial lista os resultados contendo &quot;Feriado&quot; e &quot;feriado&quot;. Em seguida, se você criar um catálogo com a intenção de encontrar produtos contendo &quot;feriado&quot;, somente os produtos contendo &quot;feriado&quot; serão exibidos. Os produtos contendo &quot;Feriado&quot; não serão exibidos.

## Vídeo de treinamento: criar coleções e exclusões no Recommendations (7:05) ![Crachá do tutorial](/help/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar uma coleção
* Criar uma exclusão

>[!VIDEO](https://video.tv.adobe.com/v/27689)