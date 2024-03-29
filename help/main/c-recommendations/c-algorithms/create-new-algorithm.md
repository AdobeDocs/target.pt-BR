---
keywords: critérios;algoritmo;vertical do setor;tipo de página;chave de recomendação;lógica de recomendação;lógica;intervalo de dados;janela de lookback;fonte de dados de comportamento;design parcial;recomendações de backup;regras de inclusão;ponderação de atributos;categoria atual;atributo personalizado;último item comprado;último item exibido;item mais exibido;item mais exibido;categoria favorita;popularidade;item exibido recentemente;última comprado;última exibido;mais exibido;favorito;exibido recentemente
description: Saiba como criar critérios que controlam o conteúdo de suas atividades do Adobe Recommendations para mostrar as recomendações mais apropriadas para sua atividade.
title: Como criar critérios no Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 3f4f59b2-6637-4c33-bf17-bff11bef7173
source-git-commit: b5fbf23e9c2dfd76565fd6287ae07df2b7df2e21
workflow-type: tm+mt
source-wordcount: '2842'
ht-degree: 52%

---

# Criar critérios

Critérios no [!UICONTROL Adobe Target] [!UICONTROL Recommendations] controlar o conteúdo do [!UICONTROL Recommendations] atividades. Crie critérios para mostrar as recomendações que são mais apropriadas para sua atividade. Esses critérios usam as ações do visitante para determinar qual conteúdo ou produtos exibir.

As seções a seguir explicam como criar um novo critério.

## Acessar a tela Criar novos critérios

Existem vários meios de alcançar a tela [!UICONTROL Criar novos critérios]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* No **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]** tela da biblioteca, clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar critérios]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!DNL Recommendations].
* Ao criar uma [!DNL Recommendations] atividade usando o [!UICONTROL Visual Experience Composer] (VEC), você será levado imediatamente ao [!UICONTROL Selecionar critério] depois de selecionar um elemento na página e clicar em [!UICONTROL Substituir por Recommendations], [!UICONTROL Inserir Recommendations antes de]ou [!UICONTROL Inserir Recommendations após]. Você pode selecionar um critério disponível ou clicar em **[!UICONTROL Criar critérios]**. Se criar um novo critério, você tem a opção de salvar seu critério para uso com outras [!DNL Recommendations] atividades. Para obter mais informações, consulte [Criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Ao editar uma [!DNL Recommendations] atividade, clique em uma caixa de [!UICONTROL Localização do Recommendations] em sua página e selecione **[!UICONTROL Alterar critérios]**. No [!UICONTROL Selecionar critério] clique em **[!UICONTROL Criar critérios]**. Você terá a opção de salvar seu novo critério para uso com outras atividades do [!DNL Recommendations].

As etapas a seguir pressupõem que você acesse o [!UICONTROL Criar novos critérios] usando o primeiro método: a variável **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]** tela da biblioteca.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar critérios]**.

   ![Criar novos critérios](assets/CreateNewCriteria_full-new.png)

1. Configure as informações nas seções a seguir.

## [!UICONTROL Informações básicas] {#info}

1. Digite um **[!UICONTROL Nome dos critérios]**.

   Este é o nome &quot;interno&quot; usado para descrever o critério. Por exemplo, você pode chamar seu critério de &quot;Produtos com margem mais alta&quot;, mas não quer que o título seja exibido publicamente. Veja a próxima etapa para definir o título aberto ao público.

   ![seção Informações básicas](assets/basic-information.png)

1. Insira um **[!UICONTROL Título de exibição]** aberto ao público que irá aparecer na página para qualquer recomendação que use este critério.

   Por exemplo, você pode decidir exibir &quot;Pessoas que viram isto também viram aquilo&quot; ou &quot;Produtos parecidos&quot; quando usar este critério para exibir recomendações.

1. Digite uma breve **[!UICONTROL Descrição]** dos critérios.

   A descrição deve ajudar a identificar o critério e pode incluir informações sobre o propósito do critério.

