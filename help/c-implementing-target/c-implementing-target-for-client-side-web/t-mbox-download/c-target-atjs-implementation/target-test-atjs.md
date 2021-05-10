---
keywords: at.js; não produção; não produção; implantar
description: Saiba mais sobre a implementação herdada da mbox.js do Adobe Target. Migrar para o SDK da Web da Adobe Experience Platform (AEP Web SDK) ou para a versão mais recente da at.js.
title: Como faço para implantar a at.js em um ambiente de não-produção?
feature: at.js
role: Developer
exl-id: 607b2b5b-bb2a-4443-abc0-452b421fc009
translation-type: tm+mt
source-git-commit: 824743300725bbd39077882a0971a9ccb4f753ab
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 80%

---

# Implantar a at.js em um ambiente de não-produção

Informações sobre as técnicas para implantar com segurança o at.js em um ambiente não de produção.

## Use a extensão &quot;Requestly&quot; do Chrome para mapear a outro arquivo

>[!NOTE]
>
>Além das seguintes informações, você pode usar a extensão de navegador [Adobe Target VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para Google Chrome.

O [Requestly](https://chrome.google.com/webstore/detail/requestly/mdnleldcmiljblolnjhpnblkcekpdkpa?hl=en) é uma extensão gratuita do Chrome que permite redirecionar solicitações para um URL alternativo.

Você implanta a at.js a um URL e usa Requestly para mapear o URL do arquivo mbox.js ao novo URL de at.js. Sempre que seu site tentar carregar a mbox.js, ele carregará a at.js. Essa abordagem também facilita o fornecimento de suporte pela Adobe.

## Implantar em um ambiente de desenvolvimento, de armazenamento temporário ou de controle de qualidade

Se você hospedar a mbox.js em sua base de código e puder fazer atualizações facilmente em seus ambientes de código, implante a at.js em um dos seus ambientes inferiores.

Para obter um melhor suporte da Adobe, implante o arquivo em um ambiente que a Adobe possa acessar.

## Use Charles ou Fiddler para mapear a um arquivo local

O [Charles Web Debugging Proxy](https://www.charlesproxy.com/) é um aplicativo disponível para Mac e Windows, cujo recurso Map Local pode ser usado para mapear o carregamento de seu arquivo mbox.js de produção em uma cópia local da at.js. Uma versão de avaliação gratuita está disponível para download para Mac e Windows.

O [Fiddler](https://www.telerik.com/fiddler) é uma ferramenta similar disponível gratuitamente para download para o Windows.

## Implantar em outro ambiente gerenciador de tags

Se estiver usando outro gerenciador de tags, provavelmente terá uma maneira de implantar a at.js com segurança, sem afetar seu tráfego de produção.
