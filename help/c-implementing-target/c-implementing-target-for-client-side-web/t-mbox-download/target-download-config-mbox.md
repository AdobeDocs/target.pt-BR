---
description: Target Standard e Premium usam uma versão modificada do arquivo da mbox.js do Adobe Target.
keywords: Implementação; Mbox; mbox.js; baixar mbox.js; configurar mbox.js
seo-description: Target Standard e Premium usam uma versão modificada do arquivo da mbox.js do Adobe Target.
seo-title: Baixar a mbox.js
solution: Target
subtopic: Introdução
title: Baixar a mbox.js
topic: Padrão
uuid: b2a46321-cac7-4924-92dd-a80b50e27cee
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Fazer download de mbox.js{#download-mbox-js}

Target Standard e Premium usam uma versão modificada do arquivo da mbox.js do Adobe Target.

Para usar o [!UICONTROL Visual Experience Editor] do [!DNL Adobe Target], você deve incluir uma linha adicional de JavaScript como parte de seu arquivo [!DNL mbox.js].

1. Clique em **[!UICONTROL Configuração]** &gt; **[!UICONTROL Implementação]** em [!DNL Target Standard].
1. Clique **[!UICONTROL em Baixar mbox.js]** e siga as instruções para salvar o arquivo.
1. (Condicional) Se você usa a versão 60 ou superior da [!DNL mbox.js], você pode configurar a biblioteca para ocultar conteúdo da página automaticamente por padrão até que mboxes sejam carregadas para reduzir a cintilação em sites responsivos.

   Para obter mais informações, consulte &quot;Suprimir cintilação de carregamento de página&quot; nas [Configurações avançadas do mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/advanced-mboxjs-settings.md#reference_A9C8DAC6DF7743EDBCF1D71F8F20843C).

1. Crie a referência à [!DNL mbox.js] no site.

   A partir da versão 57 [!DNL mbox.js], a referência [!DNL mbox.js] pode ser colocada em qualquer lugar dentro da seção `<head>` da página.

   >[!IMPORTANT]
   >
   >Se você usar uma versão de [!DNL mbox.js] anterior à versão 57, a referência deverá ser o último item na seção `<head>` de suas páginas. Se a referência não for o último item, problemas graves de tela ou desempenho poderão ocorrer. Veja os [Detalhes de implementação técnica](https://marketing.adobe.com/resources/help/en_US/target/ov/c_mbox_technical.html) para mais informações.

1. Faça upload do arquivo [!DNL mbox.js] salvo no local no seu ambiente de hospedagem especificado no código.
