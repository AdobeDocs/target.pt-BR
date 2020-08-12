---
keywords: document.write;target;implement;implement target;dtm;dynamic tag management;at.js;mbox.js;target.js;mbox
description: Implemente o Target referenciando as bibliotecas do Target (at.js ou mbox.js) nas suas páginas da Web.
title: Noções básicas sobre as bibliotecas de JavaScript do Target
feature: null
topic: Target
uuid: c8a254c9-afc9-4a55-be01-788c11bef7cc
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 100%

---


# Entender as [!DNL Target]bibliotecas JavaScript{#understand-the-target-javascript-libraries}

Implemente o [!DNL Target] referenciando as bibliotecas do [!DNL Target] (at.js ou mbox.js) nas suas páginas da Web.

>[!NOTE]
>
>A biblioteca mbox.js não está mais sendo desenvolvida. Todos os clientes devem migrar da mbox.js para a at.js. Para obter mais informações, consulte [Migrar para at.js do mbox.js](../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## Diferenças entre as duas bibliotecas {#section_40117C78C2F84FECAC4F1BA40CC4F171}

A tabela a seguir explica as diferenças entre as duas bibliotecas:

| Referência da biblioteca | Descrição |
|--- |--- |
| at.js | A at.js substitui a mbox.js para implementações do [!DNL Target].<br>Entre outros benefícios, a at.js melhora os tempos de carregamento de página para implementações da Web, melhora a segurança, evita avisos de document.write no Google Chrome e fornece opções de implementações melhores para aplicativos de página única.<br>Para obter mais informações, consulte [Implementação do at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md). |
| mbox.js | Antes do [!DNL Target] 16.3.1 (março de 2016), o [!DNL Target] exigia uma chamada para a mbox.js a fim de criar a mbox global necessária para o [!DNL Target] fornecer atividades, rastrear cliques e a maioria das métricas de sucesso. Esse arquivo contém as bibliotecas necessárias para todas as suas atividades. Você não precisa manter versões específicas de atividades diferentes do arquivo.<br>Se você já tiver mboxes de envolvimento nas suas páginas de um estilo antigo de implementação do [!DNL Target], elas ainda poderão ser usadas na nova interface. O arquivo mbox.js atualizado ainda é necessário, mas essas mboxes podem ser selecionadas para atividades e editadas usando o Visual Experience Composer.<br>[!DNL Target]O Standard e Premium atualizam e complementam a mbox.js com uma referência para um arquivo target.js. O arquivo target.js é hospedado pelo Adobe. O arquivo target.js possibilita a edição de conteúdo em qualquer página que usa o Visual Experience Composer, mesmo que a página não contenha mboxes predefinidas. Você deve mencionar esse arquivo em todas as páginas do site.<br>Para obter mais informações, consulte [Implementação do mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Importante **: a biblioteca mbox.js ainda é suportada, mas não haverá atualizações de recursos. Todos os clientes devem migrar para a at.js. Para obter mais informações, consulte[Migrar para at.js do mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)<br> |

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
