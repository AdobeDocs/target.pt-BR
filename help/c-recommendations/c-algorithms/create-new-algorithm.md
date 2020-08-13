---
description: Critérios controlam o conteúdo de suas atividades do Adobe Recommendations. Crie critérios para mostrar as recomendações que são mais apropriadas para sua atividade.
title: Criar critérios
feature: criteria
uuid: 603d4b02-cdb6-40aa-9654-0086c23b0c8e
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '3605'
ht-degree: 98%

---


# ![PREMIUM](/help/assets/premium.png) Criar critérios{#create-criteria}

Critérios controlam o conteúdo de suas atividades do Recommendations. Crie critérios para mostrar as recomendações que são mais apropriadas para sua atividade.

## Criar critérios {#task_8A9CB465F28D44899F69F38AD27352FE}

Critérios controlam o conteúdo de suas atividades do [!DNL Recommendations]. Crie critérios para mostrar as recomendações que são mais apropriadas para sua atividade.

Existem vários meios de alcançar a tela [!UICONTROL Criar novos critérios]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* Ao criar uma atividade [!DNL Recommendations], clique em **[!UICONTROL Criar novo]** na tela [!UICONTROL Selecionar critérios]. Você terá a opção de salvar seu novo critério para uso com outras atividades do [!DNL Recommendations].
* Ao editar uma [!DNL Recommendations] atividade, clique em uma caixa de [!UICONTROL Localização do Recommendations] em sua página e selecione **[!UICONTROL Alterar critérios]**. Na tela [!UICONTROL Selecionar critério], clique em **[!UICONTROL Criar novo]**. Você terá a opção de salvar seu novo critério para uso com outras atividades do [!DNL Recommendations].
* Na tela da biblioteca **[!UICONTROL Recomendações]** > **[!UICONTROL Critério]**, clique em **[!UICONTROL Criar critério]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!DNL Recommendations].

1. Clique em **[!UICONTROL Criar critérios]** ou **[!UICONTROL Criar novo]**.

   ![Botão Criar critérios](/help/c-recommendations/c-algorithms/assets/button_CreateCriteria_new.png)

1. Selecione **[!UICONTROL Criar critérios]**.

   ![Criar novos critérios](/help/c-recommendations/c-algorithms/assets/CreateNewCriteria_full-new.png)

1. Digite um **[!UICONTROL Nome dos critérios]**.

   Este é o nome &quot;interno&quot; usado para descrever o critério. Por exemplo, você pode chamar seu critério de &quot;Produtos com margem mais alta&quot;, mas não quer que o título seja exibido publicamente. Veja a próxima etapa para definir o título aberto ao público.

1. Digite um **[!UICONTROL Título de exibição]** aberto ao público para aparecer na página para as Recommendations que usam esses critérios.

   Por exemplo, você pode decidir exibir &quot;Pessoas que viram isto também viram aquilo&quot; ou &quot;Produtos parecidos&quot; quando usar este critério para exibir recomendações.

1. Digite uma breve **[!UICONTROL Descrição]** dos critérios.

   A descrição deve ajudar a identificar o critério e pode incluir informações sobre o propósito do critério.

1. Selecione um **[!UICONTROL negócio vertical]**:

   * [!UICONTROL Varejo/Comércio eletrônico]
   * [!UICONTROL Geração de lead/B2B/Serviços financeiros]
   * [!UICONTROL Mídia/Publicação]

   Outras opções de critério irão mudar de acordo com o negócio vertical que você selecionar.

1. Selecione um **[!UICONTROL Tipo de página]**.

   Você pode selecionar vários tipos de página.

   Juntos, o negócio vertical e tipos de página são usados para categorizar seu critério salvo, tornando mais fácil o reuso de critérios para outras atividades do [!DNL Recommendations].

1. Selecione uma **[!UICONTROL Chave de recomendação]**.

   Para obter mais informações sobre como basear os critérios em uma chave, consulte [Basear a recomendação em uma chave de recomendação](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B).

