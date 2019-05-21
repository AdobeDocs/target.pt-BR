---
description: As informações sobre os limites de caracteres e outros limites (tamanho da oferta, públicos, valores, parâmetros etc.) que afetam as atividades e outros elementos no Adobe Target.
keywords: limite de caracteres, parâmetros da mbox, api de entrega em lote, parâmetros do perfil, limites, perfis incorporados, máximo, limite, restrição, caractere, prática recomendada, orderid, orderTotal, mbox3rdPartyID, categoria, categoryID
seo-description: As informações sobre os limites de caracteres e outros limites (tamanho da oferta, públicos, valores, parâmetros etc.) que afetam as atividades e outros elementos no Adobe Target.
seo-title: Limites
solution: Target
title: Limites
topic: Padrão
uuid: 603fb800-a26c-43ec-b2d9-ef7a8ed8721e
translation-type: tm+mt
source-git-commit: dda07f19bddb870b20dabc484a1b97d55bcc5775

---


# Limites{#limits}

As informações sobre os limites de caracteres e outros limites (tamanho da oferta, públicos, valores, parâmetros etc.) que afetam as atividades e outros elementos no Adobe Target.

Os limites relacionados abaixo são limites recomendados. Quando esses limites são atingidos ou ultrapassados, o desempenho pode diminuir. A redução do tempo de carregamento da interface também pode ser causada por uma atividade bastante complexa, como muitos públicos-alvo, destinos e experiências em uma mesma atividade.

Atividades altamente complexas devem ser analisadas com a Consultoria da Adobe e testadas em um ambiente restrito antes de serem liberadas para produção.

## Nomes de atividades

**Limite**: 250 caracteres.

## Nomes de público-alvo

**Limite**: 256 caracteres.

Valores maiores que 256 caracteres são truncados.

## parâmetro categoryId

**Limite**: 250 caracteres.

## Nomes de atributos do cliente

**Limite**: 128 caracteres.

## ID de alias do atributo do cliente

**Limite** de 50 caracteres.

## Atributos personalizados de entidade

**Limite**: O tamanho máximo depende do idioma.

* 15,000 caracteres (idiomas de valor único, de um e dois bytes)
* Values 00 valores, 100 caracteres por valor (vários valores)

O tamanho máximo dos atributos personalizados de entidade única tem 15,000 caracteres (para idiomas codificados de um e dois bytes UTF -8, como inglês e outros alfabetos de script latinos) ou 10,000 caracteres (para idiomas codificados em três bytes, como chinês, japonês e coreano).

Atributos personalizados de entidade de vários valores podem conter não mais do que 500 valores. Cada valor individual é limitado a 100 caracteres. O número total de caracteres em todos os valores deve estar em conformidade com as limitações para o comprimento máximo dos atributos personalizados de entidade única (veja acima).

## Parâmetros entityid

**Limite**: 1,000 caracteres.

## Excludedids {#excludedid}

**Limite**: 5 KB para solicitações POST. 2,083 caracteres menos o comprimento do URL para solicitações GET.

Para solicitações GET, embora o limite no back end seja de 5 KB, devido ao fato do Microsoft Internet Explorer limitar o URL a 2,083 caracteres, o limite realista é de 2,083 caracteres, menos o comprimento atual do URL.

## Nomes de experiências

**Limite**: 20 caracteres.

## Valor do atributo de perfil in-mbox

**Limite**: 256 caracteres.

Valores mais longos do que isso são truncados.

## Perfis in-mbox em uma solicitação de mbox

**Limite**: 50 perfis.

Todos os perfis depois de 50 são ignorados.

## Nomes de perfil in-mbox

**Limite**: 128 caracteres.

## nomes de mbox

**Limite**: 250 caracteres.

## parâmetros de mbox

**Limite**: Os seguintes limites se aplicam aos parâmetros da mbox:

* parâmetros de mbox: Parameters 00 parâmetros por mbox.
* Parâmetros de perfil: 500 parâmetros.
* parâmetros de perfil por mbox:
* Outros parâmetros (URL, URL de referência etc.): 50 por mbox para cada tipo de parâmetro.

Para parâmetros que são registrados no banco de dados do Target, os limites acima são para solicitações de mbox padrão. Esses limites se aplicam a menos que a solicitação seja diminuída devido a limitações do navegador da Web.

Se estiver usando a [API de entrega em lote](https://developers.adobetarget.com/api/#server-side-batch-delivery) no SDK do Mobile Services, os limites de 50 parâmetros de mbox, 50 parâmetros de perfil e 50 para outros tipos de parâmetros são limitações da própria API. Não é possível enviar uma solicitação que contém mais que esses números usando a API de entrega em lote. Se uma solicitação contém mais que estes limites, a API retornará a seguinte mensagem de erro: &quot;O número de mboxParameters não pode exceder 100&quot;.

## Urls de solicitação de mbox

**Limite**: 2,083 caracteres.

Esse limite se deve às restrições de tamanho do Microsoft Internet Explorer.

## parâmetro mbox3rdPartyId

**Limite**: 60 caracteres.

## Nomes de ofertas

**Limite**: 250 caracteres.

## Tamanho da oferta

**Limite**: Os limites de tamanho a seguir se aplicam a ofertas:

* 256 KB para ofertas HTML.
* 64 KB para ofertas visuais da interface do usuário.
* 512 KB da API.

Se você estiver usando uma mbox global, o limite será para todo o conjunto de conteúdo retornado para a página. A limitação do tamanho da oferta melhoro o tempo de carregamento da página. Se o limite for excedido, a seguinte mensagem será exibida:

&quot;O conteúdo da experiência é grande demais para entrega. Modifique a experiência para afetar menos o código da página.&quot;

## parâmetro orderId

**Limite**: 120 caracteres.

Limite recomendado.

## parâmetro orderTotal

**Limite**: 120 caracteres.

Limite recomendado.

## parâmetro productPurchasedId

**Limite**: 47 caracteres por valor separado por vírgula.

Qualquer coisa mais é truncada pelo sistema.

## Contas/públicos-alvo reutilizáveis

**Limite**: 75 públicos-alvo.

Limite recomendado. Os limites de tempo do JavaScript ocorrem na interface caso você tenha limites demais.

## Caixa de entrada de perfil de script na interface do usuário do Target

**Limite**: 2,000 caracteres.

Limite recomendado. Depende do tamanho da cadeia de caracteres codificada, que pode ser muito maior que a cadeia bruta. Se a cadeia de caracteres for grande demais, falhará antes de chegar no Adobe Target.

## Nomes de perfil de script

**Limite**: 50 caracteres.

## Valores do perfil de script

**Limite**: 2,048 caracteres.

Por motivos de desempenho, recomendamos retornar um valor que não ultrapasse 256 caracteres.

Para um valor de retorno de string, se o tamanho do valor de retorno exceder 2,048 caracteres, o script será desativado pelo sistema.

Para um valor de retorno de matriz, se o tamanho dos valores concatenados da matriz exceder 2,048 caracteres, o script será desativado pelo sistema.

## Condições de meta

**Limite**: 1,00valores.

Limite recomendado. Isso se refere ao número de valores separados por linha na área de texto de definição de metas. Por exemplo, inserir 1.000 códigos postais em uma meta de código postal.