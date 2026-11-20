---
keywords: qa, visualização, bookmarklet, links de visualização
description: Saiba como usar o bookmarklet de controle de qualidade [!DNL Target] do Adobe para forçar o [!DNL Target] a liberá-lo do modo de controle de qualidade.
title: Como usar o bookmarklet de controle de qualidade da atividade?
feature: Activities
exl-id: dbfe59eb-6853-4909-abf1-e5630e979a98
TQID: 'https://experienceleague.adobe.com/kOQcdF2WgiAGkOS3rrLWfDSFTvRJX8jb-IeaahWnM0c'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0a683f6e68bb7481b9e45c91a275a46b84a1ffd8
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 6%
---
# Bookmarklet de controle de qualidade da atividade {#activity-qa-bookmarklet}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como usar o bookmarklet de Controle de qualidade [!DNL Target] para sair do modo **[!UICONTROL Controle de qualidade da atividade]** e exibir seu site como um visitante típico.

>[!ENDSHADEBOX]

Depois de navegar em um site no [modo de QA](/help/main/c-activities/c-activity-qa/activity-qa.md), o modo de QA persiste entre páginas até que a sessão [!DNL Target] expire. Um bookmarklet é um marcador de navegador que executa o JavaScript. O bookmarklet de controle de qualidade do [!DNL Target] força o [!DNL Target] a liberá-lo do modo de controle de qualidade, para que você não tenha que esperar a sessão expirar. Use a versão que corresponde à versão da at.js implantada em seu site.

>[!NOTE]
>
>O processo para criar um bookmarklet varia dependendo do tipo e da versão do navegador. Consulte a ajuda do seu navegador ou pesquise instruções específicas na Internet.

## Bookmarklet de Controle de qualidade da atividade para at.js 1.*x*

Para usar o bookmarklet de controle de qualidade do [!DNL Target], crie um bookmarklet que contenha o seguinte código JavaScript e o adicione à Barra de favoritos do seu navegador:

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

Você também pode forçar a sua saída manualmente carregando uma página em seu site com o parâmetro `at_preview_token` definido como um valor vazio. Por exemplo:

`https://www.mysite.com/?at_preview_token=`

## Bookmarklet de Controle de qualidade da atividade para at.js 2.*x*

Ao contrário da at.js 1.*x*, a at.js 2.*x* não oferece suporte a cookies de terceiros. O modo de controle de qualidade persiste somente para o domínio próprio, por meio de um cookie próprio definido pela at.js. Como resultado, a sessão do modo de QA é gerenciada somente no lado do cliente, e nenhum cookie do modo de QA é enviado para [!DNL Target].

Para usar o bookmarklet de controle de qualidade do [!DNL Target], crie um bookmarklet que contenha o seguinte código JavaScript e o adicione à Barra de favoritos do seu navegador:

```javascript
javascript:(
    function () {
        var AT_QA_MODE = 'at_qa_mode=';
        var isSet = document.cookie.split(';').some(function (cookie) {
            return cookie.trim().startsWith(AT_QA_MODE);
        });
        if (isSet) {            
            document.cookie = AT_QA_MODE + ';domain='+window.location.hostname+";Path=/; Max-Age=-0;";
            var token = window.location.href.indexOf("?at_preview_token")<0? "&at_preview_token" : "?at_preview_token";
            var url = window.location.href.split(token,2)[0];
            window.open(url, '_self', 'noreferrer');
        }
    })(); 
```

## Usar o bookmarklet de controle de qualidade da atividade

Depois de adicionar o bookmarklet que corresponde à versão do at.js no navegador, use-o sempre que quiser sair do modo de QA:

1. Abra qualquer página do site enquanto estiver no modo de QA.
1. Clique no bookmarklet na barra de favoritos do seu navegador.
1. Carregar uma página do site. O [!DNL Target] libera a sessão do modo de QA, e o site é exibido como para um visitante típico.
