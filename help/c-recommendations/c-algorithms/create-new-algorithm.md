---
keywords: criteria;algorithm;industry vertical;page type;recommendation key;recommendation logic;logic;data range;behavior data source;partial design;backup recommendations;inclusion rules;attribute weighting;current category;custom attribute;last purchased item;last viewed item;most viewed item;most viewed item;favorite category;popularity;recently viewed item;last purchased;last viewed;most viewed;favorite;recently viewed
description: Critérios controlam o conteúdo de suas atividades do Adobe Recommendations. Crie critérios para mostrar as recomendações que são mais apropriadas para sua atividade.
title: Criar critérios
feature: Recommendations
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '2422'
ht-degree: 66%

---


# ![PREMIUM](/help/assets/premium.png) Criar critérios{#create-criteria}

Os critérios em [!UICONTROL Adobe Target] [!UICONTROL Recommendations] controlam o conteúdo das atividades [!UICONTROL Recommendations]. Crie critérios para mostrar as recomendações que são mais apropriadas para sua atividade. Esses critérios usam as ações do visitante para determinar qual conteúdo ou produtos serão exibidos.

As seções a seguir explicam como criar um novo critério.

## Acesse a tela Criar novo critério

Existem vários meios de alcançar a tela [!UICONTROL Criar novos critérios]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* Na tela da biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**, clique em **[!UICONTROL Criar Critérios]** > **[!UICONTROL Criar Critérios]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!DNL Recommendations].
* Ao criar uma atividade [!DNL Recommendations] usando o [!UICONTROL Visual Experience Composer] (VEC), você será levado imediatamente para a tela [!UICONTROL Selecionar Critérios] depois de selecionar um elemento na página e clicar em [!UICONTROL Substituir por Recommendations], [!UICONTROL Inserir Recommendations Antes], ou [!UICONTROL Inserir Recommendations After]. Você pode selecionar um critério disponível ou clicar em **[!UICONTROL Criar critérios]**. Se você criar um novo critério, terá a opção de salvar seus critérios para uso com outras [!DNL Recommendations] atividades. Para obter mais informações, consulte [Criar uma atividade Recommendations](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Ao editar uma [!DNL Recommendations] atividade, clique em uma caixa de [!UICONTROL Localização do Recommendations] em sua página e selecione **[!UICONTROL Alterar critérios]**. Na tela [!UICONTROL Selecionar critérios], clique em **[!UICONTROL Criar critérios]**. Você terá a opção de salvar seu novo critério para uso com outras atividades do [!DNL Recommendations].

As etapas a seguir pressupõem que você acesse a tela [!UICONTROL Criar novos critérios] usando o primeiro método: a tela da biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar critérios]**.

   ![Criar novos critérios](/help/c-recommendations/c-algorithms/assets/CreateNewCriteria_full-new.png)

1. Configure as informações nas seções a seguir.

## Informações básicas   {#info}

1. Digite um **[!UICONTROL Nome dos critérios]**.

   Este é o nome &quot;interno&quot; usado para descrever o critério. Por exemplo, você pode chamar seu critério de &quot;Produtos com margem mais alta&quot;, mas não quer que o título seja exibido publicamente. Veja a próxima etapa para definir o título aberto ao público.

   ![Seção Informações básicas](/help/c-recommendations/c-algorithms/assets/basic-information.png)

1. Insira um **[!UICONTROL Título de exibição]** aberto ao público que irá aparecer na página para qualquer recomendação que use este critério.

   Por exemplo, você pode decidir exibir &quot;Pessoas que viram isto também viram aquilo&quot; ou &quot;Produtos parecidos&quot; quando usar este critério para exibir recomendações.

1. Digite uma breve **[!UICONTROL Descrição]** dos critérios.

   A descrição deve ajudá-lo a identificar os critérios e pode incluir informações sobre a finalidade dos critérios.

1. Selecione um vertical do setor com base nas metas de sua atividade de recomendações.

   | Vertical do setor | Meta |
   |--- |--- |
   | Varejo/Comércio eletrônico | Conversão resultando em compra |
   | Geração de lead/B2B/Serviços financeiros | Conversão sem compra |
   | Mídia/Publicação | Envolvimento |

   Outras opções de critério irão mudar de acordo com o negócio vertical que você selecionar.

1. Selecione um **[!UICONTROL Tipo de página]**.

   Você pode selecionar vários tipos de página.

   Juntos, o negócio vertical e tipos de página são usados para categorizar seu critério salvo, tornando mais fácil o reuso de critérios para outras atividades do [!DNL Recommendations].

