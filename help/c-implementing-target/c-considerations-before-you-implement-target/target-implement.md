---
keywords: document.write; target; implementar; implementar o target; dtm; dynamic tag management; at.js; mbox.js; target.js; mbox; adobe experience platform web skd; aep web sdk; web sdk
description: Implemente o Adobe Target referenciando as bibliotecas do Target (at.js ou mbox.js) nas suas páginas da Web.
title: Noções básicas sobre as bibliotecas de JavaScript do Target
feature: Implementação
translation-type: tm+mt
source-git-commit: abfbc08a649b31e7b784659dbf390412b2c15af2
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 23%

---


# Noções básicas sobre as bibliotecas de JavaScript do Target

Implemente [!DNL Adobe Target] referenciando as bibliotecas [!DNL Adobe Target] (Adobe Experience Platform Web SDK ou at.js) nas suas páginas da Web.

>[!NOTE]
>
>A biblioteca mbox.js não está mais sendo desenvolvida. Todos os clientes devem migrar da mbox.js para a at.js ou para o [!UICONTROL Adobe Experience Platform Web SDK] antes de 31 de março de 2021. Para obter mais informações, consulte [Migrar para at.js da mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA) ou [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md).

## Diferenças entre as bibliotecas JavaScript do Target {#section_40117C78C2F84FECAC4F1BA40CC4F171}

A tabela a seguir explica as diferenças entre as bibliotecas JavaScript [!DNL Target]:

| Referência da biblioteca | Descrição |
|--- |--- |
| Adobe Experience Platform Web SDK | O [!UICONTROL Adobe Experience Platform Web SDK] permite interagir com os vários serviços no [!DNL Experience Cloud] (incluindo [!DNL Target]) por meio da Adobe Experience Edge Network. Se você optar por migrar para o [!DNL Adobe Experience Platform Web SDK], consulte [O que é Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) no *Guia do SDK da Web*. |
| at.js  | A at.js substitui a mbox.js para implementações do [!DNL [!DNL Target]].<br>Entre outros benefícios, a at.js melhora os tempos de carregamento de página para implementações da Web, melhora a segurança, evita avisos de document.write no Google Chrome e fornece opções de implementações melhores para aplicativos de página única.<br>Para obter mais informações, consulte [Implementação do at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md). |

## Impacto da at.js no tempo de carregamento de página {#section_16630CD0FF0A498EB596A51381366A5A}

Muitos clientes e consultores querem saber o impacto de [!DNL at.js] no tempo de carregamento de página, especialmente no contexto de usuários novos e recorrentes. Infelizmente, é difícil medir e fornecer números concretos sobre como o [!DNL at.js] influencia o tempo de carregamento de página devido à implementação de cada cliente.

No entanto, se a API de visitante estiver presente na página, [!DNL Target] poderá entender melhor como [!DNL at.js] influencia no tempo de carregamento de página.

>[!NOTE]
>
>A API de visitante e [!DNL at.js] têm um impacto no tempo de carregamento de página somente quando você está usando a mbox global (por causa da técnica de ocultação do corpo). As mboxes regionais não são afetadas pela integração da API do visitante.

As seções a seguir descrevem a sequência de ações para visitantes novos e recorrentes:

### Novos visitantes

1. A API do visitante é carregada, analisada e executada.
1. A at.js é carregada, analisada e executada.
1. Se a criação automática da mbox global estiver ativada, a biblioteca JavaScript [!DNL Target]:

   * Iniciará o objeto do visitante.
   * A biblioteca [!DNL Target] tenta recuperar os dados de [!UICONTROL ID do visitante do Experience Cloud].
   * Para um novo visitante, a API de visitante aciona uma solicitação entre domínios para `demdex.net`.
   * Depois que os dados de [!UICONTROL ID de visitante do Experience Cloud] forem recuperados, uma solicitação para o Target será acionada.

### Visitantes que retornam

1. A API do visitante é carregada, analisada e executada.
1. A at.js é carregada, analisada e executada.
1. Se a criação automática da mbox global estiver ativada, a biblioteca JavaScript [!DNL Target]:

   * Iniciará o objeto do visitante.
   * A biblioteca [!DNL Target] tenta recuperar os dados de [!UICONTROL ID do visitante do Experience Cloud].
   * A API de visitante recuperará os dados dos cookies.
   * Depois que os dados de [!UICONTROL ID de visitante Experience Cloud] forem recuperados, uma solicitação para [!DNL Target] será acionada.

>[!NOTE]
>
>Para novos visitantes, quando a API de visitante estiver presente, [!DNL Target] transmitirá várias vezes para garantir que as solicitações [!DNL Target] contenham dados de [!UICONTROL ID de visitante Experience Cloud]. Para visitantes recorrentes, [!DNL Target] passa o fio somente para [!DNL Target] para recuperar o conteúdo personalizado.
