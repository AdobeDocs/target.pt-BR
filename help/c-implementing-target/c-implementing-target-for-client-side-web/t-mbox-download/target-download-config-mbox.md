---
keywords: Implementação; Mbox; mbox.js; baixar mbox.js; configurar mbox.js
description: Saiba mais sobre a implementação legada da mbox.js do Adobe Target. Migre para o Adobe Experience Platform Web SDK (AEP Web SDK) ou para a versão mais recente do at.js.
title: Como faço o download da biblioteca mbox.js do Público alvo?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 58%

---


# Fazer download de mbox.js{#download-mbox-js}

Target Standard e Premium usam uma versão modificada do arquivo da mbox.js do Adobe Target.

>[!IMPORTANT]
>
>**Fim da vida útil** do mbox.js: Em 31 de março de 2021, não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem [!DNL Target] atividades sendo executadas com o conteúdo padrão.
>
>Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca JavaScript at.js antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implemente o Público alvo para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

Para usar o [!UICONTROL Visual Experience Editor] do [!DNL Adobe Target], você deve incluir uma linha adicional de JavaScript como parte de seu arquivo [!DNL mbox.js].

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]** em [!DNL Target Standard].
1. Clique **[!UICONTROL em Baixar mbox.js]** e siga as instruções para salvar o arquivo.
1. (Condicional) Se você usa a versão 60 ou superior da [!DNL mbox.js], você pode configurar a biblioteca para ocultar conteúdo da página automaticamente por padrão até que mboxes sejam carregadas para reduzir a cintilação em sites responsivos.

   Para obter mais informações, consulte &quot;Suprimir cintilação de carregamento de página&quot; nas [Configurações avançadas do mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C).

1. Crie a referência à [!DNL mbox.js] no site.

   A partir da versão 57 [!DNL mbox.js], a referência [!DNL mbox.js] pode ser colocada em qualquer lugar dentro da seção `<head>` da página.

   >[!IMPORTANT]
   >
   >Se você usar uma versão de [!DNL mbox.js] anterior à versão 57, a referência deverá ser o último item na seção `<head>` de suas páginas. Se a referência não for o último item, problemas graves de tela ou desempenho poderão ocorrer. Consulte [O que o mbox.js faz](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-technical.md) para obter mais informações.

1. Faça upload do arquivo [!DNL mbox.js] salvo no local no seu ambiente de hospedagem especificado no código.
