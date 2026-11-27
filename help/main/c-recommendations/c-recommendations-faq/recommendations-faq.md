---
keywords: solução de problemas, perguntas frequentes, FAQ, FAQs, recommendations, caracteres especiais, ponderação de atributos, similaridade de conteúdo
description: Veja uma lista de perguntas frequentes e respostas sobre atividades do [!DNL Target Recommendations].
title: Onde posso encontrar perguntas e respostas sobre o [!DNL Recommendations]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: aaa52923-1c2d-44ae-bd89-671329222077
TQID: 'https://experienceleague.adobe.com/Hz37Dp21q-25Pj6mmbiaGqONY14eImVB9Ebz8VH9hMA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '3560'
ht-degree: 10%
---
# Perguntas frequentes do Recomendações {#recommendations-faq}

>[!BEGINSHADEBOX]

**Nesta página:** encontre respostas para perguntas frequentes sobre [!DNL Adobe Target] [!DNL Recommendations] atividades.

>[!ENDSHADEBOX]

## Dados e APIs {#data-and-apis}

+++ Os objetos [!DNL Recommendations] criados por meio da API são exibidos na interface do usuário [!DNL Target]?

Sim. Os objetos [!UICONTROL Recommendations] (**[!UICONTROL Critérios]**, **[!UICONTROL Designs]**, **[!UICONTROL Coleções]** e **[!UICONTROL Exclusões]**) criados por meio da API estão disponíveis na interface do usuário e podem ser editados por meio da API ou da interface do usuário [!DNL Target].

+++

+++ As ofertas visuais criadas na interface do usuário do [!DNL Target] podem ser gerenciadas com as APIs do [!DNL Target]?

Não. [!DNL Recommendations] atividades com ofertas visuais criadas na interface do usuário [!DNL Target] não podem ser gerenciadas com as APIs [!DNL Target]. Essas atividades são exibidas na lista **[!UICONTROL Atividades]**, mas não podem ser lidas ou atualizadas (com GET ou PUT).

+++

+++ Qual é o limite de tamanho de uma chamada à API para inserir ou atualizar produtos? É possível atualizar 50.000 produtos em uma chamada em vez de em um feed?

[!DNL Target] impõe um limite de postagem de 50 MB no nível do aplicativo, mas somente quando o cabeçalho de tipo de conteúdo `application/x-www-form-urlencoded` é passado.

É possível realizar uma única chamada com 50.000 produtos. Se a chamada falhar, ela poderá ser dividida em lotes. A Adobe recomenda lotes de 5.000 ou 10.000 produtos para diminuir a probabilidade de um tempo limite devido à carga do sistema.

+++

+++ Qual é o tamanho máximo de um arquivo CSV para um upload de feed?

Não há limite rígido de número de linhas ou tamanho do arquivo para o upload de um arquivo CSV de feed. Como prática recomendada, a Adobe limita o arquivo CSV a 1 GB para evitar falhas durante o upload. Idealmente, um arquivo que exceda 1 GB pode ser dividido em vários arquivos de feed.

O número máximo de colunas de atributos personalizados é 100, e os atributos personalizados são limitados a 4.096 caracteres. Outros limites sobre o comprimento das colunas necessárias estão disponíveis na [[!DNL Target] página de limitações do](/help/main/r-troubleshooting-target/target-limits.md).

+++

+++ Por que a **[!UICONTROL Pesquisa no catálogo]** não mostra os resultados corretos ao pesquisar em um atributo personalizado com um valor numérico?

Quando uma pesquisa de catálogo é executada em um atributo personalizado com um valor numérico, os resultados tratam o atributo como uma string em vez de um valor numérico.

No momento, não há nenhuma funcionalidade disponível que permita aos clientes alterar o tipo de um atributo. Para fazer uma alteração, [abra um problema do cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) que faz referência aos atributos cujo tipo deve mudar de sequência para numérico.

+++

## Atualizar tempo {#update-timing}

+++ Quanto tempo leva para que as atualizações nos itens do catálogo sejam refletidas no site?

O intervalo de tempo e os resultados variam dependendo de como os itens são atualizados.

