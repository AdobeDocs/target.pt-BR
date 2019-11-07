---
keywords: limite de caracteres, parâmetros da mbox, api de entrega em lote, parâmetros do perfil, limites, perfis incorporados, máximo, limite, restrição, caractere, prática recomendada, orderid, orderTotal, mbox3rdPartyID, categoria, categoryID
description: As informações sobre os limites de caracteres e outros limites (tamanho da oferta, públicos, valores, parâmetros etc.) que afetam as atividades e outros elementos no Adobe Target.
title: Limites
topic: Padrão
uuid: 603fb800-a26c-43ec-b2d9-ef7a8ed8721e
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Limites{#limits}

As informações sobre os limites de caracteres e outros limites (tamanho da oferta, públicos, valores, parâmetros etc.) que afetam as atividades e outros elementos no Adobe Target.

>[!NOTE]
>
>Os limites listados abaixo devem ser considerados limites "rígidos", a menos que especificados como "recomendados".
>
>Quando os limites designados como "recomendados" forem atingidos ou ultrapassados, o desempenho poderá ficar lento. A redução do tempo de carregamento da interface também pode ser causada por uma atividade bastante complexa, como muitos públicos-alvo, destinos e experiências em uma mesma atividade.
>
>Atividades altamente complexas devem ser analisadas com a Consultoria da Adobe e testadas em um ambiente restrito antes de serem liberadas para produção.

## Atividades

**Limite recomendado**: 10.000 atividades ativas.

**Limite** recomendado: 10.000 atividades salvas (e não encerradas) ativas.

## Nomes de atividade

**Limite**: 250 caracteres.

## Nomes do público-alvo

**Limite**: 255 caracteres.

## Públicos-alvo

**Limite**: 50 públicos-alvos por mbox, métrica ou experiência.

## parâmetro categoryId

**Limite**: 128 caracteres.

## Nomes do atributo do cliente

**Limite**: 128 caracteres.

## ID de alias do atributo do cliente

**Limite** 50 caracteres.

## Atributos personalizados da entidade

**Limite**: o tamanho máximo depende do idioma.

* 15.000 caracteres (idiomas de valor único, de um e dois bytes)
* 500 valores, 100 caracteres por valor (vários valores)

O tamanho máximo dos atributos personalizados da entidade de valor único é de 15.000 caracteres (para idiomas codificados de um e dois bytes UTF -8, como inglês e outros alfabetos de script latinos) ou 10.000 caracteres (para idiomas codificados em três bytes UTF-8, como chinês, japonês e coreano).

Os atributos personalizados de entidade de vários valores não podem conter mais de 500 valores. Cada valor individual é limitado a 100 caracteres. O número total de caracteres em todos os valores deve estar em conformidade com o limite de tamanho máximo dos atributos personalizados da entidade de valor único (veja acima).

## Parâmetros entityID

**Limite**: 1.000 caracteres.

## excludedIds {#excludedid}

**Limite**: 5 KB para solicitações POST. 2.083 caracteres menos o comprimento do URL para solicitações GET.

Para solicitações GET, embora o limite no back end seja de 5 KB, devido ao limite de 2.083 caracteres do URL do Microsoft Internet Explorer, o limite realista é de 2.083 caracteres menos o comprimento atual do URL.

## Nomes de experiência

**Limite**: 50 caracteres.

## Experiências por atividade

**Limite**: 2.000 experiências por direcionamento de experiência (XT), Teste A/B, Teste multivariado (MVT) e atividade automática do Target.

30.000 experiências por atividade de personalização automatizada (AP).

## Valor do atributo de perfil da in-mbox

**Limite**: 256 caracteres.

Valores mais longos do que isso são truncados.

## Perfis in-mbox em uma solicitação de mbox

**Limite**: 50 perfis.

Todos os perfis depois de 50 são ignorados.

## Nomes de perfil da in-mbox

**Limite**: 128 caracteres.

## nomes de mbox

**Limite**: 250 caracteres.

## parâmetros de mbox

**Limite**: os seguintes limites se aplicam aos parâmetros da mbox:

* Parâmetros da mbox: 500 parâmetros por mbox.
* Parâmetros de perfil: 500 parâmetros.
* parâmetros de perfil por mbox:
* Outros parâmetros (URL, URL de referência etc.): 50 por mbox para cada tipo de parâmetro.

Para parâmetros registrados no banco de dados do Target, os limites acima são para solicitações de mbox padrão. Esses limites se aplicam a menos que a solicitação seja diminuída devido a limitações do navegador da Web.

Se estiver usando a [API de entrega em lote](https://developers.adobetarget.com/api/#server-side-batch-delivery) no SDK do Mobile Services, os limites de 50 parâmetros de mbox, 50 parâmetros de perfil e 50 para outros tipos de parâmetros são limitações da própria API. Não é possível enviar uma solicitação que contém mais que esses números usando a API de entrega em lote. Se uma solicitação contém mais que estes limites, a API retornará a seguinte mensagem de erro:
"O número de mboxParameters não pode exceder 100".

## URLs de solicitação de mbox

**Limite**: 2.083 caracteres.

Esse limite é devido a restrições de tamanho de URL do Microsoft Internet Explorer.

## parâmetro mbox3rdPartyId

**Limite**: 60 caracteres.

## Nomes da oferta

**Limite**: 250 caracteres.

## Tamanho da oferta

**Limite**: os seguintes limites de tamanho se aplicam a ofertas:

* 256 KB para ofertas HTML.
* 64 KB para ofertas visuais da interface do usuário.
* 512 KB da API.

Se estiver usando uma mbox global, o limite será para todo o conjunto de conteúdo retornado para a página. A limitação do tamanho da oferta melhora o tempo de carregamento da página. Se o limite for excedido, a seguinte mensagem será exibida:

"O conteúdo da experiência é grande demais para entrega. Modifique a experiência para afetar menos o código da página."

## Ofertas

**Limite recomendado**: 50.000 ofertas totais.

## parâmetro orderId

**Limite recomendado**: 120 caracteres.

## parâmetro orderTotal

**Limite recomendado**: 120 caracteres.

## parâmetro productPurchasedId

**Limite**: 47 caracteres por valor separado por vírgula.

Qualquer valor maior será truncado pelo sistema.

## Scripts de perfil

**Limite recomendado**: 300 scripts de perfil ativos.

**Limite recomendado**: Número máximo de 500,000 loops por script de perfil.

## Propriedades

**Limite recomendado**: 5.000 propriedades.

## Segmentos/públicos-alvo dos relatórios

**Limite**: 50 públicos-alvos/segmentos por atividade.

## Contas/públicos-alvo reutilizáveis

**Limite recomendado**: 75 públicos-alvo.

Os limites de tempo do JavaScript ocorrem na interface caso você tenha limites demais.

## Caixa de entrada do perfil de script na interface do usuário do Target

**Limite recomendado**: 2.000 caracteres.

Depende do tamanho da cadeia de caracteres codificada, que pode ser muito maior que a cadeia bruta. Se a cadeia de caracteres for grande demais, falhará antes de chegar no Adobe Target.

## Nomes de perfil de script

**Limite**: 50 caracteres.

## Valores de perfil de script

**Limite**: 2.048 caracteres.

Por motivos de desempenho, recomendamos retornar um valor que não ultrapasse 256 caracteres.

Para um valor de retorno de Sequência de caracteres, se o tamanho do valor de retorno exceder 2.048 caracteres, o script será desativado pelo sistema.

Para um valor de retorno de matriz, se o tamanho dos valores concatenados da matriz exceder 2.048 caracteres, o script será desativado pelo sistema.

## Métricas de sucesso

**Limite**: 200 por atividade.

## Condições do Target

**Limite recomendado**: 1.000 valores.

Isso se refere ao número de valores separados por linha na área de texto de definição de metas. Por exemplo, inserir 1.000 códigos postais em uma meta de código postal.

## Regras de direcionamento

**Limite** recomendado: 2.500 caracteres por valor de regra de definição de metas.

**Limite recomendado**: 30.000 valores únicos por público-alvo nas regras de direcionamento.

**Limite recomendado**: 100.000 valores únicos de regras de direcionamento por atividade.

