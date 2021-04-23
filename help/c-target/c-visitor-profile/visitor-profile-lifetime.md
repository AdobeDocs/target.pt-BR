---
keywords: Visão geral e referência
description: Saiba mais sobre quando um perfil de visitante expira (por padrão, 14 dias) no Adobe Target. A duração do perfil pode ser estendida ao entrar em contato com o Atendimento ao cliente do Adobe.
title: Qual é a duração do perfil do visitante e posso estendê-lo?
feature: Públicos-alvo
exl-id: 70cb5e3b-ed6d-450d-8c6e-f1bfe8d26e54
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 73%

---

# Duração do perfil do visitante

Por padrão, um perfil de visitante expira após 14 dias de inatividade para esse visitante. A duração desse perfil pode ser estendida.

[Entre em contato com o Atendimento ao cliente ou com o consultor da Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para estender o tempo de vida do perfil sem custo adicional. A duração pode ser definida para até 90 dias.

A biblioteca de JavaScript do [!DNL Target] que você está usando ([!DNL at.js] ou [!DNL mbox.js]) determina se você precisa ou não baixar um novo arquivo:

| Biblioteca do Target | Detalhes |
|--- |--- |
| at.js | Você não precisa baixar um novo arquivo da at.js se o seu perfil for estendido além do padrão. |
| mbox.js | Se o seu perfil for estendido além do padrão de 14 dias, baixe um novo arquivo da mbox.js depois que o consultor ou o Atendimento ao cliente alterar suas configurações. A extensão de cookie para suportar a duração alterada do perfil está incluída no arquivo mbox.js atualizado. Após começar a usar a nova biblioteca, a duração do perfil de seus visitantes será atualizada. |

A data de validade não é redefinida em perfis existentes. Se um visitante anterior não voltar por 15 dias, o perfil irá expirar. Se um visitante anterior voltar antes de o perfil original de duas semanas expirar, o perfil será redefinido para a duração estendida. Todos os perfis do novo visitante são definidos para a duração de perfil estendida.

No cenário a seguir, suponha que um ou ambos os sites estejam implementados com a mbox.js, o que requer uma atualização de código após a atualização do perfil. Se ambos os sites estiverem em um código de cliente e um visitante acessar ambos os sites, o perfil será definido para a duração dos perfis no último site visitado. Por exemplo, se o Site 1 tiver uma duração de perfil de 84 dias e o Site 2 tiver uma duração de 14 dias, e o visitante acessar o Site 1 e, em seguida, o Site 2, o perfil do visitante expirará em 14 dias de inatividade. Se o visitante acessar o Site 1 após acessar o Site 2, o perfil expirará em 84 dias de inatividade.
