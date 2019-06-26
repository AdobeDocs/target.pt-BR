---
description: Informações para ajudar você a usar o bookmarklet de Controle de qualidade do Target para forçar o Target a liberar você do modo de controle de qualidade.
keywords: qa, visualização, bookmarklet, links de visualização
seo-description: Informações para ajudar você a usar o bookmarklet de Controle de qualidade do Target para forçar o Target a liberar você do modo de controle de qualidade.
seo-title: Bookmarklet de controle de qualidade da atividade
solution: Target
title: Bookmarklet de controle de qualidade da atividade
topic: Advanced,Standard,Classic
uuid: 2890e215-16c9-4b22-a8eb-732cd6efede3
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Bookmarklet de controle de qualidade da atividade{#activity-qa-bookmarklet}

Informações para ajudar você a usar o bookmarklet de Controle de qualidade do Target para forçar o Target a liberar você do modo de controle de qualidade.

Como o [modo de QA](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) é persistente, depois de navegar em um site no modo de QA, sua sessão do Target precisa expirar ou o Target precisa liberar você do modo de QA para exibir o site como um visitante normal. Use o bookmarklet de Controle de qualidade do Target para forçar você a sair do modo de Controle de qualidade.

Para usar o bookmarklet de controle de qualidade do Target, crie um bookmarklet que contenha o seguinte código JavaScript e o adicione à barra de favoritos do seu navegador:

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

Você também pode forçar a sua saída manualmente carregando uma página em seu site com o parâmetro `at_preview_token` com um valor vazio (por exemplo, `https://www.mysite.com/?at_preview_token=`).
