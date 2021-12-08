---
keywords: algoritmos de recomendações, treinamento de modelo, serviço de modelo, entrega de conteúdo, baseado em item, baseado em usuário, baseado em popularidade, baseado em carrinho, critérios personalizados
description: Saiba mais sobre os algoritmos usados em [!DNL Target Recommendations], incluindo a formação de modelo e a prestação de serviços de modelos.
title: Onde posso aprender sobre a ciência por trás dos algoritmos Recommendations do Target?
feature: Recommendations
mini-toc-levels: 2
source-git-commit: 85958d8398fb934e1e5428fb5c562e5463f72c55
workflow-type: tm+mt
source-wordcount: '2841'
ht-degree: 0%

---

# ![PREMIUM](/help/assets/premium.png) A ciência por trás dos algoritmos de recomendações do Target

Uma descrição detalhada dos algoritmos usados em [!DNL Adobe Target Recommendations], incluindo a lógica e os detalhes matemáticos da formação de modelos e o processo de serviço de modelos.

O treinamento de modelo é o processo de como as recomendações são geradas pelo [!DNL Adobe Target] algoritmos de aprendizagem. Serviço de modelo é como [!DNL Target] O entrega recomendações para os visitantes do site (também conhecido como entrega de conteúdo).

[!DNL Target] inclui os seguintes tipos amplos de algoritmos em [!DNL Recommendations]:

* **Algoritmos baseados em itens**: Inclua algoritmos que seguem a lógica &quot;Pessoas que visualizaram/compraram este item também visualizaram/compraram esses itens.&quot; Esses algoritmos são agrupados sob o termo guarda-chuva item-item colaborative filtering, bem como [!UICONTROL Itens com atributos similares] algoritmos.

* **Algoritmos baseados no usuário**: Inclua a [!UICONTROL Visualizados recentemente] e [!UICONTROL Recomendado para você] algoritmos.

* **Algoritmos baseados em popularidade**: Inclua algoritmos que retornam os itens mais visualizados ou mais comprados do site, ou os mais visualizados ou mais comprados por categoria ou atributo de item.

* **Algoritmos baseados no carrinho**: Inclua recomendações baseadas em vários itens com a lógica &quot;pessoas que visualizaram/compraram esses itens, também visualizaram/compraram esses itens&quot;.

* **Critérios personalizados**: Incluir recomendações com base em arquivos personalizados carregados no [!DNL Target].

>[!NOTE]
>
>Para obter informações mais gerais sobre cada tipo de algoritmo e os algoritmos individuais, consulte [Basear a recomendação em uma chave de recomendação](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

Muitos dos algoritmos listados acima são baseados na presença de uma ou várias chaves. Essas chaves são usadas para recuperar itens semelhantes no momento da entrega do conteúdo (quando as recomendações são feitas). As chaves especificadas pelo cliente podem incluir o item atual que alguém está visualizando, o último item visualizado ou comprado, o item visualizado por cima, a categoria atual ou a categoria favorita desse visitante. Outros algoritmos, como recomendações baseadas em carrinho ou baseadas no usuário, usam chaves implícitas (que não podem ser configuradas pelo cliente). Para obter mais informações, consulte *Chaves de recomendação*, em [Basear a recomendação em uma chave de recomendação](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys). No entanto, observe que essas chaves são relevantes somente no horário de serviço do modelo (entrega de conteúdo). Essas chaves não afetam a lógica de tempo de treinamento &quot;offline&quot; ou do modelo.

As seções a seguir agrupam algoritmos de maneira ligeiramente diferente dos tipos de algoritmos descritos acima. O agrupamento a seguir é baseado na similaridade da lógica de treinamento de modelo.

## Filtragem colaborativa de item

Os algoritmos incluem:

* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]

