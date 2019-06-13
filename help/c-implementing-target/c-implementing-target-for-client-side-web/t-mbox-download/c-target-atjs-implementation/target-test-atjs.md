---
description: Informações sobre como implementar com segurança a at.js em um ambiente de não-produção.
seo-description: Informações sobre como implementar com segurança a at.js em um ambiente de não-produção.
seo-title: Implementar a at.js em um ambiente de não-produção
title: Implementar a at.js em um ambiente de não-produção
uuid: 7f1adc43-35b4-442c-bb06-feab60604a87
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Implementar a at.js em um ambiente de não-produção{#deploy-at-js-to-a-non-production-environment}

Informações sobre as técnicas para implantar com segurança o at.js em um ambiente não de produção.

## Implantar no armazenamento temporário do DTM

Se usar o DTM, poderá salvar facilmente a at.js na sua configuração do Adobe Target Tool.

Depois de salvar a biblioteca, use a ferramenta DTM Switch para testá-la em seu código de produção. Isso também facilitará o suporte dos consultores da Adobe.

Para obter mais informações, consulte [Opção 3: Implementar o Target manualmente com a biblioteca de JavaScript do Target hospedada por DTM](https://marketing.adobe.com/resources/help/pt_BR/dtm/target/t_implementing-target-manually-js-hosted-dtm.html) nas _Práticas recomendadas para implementar o Adobe Target usando o guia de Dynamic Tag Management_.

## Use a extensão &quot;Requestly&quot; do Chrome para mapear a outro arquivo

>[!NOTE]
>
>Além das seguintes informações, você pode usar a extensão de navegador [Adobe Target VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para Google Chrome.

[Requestly](https://chrome.google.com/webstore/detail/requestly/mdnleldcmiljblolnjhpnblkcekpdkpa?hl=pt_br) é uma extensão gratuita do Chrome que permite redirecionar solicitações para um URL alternativo.

Você implanta a at.js a um URL e usa Requestly para mapear o URL do arquivo mbox.js ao novo URL de at.js. Sempre que seu site tentar carregar a mbox.js, ele carregará a at.js. Essa abordagem também facilita o fornecimento de suporte pela Adobe.

## Implantar em um ambiente de desenvolvimento, de armazenamento temporário ou de controle de qualidade

Se você hospedar a mbox.js em sua base de código e puder fazer atualizações facilmente em seus ambientes de código, implante a at.js em um dos seus ambientes inferiores.

Para obter um melhor suporte da Adobe, implante o arquivo em um ambiente que a Adobe possa acessar.

## Use Charles ou Fiddler para mapear a um arquivo local

[Charles Web Debugging Proxy](https://www.charlesproxy.com/) é um aplicativo disponível para Mac e Windows, cujo recurso Local do mapa pode ser usado para mapear o carregamento do arquivo mbox.js de produção para uma cópia local da at.js. Uma versão de avaliação gratuita está disponível para download para Mac e Windows.

[Fiddler](https://www.telerik.com/fiddler) é uma ferramenta semelhante disponível como download gratuito para Windows.

## Implantar em outro ambiente gerenciador de tags

Se estiver usando outro gerenciador de tags, provavelmente terá uma maneira de implantar a at.js com segurança, sem afetar seu tráfego de produção.