| Atualizar | Recomendações | Pesquisa no catálogo |
| --- | --- | --- |
| Atributos de item atualizados por meio de uma mbox ou API | Em 15 minutos | Após o índice do catálogo (3 a 8 horas) |
| Atributos de item atualizados por meio de um feed | Após a assimilação do feed (de 2 a 8 horas) | Após a assimilação do feed (de 2 a 8 horas) e o índice de catálogo subsequente (de 3 a 8 horas), dentro de 5 a 16 horas no total |
| Item excluído do catálogo por meio da interface ou da API do [!DNL Target] | Em 15 minutos | Após o índice do catálogo (3 a 8 horas) |
| Item adicionado ao catálogo por meio de uma mbox ou da API | Após a execução do próximo algoritmo. As execuções de algoritmo são agendadas a cada 12 horas para algoritmos de 1 a 2 dias e a cada 24 horas para algoritmos de mais de 7 dias | Após o índice do catálogo (3 a 8 horas) |
| Item adicionado ao catálogo por meio de um feed | Após a assimilação do feed (de 2 a 8 horas) e a execução do algoritmo subsequente, que são agendados a cada 12 horas para algoritmos de 1 a 2 dias e a cada 24 horas para algoritmos de mais de 7 dias, dentro de 2 a 32 horas no total | Após a assimilação do feed (de 2 a 8 horas) e o índice do catálogo (de 3 a 8 horas), dentro de 5 a 16 horas no total |

Até que as atualizações estejam disponíveis, o seguinte conteúdo será mostrado:

* Para itens atualizados ou excluídos, as recomendações e os atributos de item existentes são mostrados.
* Para um item adicionado, as recomendações existentes serão mostradas se o item adicionado não for uma chave solicitada. As recomendações de backup serão exibidas se o item adicionado for uma chave solicitada.

Depois que um arquivo de feed é importado ou depois que as atualizações de entidade são recebidas por meio da API ou de uma mbox, as seguintes alterações são refletidas em menos de 60 minutos:

* Se um item tiver sido excluído anteriormente, mas agora precisar ser incluído, ele será incluído na próxima execução do algoritmo (12 a 24 horas).

  Essa situação ocorre porque o [!DNL Target] aplica exclusões online e offline. Quando um item é recém-excluído, a exclusão online se aplica rapidamente. Quando um item é recém-incluído, a exclusão online desaparece rapidamente, mas a exclusão offline não desaparece até que o próximo algoritmo seja executado.

* Se um item foi incluído anteriormente, mas agora deve ser excluído, o item é excluído de acordo com as linhas de tempo na tabela, dependendo da fonte: 15 minutos por meio de uma mbox ou da API ou 12 a 24 horas por meio de um feed.

As seguintes alterações não são refletidas até que ocorra a execução do próximo algoritmo (dentro de 12 a 24 horas):

* Atributos de item usados nas regras de coleção da atividade.
* Atributos de item usados em uma promoção baseada em um atributo ou em uma coleção associada à atividade.
* A categoria do item na qual o item aparece para uma &quot;Categoria Atual&quot; ou &quot;Categoria Favorita&quot; no algoritmo **[!UICONTROL Mais Vendidos]** ou **[!UICONTROL Mais Visualizados]**.
* A classificação de itens recomendados, quando o atributo alterado é um atributo personalizado usado como chave personalizada para um algoritmo.
* A classificação dos itens recomendados com base em um ou mais atributos alterados, quando a lógica de recomendação é &quot;Itens com atributos semelhantes&quot; ou quando os fatores &quot;Similaridade de conteúdo&quot; ou &quot;Ponderação de atributos&quot; são usados.

>[!NOTE]
>
>Um arquivo de feed é considerado importado quando seu status muda de “Importando itens” para “Preparando atualizações de índice de pesquisa”. As atualizações podem levar mais de 60 minutos para serem refletidas na interface do usuário da **[!UICONTROL Pesquisa de catálogo]**. **[!UICONTROL Pesquisa no catálogo]** está atualizada quando o status do feed muda para &quot;Atualizações concluídas&quot;. Mesmo que a **[!UICONTROL Pesquisa no catálogo]** ainda não esteja atualizada, o site refletirá as atualizações nos prazos listados acima. A hora de atualização de índice da **[!UICONTROL Pesquisa no catálogo]** mais recente é exibida na página **[!UICONTROL Pesquisa no catálogo]**.

