---
keywords: adobe.target.triggerView;triggerView;triggerview;acionar exibição;at.js;funções;função viewName;viewname;exibir nome
description: Use a função adobe.target.triggerView() para o Adobe [!DNL Target] biblioteca JavaScript da at.js para uso em Aplicativos de página única (SPA). (at.js 2.x)
title: Como uso a função adobe.target.triggerView() ?
feature: at.js
role: Developer
exl-id: 619d5166-d1d9-49a6-9807-338544782e66
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 79%

---

# adobe.target.triggerView (viewName, options) - at.js 2.x

Essa função pode ser chamada sempre que uma nova página é carregada ou quando um componente em uma página é renderizado novamente. `adobe.target.triggerView()` deve ser implementado para aplicativos de página única (SPAs) para usar o Visual Experience Composer (VEC) para criar atividades de teste A/B e direcionamento de experiência (XT). Se `adobe.target.triggerView()` não estiver implementado no site, o VEC não poderá ser usado para SPA. Para obter mais informações, consulte [Implementação do aplicativo de página única](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/target-atjs-single-page-application/){target=_blank}.

>[!NOTE]
>
>Essa função foi introduzida com a at.js 2.x. Essa função não está disponível para a at.js versão 1.*x*.

| Parâmetro | Tipo | Obrigatório? | Descrição |
| --- | --- | --- | --- |
| viewName | String | Sim | Transmita qualquer nome como um tipo de sequência de caracteres que você deseja representar sua exibição. Esse nome de exibição aparece no painel [!UICONTROL Modificações] do VEC para que os profissionais de marketing criem ações e executem suas atividades A/B e XT. |
| opções | Objeto | Não |  |
| opções > página | Booleano | Não | **TRUE:** O valor padrão da página é true. Quando page=true, as notificações são enviadas ao [!DNL Target] backend para aumentar a contagem de impressões.<br>Uma notificação é sempre enviada por padrão quando uma `triggerView` é chamada, exceto quando options > page é definido como false.<br>**FALSE:** quando ocorrer page=false, as notificações não são enviadas para aumentar a contagem de impressões. Isso deve ser usado quando você deseja apenas renderizar novamente um componente em uma página com uma oferta. |

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
