---
keywords: instâncias em nuvem; lista de sufixos pública; sufixo público; cookie; cookie próprio; cookie próprio; azurewebsites.net; cloudapp.net; amazonaws.com; cloudfront.net; herokuapp.com; firebaseapp.com; targetGlobalSettings; cookieDomain
description: Explore os problemas (com soluções) que os clientes enfrentam ao usar as instâncias baseadas em nuvem para testar o Adobe [!DNL Target] ou para efeitos de prova de conceito.
title: Posso Usar [!DNL Target] com instâncias baseadas em nuvem?
feature: at.js
role: Developer
exl-id: 220371a9-ba57-4e67-b82f-8fec6f9d2833
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 67%

---

# Usar instâncias baseadas em nuvem com o Target

Informações sobre problemas que os clientes enfrentam ao usar as instâncias baseadas em nuvem para testar o [!DNL Adobe Target].

Os clientes do, às vezes, usam instâncias baseadas em nuvem com o [!DNL Target]Target para testes ou fins de prova de conceito simples. Essas instâncias podem incluir os seguintes domínios:

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com` ou `firebaseapp.com`

Esses domínios e muitos outros fazem parte da [Lista de sufixos públicos](https://publicsuffix.org/list/public_suffix_list.dat).

**Problema:** os navegadores modernos não salvam cookies, se você estiver usando esses domínios.

O [!DNL at.js] A biblioteca JavaScript usa cookies para rastrear usuários para garantir que [!DNL Target] sempre apresenta uma experiência consistente. Se a variável [!DNL Target] A biblioteca JavaScript não pode salvar cookies, [!DNL Target] as solicitações estão desativadas.

**Solução:** como prática recomendada, se você pretende usar instâncias baseadas em nuvem com domínios incluídos na Lista de sufixos públicos, certifique-se de personalizar a configuração do `cookieDomain`. Para obter mais informações, consulte [targetGlobalSettings()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/).
