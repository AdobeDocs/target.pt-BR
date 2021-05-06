---
keywords: solução de problemas, perguntas frequentes, FAQ, FAQs, recommendations, caracteres especiais, ponderação de atributos, similaridade de conteúdo
description: Exiba uma lista de perguntas e respostas frequentes sobre atividades do Adobe [!DNL Target] Recommendations.
title: Onde posso encontrar perguntas e respostas sobre o  [!DNL Target] Recommendations?
feature: Recommendations
exl-id: aaa52923-1c2d-44ae-bd89-671329222077
translation-type: tm+mt
source-git-commit: 32eeec786af7aba747881ac84ef17d7a0124a45a
workflow-type: tm+mt
source-wordcount: '2940'
ht-degree: 33%

---

# ![PREMIUM](/help/assets/premium.png) Perguntas frequentes sobre o Recommendations

Lista de perguntas frequentes sobre as atividades [!DNL Adobe Target] [!DNL Recommendations].

## Por que a [!UICONTROL Pesquisa no catálogo] não mostra os resultados corretos quando eu pesquiso em um atributo personalizado com um valor numérico?

Quando você executa uma pesquisa de catálogo em um atributo personalizado com um valor numérico, os resultados tratam o atributo personalizado como um tipo de string em vez de um valor numérico.

No momento, não há nenhuma funcionalidade disponível que permita que os clientes alterem o tipo de um atributo. Para fazer uma alteração, [abra um problema do cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) referenciando os atributos que precisam do tipo alterado de string para numérico.

## Quanto tempo leva para que as atualizações nos itens do meu catálogo sejam refletidas no meu site?

O intervalo de tempo e os resultados variam, dependendo de como os itens são atualizados.

| Fonte | Detalhes |
| --- | --- |
| Atributos de item atualizados via mbox ou API | <ul><li>O Recommendations é atualizado em 15 minutos.</li><li>Recomendações e atributos de item existentes são exibidos até que as atualizações estejam disponíveis.</li><li>A Pesquisa no catálogo é atualizada após o índice do catálogo (de 3 a 8 horas).</li></ul> |
| Atributos de item atualizados por feed | <ul><li>O Recommendations é atualizado após a assimilação do feed (de 2 a 8 horas).</li><li>Recomendações e atributos de item existentes são exibidos até que as atualizações estejam disponíveis.</li><li>A Pesquisa de catálogo é atualizada após a assimilação de feed (de 2 a 8 horas) e após o índice de catálogo subsequente (de 3 a 8 horas). A Pesquisa no catálogo é atualizada entre 5 e 16 horas no total.</li></ul> |
| Item excluído do catálogo por meio da interface do usuário ou da API [!DNL Target] | <ul><li>O Recommendations é atualizado em 15 minutos.</li><li>Recomendações e atributos de item existentes são exibidos até que as atualizações estejam disponíveis.</li><li>A Pesquisa no catálogo é atualizada após o índice do catálogo (de 3 a 8 horas).</li></ul> |
| Item adicionado ao catálogo por meio de mbox ou API | <ul><li>Recommendations são atualizados após a execução do algoritmo. As execuções de algoritmo são agendadas a cada 12 horas para algoritmos de 1 a 2 dias e a cada 24 horas para algoritmos de mais de 7 dias.</li><li>As recomendações existentes são exibidas até que as atualizações estejam disponíveis se o item adicionado não for uma chave solicitada.</li><li>As recomendações de backup são exibidas até que as atualizações estejam disponíveis se o item adicionado for uma chave solicitada.</li><li>A Pesquisa no catálogo é atualizada após o índice do catálogo (de 3 a 8 horas).</li></ul> |
| Item adicionado ao catálogo por meio de feed | <ul><li>O Recommendations é atualizado depois que o feed é assimilado (2 a 8 horas). As execuções subsequentes de algoritmos são agendadas a cada 12 horas para algoritmos de 1 a 2 dias e a cada 24 horas para algoritmos de mais de 7 dias. O Recommendations é atualizado dentro de 2 a 32 horas no total.</li><li>As recomendações existentes são exibidas até que as atualizações estejam disponíveis se o item adicionado não for uma chave solicitada.</li><li>As recomendações de backup são exibidas até que as atualizações estejam disponíveis se o item adicionado for uma chave solicitada.</li><li>A Pesquisa no catálogo é atualizada após a assimilação do feed (de 2 a 8 horas) e após o índice do catálogo (de 3 a 8 horas). A Pesquisa no catálogo é atualizada entre 5 e 16 horas no total.</li></ul> |

