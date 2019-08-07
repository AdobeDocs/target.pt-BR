---
description: 'Informações sobre a função adobe.target.triggerView (viewName, options) para at.js. '
keywords: adobe. target. triggerview; Triggerview; visualização de disparo; acionar exibição; at. js; funções; ; Viewname; nome do visualizador; exibir nome
seo-description: Informações sobre a função adobe.target.triggerView (viewName, options) da biblioteca at.js de JavaScript do Adobe Target.
seo-title: Informações sobre a função adobe.target.triggerView (viewName, options) da biblioteca at.js de JavaScript do Adobe Target.
solution: Target
subtopic: Introdução
title: adobe.target.triggerView (viewName, options)
topic: Padrão
translation-type: tm+mt
source-git-commit: ef2c4ac78fef5889d5a6e9e053dfd36b77919dd4

---


# adobe.target.triggerView (viewName, options) - at.js 2.x

Essa função pode ser chamada sempre que uma nova página é carregada ou quando um componente em uma página é renderizado novamente. `adobe.target.triggerView()` deve ser implementado para aplicativos de página única (SPAs) para usar o Visual Experience Composer (VEC) para criar atividades de teste A/B e direcionamento de experiência (XT). Se `adobe.target.triggerView()` não estiver implementado no site, o VEC não poderá ser usado para SPA. Para obter mais informações, consulte [Implementação do aplicativo de página única](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

>[!NOTE]
>
>Essa função foi introduzida com a at.js 2.x. Essa função não está disponível para a at.js versão 1.*x*.

| Parâmetro | Tipo | Obrigatório? | Descrição |
| --- | --- | --- | --- |
| viewName | String | Sim | Transmita qualquer nome como um tipo de sequência de caracteres que você deseja representar sua exibição. Esse nome de exibição aparece no painel [!UICONTROL Modificações] do VEC para que os profissionais de marketing criem ações e executem suas atividades A/B e XT. |
| opções | Objeto | Não |  |
| opções &gt; página | Booleano | Não | **TRUE:** O valor padrão da página é true. Quando page=true, as notificações são enviadas ao [!DNL Target] backend para aumentar a contagem de impressões.<br>Se nenhuma experiência de atividade ou métrica de atividade estiver associada à exibição, nenhuma notificação será enviada.<br>**FALSE:** quando ocorrer page=false, as notificações não são enviadas para aumentar a contagem de impressões. Isso deve ser usado quando você deseja apenas renderizar novamente um componente em uma página com uma oferta. |

## Exemplo: Verdadeiro

`triggerView()` para enviar uma notificação para o backend do Target para aumentar impressões de atividade e outras métricas.

```
adobe.target.triggerView("homeView")
```

## Exemplo: Falso

`triggerView()` chamada para não receber notificações enviadas ao backend do Target para contagem de impressões.

```
adobe.target.triggerView("homeView", {page: false})
```
