---
keywords: Target;at.js;migrate to at.js;readiness;audit at.js;integrate at.js
description: A migração da mbox.js para a at.js é um processo simples.
title: Como migrar da mbox.js para a at.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 99%

---


# Como migrar da mbox.js para a at.js{#how-to-migrate-to-at-js-from-mbox-js}

A migração da mbox.js para a at.js no [!DNL Adobe Target] é um processo simples.

Use os seguintes passos para migrar da [!DNL mbox.js] para a [!DNL at.js] e conferir sua migração:

1. Determine os requisitos de [suporte a navegador de sua](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100) organização.
1. Verifique a implementação atual da [!DNL mbox.js] do seu site para capacidades que não são suportadas pela [!DNL at.js].

   Ao auditar sua implementação, procure pelo seguinte:

   **Que tipos de mboxes você usa atualmente?**

   | Tipo | Detalhes |
   |--- |--- |
   | Mbox global criada automaticamente | A mbox global criada automaticamente é criada quando a única linha de código do Target no seu site é o arquivo mbox.js. Aquele arquivo gera uma chamada mbox automaticamente. |
   | Global, mboxCreate vazio | Recomenda-se que você altere para a mbox global criada automaticamente. |
   | Encapsulamento mboxCreate | A migração deve ser simples, desde que seu `mboxCreate()` seja precedido pelo `<div class="mboxDefault"></div>`. |
   | mboxUpdate | A migração deve ser simples quando o  `mboxUpdate()` é usada juntamente com `mboxDefine()` ou `mboxCreate()`. `mboxUpdate()` não atualiza a mbox global criada automaticamente ou uma mbox criada originalmente por `getOffer()`. Nessas circunstâncias, uma combinação de `getOffer()` e `applyOffer()` deve ser usada para substituir `mboxUpdate()` ao migrar para o at.js. |
   | Mboxes de clicktracking personalizadas, incluindo mboxTrack | Recomendamos que você atualize seu código para usar  `trackEvent()`. |

   >[!NOTE]
   >
   >Para obter mais informações sobre as várias funções mencionadas na tabela anterior, consulte [funções da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

   **Você tem alguma personalização no seu arquivo [!DNL mbox.js]?**

   * mboxParameters()
   * mboxSupported()
   * mboxCookieDomain()
   * JavaScript extra
   * Outros locais

   A maioria dos [objetos e métodos da mbox.js](/help/c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537) (como `mbox`, `mboxCurrent`, `mboxFactoryDefault`, `mboxFactories` e outros) não são suportados. Abordagens alternadas podem ser possíveis para realizar o que você está tentando fazer.

   **Você tem a [!DNL mbox.js] em alguma de suas páginas da Web?**

   Você não pode usar a [!DNL at.js] e a [!DNL mbox.js] na mesma página da Web. No entanto, você pode usar duas bibliotecas JavaScript em duas páginas diferentes do mesmo site.

   O cookie da mbox é o meio principal da Adobe ligar o visitante a cada página. Como parte do seu procedimento de controle de qualidade, você deve confirmar que o cookie está sendo preservado e lido corretamente conforme o visitante vai e volta entre páginas com a [!DNL at.js] e aquelas com a [!DNL mbox.js]. Certifique-se de que os mesmos valores `mboxPC` e `mboxSession` passem nas chamadas mbox, independentemente de qual seção do site ([!DNL at.js] ou [!DNL mbox.js]) o visitante entre primeiro e qual seção define o cookie originalmente. Se você usa cookies de terceiros na sua implementação, certifique-se de que esses valores permaneçam os mesmos conforme você navega pelo site.

   **Você integra o [!DNL Target] com alguma outra solução da Adobe?**

   * Analytics (A4T)
   * Analytics (integração existente)
   * AAM (backend)
   * AAM (frontend existente)
   * AEM
   * Data Workbench

   Algumas integrações existentes não são suportadas pela [!DNL at.js]. Para obter mais informações, consulte a página de [Integrações](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39).

   **Você integra o [!DNL Target] com alguma outra ferramenta de terceiros?**

   * Outras ferramentas de Analytics
   * Outros DMPs
   * Demandbase
   * Click-tale
   * Outras

   Essas integrações podem precisar de ajustes para funcionar com a [!DNL at.js]. Para obter mais informações, consulte a página de [Integrações](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39).

   **Você usa um gerenciador de tags?**

   * Dynamic Tag Management
   * Ensighten
   * Tealium
   * Signal/BrightTag

   Para obter mais informações, consulte [Integrações da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39).

   >[!NOTE]
   >
   >Se você não estiver usando atualmente um gerenciador de tags para implantar [!DNL Target], agora pode ser um bom momento para considerá-lo. O [Dynamic Tag Management da Adobe](https://dtm.adobe.com) é gratuito para [!DNL Target] os clientes e é o método recomendado para implantar[!DNL Target]. Para mais informações, consulte [Práticas recomendadas para a implementação do Adobe Target usando o Dynamic Tag Management](https://experienceleague.adobe.com/docs/dtm/implementing/overview.html).

1. Verifique se todas as atividades e integrações atuais estão funcionando como esperado.

   Essas são algumas coisas que você pode fazer enquanto teste para confirmar que a [!DNL at.js] está funcionando como o esperado:

   * Certifique-se de que todas suas atividades atuais funcionam com a nova biblioteca JavaScript.
   * Confirme que todas  [integrações](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39) e [plugins](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF) funcionam conforme esperado.
   * Verifique se você está familiarizado com [a depuração](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) das abordagens disponíveis em [!DNL at.js].

**Possíveis problemas ao migrar para o at.js** Alguns clientes relataram os seguintes problemas após executar a migração para o at.js:

* Algumas atividades do VEC que foram construídos em uma página com a [!DNL mbox.js] podem precisar ser atualizadas para funcionarem com a [!DNL at.js].

   Este problema acontece com mais frequência em sites que não usam muitos atributos id ou class em elementos HTML. Você pode confirmar se está tendo esse problema ao carregar a página e determinar se a experiência está sendo entregue como esperado ao carregar a página com `?mboxDebug=true` e revisar as declarações do console.

   ![](assets/mboxdebug.png)
Nesses casos, seletores de elementos podem começar com algo como

   ```
   HTML > BODY > DIV:nth-of-type(2)
   ```

   e foram criados com a expectativa de que [!DNL mbox.js] adicionou um elemento extra `<div>` à parte superior da página. Como [!DNL at.js] não adiciona um elemento `<div>` à parte superior da página, esse seletor não funcionaria mais com [!DNL at.js].

   Este problema pode ser corrigido ao recriar a atividade no VEC no URL usando a [!DNL at.js] ou atualizando manualmente o seletor usando a opção **[!UICONTROL &lt;/> Código]** > **[!UICONTROL Modificações]** no VEC.

   Para solucionar esse problema, você deve subtrair 1 do número nth-of-type no primeiro elemento DIV após BODY. No exemplo acima o código editado seria:

   ```
   HTML > BODY > DIV:nth-of-type(1)
   ```

   Para mais informações sobre como usar o editor de código para fazer isso, consulte  [Editor de códigos](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5).

* Como todas as mboxes agora são assíncronas, elas não vão bloquear a renderização da página ou retornar na ordem em que foram acionadas. Para obter mais informações, consulte &quot;Considerações assíncronas&quot; em  [Limitações da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#concept_FA99E4D6EC274552BF45E01AFB76CCAE).
