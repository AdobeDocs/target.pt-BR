---
keywords: limitações do visual experience composer; suporte para navegador; integrações; plugins; considerações assíncronas
description: Saiba mais sobre a implementação herdada da mbox.js do Adobe Target. Migrar para o SDK da Web da Adobe Experience Platform (AEP Web SDK) ou para a versão mais recente da at.js.
title: Quais são as diferenças entre at.js e mbox.js?
feature: at.js
role: Developer
exl-id: 2fd0db66-0b47-41c0-86b6-44e711d70027
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 91%

---

# Limitações da at.js

Há algumas diferenças entre o at.js e o mbox.js. Este tópico lista algumas das diferenças e limitações a fim de ajudar você a ser bem-sucedido com a at.js.

## Conhecer as limitações do Visual Experience Composer {#section_4B63C97169DE4C93B22944E880FD3DF1}

* As opções Inserir elemento e Reorganizar no Visual Experience Composer devem ser evitadas nos aplicativos de página única.

   Como o DOM não é limpo em eventos de carregamento de página nos aplicativos de página única, como ocorre em sites tradicionais, as manipulações de Inserir elemento e Reorganizar podem ser reaplicadas várias vezes, dependendo de como o visitante navega no SPA.

## Integrações e plug-ins  {#section_D92E31170176406AAC7B5005F03D3425}

Algumas funções da [!DNL mbox.js] não estão disponíveis na [!DNL at.js]. Métodos e objetos da [mbox.js internos](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537) (como `mbox`, `mboxCurrent`, `mboxFactoryDefault`, `mboxFactories` e outros) não são mais compatíveis com a [!DNL at.js] (por exemplo: `mboxFactoryDefault`). Isso ocorre por design, destinado a desencorajá-lo de &quot;hackear&quot; a [!DNL at.js] para desenvolver recursos não suportados que, a longo prazo, podem comprometer uma implementação e impossibilitar a atualização. Os únicos métodos expostos são abordados nas páginas da API desta documentação. Por esse motivo:

* [Integrações](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39) herdadas, baseadas em página, podem não funcionar com outras soluções da Adobe e devem ser atualizadas para integrações mais recentes no lado do servidor.

   Certifique-se de incluir plug-ins como parte do teste.

## Considerações assíncronas {#section_B586360A3DD34E2995AE25A18E3FB953}

Como todas as mboxes agora são assíncronas, elas não vão bloquear a renderização da página ou retornar na ordem em que foram acionadas.

* Se você estiver usando uma mbox global no [Form-Based Experience Composer](/help/c-experiences/experiences.md#section_3643394BD424463C8768F2907DEBCC22), esteja ciente de que as ofertas HTML devem conter somente as tags `<script>`, `<style>` e `<link>`.

   Durante a entrega, o [!DNL at.js] filtra todas as outras tags HTML ao aplicar ofertas de mbox global. As ofertas da mbox global são aplicadas ao HTML HEAD, que não permite DIV, SPAN e assim por diante. Por exemplo, `<div>test</div>` não pode ser aplicado porque a tag `<div>` pode ser usada somente dentro do CORPO HTML.

* A integração herdada, baseada em página, do [!DNL Target] para [!DNL Analytics] não funcionará.

   Essa integração exige que a chamada do [!DNL Target] seja feita antes da chamada do [!DNL Analytics].

* Atenção às dependências do JavaScript entre a sua oferta e a página.

   Você não deve pressupor que o JavaScript na sua oferta será executado antes do JavaScript codificado abaixo da mbox.

* Atenção às dependências do JavaScript entre as várias ofertas na página.

   Você não pode mais pressupor que a oferta entregue pela primeira mbox será executada antes da oferta entregue pela segunda.

* As ofertas de Manipulação e Redirecionamento de DOM devem ser entregues por meio da mbox global, criada automaticamente na [!DNL at.js], para `<head>`.

   Uma função `mboxCreate()` na parte superior do `<body>` provavelmente resultará em cintilação do conteúdo padrão.
