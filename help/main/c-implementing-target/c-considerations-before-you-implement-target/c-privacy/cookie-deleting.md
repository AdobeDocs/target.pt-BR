---
keywords: cookie, cookies, excluir cookie, excluir cookie de destino, google chrome, chrome, mozilla firefox, firefox, microsoft edge, safari
description: Saiba como excluir seu [!DNL Target] cookies do navegador para que você possa validar suas experiências.
title: Como faço para excluir o [!DNL Target] Cookie?
feature: Privacy & Security
role: Developer
exl-id: f2bc079e-593a-4689-a7cd-dfc6f86f6bb4
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 4%

---

# Exclua o [!DNL Target] cookie

Você pode excluir seu [!DNL Adobe Target] cookie do navegador (mbox) para que você possa validar todas as suas experiências durante os testes.

Se não houver [!DNL Target] cookie (mbox), você é considerado um novo visitante e recebe uma nova experiência. Existem várias formas de excluir o seu da mbox sem excluir todos os cookies do seu navegador.

>[!NOTE]
>
>As instruções a seguir estão corretas para os navegadores e versões listados. Procure na Internet instruções para o seu navegador ou versão específica.

## Exclua o [!DNL Target] cookie do Google Chrome

Versão 84.0.4147.105

1. Clique no botão **Cromo** menu > **Preferências**.
1. Clique no botão **Privacidade e segurança** guia .
1. Clique em **Cookies e outros dados do site**.
1. Clique em **Ver todos os cookies e dados do site**.
1. Expanda o `adobe.com` selecione a **mbox** e clique no ícone excluir (X).

## Exclua o [!DNL Target] cookie do Mozilla Firefox

Versão 79.0

### Excluir todos os cookies associados ao `adobe.com`

1. Clique no botão **Firefox** menu > **Preferências**.
1. Clique no botão **Privacidade e segurança** guia .
1. Em **Cookies e dados do site**, clique em **Gerenciar dados**.
1. Selecione o `adobe.com` site e, em seguida, clique em **Remover Selecionado**.

   >[!NOTE]
   >
   >Isso exclui todos os cookies associados ao `adobe.com` site. Se quiser excluir um cookie individual de um site, siga as instruções abaixo.

### Excluir um cookie individual (mbox)

1. No Firefox, clique em **Ferramentas** > **Desenvolvedor da Web** > **Inspetor de armazenamento**.
1. Clique no botão **Avançado** guia .
1. Navegue até a página da Web que contém o cookie que deseja excluir.
1. Expanda o **Cookies** e, em seguida, clique em `https://experience.adobe.com`.
1. Clique com o botão direito do mouse no **mbox** e, em seguida, clique em **Excluir**.

## Exclua o [!DNL Target] cookie do Microsoft Edge

Versão 84.0.522.52

1. Clique no botão **Microsoft Edge** menu > **Preferências**.
1. Clique no botão **Permissões do site** guia .
1. Clique em **Cookies e dados do site**.
1. Clique em **Ver todos os cookies e dados do site**.
1. Expanda o `adobe.com` selecione a **mbox** e clique no ícone excluir (X).

## Exclua o [!DNL Target] cookie do Apple Safari

Versão 13.1.2

### Excluir todos os cookies associados ao `adobe.com`

1. Clique no botão **Safari** menu > **Preferências**.
1. Clique no botão **Privacidade** guia .
1. Clique em **Gerenciar dados do site**.
1. Selecione os sites dos cookies que deseja excluir e clique em **Remover**.

   >[!NOTE]
   >
   >Isso exclui todos os cookies associados ao `adobe.com` site. Se quiser excluir um cookie individual de um site, siga as instruções abaixo.

### Excluir um cookie individual (mbox)

1. Clique no botão **Safari** menu > **Preferências**.
1. Clique no botão **Avançado** guia .
1. Selecione o **Mostrar menu Desenvolver na barra de menus** opção.
1. Navegue até a página da Web que contém o cookie que deseja excluir.
1. Clique no botão **Desenvolver** menu > **Mostrar Inspetor da Web**.
1. Clique no botão **Armazenamento** guia .
1. Expanda o **Cookies** e, em seguida, clique em `www.adobe.com`.
1. Clique com o botão direito do mouse no **mbox** e, em seguida, clique em **Excluir**.
