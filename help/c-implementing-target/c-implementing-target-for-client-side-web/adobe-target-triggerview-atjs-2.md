---
description: 'Informações sobre a função adobe. target. triggerview (viewname, options) para at. js. '
keywords: adobe.target.notificação; elemento; seletor; notificação; extensão
seo-description: Informações sobre a função adobe. target. triggerview (viewname, opções) para a biblioteca do Adobe Target at. js.
seo-title: Informações sobre a função adobe. target. triggerview (viewname, opções) para a biblioteca do Adobe Target at. js.
solution: Target
subtopic: Introdução
title: adobe.target.triggerView (viewName, options)
topic: Padrão
translation-type: tm+mt
source-git-commit: 19834da75f163d6357bc9b986a23f0bc1fea6d8e

---


# adobe. target. triggerview (viewname, options) - at. js 2. x

Essa função pode ser chamada sempre que uma nova página é carregada ou quando um componente em uma página é renderizado novamente. `adobe.target.triggerView()` deve ser implementado para aplicativos de página única (SPAs) para usar o Visual Experience Composer (VEC) para criar atividades de teste A/B e direcionamento de experiência (XT). Se `adobe.target.triggerView()` não estiver implementado no site, o VEC não poderá ser usado para SPA. Para obter mais informações, consulte [Implementação do aplicativo de página única](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

>[!NOTE]
>
>Esta função foi introduzida com at. js 2. x. Essa função não está disponível para o at. js versão 1.*x*.

| Parâmetro | Tipo | Obrigatório? | Descrição |
| --- | --- | --- | --- |
| viewName | String | Sim | Transmita qualquer nome como um tipo de sequência de caracteres que você deseja representar sua exibição. Esse nome de exibição aparece no painel [!UICONTROL Modificações] do VEC para que os profissionais de marketing criem ações e executem suas atividades A/B e XT. |
| opções | Objeto | Não |
| opções &gt; página | Booleano | Não | **TRUE:** O valor padrão da página é true. Quando page=true, as notificações são enviadas ao [!DNL Target] backend para aumentar a contagem de impressões.<br>**FALSE:** Quando page = false, as notificações não são enviadas para aumentar a contagem de impressões. Isso deve ser usado quando você deseja apenas renderizar novamente um componente em uma página com uma oferta. |

## Exemplo `triggerView()` de chamada que enviará uma notificação para o backend do Target para aumentar a contagem de impressões

```
adobe.target.triggerView("homeView")
```

## Exemplo `triggerView()` de chamada para não ter notificações enviadas ao backend do Target para contagem de impressões

```
adobe.target.triggerView("homeView", {page: false})
```
