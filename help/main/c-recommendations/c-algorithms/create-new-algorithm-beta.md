---
keywords: critérios;algoritmo;vertical do setor;tipo de página;chave de recomendação;lógica de recomendação;lógica;intervalo de dados;janela de lookback;fonte de dados de comportamento;design parcial;recomendações de backup;regras de inclusão;ponderação de atributos;categoria atual;atributo personalizado;último item comprado;último item exibido;item mais exibido;item mais exibido;categoria favorita;popularidade;item exibido recentemente;última comprado;última exibido;mais exibido;favorito;exibido recentemente
description: Saiba como criar critérios que controlam o conteúdo de suas  [!DNL Recommendations] atividades para mostrar as recomendações mais apropriadas para a sua atividade.
title: Como criar [!UICONTROL Criteria] em  [!DNL Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: c8b0e0414603761b1c67b13d74ffa96d745c99e3
workflow-type: tm+mt
source-wordcount: '2554'
ht-degree: 47%

---

# Criar critérios

Critério em [!UICONTROL Adobe Target] [!UICONTROL Recommendations] controle o conteúdo de suas atividades [!UICONTROL Recommendations]. Crie critérios para mostrar as recomendações que são mais apropriadas para sua atividade. Esses critérios usam as ações do visitante para determinar qual conteúdo ou produtos exibir.

As seções a seguir explicam como criar um novo critério.

## Acessar a tela Criar novos critérios

Há várias maneiras de acessar a tela [!UICONTROL Create New Criteria]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* Na tela da biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**, clique em **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!DNL Recommendations].
* Ao criar uma atividade do [!DNL Recommendations] usando o [!UICONTROL Visual Experience Composer] (VEC), você é imediatamente levado para a tela [!UICONTROL Select Criteria] depois de selecionar um elemento na sua página e clicar em [!UICONTROL Replace w/ Recommendations], [!UICONTROL Insert Recommendations Before] ou [!UICONTROL Insert Recommendations After]. Você pode selecionar um critério disponível ou clicar em **[!UICONTROL Create Criteria]**. Se você criar um novo critério, você tem a opção de salvar seu critério para uso com outras atividades do [!DNL Recommendations]. Para obter mais informações, consulte [Criar uma atividade de Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Quando você editar uma atividade [!DNL Recommendations], clique em uma caixa [!UICONTROL Recommendations Location] na sua página e selecione **[!UICONTROL Change Criteria]**. Na tela [!UICONTROL Select Criteria], clique em **[!UICONTROL Create Criteria]**. Você terá a opção de salvar seu novo critério para uso com outras atividades do [!DNL Recommendations].

As etapas a seguir consideram que você acesse a tela [!UICONTROL Create New Criteria] usando o primeiro método: a tela de biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Clique em **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**.

1. Configure as informações nas seções a seguir.

## [!UICONTROL Basic Information] {#info}

1. Digite um **[!UICONTROL Criteria Name]**.

   Este é o nome &quot;interno&quot; usado para descrever o critério. Por exemplo, você pode chamar seu critério de &quot;Produtos com margem mais alta&quot;, mas não quer que o título seja exibido publicamente. Veja a próxima etapa para definir o título aberto ao público.

1. Digite um **[!UICONTROL Display Title]** aberto ao público para aparecer na página para qualquer recomendação que use este critério.

   Por exemplo, você pode decidir exibir &quot;Pessoas que viram isto também viram aquilo&quot; ou &quot;Produtos parecidos&quot; quando usar este critério para exibir recomendações.

1. Digite um curto **[!UICONTROL Description]** dos critérios.

   A descrição deve ajudar a identificar o critério e pode incluir informações sobre o propósito do critério.

1. Selecione um negócio vertical com base nas metas da sua atividade de recomendações.

   | Vertical do setor | Meta |
   |--- |--- |
   | [!UICONTROL Retail/Ecommerce] | Conversão resultando em compra |
   | [!UICONTROL Lead Generation/B2B/Financial Services] | Conversão sem compra |
   | [!UICONTROL Media/Publishing] | Envolvimento |

   Outras opções de critério mudam de acordo com o negócio vertical que você selecionar.

1. Selecione um **[!UICONTROL Page Type]**.

   Você pode selecionar vários tipos de página.

   Juntos, o negócio vertical e tipos de página ajudá-lo a categorizar seu critério salvo, tornando mais fácil o reuso de critérios para outras atividades [!DNL Recommendations].

## [!UICONTROL Recommendations Algorithm] {#rec-algo}

1. Selecione um **[!UICONTROL Algorithm Type]** e **[!UICONTROL Algorithm]**:

   ![Seção de algoritmo recomendada](assets/recommended-algorithm.png)

   | Tipo de algoritmo | Quando usar / Algoritmos disponíveis |
   | --- | --- |
   | [!UICONTROL Cart-Based] | Faça recomendações com base no conteúdo do carrinho do usuário. <ul><li>[!UICONTROL People Who Viewed These, Also Viewed] </li><li>[!UICONTROL People Who Viewed These, Also Bought]</li><li>[!UICONTROL People Who Bought These, Also Bought]</li></ul> |
   | [!UICONTROL Popularity-Based] | Faça recomendações com base na popularidade geral de um item em todo o site ou na popularidade de itens na categoria, marca, gênero e assim por diante favoritas ou mais visualizadas de um usuário. <ul><li>[!UICONTROL Most Viewed Across the Site]</li><li>[!UICONTROL Most Viewed by Category]</li><li>[!UICONTROL Most Viewed by Item Attribute]</li><li>[!UICONTROL Top Sellers Across the Site]</li><li>[!UICONTROL Top Sellers by Category]</li><li>[!UICONTROL Top Sellers by Item Attribute]</li><li>[!UICONTROL Top by Analytics Metric]</li></ul> |
   | [!UICONTROL Item-Based] | Fazer recomendações com base na localização de itens semelhantes a um item que o usuário está visualizando atualmente ou que visualizou recentemente. <ul><li>[!UICONTROL People Who Viewed This, Viewed That]</li><li>[!UICONTROL People Who Viewed This, Bought That]</li><li>[!UICONTROL People Who Bought This, Bought That]</li><li>[!UICONTROL Items with Similar Attributes]</li></ul> |
   | [!UICONTROL User-Based] | Faça recomendações com base no comportamento do usuário. | <ul><li>[!UICONTROL Recently Viewed Items]</li><li>[!UICONTROL Recommended for You]</li></ul> |
   | [!UICONTROL Custom Criteria] | Faça recomendações com base em um arquivo personalizado que você fez upload. | <ul><li>Algoritmo personalizado</li></ul> |

   >[!NOTE]
   >
   >Se você selecionar **[!UICONTROL Items]**/ **[!UICONTROL Media with Similar Attributes]**, terá a opção de definir [regras de similaridade de conteúdo](#similarity).

1. Conforme necessário, selecione um **Atributo de Item** e **Atributo de Perfil a Corresponder**, uma **Chave de Recomendação**, **Chave de Filtragem** e/ou **Métrica do Analytics** para configurar o algoritmo.

As opções de configuração de algoritmo restantes variam dependendo do algoritmo selecionado. Para concluir a configuração do algoritmo, selecione um [!UICONTROL Recommendation Key], [!UICONTROL Filtering Key], [!UICONTROL Co-Occurrence Basis], [!UICONTROL Analytics Metric], e/ou [!UICONTROL Item Attribute] e [!UICONTROL Profile Attribute to Match].

Para obter mais informações sobre como escolher um [!UICONTROL Recommendation Key], consulte [Basear a recomendação em uma chave de recomendação](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## [!UICONTROL Data Source] {#data-source}

1. Selecione o **[!UICONTROL Behavioral Data Source]** desejado: [!UICONTROL Adobe Target] ou [!UICONTROL Analytics].

   >[!NOTE]
   >
   >A seção [!UICONTROL Behavioral Data Source] será exibida somente se sua implementação usar o [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Seção Behavioral Data Source](assets/data-source.png)

   Se você escolher [!UICONTROL Analytics], selecione o conjunto de relatórios desejado.

   Se os critérios usarem [!DNL Adobe Analytics] como a fonte de dados comportamentais, uma vez criado, o tempo para a disponibilidade dos critérios dependerá se o conjunto de relatórios selecionado e a janela de lookback foram usados para quaisquer outros critérios, conforme explicado abaixo:

   * **Configuração única do conjunto de relatórios**: a primeira vez que um conjunto de relatórios é usado com determinada janela de lookback do intervalo de dados, [!DNL Target Recommendations] pode levar de dois a sete dias para baixar completamente os dados comportamentais do conjunto de relatórios selecionado no [!DNL Analytics]. Este período depende da carga do sistema [!DNL Analytics].
   * **Critérios novos ou editados usando um conjunto de relatórios já disponível**: ao criar um novo critério ou editar um critério existente, se o conjunto de relatórios selecionado já tiver sido usado com o [!DNL Target Recommendations], com um intervalo de dados igual ou menor que o intervalo de dados selecionado, os dados serão imediatamente disponibilizados e a configuração única não será necessária. Nesse caso ou se as configurações de um algoritmo forem editadas, enquanto o conjunto de relatórios ou intervalo de dados selecionado não for modificado, o algoritmo será executado ou executado novamente em 12 horas.
   * **O algoritmo contínuo é executado**: os dados fluem do [!DNL Analytics] para [!DNL Target Recommendations] diariamente. Por exemplo, para a recomendação do [!UICONTROL Viewed Affinity], quando um usuário exibe um produto, uma chamada de rastreamento de exibições do produto é passada para o [!DNL Analytics] quase em tempo real. Os dados do [!DNL Analytics] são encaminhados para o [!DNL Target] no início do dia seguinte e o [!DNL Target] executa o algoritmo em menos de 12 horas.

   Para obter mais informações, consulte [Usar o Adobe Analytics com o Target Recommendations](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

1. Defina o **[!UICONTROL Lookback Window]** para determinar o intervalo de tempo de dados históricos disponíveis do comportamento do usuário, ao determinar quais recomendações serão mostradas. Esta opção está disponível para todos os algoritmos, com exceção de [!UICONTROL Items with Similar Attributes] e [!UICONTROL Custom Algorithms].

   ![Controle deslizante da Janela de Pesquisa](assets/data-range.png)

   Se seu site tiver muito tráfego e os comportamentos mudarem frequentemente, escolha uma janela de dados mais curta. Uma janela menor permite que as [!DNL Recommendations] sejam mais responsivas às alterações no mercado e em seu negócio. Por exemplo, uma janela menor significa que as [!DNL Recommendations] irão detectar alterações no comportamento do visitante conforme seus visitantes começam a fazer compras sazonais, tais como compras de volta às aulas ou de Natal, e irá recomendar itens apropriados para estas temporadas de compras.

   Caso não tenha muitos dados ou o comportamento do visitante não seja alterado com frequência, você pode selecionar uma janela maior. No entanto, para muitos sites, uma janela menor resulta em recomendações de maior qualidade.

   Os intervalos de dados disponíveis são:

   | Opção Janela de pesquisa | Frequência atualizada (exibida ao passar o mouse) | Algoritmos compatíveis |
   | --- | --- | --- |
   | Seis horas | O algoritmo é executado a cada 3-6 horas | [!UICONTROL Popularity-Based] algoritmos quando o [!UICONTROL Behavioral Data Source] selecionado for [!DNL Adobe Target] |
   | Um dia | O algoritmo é executado a cada 12-24 horas | [!UICONTROL Popularity-Based] algoritmos |
   | Dois dias | O algoritmo é executado a cada 12-24 horas | <ul><li>[!UICONTROL Popularity-Based] algoritmos</li><li>[!UICONTROL Item-Based] algoritmos</li><li>[!UICONTROL User-Based] algoritmos</li><li>[!UICONTROL Cart-Based] algoritmos</li></ul> |
   | Uma semana | O algoritmo é executado a cada 24-48 horas | <ul><li>[!UICONTROL Popularity-Based] algoritmos</li><li>[!UICONTROL Item-Based] algoritmos</li><li>[!UICONTROL User-Based] algoritmos</li><li>[!UICONTROL Cart-Based] algoritmos</li></ul> |
   | Duas semanas | O algoritmo é executado a cada 24-48 horas | <ul><li>[!UICONTROL Popularity-Based] algoritmos</li><li>[!UICONTROL Item-Based] algoritmos</li><li>Todos os algoritmos [!UICONTROL User-Based]</li><li>[!UICONTROL Cart-Based] algoritmos</li></ul> |
   | Um mês (30 dias) | O algoritmo é executado a cada 24-48 horas | <ul><li>[!UICONTROL Popularity-Based] algoritmos</li><li>[!UICONTROL Item-Based] algoritmos</li><li>[!UICONTROL User-Based] algoritmos</li><li>[!UICONTROL Cart-Based] algoritmos</li></ul> |
   | Dois meses (61 dias) | O algoritmo é executado a cada 24-48 horas | <ul><li>[!UICONTROL Popularity-Based] algoritmos</li><li>[!UICONTROL Item-Based] algoritmos</li><li>[!UICONTROL User-Based] algoritmos</li><li>[!UICONTROL Cart-Based] algoritmos</li></ul> |

## [!UICONTROL Backup Content] {#content}

[!UICONTROL Backup Content] regras determinam o que acontecerá se o número de itens recomendados não preencher seu [design de recomendações](/help/main/c-recommendations/c-design-overview/design-overview.md). É possível que os critérios [!DNL Recommendations] retornem menos recomendações do que suas chamadas de design. Como exemplo, se seu design tiver slots para quatro itens, mas seus critérios fizerem com que apenas dois itens sejam recomendados, você pode deixar os slots restantes vazios, pode usar recomendações de backup para preencher os slots extras ou pode optar por não exibir recomendações.

1. (Opcional) Deslize o botão **[!UICONTROL Partial Design Rendering]** para a posição &quot;ligado&quot;.

   O máximo possível de slots será preenchido, mas o modelo de design pode incluir espaço em branco para os slots restantes. Se essa opção estiver desativada e não houver conteúdo suficiente para preencher todos os slots disponíveis, as recomendações não serão fornecidas e o conteúdo padrão será exibido.

   Ative essa opção se desejar que as recomendações sejam atendidas com slots em branco. Use recomendações de backup se quiser que os slots de recomendação sejam preenchidos com conteúdo com base em seus critérios, com slots vazios preenchidos com conteúdo semelhante ou popular do site, conforme explicado na próxima etapa.

1. (Opcional) Deslize o botão **[!UICONTROL Show Backup Content]** para a posição &quot;ligado&quot;.

   Preencha todos os espaços vazios restantes no design com uma seleção aleatória dos produtos mais visualizados em todo o site.

   O uso de recomendações de backup garante que seu design de recomendação preencha todos os slots disponíveis. Suponha que você tenha um design 4 x 1, conforme ilustrado abaixo:

   ![4 x 1 design](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

   Suponha que seus critérios façam com que apenas dois itens sejam recomendados. Se você habilitar a opção [!UICONTROL Partial Design Rendering], os dois primeiros slots serão preenchidos, mas os dois slots restantes permanecerão vazios. No entanto, se você habilitar a opção [!UICONTROL Show Backup Recommendations], os dois primeiros slots serão preenchidos com base nos critérios especificados e os dois slots restantes serão preenchidos com base nas recomendações de backup.

   A matriz a seguir mostra o resultado que você observará ao usar as opções [!UICONTROL Partial Design Rendering] e [!UICONTROL Backup Content]:

   | Renderização parcial de design | Conteúdo de backup | Resultado |
   |--- |--- |--- |
   | Desativado | Desativado | Se forem retornadas menos recomendações do que o design solicita, o design das recomendações será substituído pelo conteúdo padrão, e nenhuma recomendação será exibida. |
   | Ativado | Desativado | O design é renderizado, mas pode incluir um espaço em branco se forem retornadas menos recomendações do que o design solicita. |
   | Ativado | Ativado | As recomendações de backup preencherão os &quot;slots&quot; de design disponíveis, renderizando totalmente o design.<br>Se a aplicação de regras de inclusão às recomendações de backup limitar o número de recomendações de backup qualificadas ao ponto de não ser possível preencher o design, o design será parcialmente renderizado.<br>Se os critérios não retornarem nenhuma recomendação e as regras de inclusão limitarem as recomendações de backup a zero, o design será substituído pelo conteúdo padrão. |
   | Desativado | Ativado | As recomendações de backup preencherão os &quot;slots&quot; de design disponíveis, renderizando totalmente o design.<br>Se a aplicação de regras de inclusão às recomendações de backup limitar o número de recomendações de backup qualificadas ao ponto de não ser possível preencher o design, o design será substituído pelo conteúdo padrão, e nenhuma recomendação será exibida. |

   Para obter mais informações, consulte [Usar uma recomendação de backup](/help/main/c-recommendations/c-algorithms/backup-recs.md).

1. (Condicional) Se você selecionou **[!UICONTROL Show Backup Content]** na etapa anterior, é possível habilitar **[!UICONTROL Apply inclusion rules to backup recommendations]**.

   As regras de inclusão determinam quais itens são incluídos em suas recomendações. As opções disponíveis dependem do seu negócio vertical.

   Para obter mais detalhes, consulte [Especificar regras de inclusão](#inclusion) abaixo.

## Similaridade de conteúdo {#similarity}

Use as regras de [!UICONTROL Content Similarity] para fazer recomendações com base nos atributos de item ou de mídia.

>[!NOTE]
>
>Se você selecionou **[!UICONTROL Item-Based]**/ **[!UICONTROL Media with Similar Attributes]** como [!UICONTROL Algorithm Type] e [!UICONTROL Algorithm], você tem a opção de definir regras de similaridade de conteúdo.

Similaridade de conteúdo compara palavras-chave de atributo do item e faz recomendações baseadas em quantas palavras-chave itens diferentes têm em comum. Recommendations baseadas em similaridade de conteúdo não requerem dados antigos para providenciar melhores resultados.

Usar a similaridade de conteúdo para gerar recomendações é especialmente eficaz para novos itens, que provavelmente não serão exibidos nas recomendações usando *Pessoas que visualizaram isto, também visualizaram* e outra lógica baseada no comportamento anterior. Você também pode usar similaridade de conteúdo para gerar recomendações úteis para novos visitantes, que não possuem compras antigas ou outros dados de histórico.

Ao selecionar **[!UICONTROL Item-Based]**/ **[!UICONTROL Media with Similar Attributes]**, você tem a opção de criar regras para aumentar ou diminuir a importância de atributos específicos do item em determinadas recomendações. Para itens como livros, você pode querer ampliar a importância de atributos como *gênero*, *autor*, *série*, e assim em diante, para recomendar livros similares.

Como a similaridade de conteúdo usa palavras-chave para comparar itens, alguns atributos, como *mensagem* ou *descrição*, podem introduzir &quot;ruído&quot; à comparação. Você pode criar regras para ignorar estes atributos.

Por padrão, todos atributos são definidos como *Linha de base*. Você não precisa criar uma regra a não ser que queira alterar esta configuração.

>[!NOTE]
>
>O algoritmo de similaridade de conteúdo pode usar amostragem aleatória ao calcular a similaridade entre itens. Como resultado, as classificações de similaridade entre itens podem variar entre execuções de algoritmo.

## Regras de inclusão {#inclusion}

Várias opções ajudam a limitar os itens que são exibidos em suas recomendações. Você pode usar regras de inclusão ao criar critérios ou promoções.

Regras de inclusão são opcionais; no entanto, configurar esses detalhes oferece mais controle sobre os itens que aparecem em suas recomendações. Cada detalhe que você configura limita ainda mais os critérios de exibição.

Por exemplo, você pode escolher exibir apenas sapatos femininos que tenham um inventário de mais de 50 e o preço entre $ 25 e $ 45. Também é possível pesar cada atributo para que os itens mais importantes para sua empresa tenham mais chances de aparecer.

Como outro exemplo, você pode escolher exibir vagas de emprego para visitantes que acessem seu site somente de certas cidades e que tenham os graus acadêmicos necessários.

Opções de regras de inclusão variam pelo negócio vertical. Por padrão, regras de inclusão são aplicadas em recomendações de backup.

>[!IMPORTANT]
>
>Você deve usar regras de inclusão com cuidado. Ela é útil se, por exemplo, sua organização tem regras que exijam que uma marca não seja recomendada se outra está sendo mostrada. No entanto, há um custo de oportunidade para este recurso. Você possivelmente perderia uma porcentagem de elevação ao restringir a exibição de alguns itens, quando, normalmente, seriam exibidos pelos critérios de atividade.

Regras de inclusão são unidas por um E. Todas as regras devem ser cumpridas para incluir um item em uma recomendação.

Para criar uma regra de inclusão simples, como mencionado anteriormente, para exibir apenas sapatos femininos que tenham um inventário de mais de 50 e o preço entre $ 25 e $ 45, siga os seguintes passos:

1. (Condicional) Deslize o botão de alternância **[!UICONTROL Allow recently purchased items to be recommended?]** para a posição &quot;ligado&quot;.

   Esta configuração é baseada no `productPurchasedId`. O comportamento padrão é não recomendar itens comprados anteriormente. Na maioria dos casos, você não deseja promover itens que um cliente comprou recentemente. Ela é útil se você vende itens que pessoas geralmente compram apenas uma vez, como caiaques. Se você vender itens que as pessoas voltam a comprar repetidamente, como shampoo ou outros itens pessoais, você deve ativar essa opção.

1. Defina um intervalo de preço para os produtos que deseja recomendar.
1. Defina o inventário mínimo para os produtos que deseja recomendar.
1. Configure a recomendação para que exiba itens que satisfaçam os critérios.

   Você pode especificar que os itens sejam incluídos apenas quando um dos atributos na lista atender ou não corresponder a uma ou mais condições especificadas.

   Os avaliadores disponíveis dependem do valor que você escolheu na primeira lista suspensa. Você pode listar vários itens. Esses itens são avaliados com OR.

   Regras múltiplas são combinadas com um AND.

   >[!NOTE]
   >
   >Essa opção limita os itens exibidos na recomendação. Isso não afeta em quais páginas a recomendação é exibida. Para limitar onde a recomendação é exibida, selecione as páginas no compositor de experiência.

Para obter mais informações, consulte [Usar regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Ponderação de atributos {#weighting}

É possível adicionar várias regras para &quot;empurrar&quot; o algoritmo com base em informações importantes ou metadados sobre o catálogo de conteúdo para que determinados itens tenham mais probabilidade de ser exibidos.

Por exemplo, você pode aplicar um peso maior aos itens à venda para que eles apareçam com mais frequência na recomendação. Itens que não estão em liquidação não são totalmente excluídos, mas aparecem com menos frequência. Podem ser aplicados muitos pesos ao mesmo algoritmo, e os pesos podem ser testados no tráfego dividido na recomendação.

1. Escolha um valor.

   O valor determina o tipo do item que é mais provável de ser exibido, baseado em um de vários critérios disponíveis.

1. Escolha um avaliador.

1. Insira a palavra-chave para completar os atributos da regra.

   Por exemplo, a regra completa pode ser &quot;Categoria contém sapatos de subsequência de caracteres&quot;.

1. Selecione o peso a ser designado à regra.

   Opções variam de 0 a 100 em incrementos de 25.

1. Adicione regras adicionais, se desejar.

Quando terminar, clique em **[!UICONTROL Create]**.

Se você estiver criando uma nova atividade [!UICONTROL Recommendations] ou editando uma atividade existente, a caixa de seleção **[!UICONTROL Save criteria for later]** será marcada por padrão. Se você não quer usar os critérios em outras atividades, desmarque a caixa de seleção antes de salvar.
