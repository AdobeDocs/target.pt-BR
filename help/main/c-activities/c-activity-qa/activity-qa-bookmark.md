---
keywords: qa, visualização, bookmarklet, links de visualização
description: Saiba como usar o bookmarklet de controle de qualidade do Adobe [!DNL Target] para forçar o [!DNL Target] a liberar você do modo de controle de qualidade.
title: Como usar o bookmarklet de controle de qualidade da atividade?
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 13%

---

# Bookmarklet de controle de qualidade da atividade

Informações para ajudá-lo a usar o bookmarklet de controle de qualidade do [!DNL Target] para forçar o [!DNL Target] a liberá-lo do modo de controle de qualidade.

>[!NOTE]
>
>O processo para criar um bookmarklet varia dependendo do tipo e da versão do navegador. Consulte a ajuda do seu navegador ou pesquise instruções específicas na internet.

## Bookmarklet de Controle de qualidade da atividade para at.js 1.*x*  

Como o [modo de QA](/help/main/c-activities/c-activity-qa/activity-qa.md) é persistente, depois de navegar em um site no modo de QA, sua sessão [!DNL Target] deve expirar ou você precisa que o [!DNL Target] o libere do modo de QA para exibir o site como um visitante típico. Use o bookmarklet de controle de qualidade [!DNL Target] para forçar você a sair do modo de controle de qualidade.

Para usar o bookmarklet de controle de qualidade do [!DNL Target], crie um bookmarklet que contenha o seguinte código JavaScript e o adicione à Barra de Favoritos do seu navegador:

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

Você também pode forçar a sua saída manualmente carregando uma página em seu site com o parâmetro `at_preview_token` com um valor vazio.

Por exemplo:

`https://www.mysite.com/?at_preview_token=`

## Bookmarklet de Controle de qualidade da atividade para at.js 2.*x*  

Em contraste com a at.js 1.*x*, at.js 2.*x* não oferece suporte a cookies de terceiros e o modo de controle de qualidade é aderente apenas ao domínio próprio (por meio de um cookie próprio definido pela at.js). Assim, no at.js 2.*x*, a sessão do modo de QA é gerenciada somente no lado do cliente e nenhum cookie do modo de QA é enviado para o Target.

Para usar o bookmarklet de controle de qualidade do [!DNL Target], crie um bookmarklet que contenha o seguinte código JavaScript e o adicione à Barra de Favoritos do seu navegador:

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

## Usar o bookmarklet de controle de qualidade da atividade

Clique no bookmarklet na barra de ferramentas do navegador.
