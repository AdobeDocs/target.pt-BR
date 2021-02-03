---
keywords: at.js;non-production;non-production;deployment
description: Informações sobre como implementar com segurança a at.js em um ambiente de não-produção.
title: Implementar a at.js em um ambiente de não-produção
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 91%

---


# Implantar o at.js em um ambiente que não seja de produção

Informações sobre as técnicas para implantar com segurança o at.js em um ambiente não de produção.

## Implantar no armazenamento temporário do DTM

Se usar o DTM, poderá salvar facilmente a at.js na sua configuração do Adobe Target Tool.

Depois de salvar a biblioteca, use a ferramenta DTM Switch para testá-la em seu código de produção. Isso também facilitará o suporte dos consultores da Adobe.

Para obter mais informações, consulte [Opção 3: implementar o Target manualmente com a Biblioteca de JavaScript do Target hospedada pelo DTM](https://experienceleague.adobe.com/docs/dtm/implementing/target/add-target/t-implementing-target-manually-js-hosted-dtm.html) no guia de *Práticas recomendadas para a implementação do Adobe Target usando o Dynamic Tag Management*.

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