Após importar um arquivo de feed ou depois de receber atualizações de entidade por meio da API ou da mbox, as seguintes alterações são refletidas em menos de 60 minutos:

* Se um item tiver sido excluído anteriormente, mas agora deve ser incluído, ele será incluído na próxima execução do algoritmo (12 a 24 horas).

   Essa situação ocorre porque [!DNL Target] aplica exclusões online e offline. Quando um item é recém-excluído, a exclusão online se aplica rapidamente. Quando um item é recém-incluído, a exclusão online desaparece rapidamente, mas a exclusão offline não desaparece até que o próximo algoritmo seja executado.

* Se um item foi incluído anteriormente, mas agora deve ser excluído, ele será excluído de acordo com os &quot;Atributos de item atualizados..&quot;. linha de tempo discutida acima, dependendo da fonte de feed (15 minutos por mbox/API ou 12 a 24 horas por feed).

As seguintes alterações não são refletidas até que ocorra a execução do próximo algoritmo (dentro de 12 a 24 horas):

* Atributos de item usados nas regras de Coleção usadas para a atividade.
* Atributos de item usados em uma promoção baseada em um atributo ou coleção associada à atividade.
* Categoria do item na qual o item aparece para uma &quot;Categoria atual&quot; ou &quot;Categoria favorita&quot; no algoritmo Mais vendidos ou Mais visualizados.
* Classificação dos itens recomendados quando o atributo mudou é um atributo personalizado usado como chave personalizada para um algoritmo.
* Classificação dos itens recomendados com base em um ou mais atributos alterados quando a lógica da recomendação é &quot;Itens com atributos semelhantes&quot;, quando os fatores de ponderação de &quot;Similaridade de conteúdo&quot; são usados ou quando os fatores de &quot;Ponderação de atributos&quot; são usados.

>[!NOTE]
>
>Um arquivo de feed é considerado importado quando seu status muda de “Importando itens” para “Preparando atualizações de índice de pesquisa”. As atualizações podem levar mais de 60 minutos para serem refletidas na interface do usuário da Pesquisa no catálogo; A Pesquisa no catálogo está atualizada quando o status do feed muda para &quot;Atualizações concluídas&quot;. Mesmo que a Pesquisa no catálogo ainda não esteja atualizada, seu site reflete as atualizações nos intervalos de tempo listados acima. O tempo mais recente de atualização de índice da Pesquisa no catálogo é exibido na página Pesquisa no catálogo.

## Quanto tempo leva para que uma alteração na configuração da minha atividade, oferta, promoções ou configurações de critérios do [!UICONTROL Recommendations] seja refletida no meu site?

* Uma alteração nas configurações de promoção pode levar até cinco horas para ser refletida no local.
* Uma alteração em outras configurações de critérios pode não ser refletida até que o próximo algoritmo seja executado:

   * Algumas configurações de critérios (por exemplo, &quot;adição de uma regra de inclusão dinâmica&quot;) são refletidas instantaneamente.
   * Outras configurações de critério (por exemplo, &quot;remoção de uma regra de inclusão dinâmica&quot;, alteração da janela de retrospectiva e assim por diante) não podem ser incorporadas até que o próximo algoritmo seja executado.
   * As execuções de algoritmo são acionadas por essas alterações, mas podem levar até 24 horas para serem concluídas. Algoritmos também são executados de forma programada a cada 12 a 24 horas.

## Quanto tempo leva para o comportamento de um usuário (por exemplo, clicar no produto A e comprar o produto B) ser refletido nas recomendações *que o usuário* recebe?

