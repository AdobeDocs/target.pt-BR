---
description: 'O Target pode trocar notificações com outras soluções da Adobe Experience Cloud usando o Adobe Pulse. O Target envia dois tipos de notificações para todos os tipos de atividades: quando uma atividade se torna ativa e quando uma atividade é desativada.'
keywords: notificações
seo-description: 'O Target pode trocar notificações com outras soluções da Adobe Experience Cloud usando o Adobe Pulse. O Target envia dois tipos de notificações para todos os tipos de atividades: quando uma atividade se torna ativa e quando uma atividade é desativada.'
seo-title: Notificações de atividade
solution: Target
title: Notificações de atividade
topic: Padrão
uuid: eb9b8657-1c8e-4eba-8f6d-612944f917f3
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Notificações de atividade{#activity-notifications}

O Target pode trocar notificações com outras soluções da Adobe Experience Cloud usando o Adobe Pulse. O Target envia dois tipos de notificações para todos os tipos de atividades: quando uma atividade se torna ativa e quando uma atividade é desativada.

As notificações de [!DNL Target] podem ser vistas em todas as soluções por usuários que têm um [!DNL Experience Cloud]contexto de produto de [!DNL Target Standard/Premium].

For information about setting up Notifications, see [Enable notifications](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/getting-started-experience-cloud.html#concept_0105453AD71847B8BFCAF4A40915F157) in the [!DNL Adobe Experience Cloud] documentation.

Acesse as notificações de qualquer local no [!DNL Target], Exceto de dentro do fluxo de Trabalho de criação da atividade. Clique no ícone de sino no cabeçalho da página para exibir ou ocultar o dispositivo de notificações.

![Ícone Notificações](assets/notifications-shell.png)

O [!DNL Target] envia dois tipos de notificações para todos os tipos de atividade:

* Quando uma atividade se torna ativa e começa a entrega de oferta:

   Por exemplo:

   ![](assets/notif_app.png)

* Quando uma atividade é desativada e para a entrega de oferta:

   Por exemplo:

   ![](assets/notif-deact.png)

As notificações similares também aparecem quando uma atividade agendada alcança à data de início e quando ela termina ao alcançar a data final.

Todas as notificações do [!DNL Target] exibem o nome da atividade que foi aprovada ou desativada, e incluem as palavras "Adobe Target" para facilitar a identificação.

Se uma única atividade envia várias notificações do mesmo tipo, elas são combinadas em um único cartão com várias notificações exibidas nela. Por exemplo:

![](assets/notif-multi.png)

Clique no cartão de notificação para visualizar os detalhes de cada notificação.

Por exemplo, se você clicar no cartão mostrado acima, as três notificações são exibidas:

![](assets/notif-multi-open.png)

## Limitações {#section_B466EB20B2554CE7B1915374B39F4322}

* As notificações não indicam a você quem aprovou, desativou ou importou a atividade.
* As notificações de MVT aparecem como "Teste A/B" pois são sincronizadas como campanhas A/B no [!DNL Target Classic].

