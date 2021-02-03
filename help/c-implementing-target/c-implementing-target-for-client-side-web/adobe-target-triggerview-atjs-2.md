---
keywords: adobe.target.triggerView;triggerView;triggerview;acionar exibição;at.js;funções;função viewName;viewname;exibir nome
description: Informações sobre a função adobe.target.triggerView (viewName, options) da biblioteca at.js de JavaScript do Adobe Target.
title: Adobe.Público alvo.Triggerview (Nome do visualizador, Opções) - at.js 2.x
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 91%

---


# adobe.público alvo.triggerView (viewName, opções) - at.js 2.x

Essa função pode ser chamada sempre que uma nova página é carregada ou quando um componente em uma página é renderizado novamente. `adobe.target.triggerView()` deve ser implementado para aplicativos de página única (SPAs) para usar o Visual Experience Composer (VEC) para criar atividades de teste A/B e direcionamento de experiência (XT). Se `adobe.target.triggerView()` não estiver implementado no site, o VEC não poderá ser usado para SPA. Para obter mais informações, consulte [Implementação do aplicativo de página única](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

>[!NOTE]
>
>Essa função foi introduzida com a at.js 2.x. Essa função não está disponível para a at.js versão 1.*x*.

| Parâmetro | Tipo | Obrigatório? | Descrição |
| --- | --- | --- | --- |
| viewName | String | Sim | Transmita qualquer nome como um tipo de sequência de caracteres que você deseja representar sua exibição. Esse nome de exibição aparece no painel [!UICONTROL Modificações] do VEC para que os profissionais de marketing criem ações e executem suas atividades A/B e XT. |
| opções | Objeto | Não |  |
| opções > página | Booleano | Não | **TRUE:** O valor padrão da página é true. Quando page=true, as notificações são enviadas ao [!DNL Target] backend para aumentar a contagem de impressões.<br>Uma notificação é sempre enviada por padrão quando um usuário  `triggerView` é chamado, exceto quando opções > página é definida como false.<br>**FALSE:** quando ocorrer page=false, as notificações não são enviadas para aumentar a contagem de impressões. Isso deve ser usado quando você deseja apenas renderizar novamente um componente em uma página com uma oferta. |

## Exemplo: Verdadeiro

Chamada `triggerView()` para enviar uma notificação para o back-end do Target para incrementar as impressões da atividade e outras métricas.

```javascript
adobe.target.triggerView("homeView")
```

## Exemplo: Falso

Chamada `triggerView()` para não enviar notificações ao back-end do Target para contagem de impressões.

```javascript
adobe.target.triggerView("homeView", {page: false})
```
