---
keywords: cookie, cookies, excluir cookie, excluir cookie de destino, google chrome, chrome, mozilla firefox, firefox, microsoft edge, safari
description: 'Saiba como excluir os cookies do navegador para que você possa validar suas experiências. [!DNL Target] '
title: Como faço para excluir o cookie  [!DNL Target] ?
feature: Privacidade e segurança
role: Developer
exl-id: f2bc079e-593a-4689-a7cd-dfc6f86f6bb4
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 4%

---

# Exclua o cookie [!DNL Target]

Você pode excluir seu [!DNL Adobe Target] cookie do navegador (mbox) para validar todas as suas experiências durante os testes.

Se não houver cookie [!DNL Target] (mbox), você será considerado um novo visitante e receberá uma nova experiência. Existem várias formas de excluir o seu da mbox sem excluir todos os cookies do seu navegador.

>[!NOTE]
>
>As instruções a seguir estão corretas para os navegadores e versões listados. Procure na Internet instruções para o seu navegador ou versão específica.

## Excluir o cookie [!DNL Target] do Google Chrome

Versão 84.0.4147.105

1. Clique no menu **Chrome** > **Preferências**.
1. Clique na guia **Privacy and Security**.
1. Clique em **Cookies e outros dados do site**.
1. Clique em **Ver todos os cookies e dados do site**.
1. Expanda a seção `adobe.com` , selecione o cookie **mbox** e clique no ícone excluir (X).

## Exclua o cookie [!DNL Target] do Mozilla Firefox

Versão 79.0

### Excluir todos os cookies associados a `adobe.com`

1. Clique no menu **Firefox** > **Preferências**.
1. Clique na guia **Privacy and Security**.
1. Em **Cookies e dados do site**, clique em **Gerenciar dados**.
1. Selecione o site `adobe.com` e clique em **Remover seleção**.

   >[!NOTE]
   >
   >Isso exclui todos os cookies associados ao site `adobe.com`. Se quiser excluir um cookie individual de um site, siga as instruções abaixo.

### Excluir um cookie individual (mbox)

1. No Firefox, clique em **Ferramentas** > **Desenvolvedor da Web** > **Inspetor de armazenamento**.
1. Clique na guia **Avançado**.
1. Navegue até a página da Web que contém o cookie que deseja excluir.
1. Expanda a seção **Cookies** e clique em `https://experience.adobe.com`.
1. Clique com o botão direito do mouse no cookie **mbox** e depois clique em **Delete**.

## Exclua o cookie [!DNL Target] do Microsoft Edge

Versão 84.0.522.52

1. Clique no menu **Microsoft Edge** > **Preferências**.
1. Clique na guia **Permissões do site**.
1. Clique em **Cookies e dados do site**.
1. Clique em **Ver todos os cookies e dados do site**.
1. Expanda a seção `adobe.com` , selecione o cookie **mbox** e clique no ícone excluir (X).

## Exclua o cookie [!DNL Target] do Apple Safari

Versão 13.1.2

### Excluir todos os cookies associados a `adobe.com`

1. Clique no menu **Safari** > **Preferências**.
1. Clique na guia **Privacy**.
1. Clique em **Gerenciar dados do site**.
1. Selecione os sites dos cookies que deseja excluir e clique em **Remover**.

   >[!NOTE]
   >
   >Isso exclui todos os cookies associados ao site `adobe.com`. Se quiser excluir um cookie individual de um site, siga as instruções abaixo.

### Excluir um cookie individual (mbox)

1. Clique no menu **Safari** > **Preferências**.
1. Clique na guia **Avançado**.
1. Selecione a opção **Mostrar menu Desenvolver na barra de menus**.
1. Navegue até a página da Web que contém o cookie que deseja excluir.
1. Clique no menu **Desenvolver** > **Mostrar Inspetor Web**.
1. Clique na guia **Storage**.
1. Expanda a seção **Cookies** e clique em `www.adobe.com`.
1. Clique com o botão direito do mouse no cookie **mbox** e depois clique em **Delete**.
