---
keywords: qa, visualização, bookmarklet, links de visualização
description: Informações para ajudá-lo a usar o bookmarklet de QA do Adobe Target para forçar o Target a liberá-lo do modo de QA.
title: bookmarklet de QA da atividade para o Adobe Target
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Bookmarklet de controle de qualidade da atividade{#activity-qa-bookmarklet}

Information to help you use the [!DNL Target] QA bookmarklet to force [!DNL Target] to release you from QA mode.

Como o [modo de QA](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) é persistente, depois de navegar em um site no modo de QA, sua sessão do precisa expirar ou o precisa liberar você do modo de QA para exibir o site como um visitante normal. [!DNL Target][!DNL Target] Use the QA [!DNL Target] bookmarklet to force yourself out of QA mode.

To use the [!DNL Target] QA bookmarklet, create a bookmarklet containing the following JavaScript code and add it to your browser's Bookmarks Toolbar:

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

O bookmarklet deve então aparecer na barra de ferramentas para reutilização.

>[!NOTE]
>
>O processo para criar um bookmarklet varia dependendo do tipo e da versão do navegador. Consulte a ajuda do seu navegador ou pesquise instruções específicas na internet.

You can also manually force yourself out of QA mode by loading a page on your site with the `at_preview_token` parameter with an empty value.

Por exemplo:

`https://www.mysite.com/?at_preview_token=`
