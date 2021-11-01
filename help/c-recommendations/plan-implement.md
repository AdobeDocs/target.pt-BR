---
keywords: Recommendations, configurações, preferências, vertical do setor, critérios incompatíveis com o filtro, grupo de hosts padrão, url de base em miniatura, token de api do recommendations
description: 'Saiba como implementar atividades do Recommendations no Adobe Target. '
title: Como Implementar As Atividades Do Recommendations?
feature: Recommendations
exl-id: b6edb504-a8b6-4379-99c1-6907e71601f9
source-git-commit: cc260620cf87feebcd4c43f45f05406ac845cf5b
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 36%

---

# ![PREMIUM](/help/assets/premium.png) Planejar e implementar [!DNL Recommendations]

Antes de configurar o seu [!DNL Recommendations] atividade em [!DNL Adobe Target], execute as seguintes etapas:

1. [Implementar [!DNL Target]](#implement-target) nas superfícies do aplicativo móvel e da Web que você deseja usar para capturar o comportamento do usuário e fornecer recomendações.
1. [Configure seu [!DNL Recommendations] catálogo](#rec-catalog) de produtos ou conteúdo que deseja recomendar aos usuários.
1. [Envio de informações e contexto comportamentais](#pass-behavioral) para [!DNL Target Recommendations] para permitir que forneça recomendações personalizadas.
1. [Configurar exclusões globais](#exclusions).
1. [Configurar [!DNL Recommendations] configurações](#concept_C1E1E2351413468692D6C21145EF0B84).

## Implementação [!DNL Target] {#implement-target}

[!DNL Target Recommendations] exige que você implemente a variável [!DNL Adobe Experience Platform Web SDK] ou at.js 0.9.2 (ou posterior). Consulte [Implementar [!DNL Target]](/help/c-implementing-target/implementing-target.md) para obter mais informações.

## Configurar o catálogo do Recommendations {#rec-catalog}

Para fornecer recomendações de alta qualidade, [!DNL Target] O deve conhecer os produtos ou conteúdo que deseja recomendar. Geralmente, seu catálogo deve incluir três tipos de informações sobre os itens que deseja recomendar. Suponha que você esteja recomendando filmes. Inclua o seguinte:

1. Os dados que você deseja exibir para o usuário que recebe a recomendação. Por exemplo, você pode exibir o nome do filme e um URL para uma imagem em miniatura do pôster do filme.
1. Dados úteis para aplicar controles de marketing e merchandising. Por exemplo, você pode exibir a classificação do filme para não recomendar filmes NC-17.
1. Dados úteis para determinar a similaridade dos itens com outros itens. Por exemplo, você pode exibir o gênero do filme e o diretor do filme.

[!DNL Target] O oferece várias opções de integração para preencher o catálogo. Essas opções podem ser usadas em combinação para atualizar itens diferentes no catálogo ou para atualizar atributos de item diferentes em frequências diferentes.

| Método | O que é | Quando usar | Informações adicionais |
| --- | --- | --- | --- |
| Feed do catálogo | Agendar um feed (CSV, Google Product XML ou [!DNL Analytics Product Classifications]) a serem carregados e assimilados diariamente. | Para enviar informações sobre vários itens de cada vez. Para enviar informações que mudam com pouca frequência. | Consulte [Feeds](/help/c-recommendations/c-products/feeds.md). |
| API de entidades | Chame uma API para enviar atualizações por minuto para um único item. | Para enviar atualizações conforme elas ocorrem sobre um item de cada vez. Para enviar informações que mudam com frequência (por exemplo, preço, inventário/nível de estoque). | Consulte a [Documentação do desenvolvedor da API de entidades](https://developers.adobetarget.com/api/recommendations/#tag/Entities). |
| Enviar atualizações na página | Envie atualizações por minuto para um único item usando JavaScript na página ou usando a API de entrega. | Para enviar atualizações conforme elas ocorrem sobre um item de cada vez. Para enviar informações que mudam com frequência (por exemplo, preço, inventário/nível de estoque). | Consulte [Visualizações de item/páginas de produto](#items-product-pages) abaixo. |

A maioria dos clientes deve implementar pelo menos um feed. Em seguida, você pode optar por complementar seu feed com atualizações de atributos ou itens alterados com frequência usando a API de entidades ou o método na página.

## Envio de informações e contexto comportamentais {#pass-behavioral}

As informações comportamentais e o contexto que você deve transmitir para [!DNL Target] depende da ação que seu visitante está realizando, que geralmente está associada ao tipo de página com a qual seu visitante está interagindo.

### Visualizações de item/páginas de produto {#items-product-pages}

Nas páginas em que um visitante está visualizando um único item, como uma página de detalhes do produto, você deve transmitir a identidade do item que o visitante está visualizando. Você também deve passar a categoria mais granular do item que o visitante está visualizando, para permitir a filtragem de recomendações para a categoria atual.

Você também pode passar determinados atributos que mudam rapidamente na própria página do produto. Por exemplo, você pode passar o preço (`value`) e nível de inventário/estoque.

```
<script type="text/javascript">
function targetPageParams() { 
   return { 
      "entity": { 
         "id": "32323", 
         "categoryId": "running-shoes", 
         "value": 119.99, 
         "inventory": 329 
      } 
   } 
}
</script>
```

### Exibições de categoria/páginas de categoria

Em uma página de categoria, você provavelmente vai querer restringir suas recomendações a produtos ou conteúdo dentro dessa categoria. Para fazer isso, certifique-se de transmitir a identidade da categoria exibida no momento.

```
function targetPageParams() { 
   return { 
      "entity": { 
         "categoryId": "running-shoes" 
      } 
   } 
}
```

### Adiciona/visualizações do carrinho/páginas de check-out {#cart}

Em uma página de carrinho, você pode recomendar itens com base no conteúdo do carrinho atual do visitante. Para fazer isso, passe as IDs de todos os itens no carrinho atual do visitante usando o parâmetro especial `cartIds`.

```
function targetPageParams() {
   return {
      "cartIds": ["352", "223", "23432", "432", "553"]
      }
}
```

Para obter mais informações sobre [!UICONTROL Baseado em carrinho] recomendações, consulte [Baseado em carrinho](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) em *Basear a recomendação em uma chave de recomendação*.

### Excluir itens já no carrinho do visitante

Em páginas em todo o site, você pode excluir alguns itens das recomendações. Por exemplo, talvez você não queira recomendar itens que já estão no carrinho atual do visitante. Para fazer isso, passe as IDs de todos os itens que deseja excluir usando o parâmetro especial `excludedIds`.

```
function targetPageParams() {
   return {
      "excludedIds": ["352", "223", "23432", "432", "553"]
      }
}
```

### Páginas de confirmação de compras/pedidos

Quando um evento de compra ocorrer, passe a identidade do item ou itens comprados. Consulte [Rastrear conversões](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053) em *Implementar [!DNL Target] sem um gerenciador de tags*.

## Configurar exclusões globais {#exclusions}

Exclua qualquer item em um nível global que você nunca deseja recomendar a um visitante. Consulte [Exclusões](/help/c-recommendations/c-products/exclusions.md).

## Configurar [!DNL Recommendations] configurações {#concept_C1E1E2351413468692D6C21145EF0B84}

Use as configurações para gerenciar a sua implementação do [!DNL Recommendations].

Para acessar o [!UICONTROL Configurações do Recommendations] opções, abrir [!DNL Target] no [!DNL Adobe Experience Cloud], depois clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Configurações]**.

![](assets/recs_settings.png)

As opções disponíveis são as seguintes:

| Configuração | Descrição |
|--- |--- |
| Mbox global personalizada | (Opcional) especifique a mbox personalizada global usada para atender às atividades do [!DNL Target]. Por padrão, a mbox global usada por [!DNL Target] é usado para [!DNL Recommendations].<br>Observação: Essa opção é definida no [!DNL Target] [!UICONTROL Administração] página. Abrir [!DNL Target], depois clique em [!UICONTROL Administração] > [!UICONTROL Visual Experience Composer]. |
| Vertical do setor | O vertical do setor é usado para ajudar a categorizar os critérios de recomendação. Essas informações ajudam os membros de sua equipe a encontrar critérios que façam sentido para uma página específica, como critérios que são melhores para a página do carrinho de compras ou para uma página de mídia. |
| Filtrar critérios incompatíveis | Ative essa opção para mostrar apenas os critérios pelos quais a página selecionada passa os dados solicitados. Nem todos os critérios são executados corretamente em cada página. A página ou a mbox devem ser enviadas `entity.id` ou `entity.categoryId` para as recomendações do item atual/categoria atual serem compatíveis. Em geral, é melhor mostrar apenas critérios compatíveis. No entanto, se você desejar que critérios incompatíveis estejam disponíveis para a atividade, desmarque essa opção.<br>É recomendável desativar esta opção se estiver usando uma solução de gerenciamento de tags.<br>Para obter mais informações sobre essa opção, consulte [Perguntas frequentes do Recommendations](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md). |
| Grupo de host padrão | Selecione o seu grupo de hosts padrão.<br>O grupo de hosts pode ser usado para separar os itens disponíveis no catálogo para diferentes usos. Por exemplo, você pode usar grupos de hosts para os ambientes de Desenvolvimento e Produção, para diferentes marcas ou diferentes regiões. Por padrão, os resultados de visualização na Pesquisa no catálogo, nas Coleções e nas Exclusões estão baseados no grupo de hosts padrão. (Também é possível selecionar um grupo de hosts diferente para visualizar os resultados, usando o filtro Ambiente.) Por padrão, os itens recém adicionados ficam disponíveis em todos os grupos de hosts, a menos que uma ID de ambiente seja especificada ao criar ou atualizar o item. As recomendações entregues dependem do grupo de hosts especificado na solicitação.<br>Se você não visualiza seus produtos, certifique-se de que você esteja usando o grupo correto de hosts. Por exemplo, se você configurar sua recomendação para usar um ambiente de preparo e você definir o grupo de hosts para Armazenamento temporário, você pode necessitar recriar suas coleções no ambiente de preparo para serem mostradas pelos produtos. Para ver quais produtos estão disponíveis em cada ambiente, use a Pesquisa de catálogo com cada ambiente. Você também pode visualizar o conteúdo das coleções e exclusões do Recommendations para um ambiente selecionado (grupo de hosts).<br>**Observação:** depois de alterar o ambiente selecionado, você deve clicar em Pesquisar para atualizar os resultados retornados.<br>O filtro de [!UICONTROL Ambiente] está disponível nos seguintes locais na interface do usuário do [!DNL Target]:<ul><li>Pesquisa do catálogo (Recommendations> Pesquisa do catálogo)</li><li>Caixa de diálogo Criar coleção ([!UICONTROL Recommendations> Coleções > Criar nova])</li><li>Caixa de diálogo Atualizar coleção ([!UICONTROL Recommendations > Coleções > Editar])</li><li>Caixa de diálogo Criar exclusão ([!UICONTROL Recommendations > Exclusões > Criar novo])</li><li>Caixa de diálogo Atualizar exclusão ([!UICONTROL Recommendations > Exclusões > Editar])</li></ul>Para obter mais informações, consulte [Hosts](/help/administrating-target/hosts.md). |
| URL de base de miniatura | Definir um URL base para o seu catálogo de produtos possibilita o uso de URLs relativos ao especificar miniaturas dos produtos ao enviar no seu URL em miniatura.<br>Por exemplo:<br>`"entity.thumbnailURL=/Images/Homepage/product1.jpg"`<br>define um URL relativo ao URL de base de miniatura. |
| Token de API do Recommendations | Use esse token em chamadas de API do Recommendations, como Baixar API. |
