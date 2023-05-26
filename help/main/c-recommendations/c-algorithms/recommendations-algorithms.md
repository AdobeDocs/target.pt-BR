---
keywords: recomendações algoritmos;treinamento de modelo;serviço de modelo;entrega de conteúdo;baseado em item;baseado em usuário;baseado em popularidade;baseado em carrinho;critérios personalizados
description: Saiba mais sobre os algoritmos usados no [!DNL Target Recommendations], incluindo a formação de modelos e o serviço de modelos.
title: Onde posso aprender sobre a ciência por trás dos algoritmos Recommendations do Target?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
mini-toc-levels: 2
exl-id: c156952b-8eda-491d-a68e-d3d09846f640
source-git-commit: 2a25fdb42ce4470f9126b7e0e7f6fd9e60c350e5
workflow-type: tm+mt
source-wordcount: '2842'
ht-degree: 1%

---

# A ciência por trás dos algoritmos de recomendações do Target

Uma descrição detalhada dos algoritmos usados no [!DNL Adobe Target Recommendations], incluindo os detalhes lógicos e matemáticos da formação de modelos e do processo de fornecimento de modelos.

O treinamento de modelo é o processo de como as recomendações são geradas pelo [!DNL Adobe Target] algoritmos de aprendizado. Fornecimento de modelo é como [!DNL Target] O entrega recomendações aos visitantes do site (também conhecido como entrega de conteúdo).

[!DNL Target] O inclui os seguintes tipos amplos de algoritmos no [!DNL Recommendations]:

* **Algoritmos baseados em item**: inclua algoritmos que sigam a lógica &quot;As pessoas que visualizaram/compraram esse item também visualizaram/compraram esses itens&quot;. Esses algoritmos são agrupados no termo abrangente filtragem colaborativa item a item, bem como [!UICONTROL Itens com atributos similares] algoritmos.

* **Algoritmos baseados no usuário**: Inclua o [!UICONTROL Visualizado recentemente] e [!UICONTROL Recomendado para você] algoritmos.

* **Algoritmos baseados em popularidade**: inclua algoritmos que retornam os itens mais visualizados ou comprados em todo o site, ou visualizados mais vezes ou comprados mais vezes por categoria ou atributo de item.

* **Algoritmos baseados em carrinho**: inclua recomendações baseadas em vários itens com a lógica &quot;pessoas que visualizaram/compraram esses itens, também visualizaram/compraram esses itens&quot;.

* **Critérios personalizados**: inclua recomendações com base em arquivos personalizados carregados no [!DNL Target].

>[!NOTE]
>
>Para obter informações mais gerais sobre cada tipo de algoritmo e os algoritmos individuais, consulte [Basear a recomendação em uma chave de recomendação](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

Muitos dos algoritmos listados acima baseiam-se na presença de uma ou várias chaves. Essas chaves são usadas para recuperar itens semelhantes no momento da entrega do conteúdo (quando as recomendações são feitas). As chaves especificadas pelo cliente podem incluir o item atual que alguém está visualizando, o último item visualizado ou comprado, o item mais visualizado, a categoria atual ou a categoria favorita desse visitante. Outros algoritmos, como baseado em carrinho ou em recomendações do usuário, usam chaves implícitas (que não podem ser configuradas pelo cliente). Para obter mais informações, consulte *Chaves de recomendação*, em [Basear a recomendação em uma chave de recomendação](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys). No entanto, observe que essas chaves são relevantes somente no momento do fornecimento do modelo (entrega de conteúdo). Essas chaves não afetam a lógica de tempo de treinamento &quot;offline&quot; ou do modelo.

As seções a seguir agrupam algoritmos de uma maneira um pouco diferente dos tipos de algoritmo descritos acima. O agrupamento a seguir é baseado na similaridade da lógica de treinamento do modelo.

## Filtragem colaborativa de item-item

Os algoritmos incluem:

* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]

