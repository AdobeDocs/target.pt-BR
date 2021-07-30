---
keywords: limite de caracteres;parâmetros da mbox;api de entrega em lote;parâmetros do perfil, limites;perfis incorporados;máximo;limite;restrição;caractere;prática recomendada;orderid;orderTotal;mbox3rdPartyID;categoria;categoryID
description: As informações sobre os limites de caracteres e outros limites (tamanho da oferta, públicos-alvo, valores, parâmetros etc.) que afetam as atividades e outros elementos no Adobe Target.
title: Quais são os vários limites de caracteres, tamanho e outros limites no Adobe Target?
feature: Solução de problemas
mini-toc-levels: 3
exl-id: b318ab16-1382-4f3a-8764-064adf384d6b
source-git-commit: ee626e29186f56bbcfc29f4c148c8bdd4f62319e
workflow-type: tm+mt
source-wordcount: '1320'
ht-degree: 90%

---

# Limites

Limites de caracteres e outros limites (tamanho da oferta, públicos, valores, parâmetros etc.) que afetam as atividades e outros elementos no [!DNL Adobe Target].

>[!NOTE]
>
>Os limites listados abaixo devem ser considerados limites &quot;rígidos&quot;, a menos que especificados como &quot;recomendados&quot;.
>
>Quando os limites designados como &quot;recomendados&quot; forem atingidos ou ultrapassados, o desempenho poderá ficar lento. A redução do tempo de carregamento da interface também pode ser causada por uma atividade bastante complexa, como muitos públicos-alvo, destinos e experiências em uma mesma atividade.
>
>Atividades altamente complexas devem ser analisadas com a consultoria da [!DNL Adobe] e testadas em um ambiente restrito antes de serem liberadas para produção.

## Atividades

### Nomes de atividade

* **Limite**: 250 caracteres.

### Número de atividades por conta

* **Limite recomendado**: 10.000 atividades ativas.

* **Limite recomendado**: 10.000 atividades ativas salvas (e não finalizadas).

## Chamadas de API do Target

* **Limite**: 50 chamadas por minuto para as APIs de Administração, Relatórios e atualização de perfil em massa. Esse limite não se aplica às APIs de entrega e atualização de perfil único.

   Se você fizer mais de 50 chamadas de API por minuto, o [!DNL Target] retornará uma mensagem de erro &quot;Status HTTP 503&quot;.

## Públicos-alvo

### Nomes do público-alvo

* **Limite**: 255 caracteres.

### Públicos-alvo, reutilizáveis por conta

* **Limite recomendado**: 20,000 públicos-alvo.

### Número de públicos-alvo por mbox, métrica e experiência

* **Limite**: 50 públicos-alvo

## parâmetro categoryId

* **Limite**: 250 caracteres.

## Entrega de conteúdo {#content-delivery}

* **Limite**: 100 solicitações de entrega de  [!DNL Target] conteúdo simultâneo por sessão de usuário.

   Se um cliente exceder 100 solicitações simultâneas de entrega de conteúdo [!DNL Target] para uma determinada sessão de usuário, todas as solicitações subsequentes para essa sessão de usuário serão bloqueadas. Duas ou mais solicitações são consideradas simultâneas se todas forem enviadas para o servidor [!DNL Target] antes que a resposta seja recebida para qualquer uma delas. [!DNL Target] processa solicitações simultâneas para a mesma sessão sequencialmente.

* **Comportamento** de erro:

   * API de entrega e Mbox de lote v2:
      * Código de erro: HTTP 420 Demasiadas Solicitações
      * Mensagem de erro: &quot;Muitas solicitações com a mesma ID de sessão&quot;
   * API mbox herdada:
      * Conteúdo padrão com comentário &quot;Muitas solicitações com a mesma ID de sessão&quot;
   * at.js:
      * Conteúdo padrão exibido



## Atributos do cliente

### Nomes do atributo do cliente

* **Limite**: 250 caracteres por meio de feed ou API.

### ID de alias do atributo do cliente

* **Limite** 50 caracteres.

### Atributos do cliente, upload

* **O tamanho máximo de arquivo para cada upload usando o método de HTTP**: 100 MB.
* **Tamanho máximo de arquivo para cada upload usando o método de FTP**: 4 GB.
* **O número de atributos permitidos para a inscrição**: 5 para o [!DNL Target Standard] e 200 para o [!DNL Target Premium].

