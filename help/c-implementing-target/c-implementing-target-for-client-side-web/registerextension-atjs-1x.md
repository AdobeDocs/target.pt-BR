---
description: 'Informações sobre a função registerextension () para at. js. '
keywords: adobe.target.notificação; elemento; seletor; notificação; extensão
seo-description: Informações sobre a função registerextension () para a biblioteca do Adobe Target no javascript.
seo-title: Informações sobre a função tregisterextension () da biblioteca do Adobe Target no javascript.
solution: Target
subtopic: Introdução
title: registerExtension()
topic: Padrão
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# registerExtension() - at.js 1.x

Fornece uma forma padrão de registrar uma extensão específica.

>[!NOTE]
>
>Essa função está disponível para a at.js versão 1.somente *x*. Essa função foi substituída pelo lançamento do at. js 2. x. Essa função retorna o conteúdo padrão se for usado com o at. js 2. x.

O parâmetro de opções é obrigatório e tem a seguinte estrutura:

| Chave | Tipo | Obrigatório | Descrição |
|--- |--- |--- |--- |
| name | String | Sim | Nome da extensão. |
| módulos | Array[String] | Sim | Uma matriz de sequências de caracteres representando nomes de módulo solicitados. |
| registrar | Função | Sim | Uma função usada para inicializar e criar a extensão. Esta função recebe argumentos com base na matriz de módulos. |

Notas:

* Se um dos parâmetros não for fornecido, uma exceção será lançada.
* Se a matriz de módulos estiver vazia, uma exceção será lançada.

Para mais informações e exemplos de como usar `registerExtension`, consulte a página [Adobe Experience Cloud Target atjs Extensions](https://github.com/Adobe-Marketing-Cloud/target-atjs-extensions) no GitHub.

## Métodos de módulo de configurações {#section_8501CDD4B0624FA2B10532C98C5F4328}

| Chave | Tipo | Descrição |
|--- |--- |--- |
| clientCode | String | Código de cliente |
| serverDomain | String | Domínio do servidor Edge |
| globalMboxName | String | Nome da mbox global do Target |
| globalMboxAutoCreate | Booleano | Indica se a criação automática está ativada ou não |
| timeout | Número | Tempo limite da solicitação |

## Métodos de módulo do agente de log {#section_10AF62B49AEF48F981E950D26E176138}

| Chave | Tipo | Descrição |
|--- |--- |--- |
| log | Função | Registra a lista variável de argumentos no console do navegador, se houver um. Ela é ativada somente quando `mboxDebug=true` é transmitido à URL. |
| error | Função | Registra a lista variável de argumentos no console do navegador. Ela só é ativada quando há erros graves, como tempo limite de rede, nó HTML não encontrado, etc. |