+++

+++ Quanto tempo leva para que uma alteração na configuração de uma atividade, oferta, promoções ou configurações de critérios do [!UICONTROL Recommendations] seja refletida no site?

* Uma alteração nas configurações de promoção pode levar até cinco horas para ser refletida no site.
* Uma alteração em outras configurações de critérios pode não ser refletida até que o próximo algoritmo seja executado:

  * Algumas configurações de critérios, por exemplo, a adição de uma regra de inclusão dinâmica, são refletidas instantaneamente.
  * Outras configurações de critérios, por exemplo, a remoção de uma regra de inclusão dinâmica ou uma alteração da janela de retrospectiva, não podem ser incorporadas até que o próximo algoritmo seja executado.
  * Essas alterações acionam uma execução de algoritmo, que pode levar até 24 horas para ser concluída. Algoritmos também são executados em um cronograma, a cada 12 a 24 horas.

+++

+++ Quanto tempo leva para o comportamento de um usuário (por exemplo, clicar no produto A e comprar o produto B) ser refletido nas recomendações que o mesmo usuário recebe?

* O produto ou conteúdo exibido ou adquirido no momento influencia as recomendações que o usuário recebe na mesma exibição de página ou solicitação de conteúdo do [!DNL Target].
* O comportamento histórico do usuário, como &quot;último produto visualizado&quot;, &quot;produto mais visualizado&quot; e o histórico geral de visualização e compra são atualizados com essa solicitação. Ele influencia as recomendações que o usuário recebe na próxima exibição de página ou solicitação de conteúdo. Por exemplo, os **[!UICONTROL Itens visualizados recentemente]** e **[!UICONTROL Recomendado para você]** são atualizados com cada exibição de produto ou compra, e a atualização é refletida na solicitação de conteúdo subsequente.

+++

+++ Quanto tempo leva para o comportamento de um usuário ser refletido nas recomendações que outros usuários recebem?

O comportamento dos usuários na agregação é incorporado ao processamento de algoritmo offline. Esse processamento ocorre com cada execução de algoritmo, a cada 12-24 horas.

+++

+++ As recomendações baseadas em itens visualizados recentemente persistem em vários dispositivos para um único visitante?

Quando um visitante inicia uma sessão, a ID da sessão é vinculada a uma única máquina de borda e um cache de perfil temporário é armazenado nessa máquina. Solicitações subsequentes da mesma sessão leem esse cache de perfil, incluindo os itens visualizados recentemente.

Quando a sessão termina (geralmente quando expira após 30 minutos sem atividade), o estado da sessão, incluindo os itens visualizados recentemente, é mantido em um armazenamento de perfil mais permanente na mesma borda geográfica. As sessões subsequentes de diferentes dispositivos podem acessar esses itens visualizados recentemente, desde que a nova sessão esteja vinculada ao perfil do cliente por meio da mesma Marketing Cloud ID (MCID), Experience Cloud ID (ECID) ou CustomerID ou `mbox3rdPartyId`.

Se um visitante tiver duas sessões ativas ao mesmo tempo, os itens visualizados recentemente em um dispositivo não atualizarão os itens visualizados recentemente no outro dispositivo, a menos que os dispositivos sejam forçados a compartilhar a ID da sessão. Existe uma possível solução alternativa, mas o [!DNL Target] não oferece suporte direto ao compartilhamento de uma ID de sessão em vários dispositivos. O cliente deve gerenciar esse compartilhamento de ID.

Esse comportamento também ocorre quando um visitante está ativo em um dispositivo e se torna ativo no outro dispositivo alguns minutos depois. A sessão do primeiro dispositivo não expira por 30 minutos e até cinco minutos de atraso podem ocorrer antes que o estado do perfil seja gravado no estado permanente e processado. Ao testar esse comportamento, aguarde 35 minutos para que a sessão expire e o perfil seja armazenado.

