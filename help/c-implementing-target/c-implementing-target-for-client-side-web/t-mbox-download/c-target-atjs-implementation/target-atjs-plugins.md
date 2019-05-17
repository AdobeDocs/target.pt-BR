---
description: Informações sobre plug-ins da at.js suportados e não suportados.
keywords: plugins da at.js; plugins compatíveis; plugins não compatíveis
seo-description: Informações sobre plug-ins da at.js suportados e não suportados.
seo-title: Plug-ins da at.js
solution: Target
title: Plug-ins da at.js
topic: Padrão
uuid: ef36b2b2-bf6d-497e-b3f5-2b572a1b8a8d
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Plug-ins da at.js{#at-js-plug-ins}

Informações sobre plug-ins da at.js suportados e não suportados.

Muitas pessoas criaram plug-ins personalizados e plug-ins de resposta para a [!DNL mbox.js]. Esses plug-ins personalizados podem não ser compatíveis com a [!DNL at.js] sem ser atualizados.

Se estiver usando um plug-in que não esteja listado aqui e gostaria de saber o status, entre em contato com o representante da sua conta.

Este é o status atual de alguns dos plug-ins usados por muitos clientes, quando usados com a [!DNL at.js]:

| Plug-in do | Detalhes |
|--- |--- |
| mboxTrack | Não suportado.<br>Isso é substituído pela função [adobe.target.trackevent(opções)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md). Atualize seus plug-ins para aplicar a nova função.<br>Consulte a página [de integrações](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md). |
| Plugin de backup de perfil persistente | Não suportado.<br>Este plug-in foi desatualizado quando o tempo de vida do perfil do Target foi estendido de duas semanas para 90 dias. Verifique a data de expiração do cookie da mbox para ver a configuração de tempo de vida do perfil na sua conta.<br>Entre em contato com o Atendimento ao cliente se desejar estender o tempo de vida do perfil para 90 dias. |
| ttMeta | Suportado.<br>Este plug-in deve continuar a funcionar com a at.js. |