1. Selecione a Lógica **[!UICONTROL de Recomendação]**.

   Para obter mais informações sobre as opções de lógica de recomendação, consulte [Critérios](../../c-recommendations/c-algorithms/algorithms.md#concept_4BD01DC437F543C0A13621C93A302750).

   >[!NOTE]
   >
   >If you select **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]**, you will have the option to set [content similarity rules](../../c-recommendations/c-algorithms/create-new-algorithm.md#concept_5402DAFA279C4E46A9A449526889A0CB).

1. Defina o **[!UICONTROL Intervalo de dados]** para determinar o intervalo de tempo de dados históricos disponíveis do comportamento do usuário, ao determinar quais recomendações serão mostradas.

   Se seu site tiver muito tráfego e os comportamentos mudarem frequentemente, escolha uma janela de dados mais curta. Uma janela menor permite que as [!DNL Recommendations] sejam mais responsivas às alterações no mercado e em seu negócio. Por exemplo, uma janela menor significa que as [!DNL Recommendations] irão detectar alterações no comportamento do visitante conforme seus visitantes começam a fazer compras sazonais, tais como compras de volta às aulas ou de Natal, e irá recomendar itens apropriados para estas temporadas de compras.

   Caso não tenha muitos dados ou o comportamento do visitante não seja alterado com frequência, você pode selecionar uma janela maior. No entanto, para muitos sites, uma janela mais curta resulta em melhores recomendações.

   Os intervalos de dados disponíveis são:

   * Dois dias
   * Uma semana
   * Duas semanas
   * Um mês
   * Dois meses

1. Selecione a **[!UICONTROL fonte de dados comportamentais]** desejada: [!UICONTROL mboxes] ou [!UICONTROL Analytics].

   Se você escolher [!UICONTROL Analytics], selecione o conjunto de relatórios desejado.

1. Defina suas **[!UICONTROL regras de conteúdo]**.

   Regras de conteúdo determinam o que acontece se o número de itens recomendados não preencher seu design. Por exemplo, se o seu design tem espaço para cinco itens mas seus critérios fazem com que apenas três itens sejam recomendados, você pode deixar os espaços restantes vazios ou pode usar recomendações de backup para preencher o espaço adicional.

   Selecione as opções apropriadas:

   * [!UICONTROL Habilitar renderização parcial de design]
   * [!UICONTROL Mostrar recomendações de backup]
   * [!UICONTROL Recomendar itens comprados anteriormente]

   Esta configuração é baseada no `productPurchasedId`. Ela é útil se você vende itens que pessoas geralmente compram apenas uma vez, como caiaques. Se você vende itens que pessoas voltam para comprar novamente, como xampu ou outros itens de uso pessoal, você deve desabilitar esta opção.

1. Defina suas **[!UICONTROL Regras de inclusão]**.

   Regras de inclusão determinam quais itens serão inclusos em suas recomendações. As opções disponíveis dependem do seu negócio vertical.

   Para obter mais detalhes, consulte  [Regras de inclusão](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_28DB20F968B1451481D8E51BAF947079).

1. Configurar **[!UICONTROL ponderação de atributos]**.

   Você pode adicionar várias regras para &quot;cutucar&quot; o algoritmo com base em descrições importantes ou metadados sobre o catálogo de conteúdo. Por exemplo, você pode aplicar um peso maior a itens em liquidação, para que apareçam com mais frequência na recomendação.

   Consulte [Ponderação de atributos](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_2AEDA0DB15B74770B76F6982B24C2E42).

1. Ao terminar, clique em **[!UICONTROL Salvar]**.

   Se você está criando uma nova atividade do [!UICONTROL Recommendations] ou editando uma atividade existente, a caixa de seleção **[!UICONTROL Salvar critérios para mais tarde]** será selecionada por padrão. Se você não quer usar os critérios em outras atividades, desmarque a caixa de seleção antes de salvar.

### Adobe Analytics

Se os critérios usarem o [!DNL Adobe Analytics] como a fonte de dados comportamentais, depois de criados, o tempo para a disponibilidade dos critérios dependerá se o conjunto de relatórios selecionado e a janela de lookback foram usados para quaisquer outros critérios.

* **Configuração única do conjunto de relatórios**: a primeira vez que um conjunto de relatórios é usado com determinada janela de lookback do intervalo de dados, [!DNL Target Recommendations] pode levar de dois a sete dias para baixar completamente os dados comportamentais do conjunto de relatórios selecionado no [!DNL Analytics]. Esse período depende da carga do sistema do [!DNL Analytics].
* **Critérios novos ou editados usando um conjunto de relatórios já disponível**: ao criar um novo critério ou editar um critério existente, se o conjunto de relatórios selecionado já tiver sido usado com o [!DNL Target Recommendations], com um intervalo de dados igual ou menor que o intervalo de dados selecionado, os dados serão imediatamente disponibilizados e a configuração única não será necessária. Nesse caso ou se as configurações de um algoritmo forem editadas, enquanto o conjunto de relatórios ou intervalo de dados selecionado não for modificado, o algoritmo será executado ou executado novamente em 12 horas.
* **O algoritmo contínuo é executado**: os dados fluem do [!DNL Analytics] para [!DNL Target Recommendations] diariamente. Por exemplo, para a recomendação [!UICONTROL Afinidade visualizada], quando um usuário exibe um produto, uma chamada de rastreamento de exibições do produto é passada para o [!DNL Analytics] quase em tempo real. Os dados do [!DNL Analytics] são encaminhados para o [!DNL Target] no início do dia seguinte e o [!DNL Target] executa o algoritmo em menos de 12 horas.

## Basear a recomendação em uma chave de recomendação {#task_2B0ED54AFBF64C56916B6E1F4DC0DC3B}

As recomendações baseadas em chaves utilizam o contexto do comportamento do visitante para mostrar resultados relevantes.

Há dois tipos de recomendações:

* **Popularidade:** lista itens de acordo com mais visualizados, mais vendidos e métricas principais. A chave fica vazia para critérios de popularidade.
* **Baseado em chave:** inclui o resto dos critérios. Recommendations oferecem um conjunto diverso de escolhas a respeito do tipo de chave. As opções vão desde &quot;item atual&quot; até &quot;parâmetros de perfil&quot;, que permitem que você defina programaticamente as chaves dos valores para recomendar. Você pode testar vários critérios uns em relação aos outros baseando cada critério em uma chave diferente.

Cada critério é definido em sua própria guia. O tráfego é dividido uniformemente entre os diferentes testes de critérios. Em outras palavras, se você tem dois critérios, o tráfego é dividido igualmente entre eles. Se você tem dois critérios e dois designs, o tráfego é dividido igualmente entre as quatro combinações. Também é possível especificar uma porcentagem de visitantes do site que veem o conteúdo padrão, para comparação. Nesse caso, o percentual especificado de visitantes acompanha o conteúdo padrão e o restante é dividido entre os seus critérios e combinações de design.

1. Crie uma nova recomendação ou selecione uma recomendação existente e clique em **[!UICONTROL Editar]**.
1. Para alterar a chave de recomendação, selecione a nova chave na lista suspensa [!UICONTROL Chave de recomendação] e clique em **[!UICONTROL Salvar]**.

   Como lógicas diferentes levam a chaves de recomendações diferentes, recomendações diferentes se apresentam para localização em diferentes tipos de páginas. Consulte as seções a seguir para obter mais informações sobre cada chave.

### Item Atual

A recomendação é determinada pelo item que o visitante está vendo atualmente.

As recomendações exibem outros itens que possam interessar o visitante que está interessado no item especificado.

Quando essa opção é selecionada, o valor `entity.id` deve ser passado como parâmetro na mbox de exibição.

**Lógica (critério)**

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Afinidade do site]

