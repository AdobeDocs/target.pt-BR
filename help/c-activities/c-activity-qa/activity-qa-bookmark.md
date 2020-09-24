---
keywords: qa;preview;bookmarklet;preview links
description: Informações para ajudá-lo a usar o bookmarklet Adobe Target QA para forçar o Público alvo a liberá-lo do modo de QA.
title: bookmarklet de QA de atividade para Adobe Target
feature: qa
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: 08ad3291a1f981fbc3963ce403bf19849c358b97
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 26%

---


# Bookmarklet de controle de qualidade da atividade{#activity-qa-bookmarklet}

Information to help you use the [!DNL Target] QA bookmarklet to force [!DNL Target] to release you from QA mode.

>[!NOTE]
>
>O processo para criar um bookmarklet varia dependendo do tipo e da versão do navegador. Consulte a ajuda do seu navegador ou pesquise instruções específicas na internet.

## bookmarklet de QA da atividade para at.js 1.*x* 

Como o [modo de QA](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) é persistente, depois de navegar em um site no modo de QA, sua sessão do precisa expirar ou o precisa liberar você do modo de QA para exibir o site como um visitante normal. [!DNL Target][!DNL Target] Use the QA [!DNL Target] bookmarklet to force yourself out of QA mode.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser&#39;s Bookmarks Toolbar:

```
javascript:(
    function () {
        if (window.location.href.indexOf('?') != -1) {
            var parts = window.location.href.split('at_preview_token',2);
            if (parts.length > 1) {
                window.location.href = parts[0].concat('at_preview_token=');
            } else {
                window.location.href = window.location.href.concat("&at_preview_token=")
            }
        } else {
            window.location.href = window.location.href.concat("?at_preview_token=")
        }
    }
)();
```

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value.

Por exemplo:

`https://www.mysite.com/?at_preview_token=`

## bookmarklet de QA da atividade para at.js 2.*x* 

Ao contrário de at.js 1.*x*, at.js 2.*O x* não suporta cookies de terceiros, e o modo de controle de qualidade só é aderente ao domínio próprio (por meio de um cookie primário definido pelo at.js). Assim, em at.js 2.*x*, a sessão do modo de QA é gerenciada somente no lado do cliente e nenhum cookie do modo de QA é enviado para o Público alvo.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser&#39;s Bookmarks Toolbar:

```
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {
            document.cookie = AT_QA_MODE + '; Path=/; Max-Age=-0;';
            var url = window.location.href.split('at_preview_token',2)[0];
            window.open(url.substring(0, url.length - 1), '_self', 'noreferrer');
        }
    })();
```

## Usar o bookmarklet de QA da Atividade

Clique no bookmarklet na barra de ferramentas do seu navegador.