* O produto/conteúdo exibido/adquirido no momento influencia as recomendações que o usuário recebe na mesma visualização de página/[!DNL Target] solicitação de conteúdo.
* O comportamento histórico do usuário, como &quot;último produto visualizado&quot;, &quot;produto mais visualizado&quot; e o histórico geral de visualização/compra são atualizados com essa solicitação e influenciam as recomendações que o usuário recebe na próxima solicitação de conteúdo de pageview/[!DNL Target]. Por exemplo, os algoritmos &quot;Itens visualizados recentemente&quot; e &quot;Recomendado para você&quot; são atualizados com cada visualização/compra de produto e refletidos na solicitação de conteúdo subsequente.

## Quanto tempo leva para o comportamento de um usuário (por exemplo, clicar no produto A e comprar o produto B) ser refletido nas recomendações *outros* que os usuários recebem?

O comportamento dos usuários na agregação é incorporado ao processamento de algoritmo offline, com cada execução de algoritmo ocorrendo a cada 12-24 horas.

## O que devo fazer se os caracteres especiais estão quebrando a matriz? {#section_D27214116EE443638A60887C7D1C534E}

Use valores removidos no JavaScript. As aspas ( &quot; ) podem quebrar a matriz. O snippet de código a seguir é um exemplo de valores removidos:

```
#set($String='') 
#set($escaper=$String.class.forName('org.apache.commons.lang.StringEscapeUtils')) 
<script type="text/javascript"> 
console.log("$escaper.escapeJavaScript($entity1.name)") 
console.log("$escaper.escapeJavaScript($entity2.name)") 
console.log('$escaper.escapeJavaScript($entity3.name)') 
names.push("$escaper.escapeJavaScript($entity4.name)") 
</script>
```

## Por que todos os critérios, incluindo os critérios personalizados, não estão disponíveis para seleção ao criar uma atividade do Recommendations?   {#section_B2265AC8B8A94E0298D495A05C5D817F}

Os critérios disponíveis são baseados na categoria atual. Ao criar ofertas do Recommendations, o seletor de algoritmo exibe critérios com base na ID de categoria.

Se a localização na qual você estiver aplicando esse critério não contiver a ID da categoria, determinados critérios não estão disponíveis no seletor de algoritmo.

Se você usar um local onde a ID da categoria está presente na mbox, o seletor de critérios conterá todos os critérios aplicáveis.

[!DNL Target] tem um  [Critério Incompatível de ](/help/c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) Filtro para controlar a filtragem inteligente do seletor de algoritmo.

>[!NOTE]
>
>Essa configuração se aplica às atividades criadas somente no Visual Experience Composer (VEC). Essa configuração não se aplica às atividades criadas no Experience Composer baseado em formulário ([!DNL Target] não tem contexto de localização).

Para acessar a configuração [!UICONTROL Critérios incompatíveis de filtro], clique em [!UICONTROL Recommendations] > [!UICONTROL Configurações]:

![](assets/recs_settings_filter.png)

Se a configuração [!UICONTROL Critérios incompatíveis de filtro] NÃO está ativado, o não filtra algoritmos no Seletor de algoritmo e todos os algoritmo são exibidos.[!DNL Target]

Se a configuração [!UICONTROL Filtrar critérios incompatíveis] estiver ativada, nas atividades do VEC, [!DNL Target] lê entityId e category Id no local selecionado e, em seguida, exibe algoritmos baseados em `currentItem|currentCategory` (se os valores respectivos estiverem presentes nesse local). Como resultado, somente os algoritmos compatíveis para o local selecionado são mostrados no seletor do algoritmo, como padrão.

Na configuração [!UICONTROL Critérios incompatíveis de filtro] estiver ativada, você ainda pode visualizar os algoritmos não compatíveis desmarcando a caixa de seleção [!UICONTROL Compatível] ao selecionar os critérios.

![](assets/compatible_checkbox.png)

A lista a seguir contém casos especiais em que [!DNL Target] não exibe a caixa de seleção [!UICONTROL Compatível]:

* EntityId e category Id estão presentes no local, então nada está sendo filtrado.
* Você está usando a [!DNL mbox.js] versão 55 ou anterior.
* Nenhuma chamada de mbox está sendo filtrada na página (!config.isAutoCreateGlobalMbox &amp;&amp; !config.isRegionalMbox)
* [!DNL Target] parâmetros não estão definidos.

