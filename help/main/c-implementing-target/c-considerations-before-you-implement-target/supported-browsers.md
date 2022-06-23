---
keywords: Navegadores; Pré-requisitos; Requisitos; internet explorer; chrome; firefox; safari; android; surface
description: Saiba quais navegadores da Internet são Adobe [!DNL Target] O suporta para sua interface e para entrega de conteúdo.
title: O que os navegadores fazem [!DNL Target] Suporte?
feature: Implementation
role: Developer
exl-id: 8a366c79-d944-4d44-be5a-7c4f65385beb
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 44%

---

# Navegadores compatíveis

O aplicativo [!DNL Adobe Target] e a entrega de conteúdo foram testados em uma grande variedade de navegadores e dispositivos.

Para obter informações mais importantes sobre TLS, consulte [Alterações na criptografia da Segurança da camada de transporte (TLS)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/).

## [!DNL Target]Interface do Standard/Premium {#section_1B73CA4B7BBC460BB7009DF00A2AFC4D}

O [!DNL Target] A interface da é compatível com os seguintes navegadores e dispositivos:

| Tipo de dispositivo | Versão do navegador |
|--- |--- |
| Windows | <ul><li>Microsoft Edge</li><li>Google Chrome (mais recente, menos 1)</li><li>Mozilla Firefox (mais recente, menos 1)</li></ul> |
| Mac | <ul><li>Firefox (mais recente, menos 1)</li><li>Chrome (mais recente, menos 1)</li></ul> |

## Entrega de conteúdo {#section_1045A946056441268D40025529918D3D}

A entrega de conteúdo foi testada nos seguintes navegadores e dispositivos:

| Tipo de dispositivo | Versão do navegador |
|--- |--- |
| Windows | <ul><li>Microsoft Internet Explorer 9 e 10. Testado no modo de emulação.<br>**Observação**: A entrega de conteúdo no IE 9 não é mais compatível com o at.js 1.3.0 (e posterior). A entrega de conteúdo no IE 10, 11 e em todas as versões mais antigas não é mais compatível com o at.js 2.5.0 (e posterior).</li><li>Internet Explorer 11 <br>**Observação**: A entrega de conteúdo no IE 10, 11 e em todas as versões mais antigas não é mais compatível com o at.js 2.5.0 (e posterior).</li><li>Microsoft Edge</li><li>Chrome (mais recente, menos 1)</li><li>Firefox (mais recente, menos 1)</li></ul> |
| Mac | <ul><li>Apple Safari (mais recente)<br>**Observação**: Para obter mais informações sobre como o Safari processa cookies próprios e de terceiros, consulte [Cookie de direcionamento](https://developer.adobe.com/target/before-implement/privacy/cookie-behavior/).</li><li>Firefox (mais recente, menos 1)</li><li>Chrome (mais recente, menos 1)</li></ul> |
| Móvel/Tablet | <ul><li>Apple iOS (mais recente)</li><li>Dispositivos e tablets Android (Android 4 e posterior)</li><li>Microsoft Surface (Windows 8.1)</li></ul> |

Observe o seguinte:

* Para implementações do [!DNL at.js], o [!DNL Target] exibe o conteúdo padrão nas versões anteriores do Internet Explorer e possivelmente nas versões anteriores dos navegadores listados.
* O Internet Explorer trata todos os elementos desconhecidos (como elementos personalizados) como o mesmo tipo de elemento. Como resultado, o delivery não funciona com elementos personalizados.
* [!DNL Target]O exibe o conteúdo padrão nos navegadores não listados acima e nos navegadores que usam o [modo QUIRKS](https://en.wikipedia.org/wiki/Quirks_mode). O at.js requer um tipo de doctype que é renderizado no modo padrão, por exemplo: `<!DOCTYPE html>`.
* A infraestrutura do Adobe Delivery está sendo protegida para NÃO ser compatível com dispositivos e navegadores que usam o TLS 1.0 após 12 de setembro de 2018. Consulte [Mudanças de criptografia TLS (Transport Layer Security)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/) para entender o impacto geral dessa mudança.