**Onde usar em seu site**

Páginas de item único, como páginas de produtos.

NÃO use em páginas de resultados de busca nulos.

### Categoria Atual

A recomendação é determinada pela categoria de produto que o visitante está vendo atualmente.

As recomendações exibem itens na categoria de produto especificada.

Quando essa opção é selecionada, o valor `entity.categoryId` deve ser passado como parâmetro para a mbox de exibição.

**Lógica (critério)**

* Mais vendidos
* Mais visualizados

**Onde usar em seu site**

Páginas de categoria única.

NÃO use em páginas de resultados de busca nulos.

### Atributo personalizado  {#custom}

Recomendação determinada por um item que é armazenado no perfil do visitante, utilizando os atributos usuário.*x* ou perfil.*x* atributos.

Quando esta opção é selecionada, o valor `entity.id` deve estar presente no atributo do perfil.

**Lógica (critério)**

* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Comportamento geral]
* [!UICONTROL Mais visualizados]
* [!UICONTROL Mais vendidos]

Se a chave é um atributo personalizado do perfil e o tipo de algoritmo é Mais visualizados ou Mais vendidos, uma nova lista suspensa que mostra o chamado &quot;Agrupado pelo valor único de&quot; que tem uma lista de atributos de entidade conhecidos (exceto ID, categoria, margem, valor, inventário e ambiente). Esse campo é obrigatório.

