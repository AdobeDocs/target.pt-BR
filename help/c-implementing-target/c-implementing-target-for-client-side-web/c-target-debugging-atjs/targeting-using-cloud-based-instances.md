---
keywords: instâncias em nuvem; lista de sufixos pública; sufixo público; cookie; cookie próprio; cookie próprio; azurewebsites.net; cloudapp.net; amazonaws.com; cloudfront.net; herokuapp.com; firebaseapp.com; targetGlobalSettings; cookieDomain
description: Explore os problemas (com soluções) que os clientes enfrentam ao usar as instâncias baseadas em nuvem para testar o Adobe [!DNL Target] ou para fins de prova de conceito.
title: Posso usar [!DNL Target] com instâncias baseadas em nuvem?
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 67%

---

# Usar instâncias baseadas em nuvem com o Target

Informações sobre problemas que os clientes enfrentam ao usar as instâncias baseadas em nuvem para testar o [!DNL Adobe Target].

Os clientes do, às vezes, usam instâncias baseadas em nuvem com o [!DNL Target]Target para testes ou fins de prova de conceito simples. Essas instâncias podem incluir os seguintes domínios:

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com` ou `firebaseapp.com`

Esses domínios e muitos outros fazem parte da [Lista de sufixos públicos](https://publicsuffix.org/list/public_suffix_list.dat).

**Problema:** os navegadores modernos não salvam cookies, se você estiver usando esses domínios.

A biblioteca JavaScript [!DNL at.js] usa cookies para rastrear usuários, para garantir que [!DNL Target] sempre apresente uma experiência consistente. Se a biblioteca JavaScript [!DNL Target] não puder salvar cookies, as solicitações [!DNL Target] serão desativadas.

**Solução:** como prática recomendada, se você pretende usar instâncias baseadas em nuvem com domínios incluídos na Lista de sufixos públicos, certifique-se de personalizar a configuração do `cookieDomain`. Para obter mais informações, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
