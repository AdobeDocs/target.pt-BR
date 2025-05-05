---
keywords: recomendações algoritmos;treinamento de modelo;serviço de modelo;entrega de conteúdo;baseado em item;baseado em usuário;baseado em popularidade;baseado em carrinho;critérios personalizados
description: Saiba mais sobre os algoritmos usados no [!DNL Target Recommendations], incluindo treinamento e fornecimento de modelos.
title: Onde posso aprender sobre a ciência por trás dos algoritmos Recommendations do Target?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
mini-toc-levels: 2
exl-id: c156952b-8eda-491d-a68e-d3d09846f640
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '2739'
ht-degree: 0%

---

# A ciência por trás dos algoritmos de recomendações do Target

Uma descrição detalhada dos algoritmos usados em [!DNL Adobe Target Recommendations], incluindo os detalhes lógicos e matemáticos do treinamento de modelos e o processo de veiculação de modelos.

O treinamento de modelo é o processo de como as recomendações são geradas pelos algoritmos de aprendizado [!DNL Adobe Target]. A veiculação de modelos é a forma como o [!DNL Target] fornece recomendações aos visitantes do site (também conhecida como entrega de conteúdo).

[!DNL Target] inclui os seguintes tipos amplos de algoritmos em [!DNL Recommendations]:

* **Algoritmos baseados em itens**: inclua algoritmos que sigam a lógica &quot;As pessoas que visualizaram/compraram este item também visualizaram/compraram esses itens.&quot; Esses algoritmos são agrupados no termo geral filtragem colaborativa item-item, bem como em algoritmos [!UICONTROL Items with Similar Attributes].

* **Algoritmos baseados em usuário**: inclua os algoritmos [!UICONTROL Recently Viewed] e [!UICONTROL Recommended for You].

* **Algoritmos baseados em popularidade**: inclua algoritmos que retornam os itens mais vistos ou mais comprados no site, ou os mais vistos ou mais comprados por categoria ou atributo de item.

* **Algoritmos baseados em carrinho**: inclua recomendações baseadas em vários itens com a lógica &quot;pessoas que visualizaram/compraram esses itens, também visualizaram/compraram esses itens&quot;.

* **Critérios personalizados**: inclua recomendações com base em arquivos personalizados carregados em [!DNL Target].