Se o visitante não tiver duas sessões ativas ao mesmo tempo, os itens visualizados recentemente em um dispositivo atualizarão os itens visualizados recentemente no outro dispositivo, desde que a sessão tenha terminado. Ao testar esse comportamento, aguarde 35 minutos para a sessão expirar.

+++

## Critérios, designs e promoções {#criteria-designs-promotions}

+++ Por que nem todos os critérios, incluindo critérios personalizados, estão disponíveis para seleção ao criar uma atividade [!DNL Recommendations]?

Os critérios disponíveis dependem da categoria atual. Quando as ofertas de recomendações são criadas, o seletor de algoritmo exibe os critérios com base na ID da categoria. Se o local onde os critérios são aplicados não contiver a ID da categoria, determinados critérios não estarão disponíveis no seletor de algoritmo. Se um local onde a ID de categoria está presente na mbox for usado, o seletor de critérios conterá todos os critérios aplicáveis.

[!DNL Target] tem uma configuração de [Critérios de Filtro Incompatíveis](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=pt-BR){target=_blank} que controla a filtragem inteligente do seletor de algoritmo. Para acessar a configuração **[!UICONTROL Critérios incompatíveis de filtro]**, clique em **[!UICONTROL Administração]** > **[!UICONTROL Recomendações]**.

![Página Configurações do Recommendations com a opção Critérios incompatíveis de filtro realçada](assets/recs_settings_filter.png)

* Se a configuração **[!UICONTROL Critérios incompatíveis de filtro]** não estiver habilitada, o [!DNL Target] não filtrará os algoritmos no seletor de algoritmo, e todos os algoritmos serão exibidos.
* Se a configuração estiver habilitada nas atividades do [!UICONTROL Visual Experience Composer] (VEC), o [!DNL Target] lerá a entityId e a id da categoria do local selecionado. Em seguida, ele exibe algoritmos com base em `currentItem|currentCategory`, se os respectivos valores estiverem presentes nesse local. Como resultado, somente os algoritmos compatíveis com a localização selecionada são mostrados no seletor de algoritmo por padrão. Os algoritmos não compatíveis ainda podem ser exibidos ao desmarcar a caixa de seleção **[!UICONTROL Compatível]** ao selecionar os critérios.

  ![Tela Selecionar critérios com a caixa de seleção Compatível realçada](assets/compatible_checkbox.png)

[!DNL Target] não exibe a caixa de seleção **[!UICONTROL Compatível]** nos seguintes casos especiais:

* A entityId e a id da categoria estão presentes no local, então nada é filtrado.
* [!DNL mbox.js] versão 55 ou anterior é usada.
* Nenhuma chamada de mbox é acionada na página (`!config.isAutoCreateGlobalMbox && !config.isRegionalMbox`).
* Os parâmetros do [!DNL Target] não estão definidos.

>[!NOTE]
>
>A configuração **[!UICONTROL Critério incompatível de filtro]** se aplica somente a atividades criadas no [!UICONTROL Visual Experience Composer] (VEC). Esta configuração não se aplica a atividades criadas no **[!UICONTROL Experience Composer baseado em formulário]**, porque [!DNL Target] não tem contexto de localização.

+++

+++ Qual a diferença entre ponderação de atributos geral e ponderação de atributo específico à similaridade de conteúdo?

A ponderação de atributos ocorre de duas formas: &quot;ponderação de atributos padrão&quot; e &quot;ponderação de atributos de similaridade de conteúdo&quot;.

* &quot;A ponderação de atributo padrão&quot; aplica-se à maioria dos tipos de critérios, não apenas à **[!UICONTROL Similaridade de conteúdo]**. Esse tipo de ponderação dá mais peso a determinados valores de atributo. No exemplo a seguir, os produtos da Nike terão um aumento nas recomendações de saída.

  ![Seção de Ponderação de Atributos com o atributo de marca definido para começar com Nike e o controle deslizante em 25%](assets/attribute_weighting_example.png)