1. Selecione uma **[!UICONTROL Chave de recomendação]**.

   Para obter mais informações sobre como basear os critérios em uma chave, consulte [Basear a recomendação em uma chave de recomendação](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

1. Selecione a Lógica **[!UICONTROL de Recomendação]**.

   Para obter mais informações sobre as opções de lógica de recomendação, consulte [Critérios](/help/c-recommendations/c-algorithms/algorithms.md).

   >[!NOTE]
   >
   >Se você selecionar **[!UICONTROL Items]**/ **[!UICONTROL Mídia com atributos semelhantes]**, terá a opção de definir [regras de similaridade de conteúdo](#similarity).

## Fonte de dados {#data-source}

1. Defina o **[!UICONTROL Intervalo de dados]** para determinar o intervalo de tempo de dados históricos disponíveis do comportamento do usuário, ao determinar quais recomendações serão mostradas.

   ![Controle deslizante do intervalo de dados](/help/c-recommendations/c-algorithms/assets/data-range.png)

   Se seu site tiver muito tráfego e os comportamentos mudarem frequentemente, escolha uma janela de dados mais curta. Uma janela menor permite que as [!DNL Recommendations] sejam mais responsivas às alterações no mercado e em seu negócio. Por exemplo, uma janela menor significa que as [!DNL Recommendations] irão detectar alterações no comportamento do visitante conforme seus visitantes começam a fazer compras sazonais, tais como compras de volta às aulas ou de Natal, e irá recomendar itens apropriados para estas temporadas de compras.

   Caso não tenha muitos dados ou o comportamento do visitante não seja alterado com frequência, você pode selecionar uma janela maior. No entanto, para muitos sites, uma janela mais curta resulta em melhores recomendações.

   Os intervalos de dados disponíveis são:

   * Dois dias
   * Uma semana
   * Duas semanas
   * Um mês
   * Dois meses

1. (Condicional) Selecione a **[!UICONTROL Fonte de dados comportamental]** desejada: [!UICONTROL mboxes] ou [!UICONTROL Analytics].

   >[!NOTE]
   >
   >A seção [!UICONTROL Fonte de Dados Comportamental] é exibida somente se sua implementação usar [Analytics para Público alvo](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Seção Fonte de dados comportamental](/help/c-recommendations/c-algorithms/assets/behavioural-data-source.png)

   Se você escolher [!UICONTROL Analytics], selecione o conjunto de relatórios desejado.

   Se o critério usar [!DNL Adobe Analytics] como fonte de dados comportamental, uma vez criado, o tempo de disponibilidade do critério dependerá se o conjunto de relatórios e a janela de pesquisa selecionados tiverem sido usados para qualquer outro critério, conforme explicado abaixo:

   * **Configuração única do conjunto de relatórios**: a primeira vez que um conjunto de relatórios é usado com determinada janela de lookback do intervalo de dados, [!DNL Target Recommendations] pode levar de dois a sete dias para baixar completamente os dados comportamentais do conjunto de relatórios selecionado no [!DNL Analytics]. Esse período depende do [!DNL Analytics] carregamento do sistema.
   * **Critérios novos ou editados usando um conjunto de relatórios já disponível**: ao criar um novo critério ou editar um critério existente, se o conjunto de relatórios selecionado já tiver sido usado com o [!DNL Target Recommendations], com um intervalo de dados igual ou menor que o intervalo de dados selecionado, os dados serão imediatamente disponibilizados e a configuração única não será necessária. Nesse caso ou se as configurações de um algoritmo forem editadas, enquanto o conjunto de relatórios ou intervalo de dados selecionado não for modificado, o algoritmo será executado ou executado novamente em 12 horas.
   * **O algoritmo contínuo é executado**: os dados fluem do [!DNL Analytics] para [!DNL Target Recommendations] diariamente. Por exemplo, para a recomendação [!UICONTROL Afinidade visualizada], quando um usuário exibe um produto, uma chamada de rastreamento de exibições do produto é passada para o [!DNL Analytics] quase em tempo real. Os dados do [!DNL Analytics] são encaminhados para o [!DNL Target] no início do dia seguinte e o [!DNL Target] executa o algoritmo em menos de 12 horas.

   Para obter mais informações, consulte [Usar o Adobe Analytics com o Público alvo Recommendations](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

## Conteúdo {#content}

As regras de conteúdo determinam o que acontece se o número de itens recomendados não preencher o [design de recomendações](/help/c-recommendations/c-design-overview/design-overview.md). É possível que os critérios [!DNL Recommendations] retornem menos recomendações do que seu design solicita. Por exemplo, se seu design tiver slots para quatro itens, mas seus critérios fazem com que apenas dois itens sejam recomendados, você pode deixar os slots restantes vazios ou usar recomendações de backup para preencher os slots extras.

![Seção de conteúdo](/help/c-recommendations/c-algorithms/assets/content.png)

1. (Opcional) Deslize a alternância **[!UICONTROL Renderização parcial de design]** para a posição &quot;ligado&quot;.

   O maior número possível de slots será preenchido, mas o modelo de design pode incluir espaço em branco para os slots restantes. Se essa opção estiver desativada e não houver conteúdo suficiente para preencher todos os slots disponíveis, as recomendações não serão atendidas e o conteúdo padrão será exibido.

   Ative essa opção se desejar que as recomendações sejam servidas com slots em branco. Use as recomendações de backup se desejar que os slots de recomendação sejam preenchidos com conteúdo baseado em seus critérios com slots vazios preenchidos com conteúdo semelhante ou popular do site, conforme explicado na próxima etapa.

1. (Opcional) Deslize a alternância **[!UICONTROL Mostrar Recommendations]** de backup para a posição &quot;ligado&quot;.

   Preencha todos os slots vazios restantes no design com uma seleção aleatória dos produtos mais visualizados de todo o site.

   O uso das recomendações de backup garante que o design da sua recomendação preencha todos os slots disponíveis. Suponha que você tenha um design de 4 x 1, conforme ilustrado abaixo:

   ![Design 4 x 1](/help/c-recommendations/c-design-overview/assets/velocity_example.png)

   Suponha que seus critérios façam com que apenas dois itens sejam recomendados. Se você ativar a opção [!UICONTROL Renderização parcial de design], os dois primeiros slots serão preenchidos, mas os dois restantes permanecerão vazios. No entanto, se você ativar a opção [!UICONTROL Mostrar Recommendations] de Backup, os dois primeiros slots serão preenchidos com base em seus critérios especificados e os dois slots restantes serão preenchidos com base em suas recomendações de backup.

   A matriz a seguir mostra o resultado que você observará ao usar as opções [!UICONTROL Renderização parcial de design] e [!UICONTROL Backup Recommendations]:

   | Renderização parcial de design | Recommendations de backup | Resultado |
   |--- |--- |--- |
   | Desativado | Desativado | Se forem retornadas menos recomendações do que o design solicita, o design das recomendações será substituído pelo conteúdo padrão, e nenhuma recomendação será exibida. |
   | Ativado | Desativado | O design é renderizado, mas pode incluir um espaço em branco se forem retornadas menos recomendações do que o design solicita. |
   | Ativado | Ativado | As recomendações de backup preencherão os &quot;slots&quot; de design disponíveis, renderizando totalmente o design.<br>Se a aplicação de regras de inclusão às recomendações de backup limitar o número de recomendações de backup qualificadas ao ponto de não ser possível preencher o design, o design será parcialmente renderizado.<br>Se os critérios não retornarem nenhuma recomendação e as regras de inclusão limitarem as recomendações de backup a zero, o design será substituído pelo conteúdo padrão. |
   | Desativado | Ativado | As recomendações de backup preencherão os &quot;slots&quot; de design disponíveis, renderizando totalmente o design.<br>Se a aplicação de regras de inclusão às recomendações de backup limitar o número de recomendações de backup qualificadas ao ponto de não ser possível preencher o design, o design será substituído pelo conteúdo padrão, e nenhuma recomendação será exibida. |

   Para obter mais informações, consulte [Use uma recomendação de backup](/help/c-recommendations/c-algorithms/backup-recs.md).

1. (Condicional) Se você selecionou **[!UICONTROL Mostrar Recommendations]** de Backup na etapa anterior, poderá ativar **[!UICONTROL Aplicar regras de inclusão às recomendações de backup]**.

   As regras de inclusão determinam quais itens são incluídos em suas recomendações. As opções disponíveis dependem do seu negócio vertical.

   Para obter mais detalhes, consulte   [Especifique ](#inclusion) as regras de inclusão abaixo.

1. (Opcional) Deslize a alternância **[!UICONTROL Recomendar itens comprados anteriormente]** para a posição &quot;ligado&quot;.

   Esta configuração é baseada no `productPurchasedId`. O comportamento padrão é não recomendar itens comprados anteriormente. Na maioria dos casos, você não deseja promover itens que um cliente comprou recentemente. Ela é útil se você vende itens que pessoas geralmente compram apenas uma vez, como caiaques. Se você vender itens que as pessoas voltam a comprar novamente repetidamente, como shampoo ou outros itens pessoais, você deve ativar essa opção.

## Similaridade de conteúdo {#similarity}

Use as regras de [!UICONTROL Similaridade de conteúdo] para fazer recomendações baseadas em atributos de item ou mídia.

>[!NOTE]
>
>Se você selecionou **[!UICONTROL Items]**/ **[!UICONTROL Mídia com atributos semelhantes]** como sua [lógica de recomendação](#info), terá a opção de definir regras de similaridade de conteúdo.

Similaridade de conteúdo compara palavras-chave de atributo do item e faz recomendações baseadas em quantas palavras-chave itens diferentes têm em comum. Recommendations baseadas em similaridade de conteúdo não requerem dados antigos para providenciar melhores resultados.

Usar similaridade de conteúdo para gerar recomendações é especialmente eficaz para novos itens, que provavelmente não aparecem em recomendações usando *pessoas que viram isto, viram aquilo* e outras lógicas baseadas em comportamento anterior. Você também pode usar similaridade de conteúdo para gerar recomendações úteis para novos visitantes, que não possuem compras antigas ou outros dados de histórico.

Quando você selecionar **[!UICONTROL Itens]**/**[!UICONTROL Mídia com atributos similares]**, você terá a opção de criar regras para aumentar ou reduzir a importância de atributos específicos do item em determinadas recomendações. Para itens como livros, você pode querer ampliar a importância de atributos como *gênero*, *autor*, *série*, e assim em diante, para recomendar livros similares.

![](assets/ContentSimilarity.png)

Como a similaridade de conteúdo usa palavras-chave para comparar itens, alguns atributos, como *mensagem* ou *descrição*, podem introduzir &quot;ruído&quot; à comparação. Você pode criar regras para ignorar estes atributos.

Por padrão, todos atributos são definidos como *Linha de base*. Você não precisa criar uma regra a não ser que queira alterar esta configuração.

>[!NOTE]
>
>O algoritmo de semelhança de conteúdo pode usar amostragem aleatória na computação de similaridade entre itens. Como resultado, as classificações de similaridade entre itens podem variar entre as execuções de algoritmos.

## Regras de inclusão {#inclusion}

Várias opções ajudam a limitar os itens que são exibidos em suas recomendações. Você pode usar regras de inclusão ao criar critérios ou promoções.

![Regras de inclusão](/help/c-recommendations/c-algorithms/assets/inclusion-rules.png)

Regras de inclusão são opcionais; no entanto, configurar esses detalhes oferece mais controle sobre os itens que aparecem em suas recomendações. Cada detalhe que você configura limita ainda mais os critérios de exibição.

Por exemplo, você pode escolher exibir apenas sapatos femininos que tenham um inventário de mais de 50 e o preço entre $ 25 e $ 45. Também é possível pesar cada atributo para que os itens mais importantes para sua empresa tenham mais chances de aparecer.

Como outro exemplo, você pode escolher exibir vagas de emprego para visitantes que acessem seu site somente de certas cidades e que tenham os graus acadêmicos necessários.

Opções de regras de inclusão variam pelo negócio vertical. Por padrão, regras de inclusão são aplicadas em recomendações de backup.

>[!IMPORTANT]
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

Para obter mais informações, consulte [Usar regras de inclusão dinâmicas e estáticas](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Ponderação de atributos {#weighting}

É possível adicionar várias regras para &quot;ajustar&quot; o algoritmo com base em informações importantes ou metadados sobre o catálogo de conteúdo, de modo que seja mais provável que determinados itens sejam exibidos.

Por exemplo, você pode aplicar um peso maior a itens em liquidação, para que apareçam com mais frequência na recomendação. Itens que não estão em liquidação não são totalmente excluídos, mas aparecem com menos frequência. Podem ser aplicados muitos pesos ao mesmo algoritmo, e os pesos podem ser testados no tráfego dividido na recomendação.

1. Escolha um valor.

   O valor determina o tipo do item que é mais provável de ser exibido, baseado em um de vários critérios disponíveis.

1. Escolha um avaliador.

1. Insira a palavra-chave para completar os atributos da regra.

   Por exemplo, a regra completa pode ser &quot;a Categoria contém sapatos de subsequência de caracteres&quot;.

   ![](assets/Recs_AttributeWeighting.png)

1. Selecione o peso a ser designado à regra.

   Opções variam de 0 a 100 em incrementos de 25.

1. Adicione regras adicionais, se desejar.

Ao terminar, clique em **[!UICONTROL Salvar]**.

Se você está criando uma nova atividade do [!UICONTROL Recommendations] ou editando uma atividade existente, a caixa de seleção **[!UICONTROL Salvar critérios para mais tarde]** será selecionada por padrão. Se você não quer usar os critérios em outras atividades, desmarque a caixa de seleção antes de salvar.

## Vídeo de treinamento: Criar critérios no Recommendations (12:33) ![Etiqueta do tutorial](/help/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar critérios
* Criar sequências de critérios
* Upload dos critérios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
