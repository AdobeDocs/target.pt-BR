---
keywords: Visão geral e referência
description: Saiba mais sobre quando um perfil de visitante expira em [!DNL Adobe Target].
title: Qual é a duração do perfil do visitante e posso estendê-lo?
feature: Audiences
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
source-git-commit: 2fce52a95f127372cc32c593b86ccf5500cbeb2c
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 62%

---

# Duração do perfil do visitante

Por padrão, um perfil de visitante em [!DNL Adobe Target] expira após 14 dias de inatividade para esse visitante. A duração desse perfil pode ser estendida.

[Entre em contato com o Atendimento ao cliente ou com o consultor da Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para estender o tempo de vida do perfil sem custo adicional. A duração pode ser definida para até 90 dias.

Não é necessário baixar um novo [!DNL Platform Web SDK] arquivo ou at.js se o seu perfil for estendido além do padrão.

A data de validade não é redefinida em perfis existentes. Se um visitante anterior não voltar por 15 dias, o perfil irá expirar. Se um visitante anterior voltar antes de o perfil original de duas semanas expirar, o perfil será redefinido para a duração estendida. Todos os perfis do novo visitante são definidos para a duração de perfil estendida.