* &quot;A ponderação do atributo de similaridade de conteúdo&quot; aplica-se somente aos critérios de **[!UICONTROL Similaridade de conteúdo]**. Esse tipo de ponderação é mais dinâmico e se baseia na &quot;chave de recomendação&quot; atual (o item visualizado no momento). No exemplo a seguir (marca x 16), um visitante que visualiza tênis da Nike tem mais probabilidade de ser recomendado a outros produtos da Nike (não necessariamente apenas tênis) do que os tênis de seus concorrentes. Um visitante que visualiza tênis da Adidas tem mais probabilidade de recomendar produtos da Adidas.

  ![Seção de similaridade de conteúdo com o atributo de marca e o controle deslizante de ponderação em 16x](assets/content_similarity_example.png)

+++

+++ O nome da mbox deve ser especificado ao criar critérios, promoções ou regras de teste do modelo de [!DNL Recommendations]?

Quando um critério, uma promoção ou uma regra de teste de modelo [!DNL Recommendations] é criada com base em um parâmetro mbox, `mboxParameter` não solicita mais `mboxName`. O nome da mbox agora é opcional. Essa alteração permite o uso de parâmetros de várias mboxes ou uma referência a um parâmetro que ainda não foi gravado na borda.

Para selecionar o parâmetro desejado, use um dos seguintes métodos:

* Ao criar critérios, promoções ou regras de teste do modelo, selecione um nome de parâmetro na lista. Comece digitando os primeiros caracteres do nome do parâmetro ou digite o nome completo.
* Se o nome da mbox for conhecido, mas o nome do parâmetro não, use a caixa de seleção para filtrar por uma mbox conhecida que transmita o parâmetro desejado.

Com qualquer método, não há link entre a mbox e o parâmetro. Os critérios, as promoções ou as regras de testes do modelo funcionarão de acordo com o parâmetro em todas as mboxes que passam esse parâmetro.

Quando um critério, uma promoção ou uma regra de teste do modelo existente é editada, a filtragem exibe o nome da mbox fornecido durante a criação.

+++

+++ O que pode ser feito quando caracteres especiais quebram uma matriz?

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

+++

+++ Uma entidade pode ser excluída dinamicamente?

Sim. As IDs de entidade para as entidades a serem excluídas das recomendações podem ser passadas na sequência de consulta. Por exemplo, os itens que já estão no carrinho de compras podem ser excluídos.

Para habilitar a função de exclusão, use o parâmetro de mbox `excludedIds`. Este parâmetro aponta para uma lista de IDs de entidade separadas por vírgulas, por exemplo `mboxCreate(..., "excludedIds=1,2,3,4,5")`. O valor é enviado quando as recomendações são solicitadas.

A exclusão é executada somente para a chamada [!DNL Target] atual. Os itens não são excluídos nas chamadas [!DNL Target] subsequentes, a menos que o valor `excludedIds` seja passado novamente. Para excluir os itens no carrinho das recomendações em cada página, continue transmitindo o valor `excludedIds` em cada página.

Para excluir `entityIds`, anexe o token `&excludes=${mbox.excludedIds}` à URL de conteúdo da oferta. Quando o URL do conteúdo for extraído, os parâmetros necessários serão substituídos pelos parâmetros de solicitação atuais do mbox.

Por padrão, esse recurso é habilitado para recomendações criadas recentemente. As recomendações existentes devem ser salvas para oferecer suporte a entidades excluídas dinamicamente.

>[!NOTE]
>
>Se muitas entidades forem excluídas, as recomendações se comportarão como se não houvesse entidades suficientes para preencher o template de recomendação.

+++

+++ Por que uma atividade herdada [!DNL Recommendations] não pode ser salva depois que um novo público-alvo é definido?

Certifique-se de que o público-alvo tenha um nome exclusivo. Se o público-alvo tiver o mesmo nome de um público-alvo existente, a atividade [!DNL Recommendations] herdada (uma atividade [!DNL Recommendations] criada antes de outubro de 2016) não poderá ser salva.

+++

+++ Um algoritmo criado em [!DNL Adobe Recommendations Classic] pode ser usado em [!DNL Recommendations Premium]?