## O que devo fazer se uma coleção no Recommendations chega a zero (0)?   {#section_E2DB2FE67CF24EEC81412BFF3FA6385D}

Considere as informações a seguir se você vir uma coleção em zero que anteriormente não estava em zero:

* Você pode salvar a coleção novamente e ver se ela atualiza o número. Ao salvar novamente, a coleção executa novamente todos os algoritmos que estão usando essa coleção.
* Você está olhando para o ambiente certo? Vá para [!DNL /target/products.html#recsSettings] para verificar novamente (conforme mostrado abaixo).

   ![](assets/product_catalog.png)

* O seu índice está atualizado? Vá para [!DNL /target/products.html#productSearch] e verifique quantas horas têm o índice (por exemplo, &quot;Indexado há 3 horas&quot;). Você pode atualizar o índice, conforme necessário.
* Você alterou algo no feed ou na camada de dados que resultou na falta de correspondência das suas entidades com as regras de coleção? Certifique-se de que as LETRAS MAIÚSCULAS E MINÚSCULAS estejam correspondentes (sensível à maiúscula e minúsculas).
* O seu feed foi executado com sucesso? Alguém alterou o diretório FTP, a senha e assim por diante?
* [!DNL Target]O faz o melhor para atualizar a entrega (na página/aplicativo do cliente) o mais rápido possível. No entanto, [!DNL Target] também precisa fornecer alguma representação na interface do usuário do profissional de marketing. [!DNL Target] O não atrasa atualizações de entrega para aguardar que as atualizações da interface do usuário estejam sincronizadas. Você pode usar [mboxTrace](/help/c-activities/c-troubleshooting-activities/content-trouble.md) para ver o que está no sistema no momento em que ocorre a solicitação.

## Qual a diferença entre ponderação de atributos geral e ponderação de atributo específico à similaridade de conteúdo? {#section_FCD96598CBB44B16A4C6C084649928FF}

A ponderação de atributos ocorre de duas formas: &quot;ponderação de atributos padrão&quot; e &quot;ponderação de atributos de similaridade de conteúdo&quot;.

&quot;A ponderação de atributo padrão&quot; aplica-se à maioria, ou todos, os tipos de critérios (não somente à Similaridade de conteúdo). Esse tipo de ponderação fornece mais peso a determinados valores de atributo. No exemplo a seguir, os produtos da Nike obtêm um salto nas recomendações de saída.

![](assets/attribute_weighting_example.png)

A &quot;ponderação de atributo por similaridade de conteúdo&quot; aplica-se aos critérios de Similaridade de conteúdo somente.

Esse tipo de ponderação é mais dinâmica e baseia-se na &quot;chave de recomendação&quot; atual (o item exibido atualmente). No exemplo a seguir (marca x 16), se um visitante estava visualizando tênis da Nike, ele tem maior probabilidade de receber recomendações de outros produtos da Nike (não necessariamente somente tênis) em vez de tênis de outros fabricantes. Se um visitante estiver visualizando tênis da Adidas, o visitante terá maior probabilidade de recomendar produtos da Adidas.

![](assets/content_similarity_example.png)

## Por que [!DNL Target] às vezes não consegue mostrar as recomendações? {#section_DB3F40673AED42228E407C05437D99E9}

[!DNL Target]Às vezes, o não consegue mostrar recomendações devido ao baixo número de recomendações disponíveis.

O número de valores gerados por critério é três vezes o número de entidades especificadas no design. A filtragem em tempo de execução (por exemplo, inventário, correspondência de atributos da mbox) é aplicada após os valores 3x serem gerados, portanto, é possível chegar com menos que valores 3x no momento da entrega. Para mitigar essa situação, aumente o número de entidades no design, ocultando outras entidades.

É possível usar o seguinte código em JavaScript no início do design para aumentar o número de entidades solicitadas. Neste exemplo, a contagem de entidades solicitadas seria de 30 (3x10).

```
#foreach($entity in $entities) 
 #if( $foreach.count > 10 ) 
  #break 
 #end 
 #set ($foo = $entity.id) 
#end 
```

## Qual é o limite de tamanho de uma chamada à API para inserir/atualizar produtos? Posso atualizar 50.000 produtos em uma chamada ao usar a API em vez de um feed?   {#section_434FE1F187B7436AA39B7C14C7895168}

[!DNL Target] impõe um limite de postagem de 50 MB no nível do aplicativo; no entanto, isso ocorre somente quando você passa o cabeçalho do tipo de  `application/x-www-form-urlencoded` conteúdo.

Certamente é possível tentar enviar 50.000 produtos em uma mesma chamada. Se falhar, você pode dividi-lo em lotes. A Adobe recomenda que os clientes quebrem suas chamadas em 5.000 ou 10.000 lotes de produtos para diminuir a probabilidade de um tempo limite devido à carga do sistema.

## Devo especificar o nome da mbox ao criar critérios, promoções ou regras de teste do modelo do Recommendations? {#section_FFA42ABCC5954B48A46526E32A3A88A2}

Ao criar critérios, promoções ou regras de testes do modelo do Recommendations com base em um parâmetro mbox, o `mboxParameter` não solicitará o `mboxName`. O nome da mbox agora é opcional. Essa alteração permite usar parâmetros de várias mboxes ou referenciar um parâmetro que ainda não foi gravado na borda.

Para selecionar o parâmetro desejado:

* Ao criar critérios, promoção ou regra de teste do modelo, selecione um nome de parâmetro na lista. Comece a digitar os primeiros caracteres do nome do parâmetro desejado ou digite o nome completo do nome do parâmetro desejado.
* Caso lembre do nome da mbox, mas não do parâmetro, use a caixa de seleção para filtrar uma mbox conhecida que passe o parâmetro desejado.

Com ambos os métodos, não há link entre a mbox e o parâmetro. Os critérios, a promoção ou a regra de teste do modelo funcionam com base no parâmetro em todas as mboxes que passam esse parâmetro.

Se você editar um critério, uma promoção ou uma regra de testes do modelo existente, os critérios de filtragem serão exibidos com o nome da mbox fornecido durante a criação.

## Por que não posso salvar minha atividade herdada de Recommendations, depois de definir um novo público-alvo?   {#section_1E47C40B1FE7479BAC3EE0F50CE7C2C4}

Certifique-se de que o público-alvo tenha um nome exclusivo. Se você deu ao público o mesmo nome de um público-alvo existente, não poderá salvar sua atividade herdada de Recommendations (uma atividade de Recommendations criada antes de outubro de 2016).

## Qual é o tamanho máximo de um arquivo CSV para um upload de feed?   {#section_20F1AF4839A447B9889B246D6E873538}

Não há limite rígido de número de linhas ou tamanho do arquivo para o upload de um arquivo CSV do feed. No entanto, como prática recomendada, o Adobe recomenda limitar o tamanho do arquivo CSV a 1 GB para evitar falhas durante o processo de upload de arquivos. Se o tamanho do arquivo exceder 1 GB, idealmente ele poderá ser dividido em vários arquivos de feed. O número máximo de colunas de atributos personalizados é 100 e os atributos personalizados são limitados a 4.096 caracteres. Outros limites sobre o comprimento das colunas necessárias estão disponíveis na página [[!DNL Target] Limitações](/help/r-troubleshooting-target/target-limits.md#reference_BEFE60C3AAA442FF94D4EBFB9D3CC9B1).

## Posso excluir dinamicamente uma entidade? {#exclude}

Na sequência de consulta, você pode passar IDs de entidades para as entidades que deseja excluir de suas recomendações. Por exemplo, você pode excluir itens que já estão no carrinho de compras.

Para ativar a função de exclusão, use o parâmetro de mbox `excludedIds`. Esse parâmetro indica uma lista de IDs de entidade separadas por vírgulas. Por exemplo, `mboxCreate(..., "excludedIds=1,2,3,4,5")`. O valor é enviado quando novas recomendações são solicitadas.

A exclusão é executada somente para a chamada [!DNL Target] atual; os itens não são excluídos nas chamadas [!DNL Target] subsequentes, a menos que o valor `excludedIds` seja passado novamente. Para excluir itens no carrinho das recomendações em cada página, continue transmitindo o valor `excludedIds` em cada página.

>[!NOTE]
>
>Se muitas entidades forem excluídas, as recomendações se comportarão como se não houvesse entidades suficientes para preencher o modelo da recomendação.

Para excluir `entityIds`, anexe o token `&excludes=${mbox.excludedIds}` ao url de conteúdo da oferta. Quando o url de conteúdo for extraído, os parâmetros solicitados serão substituídos pelos parâmetros de solicitação atuais do mbox.

Por padrão, esse recurso é ativado para recomendações criadas recentemente. As recomendações existentes precisam ser salvas para suportar entidades excluídas dinamicamente.

## O que significa a resposta NO_CONTENT às vezes retornada no rastreamento de conteúdo do Recommendations?

NO_CONTENT é retornado quando as recomendações não estão disponíveis para o algoritmo solicitado e a combinação de chaves. De modo geral, essa situação ocorre quando os backups são desativados para o algoritmo e uma ou mais das opções a seguir também são verdadeiras:

* Os resultados ainda não estão prontos.

   Normalmente, essa situação ocorre ao salvar uma atividade recém-criada ou depois que alterações de configuração são feitas na coleção, critérios ou promoções usadas na atividade.

* Os resultados estão prontos, mas ainda não são armazenados em cache no servidor de borda mais próximo, para a combinação de algoritmo/chave solicitada.

   A solicitação inicia uma operação de cache, portanto, esse problema deve se resolver após alguns recarregamentos de página e/ou alguns minutos de passagem.

* Os resultados estão prontos, mas não estão disponíveis para o valor principal fornecido.

   Normalmente, essa situação ocorre ao solicitar recomendações para um item que foi adicionado ao catálogo após a execução mais recente do algoritmo e se resolverá após a execução do próximo algoritmo.

* A renderização parcial do modelo está desativada e não há resultados suficientes disponíveis para preencher o modelo.

   Essa situação normalmente ocorre quando você tem uma regra de inclusão dinâmica, que filtra agressivamente muitos itens dos resultados possíveis. Para evitar situações, ative os backups e não aplique a regra de inclusão aos backups ou use os critérios em sequência com critérios filtrados menos agressivos.

## As recomendações baseadas em itens visualizados recentemente persistem em vários dispositivos para um único visitante? {#persist-across-devices}

Quando um visitante inicia uma sessão, a ID da sessão é vinculada a uma única máquina de borda e um cache de perfil temporário é armazenado nessa máquina de borda. Solicitações subsequentes da mesma sessão leem esse cache de perfil, incluindo itens visualizados recentemente.

Quando a sessão termina (geralmente, quando expira após 30 minutos sem atividade), o estado da sessão, incluindo itens visualizados recentemente, é mantido em um armazenamento de perfil mais permanente na mesma borda geográfica.

As sessões subsequentes de diferentes dispositivos podem acessar esses itens visualizados recentemente, desde que a nova sessão esteja vinculada ao perfil do cliente por meio da mesma ID de Marketing Cloud (MCID), ID de Experience Cloud (ECID) ou CustomerID/mbox3rdPartyId.

Se um visitante tiver duas sessões ativas ao mesmo tempo, os itens visualizados recentemente em um dispositivo não atualizarão os itens visualizados recentemente no outro dispositivo, a menos que os dispositivos sejam forçados a compartilhar a ID da sessão. Há uma possível solução alternativa para o problema, mas [!DNL Target] não oferece suporte direto ao compartilhamento de uma ID de sessão em vários dispositivos. O cliente deve gerenciar esse compartilhamento de ID sozinho.

Esse comportamento ainda ocorre se um visitante estiver ativo em um dispositivo e, em seguida, se tornar ativo no outro dispositivo alguns minutos depois. A primeira sessão do dispositivo não expira por 30 minutos e pode haver até cinco minutos de atraso antes que o estado do perfil seja gravado no estado permanente e processado. Aguarde 35 minutos para que a sessão expire e o perfil seja armazenado ao testar esse comportamento.

Se o visitante não tiver duas sessões ativas ao mesmo tempo, os itens visualizados recentemente em um dispositivo atualizarão os itens visualizados recentemente no outro dispositivo, desde que a sessão tenha terminado. Aguarde 35 minutos para a sessão expirar ao testar esse comportamento.