## Entidades

### Número de entidades

* A quantidade máxima de entidades que podem ser referenciadas em um design, seja em código fixo ou via loops, é de 99.
* O limite recomendado para obter o melhor desempenho é manter o catálogo com menos de um milhão de itens por ambiente e menos de dez milhões de itens em todos os ambientes.
* O limite máximo é de dez milhões de itens por ambiente e 100 milhões de itens em todos os ambientes. Se você tiver entre um milhão e dez milhões de itens por ambiente, o desempenho da interface do [!UICONTROL Pesquisa no catálogo] será afetado. No entanto, o [!DNL Target Recommendations] continua a produzir e fornecer recomendações.

### Atributos personalizados da entidade

* **Atributos de entidades personalizados**: 100.

* **Limite de caracteres**: o tamanho máximo depende do idioma.

   * 15.000 caracteres (idiomas de valor único, de um e dois bytes)
   * 500 valores, 100 caracteres por valor (vários valores)

   O tamanho máximo dos atributos personalizados da entidade de valor único é de 15.000 caracteres (para idiomas codificados de um e dois bytes UTF -8, como inglês e outros alfabetos de script latinos) ou 10.000 caracteres (para idiomas codificados em três bytes UTF-8, como chinês, japonês e coreano).

   Os atributos personalizados de entidade de vários valores não podem conter mais de 500 valores. Cada valor individual é limitado a 100 caracteres. O número total de caracteres em todos os valores deve estar em conformidade com o limite de tamanho máximo dos atributos personalizados da entidade de valor único (veja acima).

### Parâmetros entityID

* **Limite**: 1.000 caracteres.

## excludedIds {#excludedid}

* **Limite**: 5 KB para solicitações POST. 2.083 caracteres menos o comprimento do URL para solicitações GET.

   Para solicitações GET, embora o limite no back end seja de 5 KB, devido ao limite de 2.083 caracteres do URL do Microsoft Internet Explorer, o limite realista é de 2.083 caracteres menos o comprimento atual do URL.

## Experiências

### Nomes de experiência

* **Limite**: 50 caracteres.

### Experiências por atividade

* **Limite**: 2.000 experiências por direcionamento de experiência (XT), Teste A/B, Teste multivariado (MVT) e atividade automática do Target.

   30.000 experiências por atividade de Automated Personalization (AP).

### Modificações por experiência

* **Limite**: 50 por experiência em qualquer atividade

## mboxes

### Valor do atributo de perfil da in-mbox

* **Limite**: 256 caracteres.

   Valores mais longos do que isso são truncados.

### Nomes de perfil da in-mbox

* **Limite**: 128 caracteres.

### nomes de mbox

* **Limite**: 250 caracteres.

### parâmetros de mbox