**Onde usar em seu site**

Pode ser usado em qualquer página.

**Usar uma chave de recomendações personalizada**

Você pode basear as recomendações no valor de um atributo de perfil personalizado. Por exemplo, suponha que você deseja exibir filmes recomendados com base no filme adicionado recentemente por um visitante à fila.

1. Selecione o atributo de perfil personalizado na lista suspensa **[!UICONTROL Chave de recomendação]** (por exemplo, &quot;Último programa adicionado à Lista de favoritos&quot;).
1. Em seguida, selecione a **[!UICONTROL Lógica de recomendação]** (por exemplo, &quot;Pessoas que assistiram isto, assistiram aquilo&quot;).

   ![Caixa de diálogo Criar novos critérios](/help/c-recommendations/c-algorithms/assets/create-new-criteria-1.png)

Se o atributo de perfil personalizado não corresponder diretamente a uma única ID de entidade, é necessário explicar ao [!DNL Recommendations] como você deseja que a correspondência seja feita a uma entidade. Por exemplo, suponha que você deseja exibir os principais itens de venda da marca favorita de um visitante.

1. Selecione o atributo de perfil personalizado na lista suspensa **[!UICONTROL Chave de recomendação]** (por exemplo, &quot;Marca favorita&quot;).

1. Em seguida, selecione **[!UICONTROL Lógica de recomendação]** que deseja usar com esta chave (por exemplo, &quot;Mais vendidos&quot;).

   A opção [!UICONTROL Agrupar por valor exclusivo de] é exibida.

1. Selecione o atributo de entidade que corresponde à chave escolhida. Neste caso, &quot;Marca favorita&quot; corresponde à `entity.brand`.

   O [!DNL Recommendations] agora gera uma lista de &quot;Mais vendidos&quot; para cada marca e mostra para o visitante a lista de &quot;Mais vendidos&quot; adequada com base no valor armazenado no atributo de perfil de Marca favorita do visitante.

   ![Caixa de diálogo 2 Criar novos critérios](/help/c-recommendations/c-algorithms/assets/create-new-criteria-2.png)

### Último item comprado

A recomendação é determinada pelo último item comprado por cada visitante único. Ela é capturada automaticamente, assim nenhum valor precisa ser aprovado na página.

**Lógica (critério)**

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Afinidade do site]

**Onde usar em seu site**

Página inicial, página minha conta, anúncios em outros sites.

NÃO use nas páginas do produto ou páginas relevantes para compras.

### Último item visualizado

A recomendação é determinada pelo último item visto por cada visitante único. Ela é capturada automaticamente, assim nenhum valor precisa ser aprovado na página.

**Lógica (critério)**

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Afinidade do site]

**Onde usar em seu site**

Página inicial, página minha conta, anúncios em outros sites.

NÃO use nas páginas do produto ou páginas relevantes para compras.

### Item Mais Visualizado

A recomendação é determinada pelo item visto com mais frequência, usando o mesmo método utilizado para a categoria de favoritos.

