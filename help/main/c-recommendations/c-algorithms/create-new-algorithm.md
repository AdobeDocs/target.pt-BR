---
keywords: critérios, algoritmo, vertical do setor, tipo de página, chave de recomendação, lógica, intervalo de dados, janela de lookback, fonte de dados do comportamento, design parcial, recomendações de backup, regras de inclusão, ponderação de atributo, categoria atual, atributo personalizado, último item comprado, último item visualizado, item mais exibido, item mais visualizado, categoria favorita, popularidade, item visualizado recentemente, último comprado, mais visualizado, favorito
description: Saiba como criar critérios que controlam o conteúdo de suas atividades do Adobe Recommendations para mostrar as recomendações mais apropriadas para sua atividade.
title: Como criar critérios no Recommendations?
feature: Recommendations
exl-id: 3f4f59b2-6637-4c33-bf17-bff11bef7173
source-git-commit: 81cd39140eb21d2718f3899ed6b28217023bd680
workflow-type: tm+mt
source-wordcount: '2835'
ht-degree: 52%

---

# ![PREMIUM](/help/main/assets/premium.png) Criar critérios

Critérios em [!UICONTROL Adobe Target] [!UICONTROL Recommendations] controle o conteúdo de sua [!UICONTROL Recommendations] atividades. Crie critérios para mostrar as recomendações que são mais apropriadas para sua atividade. Esses critérios usam as ações do visitante para determinar qual conteúdo ou produtos serão exibidos.

As seções a seguir explicam como criar um novo critério.

## Acesse a tela Criar novo critério

Existem vários meios de alcançar a tela [!UICONTROL Criar novos critérios]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* No **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]** tela biblioteca, clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar critérios]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!DNL Recommendations].
* Ao criar um [!DNL Recommendations] atividade usando a [!UICONTROL Visual Experience Composer] (VEC), é imediatamente levado ao [!UICONTROL Selecionar critérios] depois de selecionar um elemento na página e clicar em [!UICONTROL Substituir por Recommendations], [!UICONTROL Inserir o Recommendations antes de]ou [!UICONTROL Inserir o Recommendations depois de]. Você pode selecionar um critério disponível ou clicar em **[!UICONTROL Criar critérios]**. Se você criar um novo critério, terá a opção de salvar seu critério para uso com outros [!DNL Recommendations] atividades. Para obter mais informações, consulte [Criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Ao editar uma [!DNL Recommendations] atividade, clique em uma caixa de [!UICONTROL Localização do Recommendations] em sua página e selecione **[!UICONTROL Alterar critérios]**. No [!UICONTROL Selecionar critérios] , clique em **[!UICONTROL Criar critérios]**. Você terá a opção de salvar seu novo critério para uso com outras atividades do [!DNL Recommendations].

As etapas a seguir pressupõem que você acesse a variável [!UICONTROL Criar novos critérios] usando o primeiro método: o **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]** tela da biblioteca.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar critérios]**.

   ![Criar novos critérios](assets/CreateNewCriteria_full-new.png)

1. Configure as informações nas seções a seguir.

## [!UICONTROL Informações básicas] {#info}

1. Digite um **[!UICONTROL Nome dos critérios]**.

   Este é o nome &quot;interno&quot; usado para descrever o critério. Por exemplo, você pode chamar seu critério de &quot;Produtos com margem mais alta&quot;, mas não quer que o título seja exibido publicamente. Veja a próxima etapa para definir o título aberto ao público.

   ![Seção Informações básicas](assets/basic-information.png)

1. Insira um **[!UICONTROL Título de exibição]** aberto ao público que irá aparecer na página para qualquer recomendação que use este critério.

   Por exemplo, você pode decidir exibir &quot;Pessoas que viram isto também viram aquilo&quot; ou &quot;Produtos parecidos&quot; quando usar este critério para exibir recomendações.

1. Digite uma breve **[!UICONTROL Descrição]** dos critérios.

   A descrição deve ajudar a identificar o critério e pode incluir informações sobre a finalidade do critério.