Os algoritmos de recomendação de filtragem colaborativa de item-item baseiam-se na ideia de que você deve usar os padrões comportamentais de muitos usuários (daí a colaboração) para fornecer recomendações úteis para um determinado item (por exemplo, filtrar o catálogo de possíveis itens a serem recomendados). Embora existam vários algoritmos diferentes que se enquadram no âmbito geral do [filtragem colaborativa](https://en.wikipedia.org/wiki/Collaborative_filtering), esses algoritmos usam universalmente fontes de dados comportamentais como entradas. Em [!DNL Target Recommendations], essas entradas são exibições e compras exclusivas de itens por usuários.

Para o algoritmo &quot;pessoas que visualizaram/compraram este item também visualizaram/compraram esses itens&quot;, o objetivo é calcular uma similaridade s(A,B) entre todos os pares de itens. Para um determinado item A, as principais recomendações são ordenadas por sua similaridade s(A,B).

Um exemplo dessa semelhança é a co-ocorrência entre os itens: uma contagem simples do número de usuários que compraram ambos os itens. Embora intuitiva, essa métrica é ingênua, na medida em que é tendenciosa em relação à recomendação de itens populares. Por exemplo, se em um varejista de compras a maioria das pessoas comprar pão, pão terá alta co-ocorrência com todos os itens, mas não é necessariamente uma boa recomendação. [!DNL Target] em vez disso, usa uma métrica de similaridade mais sofisticada conhecida como taxa de probabilidade de log (LLR). Essa quantidade é grande quando a probabilidade de dois itens, A e B, co-ocorrerem é muito diferente da probabilidade de não co-ocorrerem. Para a concretiza, considere um caso da variável [!UICONTROL Pessoas que viram isto, compraram aquilo] algoritmo. A similaridade de LLR é grande quando a probabilidade de B ser comprada é independente do fato de alguém ter ou não visualizado A.

Por exemplo, se

![Fórmula para o algoritmo visualizado/comprado](assets/formula.png)

então o item B não deve ser recomendado com o item A. São fornecidos detalhes completos sobre este cálculo da similaridade da taxa de probabilidade de log [neste PDF](/help/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf).

O fluxo lógico da implementação real do algoritmo é mostrado no diagrama esquemático a seguir:

![Diagrama esquemático de um algoritmo visualizado/comprado](assets/diagram1.png)

Os detalhes dessas etapas são os seguintes:

* **Dados de entrada**: Dados comportamentais, na forma de exibições e compras de visitantes coletadas quando você [implementar o Target](/help/c-recommendations/plan-implement.md#pass-behavioral) ou de [Adobe Analytics](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

* **Formação de modelo**:

   * **Limpeza e amostragem de dados**: Para algoritmos com uma retrospectiva de N dias, os dados comportamentais são primeiro filtrados para incluir somente esses N dias de dados. As regras de coleta e exclusões globais são aplicadas para remover qualquer item que não deve ser recomendado. Finalmente, qualquer visitante que interagiu com mais de 1.000 itens tem seus dados de uso amostrados para apenas 1.000 itens.
   * **Cálculo de similaridade de item**: Esta é a etapa computacional principal: calcular a similaridade da taxa de probabilidade de log entre todos os pares de itens candidatos e classificar pares de itens por essa pontuação de similaridade.
   * **Filtragem offline**: Finalmente, qualquer outro filtro dinâmico aplicável é aplicado (por exemplo, exclusões de categoria dinâmica). Após essa etapa, as recomendações pré-calculadas são armazenadas em cache globalmente para serem disponibilizadas.

* **Serviço de modelo**: O conteúdo da Recommendations é fornecido de [!DNL Target]&#39;s [rede global &quot;Edge&quot;](/help/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934). Quando as solicitações da mbox são feitas para [!DNL Target] e está determinado que o conteúdo das recomendações deve ser entregue à página, a solicitação do [chave de item](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#keys) O para o algoritmo do recommendations é analisado a partir da solicitação ou pesquisado a partir do perfil do usuário e, em seguida, usado para recuperar as recomendações calculadas nas etapas anteriores. Outros filtros dinâmicos são aplicados neste momento, antes da aplicação apropriada [projeto](/help/c-recommendations/c-design-overview/create-design.md) é renderizado.

## Similaridade de conteúdo

Algoritmo incluído:

* [!UICONTROL Itens com atributos similares]

Nesse tipo de algoritmo, dois itens são considerados relacionados se seus nomes e descrições textuais forem semanticamente semelhantes. Ao contrário da maioria dos algoritmos de recomendações nos quais as fontes de dados comportamentais devem ser usadas, os algoritmos de similaridade de conteúdo usam metadados de catálogos de produtos para derivar a similaridade entre itens. [!DNL Target] portanto, é capaz de direcionar recomendações em cenários chamados de &quot;inicialização a frio&quot;, em que nenhum dado comportamental foi coletado (por exemplo, no início de um [!DNL Target] atividade ).

Embora a veiculação do modelo e os aspectos de entrega de conteúdo de [!DNL Target]Os algoritmos de similaridade de conteúdo da são idênticos a outros algoritmos baseados em itens, as etapas de treinamento do modelo são drasticamente diferentes e envolvem uma série de etapas de processamento e pré-processamento de linguagem natural, conforme ilustrado no diagrama a seguir. O núcleo do cálculo de similaridade é o uso da similaridade de cosseno de vetores tf-idf modificados que representam cada item no catálogo.

![Diagrama que mostra o fluxo do processo de similaridade de conteúdo](assets/diagram2.png)

Os detalhes dessas etapas são os seguintes:

* **Dados de entrada**: Conforme descrito anteriormente, este algoritmo se baseia apenas em dados de catálogo (assimilados a [!DNL Target] via [Feed do catálogo, a API de entidades ou de atualizações na página](/help/c-recommendations/plan-implement.md#rec-catalog).

* **Formação de modelo**:

   * **Extração de atributo**: Após a aplicação de filtros estáticos regulares, regras de catálogo e exclusões globais, esse algoritmo extrai campos textuais relevantes do schema da entidade. [!DNL Target] O usa automaticamente os campos nome, mensagem e categoria dos atributos da entidade e tenta extrair qualquer campo de string do [atributos da entidade](/help/c-recommendations/c-products/entity-attributes.md). Esse processo é feito garantindo que a maioria dos valores desse campo não seja analisável como um número, data ou booleano.
   * **Remoção de mensagens e palavras-chave**: Para uma correspondência de similaridade de texto mais precisa, é prudente remover palavras &quot;stop&quot; muito comuns que não alteram significativamente o significado de um item (por exemplo, &quot;was&quot;, &quot;is&quot;, &quot;and&quot; e assim por diante). Da mesma forma, lematização refere-se ao processo de redução de palavras com sufixos diferentes para a palavra raiz, que tem um significado idêntico (por exemplo, &quot;conectar&quot;, &quot;conectar&quot; e &quot;conexão&quot; têm a mesma palavra raiz: &quot;connect&quot;). [!DNL Target] usa o Snowball. [!DNL Target] O executa a detecção automática de idioma primeiro e pode interromper a remoção de palavras para até 50 idiomas e pode ser enviada para 18 idiomas.
   * **Criação de n-grama**: Após as etapas anteriores, cada palavra é tratada como um token. O processo de combinação de sequências contíguas de tokens em um único token é chamado de criação de n-gramas. [!DNL Target]Os algoritmos da consideram até 2 gramas.
   * **computação tf-idf**: A próxima etapa envolve a criação de vetores tf-idf para refletir a importância relativa dos tokens na descrição do item. Para cada token/termo t em um item i, em um catálogo D com |D| itens, o termo frequência TF(t, i) é calculado primeiro (o número de vezes que o termo aparece no item i), bem como a frequência do documento DF(t, D). Em essência, o número de itens em que o token t existe. A medida tf-idf é então

      ![Fórmula mostrando medida tf-idf](assets/formula2.png)

      [!DNL Target] usa o Apache Spark *tf-idf* implementação de recursos, que sob o capuz apresenta cada token em um espaço de 218 tokens. Nesta etapa, o aumento e a enterramento de atributos especificados pelo cliente também são aplicados por meio do ajuste das frequências de termos em cada vetor com base nas configurações especificadas no [critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

   * **Cálculo de similaridade de item**: O cálculo final da similaridade de item é feito usando uma similaridade aproximada de cosseno. Para dois itens, *A* e *B*, com os vetores tA e tB, a similaridade de cosseno é definida como:

      ![Fórmula que mostra o cálculo da similaridade de item](assets/formula3.png)

      Para evitar uma complexidade significativa na computação de semelhanças entre todos os itens N x N, o *tf-idf* O vetor é truncado para conter apenas suas 500 entradas maiores e, em seguida, calcula as semelhanças de cosseno entre itens usando essa representação de vetor truncada. Essa abordagem se mostra mais robusta para cálculos de similaridade de vetor esparsos, em comparação a outras técnicas de vizinho mais próximo (ANN), como hash sensível à localidade.

   * **Serviço de modelo**: Esse processo é idêntico às técnicas de filtragem colaborativa de item descritas na seção anterior.

## Recomendações com várias chaves

Os algoritmos incluem:

* Recomendações baseadas no carrinho
* [!UICONTROL Recomendado Para Você]

As adições mais recentes à [!DNL Target] conjunto de algoritmos do recommendations são [!UICONTROL Recomendado Para Você] e uma série de algoritmos de recomendações baseadas em carrinho. Ambos os tipos de algoritmos usam técnicas de filtragem colaborativa para formar recomendações baseadas em itens individuais. Em seguida, no tempo de serviço, vários itens no histórico de navegação do usuário (para [!UICONTROL Recomendado Para Você]), ou o carrinho atual do usuário (para recomendações baseadas em carrinho) é usado para recuperar essas recomendações baseadas em itens, que são mescladas para formar a lista final de recomendações. Observe que existem muitas opções de algoritmos de recomendação personalizados. A escolha de um algoritmo de várias chaves significa que as recomendações estão imediatamente disponíveis depois que um visitante tem qualquer histórico de navegação e as recomendações podem ser atualizadas para responder ao comportamento do visitante mais recente.

Esses algoritmos baseiam-se nas técnicas fundamentais de filtragem colaborativa descritas na seção de recomendações baseadas em itens, mas também incorporam o ajuste de hiperparâmetros para determinar a métrica ideal de similaridade entre itens. O algoritmo executa uma divisão cronológica de dados comportamentais para cada usuário, e treina modelos de recomendação nos dados anteriores ao tentar prever os itens que um usuário visualiza ou compra posteriormente. A métrica de similaridade que produz o melhor [Precisão média](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval)#Mean_average_precision) é então escolhida.

A lógica das etapas de treinamento e pontuação do modelo é mostrada no diagrama a seguir:

![Diagrama mostrando a lógica do treinamento do modelo e as etapas de pontuação](assets/diagram3.png)

Os detalhes dessas etapas são os seguintes:

* **Dados de entrada**: Isso é idêntico aos métodos de filtragem colaborativa (CF) de item. [!UICONTROL Ambos Recomendados Para Você] Os algoritmos baseados em carrinho usam dados comportamentais, na forma de exibições e compras de usuários coletados quando você [implementar o Target](/help/c-recommendations/plan-implement.md#pass-behavioral) ou de [Adobe Analytics](/help/c-recommendations/c-algorithms/use-adobe-analytics-with-recommendations.md).

* **Formação de modelo**:

   * **Limpeza e amostragem de dados**: Isso é novamente o mesmo que para métodos de filtragem colaborativa, em que a janela de lookback é aplicada para filtrar dados comportamentais em um intervalo de datas apropriado, seguido pela aplicação de regras de catálogo e exclusões globais. Os visitantes que interagiram com mais de 1.000 itens têm apenas seus 1.000 usos mais recentes considerados.
   * **Divisão do ensaio do comboio**: Realize uma divisão cronológica dos usos para cada usuário, alocando os primeiros 80% de seus usos aos dados de treinamento, com os 20% restantes alocados aos dados de teste.
   * **Treinamento em modelo de semelhança de item**: O cálculo de similaridade de item principal difere para [!UICONTROL Recomendado Para Você] e algoritmos baseados em carrinho na maneira como os vetores de item candidatos são construídos. Para [!UICONTROL Recomendado Para Você], os vetores de item têm dimensão NUsers, em que cada entrada representa a soma das classificações implícitas para esse usuário do item. As compras de um item recebem um peso de duas vezes o das exibições do item. Para recomendações baseadas em carrinho, os vetores de item têm entradas binárias; se o comportamento na sessão for considerado somente, há uma nova entrada para cada sessão. Caso contrário, há uma entrada nesse vetor de item para cada visitante.

   A etapa de treinamento calcula vários tipos de semelhanças entre vetores: Similaridade LLR ([discutido aqui](/help/c-recommendations/c-algorithms/assets/log-likelihood-ratios-recommendation-algorithms.pdf)), semelhança de cosseno (definida anteriormente) e uma semelhança L2 normalizada, definida como:

   ![Fórmula mostrando cálculo de treinamento](assets/formula4.png)

   * **Avaliação do modelo de semelhança de item**: A avaliação do modelo é feita tomando as recomendações geradas na etapa anterior e fazendo previsões sobre o conjunto de dados de teste. A fase de pontuação online é mimetizada pela ordenação cronológica dos usos do item de cada usuário no conjunto de dados de teste, em seguida, fazendo 100 recomendações para subconjuntos ordenados de itens em uma tentativa de prever visualizações e compras subsequentes. Uma métrica de recuperação de informações, a [Precisão média](https://en.wikipedia.org/wiki/Evaluation_measures_(information_retrieval)#Mean_average_precision), é usada para avaliar a qualidade dessas recomendações. Essa métrica leva em consideração a ordem das recomendações e favorece itens relevantes mais altos na lista de recomendações, que é uma propriedade importante para classificar sistemas.
   * **Seleção de modelo**: Após a avaliação offline, o modelo com a Precisão média mais alta é selecionado e todas as recomendações de item individuais são calculadas para ele.
   * **Filtragem offline**: A fase final da formação do modelo é a aplicação de filtros dinâmicos aplicáveis. Após essa etapa, as recomendações pré-calculadas são armazenadas em cache globalmente para serem disponibilizadas.


* **Serviço de modelo**: Ao contrário dos algoritmos anteriores em que as recomendações de serviço envolvem a especificação de uma única chave para recuperação, seguida pela aplicação de regras de negócios, a variável [!UICONTROL Recomendado para você] Os algoritmos baseados em carrinho e usam um processo de tempo de execução mais complexo.

   * **Recuperação e mesclagem de várias chaves**: Para recomendações baseadas em carrinho, até dez itens passados no carrinho são considerados chaves para recuperação e as recomendações de cada um são igualmente ponderadas. Para [!UICONTROL Recomendado para você], até os últimos cinco itens visualizados e os últimos cinco itens adquiridos únicos são considerados como chaves para recuperação, com as recomendações provenientes de itens comprados ponderadas duas vezes mais que as recomendações provenientes de itens visualizados. Ao mesclar recomendações, se um item for exibido em várias listas individuais de recomendações, suas pontuações de similaridade ponderada serão adicionadas. A lista final de recomendações desse estágio é então a lista mesclada de recomendações reponderadas, classificadas em ordem decrescente.
   * **Filtragem**: Em seguida, são aplicadas regras de filtragem, como a remoção de itens visualizados e/ou comprados anteriormente, bem como outras regras comerciais dinâmicas.

Esses processos são ilustrados na imagem a seguir, onde um visitante visualizou o item A e comprou o item B. As recomendações individuais são recuperadas com as pontuações de similaridade offline mostradas abaixo de cada rótulo de item. Após a recuperação, as recomendações são mescladas com pontuações de similaridade ponderada somadas. Finalmente, em um cenário em que o cliente especificou que os itens visualizados e comprados anteriormente devem ser filtrados, a etapa de filtragem remove os itens A e B da lista de recomendações.

![Diagrama que mostra o processamento de algoritmos com várias teclas](assets/diagram4.png)

## Baseado em popularidade

Os algoritmos incluem:

* [!UICONTROL Mais visualizados no site]
* [!UICONTROL Mais visualizados por categoria]
* [!UICONTROL Mais visualizados por atributo de item]
* [!UICONTROL Mais vendidos no site]
* [!UICONTROL Mais vendidos por categoria]
* [!UICONTROL Principais Vendedores por Atributo de Item]

[!DNL Target] O fornece algoritmos baseados em popularidade para os itens mais visualizados, bem como os itens mais vendidos em um site ou detalhados por um atributo de item ou categoria. Os algoritmos baseados em popularidade classificam os itens com base no número de sessões nas quais esse item foi visualizado ou comprado em um determinado período.

Todos esses algoritmos combinam dados comportamentais agregados, onde o número total de sessões nas quais os itens foram visualizados e comprados é registrado em resoluções de hora em hora e de dia. Algoritmos individuais encontram os itens mais visualizados ou mais comprados para a janela de lookback configurada pelo cliente.

As nuances de algoritmo individuais são as seguintes:

* [!UICONTROL Mais visualizados no site] e [!UICONTROL Mais vendidos no site] Classifique os itens pelas contagens agregadas das sessões em que esses itens foram visualizados ou comprados, respectivamente. A saída é uma única lista (sem chave) de itens recomendados.
* A maioria dos vendedores visualizados/principais por categoria/atributo de item são recomendações em que os itens são ordenados pelas contagens agregadas das sessões em que esses itens foram visualizados ou comprados, mas agrupados pela categoria do item ou pelo atributo do item específico. As saídas são listas de itens recomendados, marcados por valores de categorias ou valores de atributos de item.

## Visualizados recentemente

O algoritmo de recomendações &quot;visualizadas recentemente&quot; permite a personalização das recomendações na sessão. Este algoritmo não requer &quot;treinamento de modelo&quot; offline. Em vez disso, [!DNL Target] usa o [Perfil do visitante](/help/c-target/c-visitor-profile/visitor-profile.md) para manter uma lista em execução de itens que foram visualizados em uma determinada sessão e podem exibir esses itens em atividades de recomendações. Isso permite atualizações em tempo real para recomendações e personalização da próxima página.

## Critérios personalizados

Os critérios personalizados permitem que os clientes [fazer upload de suas próprias recomendações para [!DNL Target]](/help/c-recommendations/c-algorithms/recommendations-csv.md), proporcionando flexibilidade importante e permitindo recursos de &quot;traga seu próprio modelo&quot;. Os critérios personalizados substituem a parte do &quot;treinamento offline&quot; de [!UICONTROL Baseado em item] recomendações, mas se comportam de forma semelhante aos algoritmos de recomendação baseados em itens durante a fase de entrega de conteúdo online, na medida em que uma única chave é usada para recuperar recomendações e regras/filtros de negócios são aplicadas.