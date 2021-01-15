---
keywords: document.write;target;implement;implement target;dtm;dynamic tag management;at.js;mbox.js;target.js;mbox;adobe experience platform web skd;aep web sdk;web sdk
description: Implemente o Adobe Target fazendo referência às bibliotecas de Públicos alvos (at.js ou mbox.js) em suas páginas da Web.
title: Noções básicas sobre as bibliotecas de JavaScript do Target
feature: Implementation
translation-type: tm+mt
source-git-commit: bffda8c3461998767a002d66fd9340252237ae5d
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 76%

---


# Entender as [!DNL Target]bibliotecas JavaScript

Implemente [!DNL Target] referenciando as bibliotecas [!DNL Adobe Target] (Adobe Experience Platform Web SDK, at.js ou mbox.js) em suas páginas da Web.

>[!NOTE]
>
>A biblioteca mbox.js não está mais sendo desenvolvida. Todos os clientes devem migrar da mbox.js para a at.js. Para obter mais informações, consulte [Migrar para at.js do mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## Diferenças entre as bibliotecas JavaScript de Público alvo {#section_40117C78C2F84FECAC4F1BA40CC4F171}

A tabela a seguir explica as diferenças entre as [!DNL Target] bibliotecas JavaScript:

| Referência da biblioteca | Descrição |
|--- |--- |
| Adobe Experience Platform Web SDK | O [!UICONTROL Adobe Experience Platform Web SDK] permite que você interaja com os vários serviços em [!DNL Experience Cloud] (incluindo [!DNL Target]) por meio da Adobe Experience Edge Network. Se você optar por migrar para [!DNL Adobe Experience Platform Web SDK], consulte [O que é Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md), no *Guia do SDK da Web*. |
| at.js  | O at.js substitui o mbox.js para implementações [!DNL [!DNL Target]].<br>Entre outros benefícios, a at.js melhora os tempos de carregamento de página para implementações da Web, melhora a segurança, evita avisos de document.write no Google Chrome e fornece opções de implementações melhores para aplicativos de página única.<br>Para obter mais informações, consulte [Implementação do at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md). |
| mbox.js | Antes do [!DNL Target] 16.3.1 (março de 2016), o [!DNL Target] exigia uma chamada para a mbox.js a fim de criar a mbox global necessária para o [!DNL Target] fornecer atividades, rastrear cliques e a maioria das métricas de sucesso. Esse arquivo contém as bibliotecas necessárias para todas as suas atividades. Você não precisa manter versões específicas de atividades diferentes do arquivo.<br>Se você já tiver mboxes de envolvimento nas suas páginas de um estilo antigo de implementação do [!DNL Target], elas ainda poderão ser usadas na nova interface. O arquivo mbox.js atualizado ainda é necessário, mas essas mboxes podem ser selecionadas para atividades e editadas usando o Visual Experience Composer.<br>[!DNL Target]O Standard e Premium atualizam e complementam a mbox.js com uma referência para um arquivo target.js. O arquivo target.js é hospedado pelo Adobe. O arquivo target.js possibilita a edição de conteúdo em qualquer página que usa o Visual Experience Composer, mesmo que a página não contenha mboxes predefinidas. Você deve mencionar esse arquivo em todas as páginas do site.<br>Para obter mais informações, consulte [Implementação do mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Importante**: Em 31 de março de 2021, não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem [!DNL Target] atividades sendo executadas com o conteúdo padrão. Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca JavaScript at.js antes dessa data para evitar possíveis problemas com seus sites.<br> |

## Impacto da at.js e mbox.js no tempo de carregamento de página {#section_16630CD0FF0A498EB596A51381366A5A}

Muitos clientes e consultores querem saber o impacto da [!DNL at.js] e da [!DNL mbox.js] no tempo de carregamento de página, principalmente no contexto de usuários novos e recorrentes. Infelizmente, é difícil medir e fornecer números concretos sobre como a [!DNL at.js] ou a [!DNL mbox.js] influenciam no tempo de carregamento de página devido à implementação de cada cliente.

No entanto, se a API de visitante estiver presente na página, é possível entender melhor como a [!DNL at.js] e a [!DNL mbox.js] influenciam no tempo de carregamento de página.

>[!NOTE]
>
>A API do visitante e a [!DNL at.js] ou a [!DNL mbox.js] têm um impacto no tempo de carregamento de página apenas quando estiver usando a mbox global (por causa da técnica de ocultação do corpo). As mboxes regionais não são afetadas pela integração da API do visitante.

As seções a seguir descrevem a sequência de ações para visitantes novos e recorrentes:

### Novos visitantes

1. A API do visitante é carregada, analisada e executada.
1. A at.js / mbox.js é carregada, analisada e executada.
1. Se a criação automática da mbox global estiver ativada, a biblioteca JavaScript do Target:

   * Iniciará o objeto do visitante.
   * A biblioteca do Target tentará recuperar os dados de ID de visitante da Experience Cloud.
   * Como esse é um novo visitante, a API de visitante enviará uma solicitação de domínio cruzado para demdex.net.
   * Depois que os dados de ID de visitante da Experience Cloud forem recuperados, será enviada uma solicitação para o Target.

### Visitantes que retornam

1. A API do visitante é carregada, analisada e executada.
1. A at.js / mbox.js é carregada, analisada e executada.
1. Se a criação automática da mbox global estiver ativada, a biblioteca JavaScript do Target:

   * Iniciará o objeto do visitante.
   * A biblioteca do Target tentará recuperar os dados de ID de visitante da Experience Cloud.
   * A API de visitante recuperará os dados dos cookies.
   * Depois que os dados de ID de visitante da Experience Cloud forem recuperados, será enviada uma solicitação para o Target.

>[!NOTE]
>
>Para novos visitantes, quando a API de visitante estiver presente, o Target precisará transmitir as informações várias vezes para garantir que as solicitações do Target contenham os dados de ID de visitante da Experience Cloud. Para os visitantes recorrentes, o Target transmitirá as informações apenas para recuperar o conteúdo personalizado.
