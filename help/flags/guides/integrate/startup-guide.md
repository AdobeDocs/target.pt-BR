---
title: Guia de inicialização
description: Siga estas etapas para integrar seu aplicativo aos Sinalizadores, desde a solicitação de acesso até a criação do primeiro sinalizador de recurso.
hide: true
exl-id: 7aa09535-45fa-4ddf-9e3f-a23f8a8ee666
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '436'
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
| **Clientes do lado do servidor** | Se estiver integrando com um SDK do lado do servidor, você precisará de uma ID de cliente administrador com permissões apropriadas. |
| **Clientes de desktop** | Um código de produto e uma versão de produto podem ser usados no lugar de uma ID de cliente. |

## Etapa 3: Obter suas credenciais {#step-3-credentials}

As credenciais necessárias dependem do caminho de integração:

* **Web e dispositivo móvel (baseado em marca):** Use a **ID do arquivo de ambiente** da propriedade de marca publicada. Consulte a Etapa 4a para saber como fazer isso.
* **SDKs do lado do servidor:** Solicite uma **ID de cliente de token de serviço** e faça com que o suporte a Sinalizadores a inclua na lista de permissões antes de fazer chamadas de API da SDK.
* **Desktop:** um código de produto e uma versão de produto podem ser usados no lugar de uma ID de cliente.

## Etapa 4: integrar usando uma SDK {#step-4-integrate}

Siga as [etapas de integração](integration-steps.md) para o seu tipo de aplicativo. Escolha o caminho que se ajusta à sua pilha:

* **Serviços da Web** → Java SDK ou Node.js SDK
* **Aplicativos da Web e móveis** → AEP Mobile SDK — consulte os guias do [Android](../sdk-releases/android/android-extension-integration-guide.md) e [iOS](../sdk-releases/ios/ios-extension-integration-guide.md)
* **Aplicativos da área de trabalho** → SDK (em breve)

## Etapa 4a: Configurar a coleta de dados e publicar sua configuração {#step-4a-data-collection}

Se estiver integrando por meio de uma abordagem baseada em tags (Web ou móvel), configure a propriedade da tag antes de inicializar a SDK:

1. Em [Coleção de Dados do Adobe Experience Platform](https://experience.adobe.com/#/data-collection), abra a propriedade do celular ou da Web.
1. Instale a extensão **Edge Network** e, em seguida, a extensão **Implantação da experiência** (nessa ordem).
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
* [Etapas de integração](integration-steps.md)
* [SDKs](sdks.md)

<!-- -->
