---
keywords: Implementação; Mbox; mbox.js; baixar mbox.js; configurar mbox.js
description: Saiba mais sobre a implementação herdada da mbox.js do Adobe Target. Migrar para o SDK da Web da Adobe Experience Platform (AEP Web SDK) ou para a versão mais recente da at.js.
title: Como faço o download da biblioteca  [!DNL Target] mbox.js?
feature: at.js
role: Developer
exl-id: 92096b1b-a8a5-435b-8e62-24b5d15d392f
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 74%

---

# Baixar a mbox.js

Target Standard e Premium usam uma versão modificada do arquivo da mbox.js do Adobe Target.

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

Para usar o [!UICONTROL Visual Experience Editor] do [!DNL Adobe Target], você deve incluir uma linha adicional de JavaScript como parte de seu arquivo [!DNL mbox.js].

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** em [!DNL Target Standard].
1. Clique **[!UICONTROL em Baixar mbox.js]** e siga as instruções para salvar o arquivo.
1. (Condicional) Se você usa a versão 60 ou superior da [!DNL mbox.js], você pode configurar a biblioteca para ocultar conteúdo da página automaticamente por padrão até que mboxes sejam carregadas para reduzir a cintilação em sites responsivos.

1. Crie a referência à [!DNL mbox.js] no site.

   A partir da versão 57 [!DNL mbox.js], a referência [!DNL mbox.js] pode ser colocada em qualquer lugar dentro da seção `<head>` da página.

   >[!IMPORTANT]
   >
   >Se você usar uma versão de [!DNL mbox.js] anterior à versão 57, a referência deverá ser o último item na seção `<head>` de suas páginas. Se a referência não for o último item, problemas graves de tela ou desempenho poderão ocorrer.

1. Faça upload do arquivo [!DNL mbox.js] salvo no local no seu ambiente de hospedagem especificado no código.