1. Selecione um negócio vertical com base nas metas de sua atividade do Recommendations.

   | Vertical do setor | Meta |
   |--- |--- |
   | Varejo/Comércio eletrônico | Conversão resultando em compra |
   | Geração de lead/B2B/Serviços financeiros | Conversão sem compra |
   | Mídia/Publicação | Envolvimento |

   Outras opções de critério irão mudar de acordo com o negócio vertical que você selecionar.

1. Selecione um **[!UICONTROL Tipo de página]**.

   Você pode selecionar vários tipos de página.

   Juntos, o negócio vertical e tipos de página são usados para categorizar seu critério salvo, tornando mais fácil o reuso de critérios para outras atividades do [!DNL Recommendations].

## [!UICONTROL Algoritmo Recommendations] {#rec-algo}

1. Selecione um **[!UICONTROL Tipo de algoritmo]** e **[!UICONTROL Algoritmo]**:

   ![Seção Algoritmo recomendado](assets/recommended-algorithm.png)

   | Tipo de algoritmo | Quando usar | Algoritmos disponíveis |
   | --- | --- | --- |
   | [!UICONTROL Baseado em carrinho] | Faça recomendações com base no conteúdo do carrinho do usuário. | <ul><li>Pessoas que visualizaram estes, visualizaram aqueles</li><li>Pessoas que visualizaram estes, compraram aqueles</li><li>Pessoas que compraram isto, compraram aqueles</li></ul> |
   | [!UICONTROL Baseado em popularidade] | Faça recomendações com base na popularidade geral de um item em seu site ou na popularidade dos itens em uma categoria favorita ou mais exibida do usuário, marca, gênero e assim por diante. | <ul><li>Mais visualizados no site</li><li>Mais visualizados por categoria</li><li>Mais visualizados por atributo de item</li><li>Mais vendidos no site</li><li>Mais vendidos por categoria</li><li>Principais Vendedores por Atributo de Item</li><li>Principais por métrica do Analytics</li></ul> |
   | [!UICONTROL Baseado em item] | Faça recomendações baseadas em encontrar itens semelhantes a um item que o usuário está visualizando ou visualizou recentemente. | <ul><li>Pessoas que visualizaram isto, visualizaram aquilo</li><li>Pessoas que visualizaram isto, compraram aquilo</li><li>Pessoas que compraram isto, compraram aquilo</li><li>Itens com atributos similares</li></ul> |
   | [!UICONTROL Baseado em usuário] | Faça recomendações com base no comportamento do usuário. | <ul><li>Itens visualizados recentemente </li><li>Recomendado para você</li></ul> |
   | [!UICONTROL Critérios personalizados] | Faça recomendações com base em um arquivo personalizado que você fez upload. | <ul><li>Algoritmo personalizado</li></ul> |

   >[!NOTE]
   >
   >Se você selecionar **[!UICONTROL Itens]**/ **[!UICONTROL Mídia com atributos similares]**, você terá a opção de definir [regras de similaridade de conteúdo](#similarity).

1. Conforme necessário, selecione um **Atributo do item** e **Atributo de perfil para correspondência**, a **Chave de recomendação**, **Chave de filtragem** e/ou **Métrica do Analytics** para configurar o algoritmo.

As opções restantes de configuração de algoritmo variam de acordo com o algoritmo selecionado. Para concluir a configuração do algoritmo, selecione um [!UICONTROL Chave de recomendação], [!UICONTROL Chave de filtragem], [!UICONTROL Base de Co-Ocorrência], [!UICONTROL Métrica do Analytics]e/ou [!UICONTROL Atributo do item] e [!UICONTROL Atributo de perfil para correspondência].

Para obter mais informações sobre a escolha de um [!UICONTROL Chave de recomendação], consulte [Basear a recomendação em uma chave de recomendação](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## [!UICONTROL Fonte de dados] {#data-source}

1. Selecione o **[!UICONTROL Fonte de dados comportamentais]**: [!UICONTROL Adobe Target] ou [!UICONTROL Analytics].

   >[!NOTE]
   >
   >O [!UICONTROL Fonte de dados comportamentais] a seção exibe somente se sua implementação usar [Analytics para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Seção Fonte de dados comportamentais](assets/data-source.png)

   Se você escolher [!UICONTROL Analytics], selecione o conjunto de relatórios desejado.

   Se os critérios usarem [!DNL Adobe Analytics] como a fonte de dados comportamentais, uma vez criada, o tempo para a disponibilidade dos critérios depende se o conjunto de relatórios selecionado e a janela de lookback foram usados para quaisquer outros critérios, conforme explicado abaixo:

   * **Configuração única do conjunto de relatórios**: a primeira vez que um conjunto de relatórios é usado com determinada janela de lookback do intervalo de dados, [!DNL Target Recommendations] pode levar de dois a sete dias para baixar completamente os dados comportamentais do conjunto de relatórios selecionado no [!DNL Analytics]. Esse período depende do [!DNL Analytics] carga do sistema.
   * **Critérios novos ou editados usando um conjunto de relatórios já disponível**: ao criar um novo critério ou editar um critério existente, se o conjunto de relatórios selecionado já tiver sido usado com o [!DNL Target Recommendations], com um intervalo de dados igual ou menor que o intervalo de dados selecionado, os dados serão imediatamente disponibilizados e a configuração única não será necessária. Nesse caso ou se as configurações de um algoritmo forem editadas, enquanto o conjunto de relatórios ou intervalo de dados selecionado não for modificado, o algoritmo será executado ou executado novamente em 12 horas.
   * **O algoritmo contínuo é executado**: os dados fluem do [!DNL Analytics] para [!DNL Target Recommendations] diariamente. Por exemplo, para a recomendação [!UICONTROL Afinidade visualizada], quando um usuário exibe um produto, uma chamada de rastreamento de exibições do produto é passada para o [!DNL Analytics] quase em tempo real. Os dados do [!DNL Analytics] são encaminhados para o [!DNL Target] no início do dia seguinte e o [!DNL Target] executa o algoritmo em menos de 12 horas.

   Para obter mais informações, consulte [Usar o Adobe Analytics com o Target Recommendations](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

1. Defina as **[!UICONTROL Janela de pesquisa]** para determinar o intervalo de tempo de dados históricos disponíveis do comportamento do usuário, ao determinar quais recomendações serão exibidas. Essa opção está disponível para todos os algoritmos, com exceção de Itens com Atributos similares e Algoritmos personalizados.

   ![Controle deslizante da janela de pesquisa](assets/data-range.png)

   Se seu site tiver muito tráfego e os comportamentos mudarem frequentemente, escolha uma janela de dados mais curta. Uma janela menor permite que as [!DNL Recommendations] sejam mais responsivas às alterações no mercado e em seu negócio. Por exemplo, uma janela menor significa que as [!DNL Recommendations] irão detectar alterações no comportamento do visitante conforme seus visitantes começam a fazer compras sazonais, tais como compras de volta às aulas ou de Natal, e irá recomendar itens apropriados para estas temporadas de compras.

   Caso não tenha muitos dados ou o comportamento do visitante não seja alterado com frequência, você pode selecionar uma janela maior. No entanto, para muitos sites, uma janela mais curta resulta em recomendações de maior qualidade.

   Os intervalos de dados disponíveis são:

   | Opção Janela de pesquisa | Frequência atualizada (exibida ao passar o mouse) | Algoritmos suportados |
   | --- | --- | --- |
   | Seis horas | O algoritmo é executado a cada 3-6 horas | [!UICONTROL Baseado em popularidade] algoritmos quando o [!UICONTROL Fonte de dados comportamentais] é [!DNL Adobe Target] |
   | Um dia | O algoritmo é executado a cada 12-24 horas | [!UICONTROL Baseado em popularidade] algoritmos |
   | Dois dias | O algoritmo é executado a cada 12-24 horas | <ul><li>[!UICONTROL Baseado em popularidade] algoritmos</li><li>[!UICONTROL Baseado em item] algoritmos</li><li>[!UICONTROL Baseado em usuário] algoritmos</li><li>[!UICONTROL Baseado em carrinho] algoritmos</li></ul> |
   | Uma semana | O algoritmo é executado a cada 24-48 horas | <ul><li>[!UICONTROL Baseado em popularidade] algoritmos</li><li>[!UICONTROL Baseado em item] algoritmos</li><li>[!UICONTROL Baseado em usuário] algoritmos</li><li>[!UICONTROL Baseado em carrinho] algoritmos</li></ul> |
   | Duas semanas | O algoritmo é executado a cada 24-48 horas | <ul><li>[!UICONTROL Baseado em popularidade] algoritmos</li><li>[!UICONTROL Baseado em item] algoritmos</li><li>Todos [!UICONTROL Baseado em usuário] algoritmos</li><li>[!UICONTROL Baseado em carrinho] algoritmos</li></ul> |
   | Um mês (30 dias) | O algoritmo é executado a cada 24-48 horas | <ul><li>[!UICONTROL Baseado em popularidade] algoritmos</li><li>[!UICONTROL Baseado em item] algoritmos</li><li>[!UICONTROL Baseado em usuário] algoritmos</li><li>[!UICONTROL Baseado em carrinho] algoritmos</li></ul> |
   | Dois meses (61 dias) | O algoritmo é executado a cada 24-48 horas | <ul><li>[!UICONTROL Baseado em popularidade] algoritmos</li><li>[!UICONTROL Baseado em item] algoritmos</li><li>[!UICONTROL Baseado em usuário] algoritmos</li><li>[!UICONTROL Baseado em carrinho] algoritmos</li></ul> |

## [!UICONTROL Conteúdo de backup] {#content}

[!UICONTROL Conteúdo de backup] as regras determinam o que acontece se o número de itens recomendados não preencher a [design de recomendações](/help/main/c-recommendations/c-design-overview/design-overview.md). É possível [!DNL Recommendations] critérios para retornar menos recomendações do que seu design solicita. Como exemplo, se o design tiver slots para quatro itens, mas os critérios fizerem com que apenas dois itens sejam recomendados, você poderá deixar os slots restantes vazios, poderá usar recomendações de backup para preencher os slots extras ou poderá optar por não exibir nenhuma recomendação.

![Seção de conteúdo](assets/content.png)

1. (Opcional) Deslize o **[!UICONTROL Renderização parcial do design]** alterne para a posição &quot;ativada&quot;.

   Quantos espaços forem possíveis serão preenchidos, mas o modelo de design poderá incluir espaço em branco para os espaços restantes. Se essa opção estiver desativada e não houver conteúdo suficiente para preencher todos os slots disponíveis, as recomendações não serão exibidas e o conteúdo padrão será exibido.

   Ative essa opção se desejar que as recomendações sejam exibidas com espaços em branco. Use as recomendações de backup se desejar que os slots de recomendação sejam preenchidos com conteúdo com base nos seus critérios com slots vazios preenchidos com conteúdo semelhante ou popular do seu site, conforme explicado na próxima etapa.

1. (Opcional) Deslize o **[!UICONTROL Mostrar conteúdo de backup]** alterne para a posição &quot;ativada&quot;.

   Preencha os slots vazios restantes no design com uma seleção aleatória de produtos mais visualizados de todo o site.

   Usar recomendações de backup garante que o design da recomendação preencha todos os slots disponíveis. Suponha que você tenha um design 4 x 1, conforme ilustrado abaixo:

   ![Design 4 x 1](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

   Suponha que seus critérios façam com que apenas dois itens sejam recomendados. Se você ativar a variável [!UICONTROL Renderização parcial do design] , os dois primeiros slots são preenchidos, mas os dois slots restantes permanecem vazios. No entanto, se você ativar a variável [!UICONTROL Mostrar Recommendations de Backup] , os dois primeiros slots são preenchidos com base nos critérios especificados e os dois slots restantes são preenchidos com base nas recomendações de backup.

   A matriz a seguir mostra o resultado que você observará ao usar a variável [!UICONTROL Renderização parcial do design] e [!UICONTROL Conteúdo de backup] opções:

   | Renderização parcial de design | Conteúdo de backup | Resultado |
   |--- |--- |--- |
   | Desativado | Desativado | Se forem retornadas menos recomendações do que o design solicita, o design das recomendações será substituído pelo conteúdo padrão, e nenhuma recomendação será exibida. |
   | Ativado | Desativado | O design é renderizado, mas pode incluir um espaço em branco se forem retornadas menos recomendações do que o design solicita. |
   | Ativado | Ativado | As recomendações de backup preencherão os &quot;slots&quot; de design disponíveis, renderizando totalmente o design.<br>Se a aplicação de regras de inclusão às recomendações de backup limitar o número de recomendações de backup qualificadas ao ponto de não ser possível preencher o design, o design será parcialmente renderizado.<br>Se os critérios não retornarem nenhuma recomendação e as regras de inclusão limitarem as recomendações de backup a zero, o design será substituído pelo conteúdo padrão. |
   | Desativado | Ativado | As recomendações de backup preencherão os &quot;slots&quot; de design disponíveis, renderizando totalmente o design.<br>Se a aplicação de regras de inclusão às recomendações de backup limitar o número de recomendações de backup qualificadas ao ponto de não ser possível preencher o design, o design será substituído pelo conteúdo padrão, e nenhuma recomendação será exibida. |

   Para obter mais informações, consulte [Usar uma recomendação de backup](/help/main/c-recommendations/c-algorithms/backup-recs.md).

1. (Condicional) Se você selecionou **[!UICONTROL Mostrar conteúdo de backup]** na etapa anterior, é possível ativar **[!UICONTROL Aplicar regras de inclusão às recomendações de backup]**.

   Regras de inclusão determinam quais itens estão incluídos em suas recomendações. As opções disponíveis dependem do seu negócio vertical.

   Para obter mais detalhes, consulte  [Especificar regras de inclusão](#inclusion) abaixo.

## Similaridade de conteúdo {#similarity}

Use as regras de [!UICONTROL Similaridade de conteúdo] para fazer recomendações baseadas em atributos de item ou mídia.

>[!NOTE]
>
>Se você selecionou **[!UICONTROL Baseado em item]**/ **[!UICONTROL Mídia com atributos similares]** como Tipo de algoritmo e Algoritmo, você tem a opção de definir regras de similaridade de conteúdo.

Similaridade de conteúdo compara palavras-chave de atributo do item e faz recomendações baseadas em quantas palavras-chave itens diferentes têm em comum. Recommendations baseadas em similaridade de conteúdo não requerem dados antigos para providenciar melhores resultados.

Usar similaridade de conteúdo para gerar recomendações é especialmente eficaz para novos itens, que provavelmente não aparecem em recomendações usando *pessoas que viram isto, viram aquilo* e outras lógicas baseadas em comportamento anterior. Você também pode usar similaridade de conteúdo para gerar recomendações úteis para novos visitantes, que não possuem compras antigas ou outros dados de histórico.

Ao selecionar **[!UICONTROL Baseado em item]**/ **[!UICONTROL Mídia com atributos similares]**, você tem a opção de criar regras para aumentar ou diminuir a importância de atributos específicos do item em determinadas recomendações. Para itens como livros, você pode querer ampliar a importância de atributos como *gênero*, *autor*, *série*, e assim em diante, para recomendar livros similares.

![](assets/ContentSimilarity.png)

Como a similaridade de conteúdo usa palavras-chave para comparar itens, alguns atributos, como *mensagem* ou *descrição*, podem introduzir &quot;ruído&quot; à comparação. Você pode criar regras para ignorar estes atributos.

Por padrão, todos atributos são definidos como *Linha de base*. Você não precisa criar uma regra a não ser que queira alterar esta configuração.

>[!NOTE]
>
>O algoritmo de similaridade de conteúdo pode usar amostragem aleatória na computação de similaridade entre itens. Como resultado, as classificações de similaridade entre itens podem variar entre as execuções de algoritmo.

## Regras de inclusão {#inclusion}

Várias opções ajudam a limitar os itens que são exibidos em suas recomendações. Você pode usar regras de inclusão ao criar critérios ou promoções.

![Regras de inclusão](/help/main/c-recommendations/c-algorithms/assets/inclusion-rules.png)

Regras de inclusão são opcionais; no entanto, configurar esses detalhes oferece mais controle sobre os itens que aparecem em suas recomendações. Cada detalhe que você configura limita ainda mais os critérios de exibição.

Por exemplo, você pode escolher exibir apenas sapatos femininos que tenham um inventário de mais de 50 e o preço entre $ 25 e $ 45. Também é possível pesar cada atributo para que os itens mais importantes para sua empresa tenham mais chances de aparecer.

Como outro exemplo, você pode escolher exibir vagas de emprego para visitantes que acessem seu site somente de certas cidades e que tenham os graus acadêmicos necessários.

Opções de regras de inclusão variam pelo negócio vertical. Por padrão, regras de inclusão são aplicadas em recomendações de backup.

>[!IMPORTANT]
>
>Você deve usar regras de inclusão com cuidado. Ela é útil se, por exemplo, sua organização tem regras que exijam que uma marca não seja recomendada se outra está sendo mostrada. No entanto, há um custo de oportunidade para este recurso. Você possivelmente perderia uma porcentagem de elevação ao restringir a exibição de alguns itens, quando, normalmente, seriam exibidos pelos critérios de atividade.

Regras de inclusão são unidas por um E. Todas as regras devem ser cumpridas para incluir um item em uma recomendação.

Para criar uma regra de inclusão simples, como mencionado anteriormente, para exibir apenas sapatos femininos que tenham um inventário de mais de 50 e o preço entre $ 25 e $ 45, siga os seguintes passos:

1. (Condicional) Deslize o **[!UICONTROL Permitir que itens adquiridos recentemente sejam recomendados?]** alterne para a posição &quot;ativada&quot;.

   Esta configuração é baseada no `productPurchasedId`. O comportamento padrão é não recomendar itens comprados anteriormente. Na maioria dos casos, você não deseja promover itens que um cliente comprou recentemente. Ela é útil se você vende itens que pessoas geralmente compram apenas uma vez, como caiaques. Se você vende itens que as pessoas voltam para comprar novamente repetidamente, como xampu ou outros itens pessoais, você deve habilitar essa opção.

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

Para obter mais informações, consulte [Uso das regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Ponderação de atributos {#weighting}

Você pode adicionar várias regras para &quot;ajustar&quot; o algoritmo com base em informações importantes ou metadados sobre o catálogo de conteúdo, de modo que certos itens tenham mais probabilidade de serem exibidos.

Por exemplo, você pode aplicar um peso maior a itens em liquidação, para que apareçam com mais frequência na recomendação. Itens que não estão em liquidação não são totalmente excluídos, mas aparecem com menos frequência. Podem ser aplicados muitos pesos ao mesmo algoritmo, e os pesos podem ser testados no tráfego dividido na recomendação.

1. Escolha um valor.

   O valor determina o tipo do item que é mais provável de ser exibido, baseado em um de vários critérios disponíveis.

1. Escolha um avaliador.

1. Insira a palavra-chave para completar os atributos da regra.

   Por exemplo, a regra completa pode ser &quot;Categoria contém sapatos de subsequência&quot;.

   ![](assets/Recs_AttributeWeighting.png)

1. Selecione o peso a ser designado à regra.

   Opções variam de 0 a 100 em incrementos de 25.

1. Adicione regras adicionais, se desejar.

Ao terminar, clique em **[!UICONTROL Salvar]**.

Se você está criando uma nova atividade do [!UICONTROL Recommendations] ou editando uma atividade existente, a caixa de seleção **[!UICONTROL Salvar critérios para mais tarde]** será selecionada por padrão. Se você não quer usar os critérios em outras atividades, desmarque a caixa de seleção antes de salvar.

## Vídeo de treinamento: Criar critérios no Recommendations (12:33) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar critérios
* Criar sequências de critérios
* Upload dos critérios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