Um algoritmo criado no [!DNL Recommendations Classic] não é compatível com o [!DNL Recommendations Premium]. O algoritmo herdado pode ser utilizável no [!DNL Target Premium], mas pode criar problemas de sincronização quando a atividade é desativada ou excluída na interface do usuário do [!DNL Target Premium]. Para obter mais informações sobre as diferenças entre as duas soluções, consulte [[!DNL Recommendations Classic] versus [!DNL Recommendations] atividades em [!DNL Target Premium]](/help/main/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md).

+++

+++ Como o pode apenas recomendar novos artigos ou vídeos?

Os clientes de mídia e publicação geralmente querem que os itens recomendados incluam apenas os artigos ou vídeos mais recentes. Por exemplo, um cliente do [!DNL Target] usou a seguinte abordagem para recomendar artigos com menos de 60 dias:

1. Transmita a data de publicação do artigo, no formato AAAAMMDD, como um atributo de entidade personalizado. Por exemplo:

   | Atributo de entidade | Exemplo |
   | --- | --- |
   | issueDate | 2021218 |
   | lastViewDate | 2021701 |
   | parentCategory | comentário |
   | publishDate | 20210113 |
   | publishDateDisplay | 13 de janeiro de 2021 |

1. Crie um script de perfil que retorne a data de hoje menos 60 dias, também no formato AAAAMMDD.

   ![Script de perfil chamado priorDate60, descrito como a data de hoje menos 60 dias no formato AAAAMMDD, com o script que calcula a data](/help/main/c-recommendations/c-recommendations-faq/assets/sample-profile-script.png)

1. Use uma regra de inclusão dinâmica nos critérios para que `publish date > today's date minus 60 days`.

   ![Seção Regras de inclusão com uma regra de Correspondência de atributos de perfil que compara publishDate com o valor armazenado em user.priorDate60](/help/main/c-recommendations/c-recommendations-faq/assets/sample-inclusion-rule.png)

Este exemplo também pode ser realizado com a correspondência de parâmetros, passando o valor `priorDate60` como um parâmetro de mbox.

+++

## Solução de problemas {#troubleshooting}

+++ Por que o [!DNL Target] às vezes não mostra recomendações?

Às vezes, [!DNL Target] não consegue mostrar recomendações devido ao baixo número de recomendações disponíveis.

O número de valores gerados para cada critério é o triplo do número de entidades especificadas no design. A filtragem em tempo de execução (por exemplo, correspondência de atributos de inventário ou mbox) é aplicada após os valores 3x serem gerados, portanto, menos que valores 3x podem permanecer no momento da entrega. Para atenuar essa situação, aumente o número de entidades no modelo ao ocultar as entidades adicionais.

É possível usar o seguinte código em JavaScript no início do design para aumentar o número de entidades solicitadas. Neste exemplo, a contagem de entidades solicitadas é 30 (3x10).

```
#foreach($entity in $entities) 
 #if( $foreach.count > 10 ) 
  #break 
 #end 
 #set ($foo = $entity.id) 
#end 
```

+++

+++ O que significa a resposta NO_CONTENT retornada às vezes no rastreamento de conteúdo [!DNL Recommendations]?

NO_CONTENT é retornado quando as recomendações não estão disponíveis para o algoritmo solicitado e a combinação de chaves. Essa situação geralmente ocorre quando os backups são desativados para o algoritmo e uma ou mais das seguintes condições também são verdadeiras:

* Os resultados ainda não estão prontos.

  Normalmente, essa situação ocorre quando uma atividade recém-criada é salva pela primeira vez ou depois que alterações de configuração são feitas na coleção, nos critérios ou nas promoções usadas na atividade.

* Os resultados estão prontos, mas ainda não são armazenados em cache no servidor de borda mais próximo para o algoritmo solicitado e a combinação de chaves.

  A solicitação inicia uma operação de cache, portanto, esse problema é resolvido após alguns recarregamentos de página ou após alguns minutos.

* Os resultados estão prontos, mas não estão disponíveis para o valor principal fornecido.

  Normalmente, essa situação ocorre quando as recomendações são solicitadas para um item que foi adicionado ao catálogo após a execução mais recente do algoritmo. Ela resolve após a execução do próximo algoritmo.

