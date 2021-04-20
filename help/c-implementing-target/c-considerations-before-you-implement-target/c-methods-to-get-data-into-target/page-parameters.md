---
keywords: implementar; implementação; configuração; configurar; parâmetros da página
description: Obtenha dados no Target usando parâmetros de página.
title: Como obtenho dados no Target usando parâmetros de página?
feature: Implementation
role: Developer
exl-id: a285eadc-b71e-49a8-9071-397ada283baf
translation-type: tm+mt
source-git-commit: 8a12ef3581d3f99f21c0d6d50af0ac09e6aebd4c
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 45%

---

# Parâmetros da página

Os parâmetros de página (também chamados &quot;parâmetros de mbox&quot;) são pares de nome/valor passados diretamente pelo código de página que não são armazenados no perfil do visitante para uso futuro.

Os parâmetros de página são úteis para enviar dados de página para o Target, que não precisam ser armazenados com o perfil do visitante para uso futuro de definição de metas. Esses valores são usados para descrever a página ou a ação que o usuário fez na página específica.

## Formato

Os parâmetros da página são enviados ao Target por uma chamada de servidor como par de nome/valor de cadeia de caracteres. Os nomes e valores do parâmetro são personalizáveis (embora alguns sejam &quot;nomes reservados&quot; para usos específicos).

### Exemplos

* `page=productPage`

* `categoryId=homeLoans`

## Exemplo de casos de uso

* **Páginas** do produto: Enviar informações sobre o produto específico exibido (este método é o funcionamento do Recommendations)
* **Detalhes** do pedido: Enviar a ID do pedido, orderTotal e assim por diante, para a coleção de pedidos
* **Afinidade de categorias**: envia informações visualizadas por categoria para o Target, gerando conhecimento da afinidade do usuário a determinadas categorias do site
* **Dados de terceiros**: envia informações de fontes de dados de terceiros, como provedores de definição de direcionamento meteorológico, dados de conta (por exemplo, DemandBase), dados demográficos (por exemplo, Experiência) e muito mais.

## Benefícios do método

Os dados são enviados ao Target em tempo real e podem ser usados na mesma chamada de servidor dos dados em que são recebidos.

## Avisos

* Precisa de atualização do código da página (diretamente ou por meio de um sistema de gerenciamento de tags).
* Se os dados tiverem de ser usados para direcionamento em uma chamada de página/servidor subsequente, eles deverão ser traduzidos para um script de perfil.
* As sequências de caracteres podem conter somente os caracteres, conforme o padrão [Internet Engineering Task Force (IETF)](https://www.ietf.org/rfc/rfc3986.txt).

   Além dos caracteres mencionados no site do IETF, o Target permite os seguintes caracteres nas sequências de consulta:

   `&lt; > # % &quot; { } | \\ ^ \[\] \``

   O restante deve ser codificado em url. O padrão especifica o seguinte formato ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ), conforme ilustrado abaixo:

   ![](assets/ietf1.png)

   Ou, a lista completa para simplicidade:

   ![](assets/ietf2.png)

## Exemplos de código

targetPageParamsAll (anexa os parâmetros a todas as chamadas de mbox na página):

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams (anexa os parâmetros ao mbox global na página):

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

Parâmetros no código mboxCreate:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

## Links para informações relevantes

Recommendations: [implementação de acordo com o tipo de página](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

Confirmação do pedido: [rastreia conversões](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

Afinidade de categorias: [afinidade de categorias](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)
