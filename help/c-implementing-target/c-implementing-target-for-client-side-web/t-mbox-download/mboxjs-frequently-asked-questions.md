---
keywords: mbox.js faq; perguntas frequentes do mbox.js; document.write; tt.omtrdc.net; bloqueio do analisador
description: Saiba mais sobre a implementação herdada da mbox.js do Adobe Target. Migrar para o SDK da Web da Adobe Experience Platform (AEP Web SDK) ou para a versão mais recente da at.js.
title: Quais são algumas das perguntas mais frequentes sobre [!DNL Target] mbox.js?
feature: at.js
role: Developer
exl-id: 0e207896-d45b-45f9-8556-6532fda72a45
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 75%

---

# Perguntas frequentes sobre a mbox.js

Respostas às perguntas mais frequentes sobre a mbox.js.

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Por que as mboxes não estão sendo acionadas nas minhas páginas da Web? {#section_4BA5DA424B734324AAB51E4588FA50F5}

Os clientes do, às vezes, usam instâncias baseadas em nuvem com o [!DNL Target]Target para testes ou fins de prova de conceito simples. Esses domínios e muitos outros fazem parte da [Lista de sufixos públicos](https://publicsuffix.org/list/public_suffix_list.dat).

Se estiver usando esses domínios, os navegadores modernos não salvarão os cookies, a menos que você personalize a configuração de `cookieDomain` usando targetGlobalSettings(). Para obter mais informações, consulte [Uso de instâncias baseadas em nuvem com o Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566).

## Qual é o domínio tt.omtrdc.net para o qual as chamadas de servidor [!DNL Target] são direcionadas? {#section_999C29940E8B4CAD8A957A6B1D440317}

O [!DNL tt.omtrdc.net] é o nome de domínio da rede EDGE da Adobe, usado para receber todas as chamadas do Target.

## Por que a at.js e mbox.js não usam os sinalizadores de cookies HttpOnly e Seguro? {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly pode ser definido somente pelo código do lado do servidor. Os cookies do Target, como mbox, são criados e salvos pelo código JavaScript, para que o Target não possa usar o sinalizador de cookies HttpOnly.

Seguro pode ser definido somente por JavaScript, quando a página tiver sido carregada por HTTPS. Se a página inicialmente carregar por meio de HTTP, o JavaScript não poderá definir esse sinalizador. Além disso, se o sinalizador Seguro for usado, o cookie estará disponível somente nas páginas HTTPS.

Para garantir que o Target possa rastrear os usuários corretamente e, como os cookies são gerados no lado do cliente, o Target não usa nenhum desses sinalizadores.
