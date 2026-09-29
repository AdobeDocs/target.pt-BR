---
title: Integrar seu aplicativo
description: Saiba como integrar um novo aplicativo aos Sinalizadores para começar a criar e gerenciar sinalizadores de recursos.
badge: label="Beta" type="Informative"
hide: true
exl-id: d88c27a5-f490-4504-9764-5e4ce98fdf20
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 5%
---
# Integrar seu aplicativo {#onboard-your-application}

Você deve ter a função de **Administrador** para adicionar um novo aplicativo. Entre em contato com o administrador se precisar verificar ou atualizar sua função.

## Adicionar um novo aplicativo {#add-application}

1. Faça logon no console Sinalizadores e navegue até **Sinalizadores > Aplicativos**.

   >[!NOTE]
   >
   >Se o botão **Novo Aplicativo** não estiver visível, verifique se você tem a função de **Administrador**.

2. Selecione **Novo Aplicativo**.

3. Selecione a **plataforma** que corresponde ao seu tipo de aplicativo (Web ou móvel).

4. Forneça as seguintes informações:

   Os campos marcados com * são obrigatórios.

   | Campo | Descrição |
   | --- | --- |
   | **Nome do aplicativo** * | Um nome de exibição para o aplicativo. |
   | **ID do aplicativo** * | Um identificador exclusivo usado ao chamar Sinalizadores de seu código. Use a ID de cliente do aplicativo. |
   | **Intervalo de sondagem** | O intervalo de pesquisa (em segundos) para atualizar o cache por aplicativo. Aplicável somente aos SDKs do lado do servidor. |

5. Selecione **Adicionar**. Seu aplicativo agora está registrado e pronto para a configuração do sinalizador de recurso.

## O que vem a seguir {#next-steps}

Depois que o aplicativo for integrado, você poderá começar a criar sinalizadores de recursos:

* [Criar o primeiro sinalizador de recurso](../feature-flags/create-your-first-feature-flag.md)
* [Sinalizadores de integração no aplicativo](../integrate/integrating-in-your-app.md)

## Consulte também {#see-also}

* [Gerenciar aplicativos](manage-applications.md)
* [Fazer logon no console](../console/log-in-to-the-console.md)

<!-- -->