* A renderização parcial do modelo está desativada e não há resultados suficientes disponíveis para preencher o modelo.

  Normalmente, essa situação ocorre com uma regra de inclusão dinâmica que filtra agressivamente muitos itens dos resultados possíveis. Para evitar essa situação, ative os backups e não aplique a regra de inclusão aos backups ou use os critérios em sequência com critérios filtrados menos agressivos.

+++

+++ O que deve ser feito quando uma coleção em [!DNL Recommendations] chega a zero (0)?

Considere o seguinte quando uma coleção que anteriormente não estava em zero chegar a zero:

* Salve novamente a coleção e verifique se o número é atualizado. Salvar novamente executa todos os algoritmos que usam essa coleção.
* Verifique se o ambiente correto é exibido. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Recomendações]** e verifique a configuração **[!UICONTROL Grupo de Hosts Padrão]** na seção **[!UICONTROL Catálogo de Produtos]**.

  ![Página Recomendações da guia Administração com o menu suspenso Grupo de Hosts Padrão realçado na seção Catálogo de Produtos](../assets/reco_faq_1.png)

* Verifique se o índice está atualizado. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Pesquisa no catálogo]** e verifique quantas horas têm o índice (por exemplo, &quot;Indexado há 3 horas&quot;). O índice pode ser atualizado conforme necessário.
* Verifique se algo foi alterado no feed ou na camada de dados que resultou nas entidades que não correspondem mais às regras de coleção. Verifique se a caixa corresponde (as regras diferenciam maiúsculas de minúsculas).
* Verifique se o feed foi executado com sucesso ou se alguém alterou o diretório FTP, a senha e assim por diante.
* O [!DNL Target] atualiza a entrega (na página ou no aplicativo do cliente) o mais rápido possível e também precisa fornecer uma representação na interface do usuário para o profissional de marketing. O [!DNL Target] não atrasa a entrega de atualizações para esperar que as atualizações da interface estejam em sincronia. Use [mboxTrace](/help/main/c-activities/c-troubleshooting-activities/content-trouble.md) para ver o que há no sistema no momento em que a solicitação é recebida.

+++

+++ Por que a ação **[!UICONTROL Baixar dados]** falha em uma atividade [!DNL Recommendations]?

Quando **[!UICONTROL Dados de download]** são clicados na página **[!UICONTROL Visão geral da atividade]** de uma atividade [!DNL Recommendations], a interface do usuário [!DNL Target] pode exibir o erro `Error while fetching recommendation data file.`

Normalmente, esse erro ocorre quando a atividade tem um conjunto de resultados muito grande. O CSV gerado excede o tamanho da resposta que pode ser retornado pela interface do usuário em um único download. Os dados da recomendação estão intactos. Somente o caminho de download no navegador não pode fornecer um arquivo desse tamanho.

+++

## Problemas conhecidos {#known-issues}

A seguir, os problemas conhecidos com [!UICONTROL atividades do Recommendations]:

* Quando [!DNL Target] retorna uma oferta JSON com `getOffer()`, ela retorna um tipo de JSON. No entanto, um design JSON [!DNL Recommendations] retorna um tipo de HTML.
* As entidades expiradas expiram corretamente após 60 dias sem receber nenhuma atualização por meio de um feed ou da API. No entanto, as entidades expiradas não são removidas do índice **[!UICONTROL Pesquisa de catálogo]** após a expiração. As entidades excluídas por meio de um feed ou da API também não são removidas do índice **[!UICONTROL Pesquisa de catálogo]**. (IRI-857)
* As ofertas do [!DNL Recommendations] nas atividades A/B e direcionamento de experiência não mostram uma visualização visual da bandeja do [!DNL Recommendations]. (TGT-33426)
* O status do feed de Critérios personalizados exibido na visualização da lista de critérios (cartão) é atualizado a cada dez minutos e pode estar desatualizado em mais de dez minutos em raras circunstâncias. O status exibido na visualização de edição de Critérios personalizados é buscado em tempo real e está sempre atualizado. (TGT-35896, TGT-36173)
