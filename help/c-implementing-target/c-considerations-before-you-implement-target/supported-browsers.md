---
description: O aplicativo Adobe Target e a entrega de conteúdo foram testados em uma grande variedade de navegadores e dispositivos.
keywords: Navegadores; Pré-requisitos; Requisitos; internet explorer; chrome; firefox; safari; android; surface
seo-description: O aplicativo Adobe Target e a entrega de conteúdo foram testados em uma grande variedade de navegadores e dispositivos.
seo-title: Navegadores compatíveis
solution: Target
subtopic: Introdução
title: Navegadores compatíveis
topic: Padrão
uuid: 614088da-412c-45e3-9f2d-6985391973be
translation-type: tm+mt
source-git-commit: 16bbe7b628c6f72f63465d4dfd4ca0e9c63b57e7

---


# Navegadores compatíveis{#supported-browsers}

O aplicativo [!DNL Adobe Target] e a entrega de conteúdo foram testados em uma grande variedade de navegadores e dispositivos.

Para obter informações importantes sobre TLS, consulte [Alterações de criptografia de TLS (Transport Layer Security)](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

## [!DNL Target] Interface padrão/Premium {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

A interface do [!DNL [!DNL Target]] Standard/Premium] é compatível com os seguintes navegadores e dispositivos:

| Tipo de dispositivo | Versão do navegador |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome (mais recente, uma versão anterior à mais recente)</li><li>Mozilla Firefox (mais recente, uma versão anterior à mais recente)</li></ul> |
| Mac | <ul><li>Firefox (mais recente, uma versão anterior à mais recente)</li><li>Chrome (mais recente, uma versão anterior à mais recente)</li></ul> |

## Entrega de conteúdo {#section_1045A946056441268D40025529918D3D}

A entrega de conteúdo foi testada nos seguintes navegadores e dispositivos:

| Tipo de dispositivo | Versão do navegador |
|--- |--- |
| Windows | <ul><li>Internet Explorer 9 e 10. Testado no modo de emulação.<br>**Observação**: o at.js 1.3.0 (e posterior) não oferece mais suporte à entrega de conteúdo no Microsoft Internet Explorer 9.</li><li>Internet Explorer 11</li><li>Microsoft Edge</li><li>Chrome (mais recente, uma versão anterior à mais recente)</li><li>Firefox (mais recente, uma versão anterior à mais recente)</li></ul> |
| Mac | <ul><li>Apple Safari (mais recente)<br>**Observação**: para obter mais informações sobre como o Safari processa cookies próprios e de terceiros, consulte [Cookie do Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/cookie-behavior.md).</li><li>Firefox (mais recente, uma versão anterior à mais recente)</li><li>Chrome (mais recente, uma versão anterior à mais recente)</li></ul> |
| Móvel/Tablet | <ul><li>Apple iOS (mais recente)</li><li>Dispositivos e tablets Android (Android 4 e posterior)</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

Para implementações do [!DNL at.js], o [!DNL Target] exibe o conteúdo padrão nas versões anteriores do Internet Explorer e possivelmente nas versões anteriores dos navegadores listados. Para implementações do [!DNL mbox.js], o [!DNL Target] tenta renderizar o conteúdo, mas pode não ser bem-sucedido.

[!DNL Target]O exibe o conteúdo padrão nos navegadores não listados acima e nos navegadores que usam o [modo QUIRKS](https://en.wikipedia.org/wiki/Quirks_mode). O at.js requer um tipo de doctype que é renderizado no modo padrão, por exemplo: `<!DOCTYPE html>`.

>[!NOTE]
>
>A infraestrutura do Adobe Delivery está sendo protegida para NÃO ser compatível com dispositivos e navegadores que usam o TLS 1.0 após 12 de setembro de 2018. Consulte [Mudanças de criptografia TLS (Transport Layer Security)](../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) para entender o impacto geral dessa mudança.