Os algoritmos de recomendação do filtro colaborativo Item-Item são baseados na ideia de que você deve usar os padrões de comportamento de muitos usuários (portanto, colaborativos) para fornecer recomendações úteis para um determinado item (por exemplo, filtrar o catálogo de itens possíveis a serem recomendados). Embora existam vários algoritmos diferentes que se enquadram no âmbito [filtragem colaborativa](https://en.wikipedia.org/wiki/Collaborative_filtering), esses algoritmos universalmente usam fontes de dados comportamentais como entradas. Entrada [!DNL Target Recommendations], essas entradas são as visualizações e compras exclusivas de itens por usuários.

Para o algoritmo &quot;pessoas que visualizaram/compraram esse item também visualizaram/compraram esses itens&quot;, o objetivo é calcular uma similaridade s(A,B) entre todos os pares de itens. Para um determinado item A, as principais recomendações são ordenadas por sua similaridade s(A,B).

Um exemplo de similaridade é a coocorrência entre itens: uma contagem simples do número de usuários que compraram ambos os itens. Embora intuitiva, essa métrica é ingênua, pois é tendenciosa para recomendar itens populares. Por exemplo, se em um supermercado a maioria das pessoas comprar pão, o pão terá uma alta coocorrência com todos os itens, mas não é necessariamente uma boa recomendação. [!DNL Target] em vez disso, o usa uma métrica de similaridade mais sofisticada conhecida como razão de probabilidade de log (LLR). Essa quantidade é grande quando a probabilidade de dois itens, A e B, coocorrendo é muito diferente da probabilidade deles não coocorrendo. Para ser concreto, considere um caso de [!UICONTROL Pessoas que visualizaram isto, compraram aquilo] algoritmo. A similaridade LLR é grande quando a probabilidade de B ter sido comprado é *não* independentemente de alguém ter visto A.

Por exemplo, se

![Fórmula para o algoritmo exibido/comprado](assets/formula.png)

então, o item B não deve ser recomendado com o item A. Detalhes completos desse cálculo de similaridade da taxa de probabilidade do log são fornecidos [nesta PDF](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf).

O fluxo lógico da implementação real do algoritmo é mostrado no diagrama esquemático a seguir:

![Diagrama esquemático de um algoritmo visualizado/comprado](assets/diagram1.png)

Veja a seguir os detalhes dessas etapas:

* **Dados de entrada**: dados comportamentais, na forma de exibições e compras de visitantes coletados quando você [implementar o Target](https://experienceleague.corp.adobe.com/docs/target-dev/developer/recommendations.html?lang=pt-BR){target=_blank} or from [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}.

* **Treinamento de modelo**:

   * **Limpeza de dados e amostragem**: Para algoritmos com uma retrospectiva de N dias, os dados comportamentais são filtrados primeiro para incluir apenas esses N dias de dados. As regras de coleção e as exclusões globais são aplicadas para remover quaisquer itens que não devem ser recomendados. Por fim, todos os visitantes que interagiram com mais de 1.000 itens têm seus dados de uso amostrados para apenas 1.000 itens.
   * **Cálculo de similaridade de item**: esta é a etapa computacional principal: calcular a similaridade da taxa de probabilidade do log entre todos os pares de itens candidatos e classificar pares de itens por essa pontuação de similaridade.
   * **Filtragem offline**: por fim, outros filtros dinâmicos aplicáveis são aplicados (por exemplo, exclusões de categoria dinâmica). Após essa etapa, as recomendações pré-calculadas são armazenadas em cache globalmente para estarem disponíveis para veiculação.

* **Veiculação de modelos**: o conteúdo do Recommendations é entregue de [!DNL Target]do [rede global de &quot;borda&quot;](/help/main/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934). Quando as solicitações da mbox são feitas no [!DNL Target] e for determinado que o conteúdo das recomendações deve ser entregue à página, a solicitação para o conteúdo [chave do item](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys) para o algoritmo de recomendações é analisado a partir da solicitação ou pesquisado a partir do perfil do usuário e, em seguida, usado para recuperar as recomendações calculadas nas etapas anteriores. Filtros dinâmicos adicionais são aplicados neste momento, antes do filtro apropriado [design](/help/main/c-recommendations/c-design-overview/create-design.md) é renderizado.

## Similaridade de conteúdo

Algoritmo incluído:

* [!UICONTROL Itens com atributos similares]

Neste tipo de algoritmo, dois itens são considerados relacionados se seus nomes e descrições textuais são semanticamente semelhantes. Diferentemente da maioria dos algoritmos de recomendações, nos quais as fontes de dados comportamentais devem ser usadas, os algoritmos de similaridade de conteúdo usam metadados de catálogos de produtos para derivar a similaridade entre itens. [!DNL Target] é, portanto, capaz de orientar recomendações em cenários chamados de &quot;início frio&quot;, nos quais nenhum dado comportamental foi coletado (por exemplo, no início de um [!DNL Target] atividade).

Embora os aspectos de veiculação e entrega de conteúdo do modelo [!DNL Target]Os algoritmos de similaridade de conteúdo do são idênticos a outros algoritmos baseados em itens. As etapas de treinamento do modelo são drasticamente diferentes e envolvem uma série de etapas de processamento e pré-processamento de linguagem natural, conforme mostrado no diagrama a seguir. O núcleo do cálculo de similaridade é o uso da similaridade do cosseno de vetores tf-idf modificados que representam cada item no catálogo.

![Diagrama que mostra o fluxo do processo de similaridade de conteúdo](assets/diagram2.png)

Veja a seguir os detalhes dessas etapas:

* **Dados de entrada**: conforme descrito anteriormente, esse algoritmo se baseia meramente nos dados de catálogo (assimilados para [!DNL Target] via [Feed de catálogo, API de entidades ou de atualizações na página](https://experienceleague.corp.adobe.com/docs/target-dev/developer/recommendations.html?lang=pt-BR){target=_blank}.

* **Treinamento de modelo**:

   * **Extração de atributo**: após a aplicação de filtros estáticos regulares, regras de catálogo e exclusões globais, esse algoritmo extrai campos textuais relevantes do esquema de entidade. [!DNL Target] O usa automaticamente os campos name, message e category dos atributos de entidade e tenta extrair quaisquer campos de string do personalizado [atributos de entidade](/help/main/c-recommendations/c-products/entity-attributes.md). Esse processo é feito garantindo que a maioria dos valores desse campo não seja analisável como um número, data ou booleano.
   * **Remoção de lematização e palavras de interrupção**: para uma correspondência de similaridade de texto mais precisa, é prudente remover palavras &quot;stop&quot; muito comuns que não alteram significativamente o significado de um item (por exemplo, &quot;foi&quot;, &quot;é&quot;, &quot;e&quot; e assim por diante). Da mesma forma, o radical refere-se ao processo de redução de palavras com sufixos diferentes para sua palavra raiz, que tem um significado idêntico (por exemplo, &quot;conectar&quot;, &quot;conectar&quot; e &quot;conexão&quot; têm a mesma palavra raiz: &quot;conectar&quot;). [!DNL Target] usa o lematizador de Snowball. [!DNL Target] O executa a detecção automática de idioma primeiro e pode fazer a remoção de palavras de interrupção para até 50 idiomas e a ramificação para 18 idiomas.
   * **criação de n-gramas**: após as etapas anteriores, cada palavra é tratada como um token. O processo de combinação de sequências contíguas de tokens em um único token é conhecido como criação n-grama. [!DNL Target]Os algoritmos do consideram até 2 gramas.
   * **computação de tf-idf**: a próxima etapa envolve a criação de vetores tf-idf para refletir a importância relativa de tokens na descrição do item. Para cada ficha/termo t num item i, num catálogo D com |D| itens, o termo frequência TF(t, i) é calculado primeiro (o número de vezes que o termo aparece no item i), bem como a frequência do documento DF(t, D). Em essência, o número de itens em que o token t existe. A medida tf-idf é então

      ![Fórmula mostrando a medida tf-idf](assets/formula2.png)

      [!DNL Target] usa o Apache Spark *tf-idf* implementação de recursos do, que sob o capô hash cada token para um espaço de 218 tokens. Nesta etapa, o reforço e a enterramento de atributos especificados pelo cliente também são aplicados ajustando as frequências do termo em cada vetor com base nas configurações especificadas no [critérios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

   * **Cálculo de similaridade de item**: o cálculo de similaridade do item final é feito usando uma similaridade aproximada do cosseno. Para dois itens, *A* e *B*, com os vetores tA e tB, a similaridade do cosseno é definida como:

      ![Fórmula mostrando o cálculo de similaridade de item](assets/formula3.png)

      Para evitar uma complexidade significativa no cálculo das semelhanças entre todos os elementos N x N, a *tf-idf* o vetor é truncado para conter apenas suas 500 maiores entradas e, em seguida, calcula as semelhanças do cosseno entre os itens usando essa representação de vetor truncada. Essa abordagem se mostra mais robusta para computações de similaridade de vetor esparso, em comparação a outras técnicas de vizinho mais próximo aproximado (ANN), como hash sensível à localidade.

   * **Veiculação de modelos**: esse processo é idêntico às técnicas de filtragem colaborativa item a item descritas na seção anterior.

## Recomendações de várias chaves

Os algoritmos incluem:

* Recomendações baseadas em carrinho
* [!UICONTROL Recomendado Para Você]

As adições mais recentes à [!DNL Target] conjunto de algoritmos de recomendações são [!UICONTROL Recomendado Para Você] e uma série de algoritmos de recomendações baseados em carrinho. Ambos os tipos de algoritmos usam técnicas de filtragem colaborativa para formar recomendações individuais baseadas em itens. Em seguida, no momento do servidor, vários itens no histórico de navegação do usuário (para [!UICONTROL Recomendado Para Você]), ou o carrinho atual do usuário (para recomendações baseadas em carrinho) é usado para recuperar essas recomendações baseadas em itens, que são mescladas para formar a lista final de recomendações. Observe que existem muitas opções de algoritmos de recomendação personalizados. A escolha de um algoritmo de várias chaves significa que as recomendações são disponibilizadas imediatamente depois que um visitante tem um histórico de navegação e as recomendações podem ser atualizadas para responder ao comportamento mais recente do visitante.

Esses algoritmos se baseiam nas técnicas fundamentais de filtragem colaborativa descritas na seção recomendações baseadas em itens, mas também incorporam o ajuste de hiperparâmetros para determinar a métrica de similaridade ideal entre itens. O algoritmo executa uma divisão cronológica de dados comportamentais para cada usuário e treina modelos de recomendação nos dados anteriores enquanto tenta prever os itens que um usuário visualiza ou compra posteriormente. A métrica de similaridade que produz o ideal [Precisão Média Média](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval) é então escolhido.

A lógica das etapas de treinamento e pontuação do modelo é mostrada no diagrama a seguir:

![Diagrama que mostra a lógica das etapas de treinamento e pontuação do modelo](assets/diagram3.png)

Veja a seguir os detalhes dessas etapas:

* **Dados de entrada**: é idêntico aos métodos de Filtragem colaborativa (CF) item-item. [!UICONTROL Ambos Recomendados Para Você] Os algoritmos baseados em carrinho e carrinho usam dados comportamentais, na forma de exibições e compras de usuários coletadas quando você [implementar o Target](https://experienceleague.corp.adobe.com/docs/target-dev/developer/recommendations.html?lang=pt-BR){target=_blank} or from [Adobe Analytics](/help/main/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md){target=_blank}.

* **Treinamento de modelo**:

   * **Limpeza de dados e amostragem**: é o mesmo para métodos de filtragem colaborativa, em que a janela de pesquisa é aplicada para filtrar dados comportamentais para um intervalo de datas apropriado, seguido pela aplicação de regras de catálogo e exclusões globais. Os visitantes que interagiram com mais de 1.000 itens têm apenas seus 1.000 usos mais recentes considerados.
   * **Divisão do teste do comboio**: executa uma divisão cronológica dos usos para cada usuário, alocando os primeiros 80% de seus usos para dados de treinamento, com os 20% restantes alocados para os dados de teste.
   * **Treinamento de modelo de similaridade de item**: o cálculo de similaridade do item principal é diferente para [!UICONTROL Recomendado Para Você] e algoritmos baseados em carrinho na forma como os vetores de item candidatos são construídos. Para [!UICONTROL Recomendado Para Você], os vetores de item têm NUsers de dimensão, onde cada entrada representa a soma das classificações implícitas para esse usuário do item. As compras de um item recebem um peso 2x maior que as visualizações do item. Para recomendações Baseadas em Carrinho, os vetores de item têm entradas binárias; se o comportamento dentro da sessão for considerado apenas, haverá uma nova entrada para cada sessão. Caso contrário, haverá uma entrada nesse vetor de item para cada visitante.

   A etapa de treinamento calcula vários tipos de similaridades de vetor: similaridade de LLR ([discutido aqui](/help/main/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf)), similaridade do cosseno (definida anteriormente) e uma similaridade L2 normalizada, definida como:

   ![Fórmula mostrando o cálculo do treinamento](assets/formula4.png)

   * **Avaliação de modelo de similaridade de item**: a avaliação do modelo é feita tomando as recomendações geradas na etapa anterior e fazendo previsões no conjunto de dados de teste. A fase de pontuação online é imitada pela ordem cronológica do uso dos itens de cada usuário no conjunto de dados de teste, fazendo 100 recomendações para subconjuntos ordenados de itens em uma tentativa de prever exibições e compras subsequentes. Uma métrica de recuperação de informações, a variável [Precisão Média Média](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval), é usado para avaliar a qualidade dessas recomendações. Essa métrica leva em conta a ordem das recomendações e favorece itens relevantes mais altos na lista de recomendações, o que é uma propriedade importante para os sistemas de classificação.
   * **Seleção de modelo**: Após a avaliação offline, o modelo com a Precisão Média mais alta é selecionado e todas as recomendações individuais de item são computadas para ele.
   * **Filtragem offline**: a fase final do treinamento de modelo é a aplicação de quaisquer filtros dinâmicos aplicáveis. Após essa etapa, as recomendações pré-calculadas são armazenadas em cache globalmente para estarem disponíveis para veiculação.


* **Veiculação de modelos**: Ao contrário de algoritmos anteriores, nos quais as recomendações de veiculação envolvem a especificação de uma única chave para recuperação, seguida da aplicação de regras de negócios, a variável [!UICONTROL Recomendado para você] Os algoritmos baseados em carrinho e carrinho empregam um processo de tempo de execução mais complexo.

   * **Recuperação e mesclagem de várias chaves**: Para recomendações baseadas em carrinho, até dez itens passados no carrinho são considerados como chaves para recuperação, e as recomendações de cada um são ponderadas igualmente. Para [!UICONTROL Recomendado para você], até os últimos cinco itens visualizados únicos e os últimos cinco itens comprados únicos são considerados como chaves para recuperação, com recomendações provenientes de itens comprados ponderadas duas vezes mais do que recomendações provenientes de itens visualizados. Ao mesclar recomendações, se um item aparecer em várias listas individuais de recomendações, suas pontuações de similaridade ponderadas serão adicionadas. A lista final de recomendações desse estágio é, então, a lista mesclada de recomendações reponderadas, classificadas em ordem decrescente.
   * **Filtragem**: Em seguida, as regras de filtragem, como a remoção de itens visualizados e/ou comprados anteriormente, bem como outras regras de negócios dinâmicas, são aplicadas.

Esses processos são ilustrados na imagem a seguir, em que um visitante visualizou o item A e comprou o item B. As recomendações individuais são recuperadas com as pontuações de similaridade offline exibidas abaixo de cada rótulo de item. Após a recuperação, as recomendações são mescladas com pontuações de similaridade ponderadas somadas. Por fim, em um cenário em que o cliente especificou que os itens visualizados e comprados anteriormente devem ser filtrados, a etapa de filtragem remove os itens A e B da lista de recomendações.

![Diagrama que mostra o processamento de algoritmos de várias chaves](assets/diagram4.png)

## Baseado em popularidade

Os algoritmos incluem:

* [!UICONTROL Mais visualizados no site]
* [!UICONTROL Mais visualizados por categoria]
* [!UICONTROL Mais visualizados pelo atributo de item]
* [!UICONTROL Mais vendidos em todo o site]
* [!UICONTROL Mais vendidos por categoria]
* [!UICONTROL Mais Vendidos por Atributo de Item]

[!DNL Target] O fornece algoritmos baseados em popularidade para os itens mais visualizados, bem como para os itens mais vendidos em um site ou detalhados por um atributo ou categoria de item. Os algoritmos baseados em popularidade classificam os itens com base no número de sessões em que esse item foi exibido ou comprado em um determinado período.

Todos esses algoritmos combinam dados comportamentais agregados em que o número total de sessões em que os itens foram visualizados e comprados é registrado em resoluções horárias e diárias. Algoritmos individuais encontram os itens mais visualizados ou comprados para a janela de pesquisa configurada pelo cliente.

As nuances individuais do algoritmo são as seguintes:

* [!UICONTROL Mais visualizados no site] e [!UICONTROL Mais vendidos em todo o site] classificar itens pelas contagens agregadas de sessões em que esses itens foram exibidos ou comprados, respectivamente. A saída é uma lista única (sem chave) de itens recomendados.
* Mais Vendidos/Mais Vendidos por Categoria/Atributo do Item são recomendações em que os itens são ordenados pela contagem agregada de sessões em que esses itens foram exibidos ou comprados, mas agrupados pela categoria do item ou pelo atributo do item específico. As saídas são listas de itens recomendados, digitadas por valores de categorias ou valores de atributos de item.

## Visualizado recentemente

O algoritmo de recomendações &quot;visualizado recentemente&quot; permite a personalização das recomendações na sessão. Este algoritmo não requer &quot;treinamento de modelo&quot; offline. Em vez disso, [!DNL Target] usa o único [Perfil do visitante](/help/main/c-target/c-visitor-profile/visitor-profile.md) para manter uma lista em execução de itens que foram visualizados em uma determinada sessão e podem exibir esses itens em atividades de recomendações. Isso permite atualizações em tempo real para recomendações e personalização da próxima página.

## Critérios personalizados

Os critérios personalizados permitem que os clientes [fazer upload de suas próprias recomendações para [!DNL Target]](/help/main/c-recommendations/c-algorithms/recommendations-csv.md), proporcionando flexibilidade importante e permitindo recursos de &quot;trazer seu próprio modelo&quot;. Os critérios personalizados substituem a parte de &quot;treinamento offline&quot; do [!UICONTROL Baseado em Item] Recommendations, mas se comportam de forma semelhante aos algoritmos de recomendação baseados em itens durante a fase de entrega de conteúdo online, em que uma única chave é usada para recuperação de recomendações e regras/filtros de negócios são aplicados.
