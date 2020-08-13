---
keywords: Overview and Reference
description: Por padrão, os perfis de visitantes são armazenados por 14 dias. A duração desse perfil pode ser estendida.
title: Duração do perfil do visitante
feature: visitor profiles
subtopic: Getting Started
topic: Standard
uuid: 01ccda60-7e28-4d26-8d5d-1c0a022bbef0
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 100%

---


# Duração do perfil do visitante{#visitor-profile-lifetime}

Por padrão, um perfil de visitante expira após 14 dias de inatividade para esse visitante. A duração desse perfil pode ser estendida.

[Entre em contato com o Atendimento ao cliente ou com o consultor da Adobe](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para estender o tempo de vida do perfil sem custo adicional. A duração pode ser definida para até 90 dias.

A biblioteca de JavaScript do [!DNL Target] que você está usando ([!DNL at.js] ou [!DNL mbox.js]) determina se você precisa ou não baixar um novo arquivo:

| Biblioteca do Target | Detalhes |
|--- |--- |
| at.js | Você não precisa baixar um novo arquivo da at.js se o seu perfil for estendido além do padrão. |
| mbox.js | Se o seu perfil for estendido além do padrão de 14 dias, baixe um novo arquivo da mbox.js depois que o consultor ou o Atendimento ao cliente alterar suas configurações. A extensão de cookie para suportar a duração alterada do perfil está incluída no arquivo mbox.js atualizado. Após começar a usar a nova biblioteca, a duração do perfil de seus visitantes será atualizada. |

A data de validade não é redefinida em perfis existentes. Se um visitante anterior não voltar por 15 dias, o perfil irá expirar. Se um visitante anterior voltar antes de o perfil original de duas semanas expirar, o perfil será redefinido para a duração estendida. Todos os perfis do novo visitante são definidos para a duração de perfil estendida.

Se você tiver dois sites em um código de cliente e um visitante acessar ambos os sites, o perfil será definido para a duração dos perfis no último site visitado. Por exemplo, se o Site 1 tiver uma duração de perfil de 84 dias e o Site 2 tiver uma duração de 14 dias, e o visitante acessar o Site 1 e, em seguida, o Site 2, o perfil do visitante expirará em 14 dias de inatividade. Se o visitante acessar o Site 1 após acessar o Site 2, o perfil expirará em 84 dias de inatividade.
