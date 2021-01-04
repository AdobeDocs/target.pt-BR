---
keywords: qa;preview;bookmarklet;preview links
description: Informações para ajudá-lo a usar o bookmarklet Adobe Target QA para forçar o Público alvo a liberá-lo do modo de QA.
title: bookmarklet de QA de atividade para Adobe Target
feature: Activities
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 26%

---


# Bookmarklet de controle de qualidade da atividade

Informações para ajudá-lo a usar o bookmarklet de QA [!DNL Target] para forçar [!DNL Target] a liberá-lo do modo de QA.

>[!NOTE]
>
>O processo para criar um bookmarklet varia dependendo do tipo e da versão do navegador. Consulte a ajuda do seu navegador ou pesquise instruções específicas na internet.

## bookmarklet de QA da atividade para at.js 1.*x* 

Como o [modo de QA](/help/c-activities/c-activity-qa/activity-qa.md) é persistente, depois de navegar em um site no modo de QA, sua sessão do precisa expirar ou o precisa liberar você do modo de QA para exibir o site como um visitante normal. [!DNL Target][!DNL Target] Use o bookmarklet QA [!DNL Target] para se forçar a sair do modo de QA.

Para usar o bookmarklet [!DNL Target] QA, crie um bookmarklet contendo o seguinte código JavaScript e adicione-o à barra de favoritos do seu navegador:

```javascript
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

Você também pode se forçar manualmente a sair do modo de QA carregando uma página no seu site com o parâmetro `at_preview_token` com um valor vazio.

Por exemplo:

`https://www.mysite.com/?at_preview_token=`

## bookmarklet de QA da atividade para at.js 2.*x* 

Ao contrário de at.js 1.*x*, at.js 2.*O* xdoes não é compatível com cookies de terceiros, e o modo de controle de qualidade só é aderente ao domínio próprio (por meio de um cookie primário definido pelo at.js). Assim, em at.js 2.*x*, a sessão do modo de QA é gerenciada somente no lado do cliente e nenhum cookie do modo de QA é enviado para o Público alvo.

Para usar o bookmarklet [!DNL Target] QA, crie um bookmarklet contendo o seguinte código JavaScript e adicione-o à barra de favoritos do seu navegador:

```javascript
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

