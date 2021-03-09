---
keywords: limite de caracteres, parâmetros da mbox, api de entrega em lote, parâmetros do perfil, limites, perfis incorporados, máximo, limite, restrição, caractere, prática recomendada, orderid, orderTotal, mbox3rdPartyID, categoria, categoryID, solução de problemas
description: Exibir uma lista de limites de caracteres e outros limites (tamanho da oferta, públicos, perfis, valores, parâmetros etc.) que afetam as atividades e outros elementos no Adobe Target.
title: Quais são os vários caracteres, tamanho e outros limites no Adobe Target?
feature: Solução de problemas
mini-toc-levels: 3
translation-type: tm+mt
source-git-commit: 801a2717615a1f0ff2ce306cda59f68cc5c4a8f8
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 64%

---


# Limites

Limites de caracteres e outros limites (tamanho da oferta, públicos, perfis, valores, parâmetros etc.) que afetam as atividades e outros elementos no [!DNL Adobe Target].

>[!NOTE]
>
>Os limites listados abaixo devem ser considerados limites &quot;rígidos&quot;, a menos que especificados como &quot;recomendados&quot;.
>
>Quando os limites designados como &quot;recomendados&quot; forem atingidos ou ultrapassados, o desempenho poderá ficar lento. A redução do tempo de carregamento da interface também pode ser causada por uma atividade bastante complexa, como muitos públicos-alvo, destinos e experiências em uma mesma atividade.
>
>Atividades altamente complexas devem ser analisadas com a [!DNL Adobe] Consulting e testadas em um ambiente limitado antes de serem liberadas para produção.

## Atividades

### Nomes de atividade

* **Limite**: 250 caracteres.

### Número de atividades por conta

* **Limite recomendado**: 10.000 atividades ativas.

* **Limite** recomendado: 10.000 atividades ativas salvas (e não finalizadas).

## Públicos-alvo

### Nomes do público-alvo

* **Limite**: 255 caracteres.

### Públicos-alvo, reutilizáveis por conta

* **Limite recomendado**: 20,000 públicos-alvo.

### Número de públicos-alvo por mbox, métrica ou experiência

* **Limite**: 50 públicos-alvo

## parâmetro categoryId

* **Limite**: 128 caracteres.

## Atributos do cliente

### Nomes do atributo do cliente

* **Limite**: 250 caracteres por meio de feed ou API.

### ID de alias do atributo do cliente

* **Limite** 50 caracteres.

### Atributos do cliente, upload

* **Tamanho máximo de arquivo para cada upload usando o método** HTTP: 100 MB.
* **tamanho máximo de arquivo para cada upload usando o método** FTP: 4 GB
* **Número de atributos permitidos para a inscrição**: 5 para  [!DNL Target Standard] e 200 para  [!DNL Target Premium].

## Entidades

### Número de entidades

* A quantidade máxima de entidades que podem ser referenciadas em um design, seja em código fixo ou via loops, é de 99.

### Atributos personalizados da entidade

* **Atributos** de entidade personalizados: 100.

* **Limite** de caracteres: O comprimento máximo de caracteres depende do idioma.

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

   30.000 experiências por atividade de personalização automatizada (AP).

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
   * Parâmetros do perfil: 500 parâmetros de perfil por mbox.
   * Outros parâmetros (URL, URL de referência etc.): 50 por mbox para cada tipo de parâmetro.

   Esses limites se aplicam a menos que a solicitação seja diminuída devido a limitações do navegador da Web.

   Se estiver usando a API de entrega em lote, o limite será de 50 mboxes por solicitação em lote.

   Se estiver usando a [API de entrega em lote](https://developers.adobetarget.com/api/#server-side-batch-delivery) no SDK do Mobile Services, os limites de 50 parâmetros de mbox, 50 parâmetros de perfil e 50 para outros tipos de parâmetros são limitações da própria API. Não é possível enviar uma solicitação que contém mais que esses números usando a API de entrega em lote. Se uma solicitação contém mais que esses limites, a API retornará a seguinte mensagem de erro:

   &quot;O número de mboxParameters não pode exceder 50.&quot;

   Limites definidos para endpoints:

   **Mbox em lote v2**:

   * Parâmetros da mbox 100
   * Comprimento máximo do nome do parâmetro da mbox 128
   * O valor do parâmetro da mbox não pode ser nulo
   * valor do parâmetro da mbox 5000
   * parâmetros de perfil 50
   * comprimento máximo do nome de parâmetro do perfil 128
   * o valor do parâmetro do perfil não pode ser nulo
   * comprimento máximo do valor do parâmetro do perfil 256

   **Ponto de extremidade** da API de entrega:

   * parâmetros da mbox 50
   * Comprimento máximo do nome do parâmetro da mbox 128
   * O valor do parâmetro da mbox não pode ser nulo
   * valor do parâmetro da mbox 5000
   * parâmetros de perfil 50
   * comprimento máximo do nome de parâmetro do perfil 128
   * o valor do parâmetro do perfil não pode ser nulo
   * comprimento máximo do valor do parâmetro do perfil 256



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

Os seguintes limites de tamanho se aplicam a ofertas:

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

* **Limite**: 47 caracteres por valor separado por vírgulas e 250 caracteres no total. Valores individuais com mais de 47 caracteres podem ser truncados pelo sistema. Comprimentos totais acima de 250 caracteres podem resultar em um erro 400.

## Scripts de perfil

* **Limite recomendado de scripts** de perfil ativos: 300

* **Limite recomendado do total de scripts de perfil por conta**: 2.000

* **Recomendações para limitar a complexidade** do script de perfil: Os scripts de perfil podem executar um número limitado de instruções. Para obter mais informações, consulte [Práticas recomendadas](/help/c-target/c-visitor-profile/profile-parameters.md#best) em *Atributos do perfil*.

## Propriedades

* **Limite recomendado**: 5.000 propriedades.

## Segmentos/públicos-alvo dos relatórios

* **Limite**: 50 públicos-alvos/segmentos por atividade.

## Caixa de entrada do perfil de script na interface do usuário do Target

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

* **Limite** recomendado: 2.500 caracteres por valor de regra de direcionamento.
* **Limite recomendado**: 30.000 valores únicos por público-alvo nas regras de direcionamento.
* **Limite recomendado**: 100.000 valores únicos de regras de direcionamento por atividade.