* **Limite**: os seguintes limites se aplicam aos parâmetros da mbox:

   Para chamadas de mbox padrão:

   * Parâmetros da mbox: 500 parâmetros por mbox.
   * Parâmetros do perfil: 500 parâmetros do perfil por mbox.
   * Outros parâmetros (URL, URL de referência etc.): 50 por mbox para cada tipo de parâmetro.

   Esses limites se aplicam a menos que a solicitação seja diminuída devido a limitações do navegador da Web.

   Se estiver usando a API de entrega em lote, o limite será de 50 mboxes por solicitação em lote.

   Se estiver usando a [API de entrega em lote](https://developers.adobetarget.com/api/#server-side-batch-delivery) no SDK do Mobile Services, os limites de 50 parâmetros de mbox, 50 parâmetros de perfil e 50 para outros tipos de parâmetros são limitações da própria API. Não é possível enviar uma solicitação que contém mais que esses números usando a API de entrega em lote. Se uma solicitação contém mais que esses limites, a API retornará a seguinte mensagem de erro:

   &quot;O número de mboxParameters não pode exceder 50.&quot;

   Limites definidos para endpoints:

   **Batch mbox v2**:

   * 100 parâmetros de mbox
   * tamanho máx. do nome do parâmetro da mbox 128
   * O valor do parâmetro da mbox não pode ser nulo
   * valor do parâmetro da mbox 5000
   * parâmetros de perfil 50
   * tamanho máx. do nome do parâmetro do perfil 128
   * O valor do parâmetro do perfil não pode ser nulo
   * tamanho máximo do valor do parâmetro do perfil 256

   **Endpoint da API de entrega**:

   * parâmetros de mbox 50
   * tamanho máx. do nome do parâmetro da mbox 128
   * O valor do parâmetro da mbox não pode ser nulo
   * valor do parâmetro da mbox 5000
   * parâmetros de perfil 50
   * tamanho máx. do nome do parâmetro do perfil 128
   * O valor do parâmetro do perfil não pode ser nulo
   * tamanho máximo do valor do parâmetro do perfil 256



### URLs de solicitação de mbox

* **Limite**: 2.083 caracteres.

   Esse limite é devido a restrições de tamanho de URL do Microsoft Internet Explorer.

### parâmetro mbox3rdPartyId

* **Limite**: 60 caracteres.

## Ofertas

### Nomes da oferta

* **Limite**: 250 caracteres.

### Número de ofertas

* **Limite recomendado**: 50.000 ofertas totais.

### Tamanho da oferta {#offer-size}

Os seguintes limites de tamanho se aplicam às ofertas:

* 1024 KB para ofertas HTML.
* 1024 KB (para cada experiência) para ofertas visuais da interface do usuário.
* 1024 KB da API.

   Se estiver usando uma mbox global, o limite será para todo o conjunto de conteúdo retornado para a página. A limitação do tamanho da oferta melhora o tempo de carregamento da página. Se o limite for excedido, a seguinte mensagem será exibida:

   &quot;O conteúdo da experiência é grande demais para entrega. Modifique a experiência para afetar menos o código da página.&quot;

## parâmetro orderId

* **Limite recomendado**: 120 caracteres.

## parâmetro orderTotal

* **Limite recomendado**: 120 caracteres.

## parâmetro productPurchasedId

* **Limite**: 50 caracteres por valor separado por vírgulas e 250 caracteres no total. Valores individuais com mais de 50 caracteres são truncados pelo sistema. O total de comprimentos acima de 250 caracteres resulta em um erro de 400.

## Scripts de perfil

* **Limite recomendado de scripts de perfil ativos (aqueles que estão ativados)**: 300

* **Limite recomendado do total de scripts de perfil por conta**: 2.000

* **Recomendações para limitar a complexidade do script de perfil**: os scripts de perfil podem executar um número limitado de instruções. Para obter mais informações, consulte [Práticas recomendadas](/help/c-target/c-visitor-profile/profile-parameters.md#best) em *Atributos do perfil*.

## Propriedades

* **Limite recomendado**: 5.000 propriedades.

## Segmentos/públicos-alvo dos relatórios

* **Limite**: 50 públicos-alvos/segmentos por atividade.

## Caixa de entrada de perfil de script na interface do [!DNL Target]

* **Limite recomendado**: 2.000 caracteres.

   Depende do tamanho da cadeia de caracteres codificada, que pode ser muito maior que a cadeia bruta. Se a cadeia de caracteres for grande demais, falhará antes de chegar no Adobe Target.

## Perfis de script

### Nomes de perfil de script

* **Limite**: 50 caracteres.

### Valores de perfil de script

* **Limite**: 2.048 caracteres.

   Por motivos de desempenho, recomendamos retornar um valor que não ultrapasse 256 caracteres.

   Para um valor de retorno de Sequência de caracteres, se o tamanho do valor de retorno exceder 2.048 caracteres, o script será desativado pelo sistema.

   Para um valor de retorno de matriz, se o tamanho dos valores concatenados da matriz exceder 2.048 caracteres, o script será desativado pelo sistema.

## Métricas de sucesso

* **Limite**: 200 por atividade.

## Direcionamento

### Condições do Target

* **Limite recomendado**: 1.000 valores.

   Isso se refere ao número de valores separados por linha na área de texto de definição de metas. Por exemplo, inserir 1.000 códigos postais em uma meta de código postal.

### Regras de direcionamento

* **Limite recomendado**: 2.500 caracteres por valor de regra de direcionamento.
* **Limite recomendado**: 30.000 valores únicos por público-alvo nas regras de direcionamento.
* **Limite recomendado**: 100.000 valores únicos de regras de direcionamento por atividade.