1. Selecione um negócio vertical com base nas metas da sua atividade de recomendações.

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
   | [!UICONTROL Baseado em carrinho] | Faça recomendações com base no conteúdo do carrinho do usuário. | <ul><li>Pessoas que visualizaram isto, visualizaram aquilo</li><li>Pessoas que visualizaram e compraram essas</li><li>Pessoas que compraram isto, compraram aquilo</li></ul> |
   | [!UICONTROL Baseado em popularidade] | Faça recomendações com base na popularidade geral de um item em todo o site ou na popularidade de itens na categoria, marca, gênero e assim por diante favoritas ou mais visualizadas de um usuário. | <ul><li>Mais visualizados no site</li><li>Mais visualizados por categoria</li><li>Mais visualizados pelo atributo de item</li><li>Mais vendidos em todo o site</li><li>Mais vendidos por categoria</li><li>Mais Vendidos por Atributo de Item</li><li>Comece pela métrica do Analytics</li></ul> |
   | [!UICONTROL Baseado em Item] | Fazer recomendações com base na localização de itens semelhantes a um item que o usuário está visualizando atualmente ou que visualizou recentemente. | <ul><li>Pessoas que visualizaram isto, visualizaram aquilo</li><li>Pessoas que visualizaram isto, compraram aquilo</li><li>Pessoas que compraram isto, compraram aquilo</li><li>Itens com atributos similares</li></ul> |
   | [!UICONTROL Baseado em usuário] | Faça recomendações com base no comportamento do usuário. | <ul><li>Itens visualizados recentemente </li><li>Recomendado para você</li></ul> |
   | [!UICONTROL Critérios personalizados] | Faça recomendações com base em um arquivo personalizado que você fez upload. | <ul><li>Algoritmo personalizado</li></ul> |

   >[!NOTE]
   >
   >Se você selecionar **[!UICONTROL Itens]**/ **[!UICONTROL Mídia com atributos similares]**, você terá a opção de definir [regras de similaridade de conteúdo](#similarity).

1. Conforme necessário, selecione um **Atributo de item** e **Atributo de perfil a corresponder**, um **Chave de recomendação**, **Chave do filtro**, e/ou **Métrica do Analytics** para configurar o algoritmo.

As opções de configuração de algoritmo restantes variam dependendo do algoritmo selecionado. Para concluir a configuração do algoritmo, selecione um [!UICONTROL Chave de recomendação], [!UICONTROL Chave do filtro], [!UICONTROL Base de co-ocorrência], [!UICONTROL Métrica do Analytics], e/ou [!UICONTROL Atributo de item] e [!UICONTROL Atributo de perfil a corresponder].

Para obter mais informações sobre a escolha de um [!UICONTROL Chave de recomendação], consulte [Basear a recomendação em uma chave de recomendação](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## [!UICONTROL Fonte de dados] {#data-source}

1. Selecione o desejado **[!UICONTROL Fonte de dados comportamentais]**: [!UICONTROL Adobe Target] ou [!UICONTROL Analytics].

   >[!NOTE]
   >
   >A variável [!UICONTROL Fonte de dados comportamentais] é exibida somente se sua implementação usar [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).

   ![Seção Fonte de dados comportamentais](assets/data-source.png)

   Se você escolher [!UICONTROL Analytics], selecione o conjunto de relatórios desejado.

   Se os critérios usarem [!DNL Adobe Analytics] como a fonte de dados comportamentais, depois de criada, o tempo para a disponibilidade dos critérios depende de o conjunto de relatórios selecionado e a janela de lookback terem sido usados para quaisquer outros critérios, conforme explicado abaixo:

   * **Configuração única do conjunto de relatórios**: a primeira vez que um conjunto de relatórios é usado com determinada janela de lookback do intervalo de dados, [!DNL Target Recommendations] pode levar de dois a sete dias para baixar completamente os dados comportamentais do conjunto de relatórios selecionado no [!DNL Analytics]. Esse intervalo de tempo depende do [!DNL Analytics] carregamento do sistema.
   * **Critérios novos ou editados usando um conjunto de relatórios já disponível**: ao criar um novo critério ou editar um critério existente, se o conjunto de relatórios selecionado já tiver sido usado com o [!DNL Target Recommendations], com um intervalo de dados igual ou menor que o intervalo de dados selecionado, os dados serão imediatamente disponibilizados e a configuração única não será necessária. Nesse caso ou se as configurações de um algoritmo forem editadas, enquanto o conjunto de relatórios ou intervalo de dados selecionado não for modificado, o algoritmo será executado ou executado novamente em 12 horas.
   * **O algoritmo contínuo é executado**: os dados fluem do [!DNL Analytics] para [!DNL Target Recommendations] diariamente. Por exemplo, para a recomendação [!UICONTROL Afinidade visualizada], quando um usuário exibe um produto, uma chamada de rastreamento de exibições do produto é passada para o [!DNL Analytics] quase em tempo real. Os dados do [!DNL Analytics] são encaminhados para o [!DNL Target] no início do dia seguinte e o [!DNL Target] executa o algoritmo em menos de 12 horas.

   Para obter mais informações, consulte [Usar o Adobe Analytics com o Target Recommendations](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

1. Defina o **[!UICONTROL Janela de pesquisa]** para determinar o intervalo de tempo de dados históricos disponíveis do comportamento do usuário, ao determinar quais recomendações serão mostradas. Esta opção está disponível para todos os algoritmos, com exceção dos Itens com Atributos similares e Algoritmos personalizados.

   ![Controle deslizante da janela de pesquisa](assets/data-range.png)

   Se seu site tiver muito tráfego e os comportamentos mudarem frequentemente, escolha uma janela de dados mais curta. Uma janela menor permite que as [!DNL Recommendations] sejam mais responsivas às alterações no mercado e em seu negócio. Por exemplo, uma janela menor significa que as [!DNL Recommendations] irão detectar alterações no comportamento do visitante conforme seus visitantes começam a fazer compras sazonais, tais como compras de volta às aulas ou de Natal, e irá recomendar itens apropriados para estas temporadas de compras.

   Caso não tenha muitos dados ou o comportamento do visitante não seja alterado com frequência, você pode selecionar uma janela maior. No entanto, para muitos sites, uma janela menor resulta em recomendações de maior qualidade.

   Os intervalos de dados disponíveis são:

   | Opção Janela de pesquisa | Frequência atualizada (exibida ao passar o mouse) | Algoritmos compatíveis |
   | --- | --- | --- |
   | Seis horas | O algoritmo é executado a cada 3-6 horas | [!UICONTROL Baseado em popularidade] algoritmos quando o [!UICONTROL Fonte de dados comportamentais] é [!DNL Adobe Target] |
   | Um dia | O algoritmo é executado a cada 12-24 horas | [!UICONTROL Baseado em popularidade] algoritmos |
   | Dois dias | O algoritmo é executado a cada 12-24 horas | <ul><li>[!UICONTROL Baseado em popularidade] algoritmos</li><li>[!UICONTROL Baseado em Item] algoritmos</li><li>[!UICONTROL Baseado em usuário] algoritmos</li><li>[!UICONTROL Baseado em carrinho] algoritmos</li></ul> |
   | Uma semana | O algoritmo é executado a cada 24-48 horas | <ul><li>[!UICONTROL Baseado em popularidade] algoritmos</li><li>[!UICONTROL Baseado em Item] algoritmos</li><li>[!UICONTROL Baseado em usuário] algoritmos</li><li>[!UICONTROL Baseado em carrinho] algoritmos</li></ul> |
   | Duas semanas | O algoritmo é executado a cada 24-48 horas | <ul><li>[!UICONTROL Baseado em popularidade] algoritmos</li><li>[!UICONTROL Baseado em Item] algoritmos</li><li>Todos [!UICONTROL Baseado em usuário] algoritmos</li><li>[!UICONTROL Baseado em carrinho] algoritmos</li></ul> |
   | Um mês (30 dias) | O algoritmo é executado a cada 24-48 horas | <ul><li>[!UICONTROL Baseado em popularidade] algoritmos</li><li>[!UICONTROL Baseado em Item] algoritmos</li><li>[!UICONTROL Baseado em usuário] algoritmos</li><li>[!UICONTROL Baseado em carrinho] algoritmos</li></ul> |
   | Dois meses (61 dias) | O algoritmo é executado a cada 24-48 horas | <ul><li>[!UICONTROL Baseado em popularidade] algoritmos</li><li>[!UICONTROL Baseado em Item] algoritmos</li><li>[!UICONTROL Baseado em usuário] algoritmos</li><li>[!UICONTROL Baseado em carrinho] algoritmos</li></ul> |

## [!UICONTROL Conteúdo de backup] {#content}

[!UICONTROL Conteúdo de backup] as regras determinam o que acontecerá se o número de itens recomendados não preencher o [design de recomendações](/help/main/c-recommendations/c-design-overview/design-overview.md). É possível que [!DNL Recommendations] critérios para retornar menos recomendações do que o exigido pelo design. Como exemplo, se seu design tiver slots para quatro itens, mas seus critérios fizerem com que apenas dois itens sejam recomendados, você pode deixar os slots restantes vazios, pode usar recomendações de backup para preencher os slots extras ou pode optar por não exibir recomendações.

![Seção de conteúdo](assets/content.png)

1. (Opcional) Deslize o **[!UICONTROL Renderização de design parcial]** alterne para a posição &quot;ligado&quot;.

   O máximo possível de slots será preenchido, mas o modelo de design pode incluir espaço em branco para os slots restantes. Se essa opção estiver desativada e não houver conteúdo suficiente para preencher todos os slots disponíveis, as recomendações não serão fornecidas e o conteúdo padrão será exibido.

   Ative essa opção se desejar que as recomendações sejam atendidas com slots em branco. Use recomendações de backup se quiser que os slots de recomendação sejam preenchidos com conteúdo com base em seus critérios, com slots vazios preenchidos com conteúdo semelhante ou popular do site, conforme explicado na próxima etapa.

1. (Opcional) Deslize o **[!UICONTROL Mostrar conteúdo do backup]** alterne para a posição &quot;ligado&quot;.

   Preencha todos os espaços vazios restantes no design com uma seleção aleatória dos produtos mais visualizados em todo o site.

   O uso de recomendações de backup garante que seu design de recomendação preencha todos os slots disponíveis. Suponha que você tenha um design 4 x 1, conforme ilustrado abaixo:

   ![Design 4 x 1](/help/main/c-recommendations/c-design-overview/assets/velocity_example.png)

   Suponha que seus critérios façam com que apenas dois itens sejam recomendados. Se você habilitar a opção [!UICONTROL Renderização de design parcial] os dois primeiros slots estarão preenchidos, mas os dois slots restantes permanecerão vazios. No entanto, se você ativar a opção [!UICONTROL Mostrar Recommendations de backup] , os dois primeiros slots serão preenchidos com base nos critérios especificados e os dois slots restantes serão preenchidos com base nas recomendações de backup.

   A matriz a seguir mostra o resultado que você observará ao usar o [!UICONTROL Renderização de design parcial] e [!UICONTROL Conteúdo de backup] opções:

   | Renderização parcial de design | Conteúdo de backup | Resultado |
   |--- |--- |--- |
   | Desativado | Desativado | Se forem retornadas menos recomendações do que o design solicita, o design das recomendações será substituído pelo conteúdo padrão, e nenhuma recomendação será exibida. |
   | Ativado | Desativado | O design é renderizado, mas pode incluir um espaço em branco se forem retornadas menos recomendações do que o design solicita. |
   | Ativado | Ativado | As recomendações de backup preencherão os &quot;slots&quot; de design disponíveis, renderizando totalmente o design.<br>Se a aplicação de regras de inclusão às recomendações de backup limitar o número de recomendações de backup qualificadas ao ponto de não ser possível preencher o design, o design será parcialmente renderizado.<br>Se os critérios não retornarem nenhuma recomendação e as regras de inclusão limitarem as recomendações de backup a zero, o design será substituído pelo conteúdo padrão. |
   | Desativado | Ativado | As recomendações de backup preencherão os &quot;slots&quot; de design disponíveis, renderizando totalmente o design.<br>Se a aplicação de regras de inclusão às recomendações de backup limitar o número de recomendações de backup qualificadas ao ponto de não ser possível preencher o design, o design será substituído pelo conteúdo padrão, e nenhuma recomendação será exibida. |

   Para obter mais informações, consulte [Usar uma recomendação de backup](/help/main/c-recommendations/c-algorithms/backup-recs.md).

1. (Condicional) Se você selecionou **[!UICONTROL Mostrar conteúdo do backup]** na etapa anterior, é possível ativar **[!UICONTROL Aplicar regras de inclusão às recomendações de backup]**.

   As regras de inclusão determinam quais itens são incluídos em suas recomendações. As opções disponíveis dependem do seu negócio vertical.

   Para obter mais detalhes, consulte  [Especificar regras de inclusão](#inclusion) abaixo.

## Similaridade de conteúdo {#similarity}

Use as regras de [!UICONTROL Similaridade de conteúdo] para fazer recomendações baseadas em atributos de item ou mídia.

>[!NOTE]
>
>Se você selecionou **[!UICONTROL Baseado em Item]**/ **[!UICONTROL Mídia com atributos similares]** Como seu Tipo de algoritmo e Algoritmo, você tem a opção de definir regras de similaridade de conteúdo.

Similaridade de conteúdo compara palavras-chave de atributo do item e faz recomendações baseadas em quantas palavras-chave itens diferentes têm em comum. Recommendations baseadas em similaridade de conteúdo não requerem dados antigos para providenciar melhores resultados.

Usar similaridade de conteúdo para gerar recomendações é especialmente eficaz para novos itens, que provavelmente não aparecem em recomendações usando *pessoas que viram isto, viram aquilo* e outras lógicas baseadas em comportamento anterior. Você também pode usar similaridade de conteúdo para gerar recomendações úteis para novos visitantes, que não possuem compras antigas ou outros dados de histórico.

Ao selecionar **[!UICONTROL Baseado em Item]**/ **[!UICONTROL Mídia com atributos similares]**, você tem a opção de criar regras para aumentar ou diminuir a importância de atributos de item específicos em determinadas recomendações. Para itens como livros, você pode querer ampliar a importância de atributos como *gênero*, *autor*, *série*, e assim em diante, para recomendar livros similares.

![Imagem ContentSimilarity](assets/ContentSimilarity.png)

Como a similaridade de conteúdo usa palavras-chave para comparar itens, alguns atributos, como *mensagem* ou *descrição*, podem introduzir &quot;ruído&quot; à comparação. Você pode criar regras para ignorar estes atributos.

Por padrão, todos atributos são definidos como *Linha de base*. Você não precisa criar uma regra a não ser que queira alterar esta configuração.

>[!NOTE]
>
>O algoritmo de similaridade de conteúdo pode usar amostragem aleatória ao calcular a similaridade entre itens. Como resultado, as classificações de similaridade entre itens podem variar entre execuções de algoritmo.

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

1. (Condicional) Deslize o **[!UICONTROL Permitir que itens adquiridos recentemente sejam recomendados?]** alterne para a posição &quot;ligado&quot;.

   Esta configuração é baseada no `productPurchasedId`. O comportamento padrão é não recomendar itens comprados anteriormente. Na maioria dos casos, você não deseja promover itens que um cliente comprou recentemente. Ela é útil se você vende itens que pessoas geralmente compram apenas uma vez, como caiaques. Se você vender itens que as pessoas voltam a comprar repetidamente, como shampoo ou outros itens pessoais, você deve ativar essa opção.

1. Defina um intervalo de preço para os produtos que deseja recomendar.
1. Defina o inventário mínimo para os produtos que deseja recomendar.
1. Configure a recomendação para que exiba itens que satisfaçam os critérios.

   ![Imagem Recs_InclusionRules](assets/Recs_InclusionRules.png)

   Você pode especificar que os itens sejam incluídos apenas quando um dos atributos na lista atender ou não corresponder a uma ou mais condições especificadas.

   Os avaliadores disponíveis dependem do valor que você escolheu na primeira lista suspensa. Você pode listar vários itens. Esses itens são avaliados com OR.

   Regras múltiplas são combinadas com um AND.

   >[!NOTE]
   >
   >Essa opção limita os itens exibidos na recomendação. Isso não afeta em quais páginas a recomendação é exibida. Para limitar onde a recomendação é exibida, selecione as páginas no compositor de experiência.

Para obter mais informações, consulte [Uso das regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Ponderação de atributos {#weighting}

É possível adicionar várias regras para &quot;empurrar&quot; o algoritmo com base em informações importantes ou metadados sobre o catálogo de conteúdo para que determinados itens tenham mais probabilidade de ser exibidos.

Por exemplo, você pode aplicar um peso maior a itens em liquidação, para que apareçam com mais frequência na recomendação. Itens que não estão em liquidação não são totalmente excluídos, mas aparecem com menos frequência. Podem ser aplicados muitos pesos ao mesmo algoritmo, e os pesos podem ser testados no tráfego dividido na recomendação.

1. Escolha um valor.

   O valor determina o tipo do item que é mais provável de ser exibido, baseado em um de vários critérios disponíveis.

1. Escolha um avaliador.

1. Insira a palavra-chave para completar os atributos da regra.

   Por exemplo, a regra completa pode ser &quot;Categoria contém sapatos de subsequência de caracteres&quot;.

   ![Recs_AttributePonderando imagem](assets/Recs_AttributeWeighting.png)

1. Selecione o peso a ser designado à regra.

   Opções variam de 0 a 100 em incrementos de 25.

1. Adicione regras adicionais, se desejar.

Ao terminar, clique em **[!UICONTROL Salvar]**.

Se você está criando uma nova atividade do [!UICONTROL Recommendations] ou editando uma atividade existente, a caixa de seleção **[!UICONTROL Salvar critérios para mais tarde]** será selecionada por padrão. Se você não quer usar os critérios em outras atividades, desmarque a caixa de seleção antes de salvar.

## Vídeo de treinamento: criar critérios no Recommendations (12:33) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar critérios
* Criar sequências de critérios
* Upload dos critérios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