Isso é determinado pelos critérios de recenticidade/frequência que funciona da seguinte maneira:

* 10 pontos para primeira visualização de produto
* 5 pontos para cada visualização seguinte
* No fim da sessão, divida todos os valores por 2

Por exemplo, visualizar a prancha_de_surfe_A e depois a prancha_de_surfe_B em uma sessão resulta em A: 10, B: 5. Quando a sessão é encerrada, você tem A: 5, B: 2,5. Se você exibir os mesmos itens na sessão seguinte, os valores vão mudar para A: 15 B: 7,5.

**Lógica (critério)**

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Afinidade do site]

**Onde usar em seu site**

Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

### Categoria favorita

A recomendação é determinada pela categoria que recebeu a mais atividade, utilizando o mesmo método usado para &quot;item mais visto&quot;, exceto que as categorias são classificadas, em vez de os produtos.

Isso é determinado pelos critérios de recenticidade/frequência que funciona da seguinte maneira:

* 10 pontos para primeira visualização de categoria
* 5 pontos para cada visualização seguinte

Categorias visitadas pela primeira vez recebem 10 pontos. 5 pontos são dados para visitas seguintes para a mesma categoria. Com cada visita, categorias não atuais que foram vistas anteriormente são diminuídas em 1.

Por exemplo, a visualização da categoria A e da categoria B em uma sessão resulta em A: 9, B: 10. Se você viu os mesmos itens na próxima sessão, os valores mudam para A: 20, B: 9.

**Lógica (critério)**

* [!UICONTROL Mais vendidos]
* [!UICONTROL Mais visualizados]

**Onde usar em seu site**

Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

### Popularidade

A recomendação é determinada pela popularidade de itens em seu site. A popularidade inclui os principais vendedores e os mais visualizados por dados de mbox e, se você utilizar o Adobe Analytics, todas as métricas disponíveis no relatório do produto. Itens são classificados de acordo com a lógica de recomendação que você selecionou.

**Lógica (critério)**

* [!UICONTROL Mais vendidos]
* [!UICONTROL Mais visualizados]
* Métricas de relatório do produto (se você estiver usando o Adobe Analytics)

**Onde usar em seu site**

Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

### Itens visualizados recentemente  {#recently-viewed}

Use o histórico do visitante (abrangendo sessões) para apresentes os últimos *x* itens que o visitante viu, baseado no número de slots no design.

O critério Itens visualizados recentemente agora retorna resultados específicos a um certo [ambiente](/help/administrating-target/hosts.md). Se dois sites pertencerem a ambientes diferentes e um visitante alternar entre os dois sites, cada site exibirá somente itens visualizados recentemente do site em questão. Caso dois sites estejam no mesmo ambiente e um visitante alternar entre eles, ele verá os mesmos itens visualizados recentemente em ambos os sites.

**Onde usar em seu site**

Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

>[!NOTE]
>
>Os Itens visualizados recentemente respeitam as configurações globais de Exclusões e a configuração de Coleção selecionada para a Atividade. Se um item for excluído por uma Exclusão global ou não fizer parte da Coleção selecionada, ele não será exibido; portanto, ao usar um critério de Itens visualizados recentemente, a configuração “Todas as coleções” geralmente deve ser usada.

## Regras de inclusão {#task_28DB20F968B1451481D8E51BAF947079}

Várias opções ajudam a limitar os itens que são exibidos em suas recomendações. Você pode usar regras de inclusão ao criar critérios ou promoções.

Regras de inclusão são opcionais; no entanto, configurar esses detalhes oferece mais controle sobre os itens que aparecem em suas recomendações. Cada detalhe que você configura limita ainda mais os critérios de exibição.

Por exemplo, você pode optar por exibir apenas sapatos femininos que tenham um inventário acima de 50 e o preço entre \$25 e \$45. Também é possível pesar cada atributo para que os itens mais importantes para sua empresa tenham mais chances de aparecer.

Como outro exemplo, você pode escolher exibir vagas de emprego para visitantes que acessem seu site somente de certas cidades e que tenham os graus acadêmicos necessários.

