---
keywords: instâncias em nuvem; lista de sufixos pública; sufixo público; cookie; cookie próprio; cookie próprio; azurewebsites.net; cloudapp.net; amazonaws.com; cloudfront.net; herokuapp.com; firebaseapp.com; targetGlobalSettings; cookieDomain
description: Informações sobre problemas que os clientes enfrentam ao usar as instâncias baseadas em nuvem para testar o Adobe Target.
title: Usar instâncias baseadas em nuvem com o Target
uuid: dcaba49e-7567-4970-bb9a-19377aff7d38
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Usar instâncias baseadas em nuvem com o Target{#use-cloud-based-instances-with-target}

Informações sobre problemas que os clientes enfrentam ao usar as instâncias baseadas em nuvem para testar o [!DNL Adobe Target].

Os clientes do, às vezes, usam instâncias baseadas em nuvem com o [!DNL Target]Target para testes ou fins de prova de conceito simples. Essas instâncias podem incluir os seguintes domínios:

`azurewebsites.net`, `cloudapp.net`, `amazonaws.com`, `cloudfront.net`, `herokuapp.com` ou `firebaseapp.com`

Esses domínios e muitos outros fazem parte da [Lista de sufixos públicos](https://publicsuffix.org/list/public_suffix_list.dat).

**Problema:** os navegadores modernos não salvam cookies, se você estiver usando esses domínios.

As bibliotecas de JavaScript [!DNL at.js] e [!DNL mbox.js] usam cookies para rastrear usuários, para garantir que o [!DNL Target] sempre apresente uma experiência consistente. Se as bibliotecas de JavaScript do [!DNL Target] não puderem salvar cookies, as solicitações do [!DNL Target] serão desativadas.

**Solução:** como prática recomendada, se você pretende usar instâncias baseadas em nuvem com domínios incluídos na Lista de sufixos públicos, certifique-se de personalizar a configuração do `cookieDomain`. Para obter mais informações, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
