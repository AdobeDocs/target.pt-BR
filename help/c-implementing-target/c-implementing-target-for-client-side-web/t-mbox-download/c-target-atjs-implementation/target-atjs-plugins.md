---
keywords: plug-ins do at.js; plug-ins compatíveis; plug-ins incompatíveis; ttMeta; ttmeta; mboxTrack
description: Informações sobre plug-ins compatíveis e incompatíveis do Adobe Target.
title: Plug-ins do at.js
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 96%

---


# Plug-ins do at.js

Informações sobre plug-ins compatíveis e incompatíveis no Adobe Target.

Muitas pessoas criaram plug-ins personalizados e plug-ins de resposta para a [!DNL mbox.js]. Esses plug-ins personalizados podem não ser compatíveis com a [!DNL at.js] sem ser atualizados.

Se estiver usando um plug-in que não esteja listado aqui e gostaria de saber o status, entre em contato com o representante da sua conta.

Este é o status atual de alguns dos plug-ins usados por muitos clientes, quando usados com a [!DNL at.js]:

| Plug-in do | Detalhes |
|--- |--- |
| mboxTrack | Não suportado.<br>Isso é substituído pela função [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md). Atualize seus plug-ins para aplicar a nova função.<br>Consulte a página [de integrações](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md). |
| Plugin de backup de perfil persistente | Não suportado.<br>Este plug-in foi desatualizado quando o tempo de vida do perfil do Target foi estendido de duas semanas para 90 dias. Verifique a data de expiração do cookie da mbox para ver a configuração de tempo de vida do perfil na sua conta.<br>Entre em contato com o Atendimento ao cliente se desejar estender o tempo de vida do perfil para 90 dias. |
| ttMeta | Os plug-ins antigos do SiteCatalyst devem ser desativados e substituídos pelo [Adobe Analytics como a fonte de relatórios do Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). O plugin ttMeta deve ser desativado e substituído pelo [depurador da Adobe Experience Cloud](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj). |