Opções de regras de inclusão variam pelo negócio vertical. Por padrão, regras de inclusão são aplicadas em recomendações de backup.

>[!NOTE]
>
>Você deve usar regras de inclusão com cuidado. Ela é útil se, por exemplo, sua organização tem regras que exijam que uma marca não seja recomendada se outra está sendo mostrada. No entanto, há um custo de oportunidade para este recurso. Você possivelmente perderia uma porcentagem de elevação ao restringir a exibição de alguns itens, quando, normalmente, seriam exibidos pelos critérios de atividade.

Regras de inclusão são unidas por um E. Todas as regras devem ser cumpridas para incluir um item em uma recomendação.

Para criar uma regra de inclusão simples, como mencionado anteriormente, para exibir apenas sapatos femininos que tenham um inventário de mais de 50 e o preço entre $ 25 e $ 45, siga os seguintes passos:

1. Defina um intervalo de preço para os produtos que deseja recomendar.
1. Defina o inventário mínimo para os produtos que deseja recomendar.
1. Configure a recomendação para que exiba itens que satisfaçam os critérios.

   ![](assets/Recs_InclusionRules.png)

   Você pode especificar que os itens sejam incluídos apenas quando um dos atributos na lista atender ou não corresponder a uma ou mais condições especificadas.

   Os avaliadores disponíveis dependem do valor que você escolheu na primeira lista suspensa. Você pode listar vários itens. Esses itens são avaliados com OR.

   Regras múltiplas são combinadas com um AND.

   >[!NOTE]
   >
   >Essa opção limita os itens exibidos na recomendação. Isso não afeta em quais páginas a recomendação é exibida. Para limitar onde a recomendação é exibida, selecione as páginas no compositor de experiência.

## Ponderação de atributos {#task_2AEDA0DB15B74770B76F6982B24C2E42}

Use a ponderação de atributos para &quot;ajustar&quot; o algoritmo de modo que seja mais provável que determinados itens sejam exibidos. Os profissionais de marketing podem influenciar o algoritmo com base em descrições importantes ou metadados sobre o catálogo de conteúdo.

Aplique um peso maior a esses itens em liquidação, para que apareçam com mais frequência na recomendação. Itens que não estão em liquidação não são totalmente excluídos, mas aparecem com menos frequência. Podem ser aplicados muitos pesos ao mesmo algoritmo, e os pesos podem ser testados no tráfego dividido na recomendação.

1. Escolha um valor.

   O valor determina o tipo do item que é mais provável de ser exibido, baseado em um de vários critérios disponíveis.

1. Escolha um avaliador.
1. Insira a palavra-chave para completar os atributos da regra.

   Por exemplo, a regra completa pode ser &quot;Categoria contém sapatos&quot;.

   ![](assets/Recs_AttributeWeighting.png)

1. Selecione o peso a ser designado à regra.

   Opções variam de 0 a 100 em incrementos de 25.

1. Adicione regras adicionais, se desejar.

## Configurações de conteúdo {#concept_BC16005C7A1E4F1A87E33D16221F4A96}

As configurações de [!UICONTROL Conteúdo] determinam como as recomendações são exibidas no design.

É possível que os critérios de [!UICONTROL recomendações] exibam menos recomendações que seu design solicita. Por exemplo, seu design pode ter cinco &quot;slots&quot; disponíveis, mas o critério retorna apenas três itens recomendados. As configurações de [!UICONTROL conteúdo] controlam como as recomendações são apresentadas quando isto acontece.

Regras de conteúdo determinam o que acontece se o número de itens recomendados não preencher seu design. Por exemplo, se o seu design tem espaço para cinco itens mas seus critérios fazem com que apenas três itens sejam recomendados, você pode deixar os espaços restantes vazios ou pode usar recomendações de backup para preencher o espaço adicional.

Selecione as opções apropriadas:

* [!UICONTROL Habilitar renderização parcial de design]
* [!UICONTROL Mostrar recomendações de backup]
* [!UICONTROL Aplicar regras de inclusão em recomendações de backup]
* [!UICONTROL Recomendar itens comprados anteriormente]

   Esta configuração é baseada no valor de perfil `productPurchasedId`. O comportamento padrão é não recomendar itens comprados anteriormente. Na maioria dos casos, você não deseja promover itens que um cliente comprou recentemente. Se os clientes normalmente comprarem determinados itens repetidamente, a ativação desse recurso permitirá que itens adquiridos anteriormente continuem sendo recomendados.

Se ativar **[!UICONTROL Mostrar recomendações de backup]**, a opção para aplicar suas [regras de inclusão](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_28DB20F968B1451481D8E51BAF947079) às recomendações de backup será ativada por padrão.

![](assets/Recs_ContentControls.png)

| Renderização parcial de design | Recommendations de backup | Resultado |
|--- |--- |--- |
| Desativado | Desativado | Se forem retornadas menos recomendações do que o design solicita, o design das recomendações será substituído pelo conteúdo padrão, e nenhuma recomendação será exibida. |
| Ativado | Desativado | O design é renderizado, mas pode incluir um espaço em branco se forem retornadas menos recomendações do que o design solicita. |
| Ativado | Ativado | As recomendações de backup preencherão os &quot;slots&quot; de design disponíveis, renderizando totalmente o design.<br>Se a aplicação de regras de inclusão às recomendações de backup limitar o número de recomendações de backup qualificadas ao ponto de não ser possível preencher o design, o design será parcialmente renderizado.<br>Se os critérios não retornarem nenhuma recomendação e as regras de inclusão limitarem as recomendações de backup a zero, o design será substituído pelo conteúdo padrão. |
| Desativado | Ativado | As recomendações de backup preencherão os &quot;slots&quot; de design disponíveis, renderizando totalmente o design.<br>Se a aplicação de regras de inclusão às recomendações de backup limitar o número de recomendações de backup qualificadas ao ponto de não ser possível preencher o design, o design será substituído pelo conteúdo padrão, e nenhuma recomendação será exibida. |

## Similaridade de conteúdo {#concept_5402DAFA279C4E46A9A449526889A0CB}

Use as regras de [!UICONTROL Similaridade de conteúdo] para fazer recomendações baseadas em atributos de item ou mídia.

Similaridade de conteúdo compara palavras-chave de atributo do item e faz recomendações baseadas em quantas palavras-chave itens diferentes têm em comum. Recommendations baseadas em similaridade de conteúdo não requerem dados antigos para providenciar melhores resultados.

Usar similaridade de conteúdo para gerar recomendações é especialmente eficaz para novos itens, que provavelmente não aparecem em recomendações usando *pessoas que viram isto, viram aquilo* e outras lógicas baseadas em comportamento anterior. Você também pode usar similaridade de conteúdo para gerar recomendações úteis para novos visitantes, que não possuem compras antigas ou outros dados de histórico.

Quando você selecionar **[!UICONTROL Itens]**/**[!UICONTROL Mídia com atributos similares]**, você terá a opção de criar regras para aumentar ou reduzir a importância de atributos específicos do item em determinadas recomendações. Para itens como livros, você pode querer ampliar a importância de atributos como *gênero*, *autor*, *série*, e assim em diante, para recomendar livros similares.

![](assets/ContentSimilarity.png)

Como a similaridade de conteúdo usa palavras-chave para comparar itens, alguns atributos, como *mensagem* ou *descrição*, podem introduzir &quot;ruído&quot; à comparação. Você pode criar regras para ignorar estes atributos.

Por padrão, todos atributos são definidos como *Linha de base*. Você não precisa criar uma regra a não ser que queira alterar esta configuração.

>[!NOTE]
>
>O algoritmo de semelhança de conteúdo pode usar amostragem aleatória na computação de similaridade entre itens. Como resultado, as classificações de similaridade entre itens podem variar entre execuções de algoritmos.

## Training video: Create criteria in Recommendations (12:33) ![Tutorial badge](/help/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar critérios
* Criar sequências de critérios
* Upload dos critérios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