>[!NOTE]
>
>Para obter informações mais gerais sobre cada tipo de algoritmo e os algoritmos individuais, consulte [Basear a recomendação em uma chave de recomendação](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

Muitos dos algoritmos listados acima baseiam-se na presença de uma ou várias chaves. Essas chaves são usadas para recuperar itens semelhantes no momento da entrega do conteúdo (quando as recomendações são feitas). As chaves especificadas pelo cliente podem incluir o item atual que alguém está visualizando, o último item visualizado ou comprado, o item mais visualizado, a categoria atual ou a categoria favorita desse visitante. Outros algoritmos, como baseado em carrinho ou em recomendações do usuário, usam chaves implícitas (que não podem ser configuradas pelo cliente). Para obter mais informações, consulte *Chaves de recomendação*, em [Basear a recomendação em uma chave de recomendação](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys). No entanto, observe que essas chaves são relevantes somente no momento do fornecimento do modelo (entrega de conteúdo). Essas chaves não afetam a lógica de tempo de treinamento &quot;offline&quot; ou do modelo.

As seções a seguir agrupam algoritmos de uma maneira um pouco diferente dos tipos de algoritmo descritos acima. O agrupamento a seguir é baseado na similaridade da lógica de treinamento do modelo.

## Filtragem colaborativa de item-item

Os algoritmos incluem:

* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Os algoritmos de recomendação do filtro colaborativo Item-Item são baseados na ideia de que você deve usar os padrões de comportamento de muitos usuários (portanto, colaborativos) para fornecer recomendações úteis para um determinado item (por exemplo, filtrar o catálogo de itens possíveis a serem recomendados). Embora existam vários algoritmos diferentes que se enquadram no âmbito geral da [filtragem colaborativa](https://en.wikipedia.org/wiki/Collaborative_filtering), esses algoritmos universalmente usam fontes de dados comportamentais como entradas. No [!DNL Target Recommendations], essas entradas são exibições e compras de itens por usuários.

Para o algoritmo &quot;pessoas que visualizaram/compraram esse item também visualizaram/compraram esses itens&quot;, o objetivo é calcular uma similaridade s(A,B) entre todos os pares de itens. Para um determinado item A, as principais recomendações são ordenadas por sua similaridade s(A,B).

Um exemplo de similaridade é a coocorrência entre itens: uma contagem simples do número de usuários que compraram ambos os itens. Embora intuitiva, essa métrica é ingênua, pois é tendenciosa para recomendar itens populares. Por exemplo, se em um supermercado a maioria das pessoas comprar pão, o pão terá uma alta coocorrência com todos os itens, mas não é necessariamente uma boa recomendação. [!DNL Target] em vez disso, usa uma métrica de similaridade mais sofisticada conhecida como LLR (log probability ratio, taxa de probabilidade de log). Essa quantidade é grande quando a probabilidade de dois itens, A e B, coocorrendo é muito diferente da probabilidade deles não coocorrendo. Para concretude, considere um caso do algoritmo [!UICONTROL People Who Viewed This, Bought That]. A similaridade LLR é grande quando a probabilidade de B ter sido comprado é *não*, independentemente de alguém ter visto A.

Por exemplo, se

![Fórmula para o algoritmo exibido/comprado](assets/formula.png)

então o item B não deve ser recomendado com o item A. Detalhes completos deste cálculo de similaridade da taxa de probabilidade de log são fornecidos [neste PDF](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf).

O fluxo lógico da implementação real do algoritmo é mostrado no diagrama esquemático a seguir:

![Diagrama esquemático de um algoritmo visualizado/comprado](assets/diagram1.png)

Veja a seguir os detalhes dessas etapas:

* **Dados de entrada**: dados comportamentais, na forma de exibições e compras de visitantes coletados quando você [implementa o Target](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} ou o [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}.

* **Treinamento de modelo**:

   * **Limpeza e amostragem de dados**: para algoritmos com retrospectiva de N dias, os dados comportamentais são filtrados pela primeira vez para incluir apenas esses N dias de dados. As regras de coleção e as exclusões globais são aplicadas para remover quaisquer itens que não devem ser recomendados. Por fim, todos os visitantes que interagiram com mais de 1.000 itens têm seus dados de uso amostrados para apenas 1.000 itens.
   * **Cálculo de similaridade de item**: esta é a etapa computacional principal: calcular a similaridade da taxa de probabilidade do log entre todos os pares de itens candidatos e classificar pares de itens por essa pontuação de similaridade.
   * **Filtragem offline**: finalmente, todos os outros filtros dinâmicos aplicáveis são aplicados (por exemplo, exclusões de categoria dinâmica). Após essa etapa, as recomendações pré-calculadas são armazenadas em cache globalmente para estarem disponíveis para veiculação.

* **Serviço de modelo**: o conteúdo do Recommendations é entregue a partir da [rede &quot;Edge&quot; global](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934) da [!DNL Target]. Quando as solicitações da mbox são feitas para [!DNL Target] e é determinado que o conteúdo das recomendações deve ser entregue à página, a solicitação da [chave de item](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys) apropriada para o algoritmo de recomendações é analisada a partir da solicitação ou pesquisada a partir do perfil do usuário e, em seguida, usada para recuperar as recomendações computadas nas etapas anteriores. Filtros dinâmicos adicionais são aplicados neste momento, antes que o [design](/help/main/c-recommendations/c-design-overview/create-design.md) apropriado seja renderizado.

## Similaridade de conteúdo

Algoritmo incluído:

* [!UICONTROL Items with Similar Attributes]

Neste tipo de algoritmo, dois itens são considerados relacionados se seus nomes e descrições textuais são semanticamente semelhantes. Diferentemente da maioria dos algoritmos de recomendações, nos quais as fontes de dados comportamentais devem ser usadas, os algoritmos de similaridade de conteúdo usam metadados de catálogos de produtos para derivar a similaridade entre itens. [!DNL Target] é, portanto, capaz de orientar recomendações nos chamados cenários de &quot;início frio&quot;, onde nenhum dado comportamental foi coletado (por exemplo, no início de uma atividade [!DNL Target]).

Embora os aspectos de veiculação e entrega de conteúdo dos algoritmos de similaridade de conteúdo do [!DNL Target] sejam idênticos a outros algoritmos baseados em itens, as etapas de treinamento do modelo são drasticamente diferentes e envolvem uma série de etapas de processamento e pré-processamento de linguagem natural, conforme mostrado no diagrama a seguir. O núcleo do cálculo de similaridade é o uso da similaridade do cosseno de vetores tf-idf modificados que representam cada item no catálogo.

![Diagrama mostrando o fluxo do processo de similaridade de conteúdo](assets/diagram2.png)

Veja a seguir os detalhes dessas etapas:

* **Dados de entrada**: conforme descrito anteriormente, este algoritmo se baseia exclusivamente nos dados de catálogo (assimilados para [!DNL Target] por meio de um [Feed de Catálogo, da API de Entidades ou de atualizações na página](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank}.

* **Treinamento de modelo**:

   * **Extração de atributo**: após a aplicação de filtros estáticos regulares, regras de catálogo e exclusões globais, este algoritmo extrai campos textuais relevantes do esquema de entidade. [!DNL Target] usa automaticamente os campos de nome, mensagem e categoria dos atributos de entidade e tenta extrair quaisquer campos de sequência de caracteres dos [atributos de entidade](/help/main/c-recommendations/c-products/entity-attributes.md) personalizados. Esse processo é feito garantindo que a maioria dos valores desse campo não seja analisável como um número, data ou booleano.
   * **Remoção de palavras irrelevantes e de palavras de interrupção**: para obter uma correspondência de similaridade de texto mais precisa, é prudente remover palavras de &quot;interrupção&quot; muito comuns que não alteram significativamente o significado de um item (por exemplo, &quot;era&quot;, &quot;é&quot;, &quot;e&quot; e assim por diante). Da mesma forma, o radical refere-se ao processo de redução de palavras com sufixos diferentes para sua palavra raiz, que tem um significado idêntico (por exemplo, &quot;conectar&quot;, &quot;conectar&quot; e &quot;conexão&quot; têm a mesma palavra raiz: &quot;conectar&quot;). [!DNL Target] usa o lematizador de Snowball. O [!DNL Target] executa a detecção automática de idioma primeiro e pode fazer a remoção de palavras de interrupção para até 50 idiomas e a ramificação para 18 idiomas.
   * **n-grama criação**: após as etapas anteriores, cada palavra é tratada como um token. O processo de combinação de sequências contíguas de tokens em um único token é conhecido como criação n-grama. Os algoritmos de [!DNL Target] consideram até 2 gramas.
   * **computação de tf-idf**: a próxima etapa envolve a criação de vetores tf-idf para refletir a importância relativa de tokens na descrição do item. Para cada ficha/termo t num item i, num catálogo D com |D| itens, o termo frequência TF(t, i) é calculado primeiro (o número de vezes que o termo aparece no item i), bem como a frequência do documento DF(t, D). Em essência, o número de itens em que o token t existe. A medida tf-idf é então

     ![Fórmula mostrando tf-idf measure](assets/formula2.png)

     O [!DNL Target] usa a implementação de recurso *tf-idf* do Apache Spark, que sob o capô hash cada token para um espaço de 218 tokens. Nesta etapa, o aumento e a enterramento de atributos especificados pelo cliente também são aplicados ajustando as frequências dos termos em cada vetor com base nas configurações especificadas nos [critérios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

   * **Computação de similaridade de item**: a computação de similaridade de item final é feita usando uma similaridade aproximada de cosseno. Para dois itens, *A* e *B*, com os vetores tA e tB, a similaridade do cosseno é definida como:

     ![Fórmula mostrando o cálculo de similaridade de item](assets/formula3.png)

     Para evitar complexidade significativa em calcular semelhanças entre todos os itens N x N, o vetor *tf-idf* é truncado para conter apenas suas 500 maiores entradas e, em seguida, calcula as semelhanças do cosseno entre os itens usando essa representação de vetor truncada. Essa abordagem se mostra mais robusta para computações de similaridade de vetor esparso, em comparação a outras técnicas de vizinho mais próximo aproximado (ANN), como hash sensível à localidade.

   * **Serviço de modelo**: esse processo é idêntico às técnicas de filtragem colaborativa item-item descritas na seção anterior.

## Recomendações de várias chaves

Os algoritmos incluem:

* Recomendações baseadas em carrinho
* [!UICONTROL Recommended For You]

As adições mais recentes ao conjunto [!DNL Target] de algoritmos de recomendações são [!UICONTROL Recommended For You] e uma série de algoritmos de recomendações baseadas em carrinho. Ambos os tipos de algoritmos usam técnicas de filtragem colaborativa para formar recomendações individuais baseadas em itens. Em seguida, no momento do servidor, vários itens no histórico de navegação do usuário (para [!UICONTROL Recommended For You]) ou no carrinho atual do usuário (para recomendações baseadas em carrinho) são usados para recuperar essas recomendações baseadas em itens, que são mescladas para formar a lista final de recomendações. Observe que existem muitas opções de algoritmos de recomendação personalizados. A escolha de um algoritmo de várias chaves significa que as recomendações são disponibilizadas imediatamente depois que um visitante tem um histórico de navegação e as recomendações podem ser atualizadas para responder ao comportamento mais recente do visitante.

Esses algoritmos se baseiam nas técnicas fundamentais de filtragem colaborativa descritas na seção recomendações baseadas em itens, mas também incorporam o ajuste de hiperparâmetros para determinar a métrica de similaridade ideal entre itens. O algoritmo executa uma divisão cronológica de dados comportamentais para cada usuário e treina modelos de recomendação nos dados anteriores enquanto tenta prever os itens que um usuário visualiza ou compra posteriormente. A métrica de similaridade que produz a [Precisão média ideal] (https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval) é escolhida.

A lógica das etapas de treinamento e pontuação do modelo é mostrada no diagrama a seguir:

![Diagrama que mostra a lógica de etapas de treinamento e pontuação do modelo](assets/diagram3.png)

Veja a seguir os detalhes dessas etapas:

* **Dados de entrada**: é idêntico aos métodos de filtragem colaborativa (CF) item-item. O [!UICONTROL Both Recommended For You] e os algoritmos baseados em carrinho usam dados comportamentais, na forma de exibições e compras de usuários coletados quando você [implementa o Target](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} ou o [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}.

* **Treinamento de modelo**:

   * **Limpeza de dados e amostragem**: é o mesmo para métodos de filtragem colaborativa, em que a janela de pesquisa é aplicada para filtrar dados comportamentais para um intervalo de datas apropriado, seguido pela aplicação de regras de catálogo e exclusões globais. Os visitantes que interagiram com mais de 1.000 itens têm apenas seus 1.000 usos mais recentes considerados.
   * **Divisão do teste de treinamento**: execute uma divisão cronológica dos usos para cada usuário, alocando os primeiros 80% de seus usos para dados de treinamento, com os 20% restantes alocados para os dados de teste.
   * **Treinamento do modelo de similaridade de item**: o cálculo de similaridade de item principal difere para [!UICONTROL Recommended For You] e algoritmos baseados em carrinho na maneira como os vetores de item candidatos são construídos. Para [!UICONTROL Recommended For You], os vetores de item têm NUsers de dimensão, em que cada entrada representa a soma das classificações implícitas para esse usuário do item. As compras de um item recebem um peso 2x maior do que as visualizações do item. Para recomendações Baseadas em Carrinho, os vetores de item têm entradas binárias; se o comportamento dentro da sessão for considerado apenas, haverá uma nova entrada para cada sessão. Caso contrário, haverá uma entrada nesse vetor de item para cada visitante.

  A etapa de treinamento calcula vários tipos de similaridades de vetor: similaridade de LLR ([discutido aqui](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf)), similaridade de cosseno (definida anteriormente) e similaridade de L2 normalizada, definida como:

  ![Fórmula mostrando o cálculo de treinamento](assets/formula4.png)

   * **Avaliação do modelo de similaridade de item**: a avaliação do modelo é feita tomando as recomendações geradas na etapa anterior e fazendo previsões no conjunto de dados de teste. A fase de pontuação online é imitada pela ordem cronológica do uso dos itens de cada usuário no conjunto de dados de teste, fazendo 100 recomendações para subconjuntos ordenados de itens em uma tentativa de prever exibições e compras subsequentes. Uma métrica de recuperação de informações, a [Precisão média média](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval)), é usada para avaliar a qualidade dessas recomendações. Essa métrica leva em conta a ordem das recomendações e favorece itens relevantes mais altos na lista de recomendações, o que é uma propriedade importante para os sistemas de classificação.
   * **Seleção de modelo**: após a avaliação offline, o modelo que tem a Precisão Média mais alta é selecionado e todas as recomendações individuais de item são computadas para ele.
   * **Filtragem offline**: a etapa final do treinamento de modelo é a aplicação de filtros dinâmicos aplicáveis. Após essa etapa, as recomendações pré-calculadas são armazenadas em cache globalmente para estarem disponíveis para veiculação.

* **Atendimento de modelo**: diferentemente dos algoritmos anteriores, nos quais as recomendações de atendimento envolvem a especificação de uma única chave para recuperação, seguida pela aplicação de regras de negócios, os algoritmos [!UICONTROL Recommended for You] e Baseados em carrinho empregam um processo de tempo de execução mais complexo.

   * **Recuperação e mesclagem de várias chaves**: para recomendações baseadas em carrinho, até dez itens passados no carrinho são considerados chaves para recuperação, e as recomendações de cada um são igualmente ponderadas. Para [!UICONTROL Recommended for You], até os últimos cinco itens visualizados únicos e os últimos cinco itens comprados exclusivos são considerados como chaves para recuperação, com recomendações provenientes de itens comprados ponderadas duas vezes mais do que recomendações provenientes de itens visualizados. Ao mesclar recomendações, se um item aparecer em várias listas individuais de recomendações, suas pontuações de similaridade ponderadas serão adicionadas. A lista final de recomendações desse estágio é, então, a lista mesclada de recomendações reponderadas, classificadas em ordem decrescente.
   * **Filtragem**: em seguida, regras de filtragem, como remoção de itens visualizados e/ou comprados anteriormente, bem como outras regras comerciais dinâmicas, serão aplicadas.

Esses processos são ilustrados na imagem a seguir, em que um visitante visualizou o item A e comprou o item B. As recomendações individuais são recuperadas com as pontuações de similaridade offline exibidas abaixo de cada rótulo de item. Após a recuperação, as recomendações são mescladas com pontuações de similaridade ponderadas somadas. Por fim, em um cenário em que o cliente especificou que os itens visualizados e comprados anteriormente devem ser filtrados, a etapa de filtragem remove os itens A e B da lista de recomendações.

![Diagrama mostrando o processamento de algoritmos de várias chaves](assets/diagram4.png)

## Baseado em popularidade

Os algoritmos incluem:

* [!UICONTROL Most Viewed Across the Site]
* [!UICONTROL Most Viewed by Category]
* [!UICONTROL Most Viewed by Item Attribute]
* [!UICONTROL Top Sellers Across the Site]
* [!UICONTROL Top Sellers by Category]
* [!UICONTROL Top Sellers by Item Attribute]

O [!DNL Target] fornece algoritmos baseados em popularidade para os itens mais visualizados, bem como para os itens mais vendidos em um site ou detalhados por um atributo ou categoria de item. Os algoritmos baseados em popularidade classificam os itens com base no número de sessões em que esse item foi exibido ou comprado em um determinado período.

Todos esses algoritmos combinam dados comportamentais agregados em que o número total de sessões em que os itens foram visualizados e comprados é registrado em resoluções horárias e diárias. Algoritmos individuais encontram os itens mais visualizados ou comprados para a janela de pesquisa configurada pelo cliente.

As nuances individuais do algoritmo são as seguintes:

* [!UICONTROL Most Viewed Across the Site] e [!UICONTROL Top Sellers Across the Site] classificam os itens pela contagem agregada de sessões em que esses itens foram visualizados ou comprados, respectivamente. A saída é uma lista única (sem chave) de itens recomendados.
* Mais Vendidos/Mais Vendidos por Categoria/Atributo do Item são recomendações em que os itens são ordenados pela contagem agregada de sessões em que esses itens foram exibidos ou comprados, mas agrupados pela categoria do item ou pelo atributo do item específico. As saídas são listas de itens recomendados, digitadas por valores de categorias ou valores de atributos de item.

## Visualizado recentemente

O algoritmo de recomendações &quot;visualizado recentemente&quot; permite a personalização das recomendações na sessão. Este algoritmo não requer &quot;treinamento de modelo&quot; offline. Em vez disso, [!DNL Target] usa o [Perfil do Visitante](/help/main/c-target/c-visitor-profile/visitor-profile.md) exclusivo para manter uma lista em execução de itens que foram visualizados em uma determinada sessão e podem exibir esses itens em atividades de recomendações. Isso permite atualizações em tempo real para recomendações e personalização da próxima página.

## Critérios personalizados

Os critérios personalizados permitem que os clientes [carreguem suas próprias recomendações para [!DNL Target]](/help/main/c-recommendations/c-algorithms/recommendations-csv.md), proporcionando flexibilidade importante e permitindo recursos de &quot;trazer seu próprio modelo&quot;. Os critérios personalizados substituem a parte de &quot;treinamento offline&quot; das recomendações do [!UICONTROL Item-Based], mas se comportam de forma semelhante aos algoritmos de recomendação baseados em itens durante a fase de entrega de conteúdo online, na medida em que uma única chave é usada para recuperação de recomendações e regras/filtros de negócios são aplicados.
