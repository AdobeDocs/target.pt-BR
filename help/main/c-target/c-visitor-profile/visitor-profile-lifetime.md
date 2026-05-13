---
keywords: Visão geral e referência
description: Saiba mais sobre quando um perfil de visitante expira em [!DNL Adobe Target].
title: Qual é a duração do perfil do visitante e posso estendê-lo?
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
TQID: https://experienceleague.adobe.com/yMfacKgQthOmpfhFiuO-jGGPWZh5VrliOSi0TQ-uis0
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 147
ht-degree: 62%

---

# Duração do perfil do visitante

Por padrão, um perfil de visitante no [!DNL Adobe Target] expira após 14 dias de inatividade para esse visitante. A duração desse perfil pode ser estendida.

[Entre em contato com o Atendimento ao cliente ou com o consultor da Adobe](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para estender o tempo de vida do perfil sem custo adicional. A duração pode ser definida para até 90 dias.

Você não precisa baixar um novo arquivo [!DNL Platform Web SDK] ou arquivo at.js se o seu perfil for estendido além do padrão.

A data de validade não é redefinida em perfis existentes. Se um visitante anterior não voltar por 15 dias, o perfil irá expirar. Se um visitante anterior voltar antes de o perfil original de duas semanas expirar, o perfil será redefinido para a duração estendida. Todos os perfis do novo visitante são definidos para a duração de perfil estendida.
