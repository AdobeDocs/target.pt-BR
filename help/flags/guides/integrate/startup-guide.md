---
title: Guia de inicialização
description: Siga estas etapas para integrar seu aplicativo aos Sinalizadores, desde a solicitação de acesso até a criação do primeiro sinalizador de recurso.
hide: true
exl-id: 7aa09535-45fa-4ddf-9e3f-a23f8a8ee666
source-git-commit: 9a4e16418c93fa163d821409a0eecb251f2a9929
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 1%

---

# Guia de inicialização {#startup-guide}

Siga estas etapas para integrar Sinalizadores ao seu aplicativo.

## Etapa 1: solicitar acesso {#step-1-access}

Solicite acesso ao console Sinalizadores e entre em sua equipe. Consulte [Solicitar acesso](../console/request-access.md) para obter instruções passo a passo.

## Etapa 2: integrar seu aplicativo {#step-2-onboard}

Depois de obter acesso, faça logon no console Sinalizadores e verifique se seu aplicativo está listado na equipe. Caso contrário, peça ao administrador da equipe para adicioná-lo. Consulte [Integrar seu aplicativo](../applications/onboard-your-application.md).

Antes da integração, prepare o seguinte:

| Requisito | Detalhes |
|---|---|
| **ID do aplicativo** | Um identificador de cliente exclusivo usado ao chamar as APIs de Sinalizadores. Use a ID de cliente existente do aplicativo, quando disponível. |

## Etapa 3: obter a ID do arquivo do ambiente {#step-3-credentials}

A ID do arquivo de ambiente necessária depende do caminho de integração:

* **Web e dispositivo móvel (baseado em marca):** Use a **ID do arquivo de ambiente** da propriedade de marca publicada. Consulte a Etapa 4a para saber como fazer isso.

## Etapa 4: integrar usando uma SDK {#step-4-integrate}

Siga o guia de integração do seu tipo de aplicativo. Escolha o caminho que se ajusta à sua pilha:

* **Aplicativos da Web e móveis** — consulte os guias do [Android](../sdk-releases/android/android-extension-integration-guide.md), [iOS](../sdk-releases/ios/ios-extension-integration-guide.md) e [Web](../sdk-releases/web/web-extension-integration-guide.md) na seção do guia de integração

## Etapa 4a: Configurar a coleta de dados e publicar sua configuração {#step-4a-data-collection}

Se estiver integrando por meio de uma abordagem baseada em tags (Web ou móvel), configure a propriedade da tag antes de inicializar a SDK:

1. Em [Coleção de Dados do Adobe Experience Platform](https://experience.adobe.com/#/data-collection), abra a propriedade do celular ou da Web.
1. Instale a extensão **Edge Network** e, em seguida, a extensão **Sinalizadores** (nesta ordem).
1. Selecione seu **fluxo de dados** (deve incluir o conjunto de dados do Customer Journey Analytics) e seu domínio de borda.
1. Publique a configuração por meio de **Desenvolvimento → Preparo → Produção**.
1. Copie a **ID do arquivo de ambiente** da guia **Ambientes** — você usará isso para inicializar o SDK.

>[!IMPORTANT]
>
>No ambiente de **preparo**, adicione o prefixo `staging/` à ID do arquivo de ambiente — isto é, use `staging/<environmentId>`. Em **produção**, use a ID do arquivo de ambiente diretamente.

## Etapa 5: criar e testar o primeiro sinalizador de recurso {#step-5-feature-flag}

Quando a integração for concluída, crie seu primeiro sinalizador de recurso no console e teste-o:

* [Criar o primeiro sinalizador de recurso](../feature-flags/create-your-first-feature-flag.md)

## Consulte também {#see-also}

* [Sinalizadores de integração no aplicativo](integrating-in-your-app.md)
* [SDKs](sdks.md)

<!-- -->
