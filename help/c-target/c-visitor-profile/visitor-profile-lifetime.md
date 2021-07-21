---
keywords: Visão geral e referência
description: Saiba mais sobre quando um perfil de visitante expira em [!DNL Adobe Target].
title: Qual é a duração do perfil do visitante e posso estendê-lo?
feature: Públicos-alvo
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
source-git-commit: c19163020cdcb41a17ea6b65b5b500fadc9c7512
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 45%

---

# Duração do perfil do visitante

Por padrão, um perfil de visitante em [!DNL Adobe Target] expira após 14 dias de inatividade para esse visitante. A duração desse perfil pode ser estendida.

[Entre em contato com o Atendimento ao cliente ou com o consultor da Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para estender o tempo de vida do perfil sem custo adicional. A duração pode ser definida para até 90 dias.

Não é necessário baixar um novo arquivo [!DNL Platform Web SDK] ou at.js se o perfil for estendido além do padrão.

A data de validade não é redefinida em perfis existentes. Se um visitante anterior não voltar por 15 dias, o perfil irá expirar. Se um visitante anterior voltar antes de o perfil original de duas semanas expirar, o perfil será redefinido para a duração estendida. Todos os perfis do novo visitante são definidos para a duração de perfil estendida.

No cenário a seguir, suponha que um ou ambos os sites estejam implementados com o [!DNL Platform Web SDK]. Se ambos os sites estiverem em um código de cliente e um visitante acessar ambos os sites, o perfil será definido para a duração dos perfis no último site visitado. Por exemplo, suponha que o Site 1 tenha uma duração de perfil de 84 dias. O Site 2 tem duração de 14 dias. Se o visitante acessar o Site 1 e, em seguida, o Site 2, o perfil do visitante expirará em 14 dias de inatividade. Se o visitante acessar o Site 1 após acessar o Site 2, o perfil expirará em 84 dias de inatividade.
