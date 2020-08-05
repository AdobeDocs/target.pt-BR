---
description: Exclua os cookies do navegador do Target para que você possa validar todas as suas experiências.
title: Excluir o cookie Adobe Target
topic: Standard
uuid: 6e95ee4d-dbf2-4432-8abe-cfd9bc928f0c
translation-type: tm+mt
source-git-commit: 79bcd452a9faa0883272d2e686efd7c4ddfa34a2
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 5%

---


# Excluir o cookie do Target{#delete-the-target-cookie}

Você pode excluir o cookie [!DNL Target] do navegador (mbox) para que possa validar todas as suas experiências durante os testes.

If there is no [!DNL Target] cookie (mbox), you are considered a new visitor and shown a new experience. There are several ways to delete your [!DNL Target] cookies without deleting all of your browser cookies.

>[!NOTE]
>
>As instruções a seguir estão corretas para os navegadores e versões listados. Procure na Internet instruções para o seu navegador ou versão específica.

## Exclua o cookie do Público alvo do Google Chrome

Versão 84.0.4147.105

1. Clique no menu **Chrome** > **Preferências**.
1. Clique na guia **Privacidade e segurança** .
1. Clique em **Cookies e outros dados** do site.
1. Clique em **Ver todos os cookies e dados** do site.
1. Expanda a seção, selecione o cookie da `adobe.com` mbox **** e clique no ícone Excluir (X).

## Exclua o cookie do Público alvo do Mozilla Firefox

Versão 79.0

1. Clique no menu **Firefox** > **Preferências**.
1. Clique na guia **Privacidade e segurança** .
1. Em **Cookies e Dados** do site, clique em **Gerenciar dados**.
1. Selecione o `adobe.com` site e clique em **Remover selecionados**.

   >[!NOTE]
   >
   >Isso exclui todos os cookies associados ao `adobe.com` site. Se quiser excluir ou editar cookies individuais de um site, você pode fazer isso no Inspetor de [armazenamentos das ferramentas](https://developer.mozilla.org/en-US/docs/Tools/Storage_Inspector)do desenvolvedor. O cookie específico que você deve excluir é chamado de &quot;mbox&quot;.

## Exclua o cookie do Público alvo do Microsoft Edge

Versão 84.0.522.52

1. Clique no menu **Microsoft Edge** > **Preferências**.
1. Click the **Site Permissions** tab.
1. Clique em **Cookies e dados** do site.
1. Clique em **Ver todos os cookies e dados** do site.
1. Expanda a seção, selecione o cookie da `adobe.com` mbox **** e clique no ícone Excluir (X).

## Exclua o cookie do Público alvo do Apple Safari

Versão 13.1.2

1. Clique no menu **Safari** > **Preferências**.
1. Click the **Privacy** tab.
1. Clique em **Gerenciar dados** do site.
1. Selecione os sites dos cookies que deseja excluir e clique em **Remover**.

>[!NOTE]
>
>Isso exclui todos os cookies associados ao `adobe.com` site. Se desejar excluir um cookie individual para um site, siga as instruções abaixo:

1. Clique no menu **Safari** > **Preferências**.
1. Click the **Advanced** tab.
1. Selecione o menu **Mostrar revelação na opção da barra** de menus.
1. Navegue até a página da Web que contém o cookie que deseja excluir.
1. Clique no menu **Desenvolver** > **Mostrar inspetor** da Web.
1. Click the **Storage** tab.
1. Expanda a seção **Cookies** e clique em `www.adobe.com`.
1. Clique com o botão direito do mouse no cookie da **mbox** e clique em **Excluir**.