---
keywords: interface do usuário de destino;interface do usuário;ui;anúncios;eventos;notificações
description: Familiarize-se com a interface do usuário e encontre links para informações mais detalhadas para aproveitar ao máximo o  [!DNL Target].
title: Como faço para usar a interface do [!DNL Target] ?
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: 84f2e590ee9fb984a3b272240b0373072057ca32
workflow-type: tm+mt
source-wordcount: '1387'
ht-degree: 26%

---

# Compreensão da interface do [!DNL Target]

A interface do usuário é organizada em um formato lógico e amigável para ajudar você o a aproveitar ao máximo o [!DNL Adobe Target]. A breve visão geral a seguir ajuda você a se familiarizar com o [!DNL Target] e fornece links para informações mais detalhadas e instruções passo a passo.

## Cabeçalho da interface do usuário [!DNL Target]

O cabeçalho na parte superior da interface do usuário do [!DNL Target] contém guias e opções para ajudar você a navegar pelos diferentes recursos da solução. Você também pode alternar organizações e soluções do [!DNL Adobe Experience Cloud], fornecer feedback se fizer parte de um programa do Beta, acessar o Assistente de IA, obter ajuda e notificações, gerenciar o perfil do [!DNL Adobe] e sair do [!DNL Target].

![Cabeçalho do Target](/help/main/c-intro/assets/target-header.png)

As guias no lado esquerdo permitem que você acesse os vários recursos do [!DNL Target], que serão discutidos posteriormente. Vamos começar discutindo as opções no lado direito antes de discutir as guias.

### [!UICONTROL Organization]

Uma *organização* é a entidade que permite a um administrador configurar grupos e usuários, além de controlar o logon único na [!DNL Adobe Experience Cloud]. A organização funciona como uma empresa para logon que abrange os produtos e as soluções da [!DNL Experience Cloud]. Frequentemente, a organização é o nome da empresa. Contudo, uma empresa pode ter muitas organizações.

Selecione a organização desejada na lista suspensa [!UICONTROL Organization] se sua empresa tiver várias organizações:

![Lista suspensa de organização](/help/main/c-intro/assets/organizations.png)

### [!UICONTROL Beta Feedback]

(Condicional) Se você fizer parte de um programa oficial do Beta [!DNL Target], poderá ver o ícone [!UICONTROL Beta Feedback].

![Ícone do Beta Feedback](/help/main/c-intro/assets/beta-feedback.png)

Forneça uma descrição para seus comentários, inclua arquivos ou capturas de tela aplicáveis e detalhes adicionais, conforme necessário, e clique em **[!UICONTROL Submit]**.

### [!DNL AI Assistant]

(Condicional) Se você recebeu direitos para usar o [!DNL AI Assistant] pela sua organização, clique no ícone [!DNL AI Assistant].

Para obter mais informações, consulte [Visão geral do Assistente do Adobe Experience Platform AI](/help/main/c-intro/ai-assistant.md).

### Ajuda

Clicar no ícone [!UICONTROL Help] ( ![ícone da Ajuda](/help/main/assets/icons/HelpOutline.svg) ) permite acessar informações, vídeos, blogs e muito mais para ajudá-lo a usar o [!DNL Target] com mais eficiência. Você pode criar um tíquete de suporte, encontrar números de telefone de suporte, fazer perguntas pelo Twitter ou fornecer feedback sobre o [!DNL Target] para deixar seus comentários.[!DNL Target]

![Ajuda ](/help/main/c-intro/assets/help.png)

### Solicitações, notificações e anúncios {#notifications-announcements}

Os painéis [!UICONTROL Requests], [!UICONTROL Notifications] e [!UICONTROL Announcements] ajudam a manter você atualizado sobre tudo [!DNL Adobe Target]. As notificações proativas ajudam a manter você informado sobre o status de [!DNL Adobe Experience Cloud] soluções e [!DNL Target] eventos. As notificações proativas alertam você sobre eventos de interrupção e manutenção.

Clique no ícone [!UICONTROL Notifications] ( ![Ícone Notificações](/help/main/assets/icons/Bell.svg) ) no cabeçalho para exibir as notificações:

O painel contém guias para [!UICONTROL Requests], [!UICONTROL Notifications] e [!UICONTROL Announcements].

![Notificações](assets/notifications.png)

As seções a seguir contêm informações sobre cada guia e como configurar notificações e anúncios:

#### Notificações {#notifications}

[!DNL Target] notificações de eventos incluem:

* **Atividades**: notificações para todos os tipos de atividade quando uma atividade é aprovada ou desativada manualmente ou quando atinge sua data inicial ou final. A notificação inclui o nome da atividade com um link para a página de visão geral da atividade.

  As notificações podem ser configuradas e são recebidas, por padrão, por administradores de produtos, editores e aprovadores no espaço de trabalho da atividade para contas do [!DNL Target Premium]. Para contas do [!DNL Target Standard], as notificações são recebidas por todos os editores e aprovadores.

  As notificações são formatadas como os seguintes exemplos:

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **Scripts de perfil**: notificações quando um script de perfil é ativado ou desativado manualmente ou por [!DNL Target].

  As notificações podem ser configuradas e são recebidas, por padrão, por administradores de produtos e aprovadores de contas do [!DNL Target Premium] e do [!DNL Target Standard].

  As notificações são formatadas como os seguintes exemplos:

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Feeds do Recommendations**: notificações quando um feed do [!DNL Recommendations] é ativado ou desativado manualmente ou por [!DNL Target]. Notificações também são enviadas quando um feed [!DNL Recommendations] falha.

  As notificações podem ser configuradas e são recebidas, por padrão, por administradores de produtos e aprovadores de contas do [!DNL Target Premium]. [!DNL Recommendations] é um recurso [!DNL Target Premium] e não está disponível em [!DNL Target Standard].

  As notificações são formatadas como os seguintes exemplos:

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed`
   * `Feed {target.feed.name} has failed to import from source`

Você pode marcar as notificações individuais como lidas, passando o mouse sobre a notificação desejada e clicando na marca de seleção. Você pode marcar todas as notificações como lidas ou exibir todas as notificações clicando em [!UICONTROL "Mark as Read"] ou [!UICONTROL "View All"] na parte inferior do painel.

Você também pode definir um lembrete para ser notificado novamente, passando o mouse sobre uma notificação, clicando no ícone &quot;[!UICONTROL Remind me]&quot; e selecionando quando deseja ser notificado: 5 minutos, 15 minutos, uma hora ou amanhã.

#### Anúncios

As notificações proativas alertam você sobre eventos de interrupção e manutenção.

Informações mais detalhadas podem ser encontradas na página [Status do Adobe](https://status.adobe.com/pt).

### Configurar notificações e anúncios

Para editar suas preferências de notificações:

1. Clique no ícone de engrenagem e, em seguida, clique em **[!UICONTROL Notifications]**.
1. Em **[!UICONTROL Target]**, clique em **[!UICONTROL Customize]**.
1. Selecione ou desmarque as categorias para as quais deseja receber notificações:

   * Solicitações: quando alguém envia uma solicitação para aprovar um objeto ou conceder acesso a um objeto. Não é possível cancelar a inscrição nesta categoria.
   * Atribuído a mim: quando alguém atribui um objeto a você.
   * Menções: quando alguém menciona você em um comentário.
   * Novas versões: quando uma nova versão está disponível para um produto ou serviço ao qual você tem acesso.
   * Compartilhado comigo: quando alguém compartilha um objeto com você.
   * Atualizações no conteúdo: quando alguém edita, exclui ou comenta em um objeto que você criou ou seguiu.
   * Outros:

   >[!NOTE]
   >
   >&quot;Novas versões&quot; e &quot;Atualizações de conteúdo&quot; são as únicas categorias de notificação que se aplicam a [!DNL Target]. As outras categorias se aplicam a outras soluções da Adobe.

1. Selecione as categorias que você deseja que sejam consideradas de alta prioridade.
1. Selecione as notificações para as quais deseja que os alertas sejam exibidos no navegador.

   Esses alertas são exibidos no canto superior direito do navegador por alguns segundos. Você pode optar por ver categorias de alta prioridade, todas as categorias ou ocultar todos os pop-ups de notificação. Você também pode configurar se deseja que as notificações permaneçam visíveis até que você as ignore ou pode configurar a duração da notificação.

1. Selecione a frequência com que deseja receber emails de notificação:

   * Não enviar emails
   * Notificações instantâneas
   * Resumo diário
   * Resumo semanal

### Seletor de aplicativos

O seletor de aplicativos permite acessar rapidamente as soluções da [!DNL Adobe Experience Cloud] às quais você tem acesso.

![Seletor de aplicativos](/help/main/c-intro/assets/apps.png)

### Perfil

Clique no avatar do seu perfil para editar suas preferências da [!DNL Adobe Experience Cloud] ou para fazer logoff do [!DNL Target]. Você também pode acessar ou editar seu perfil da [!DNL Adobe].

![Avatar do perfil](/help/main/c-intro/assets/change-language.png)

Agora vamos discutir as guias no lado esquerdo do cabeçalho do [!DNL Target].

## Atividades

A lista **[!UICONTROL Activities]** é o modo de exibição padrão quando você abre [!DNL Target]. Você pode criar atividades nesta página e gerenciar atividades existentes.

![Lista de atividades](/help/main/c-intro/assets/activities-list.png)

Consulte [Atividades](/help/main/c-activities/activities.md) para obter informações detalhadas sobre os tipos de atividades disponíveis em [!DNL Target] e para saber mais sobre a interface do usuário da lista [!UICONTROL Activity].

## Públicos-alvo

Clique na guia **[!UICONTROL Audiences]** para exibir a lista [!UICONTROL Audiences], onde é possível criar públicos e gerenciar públicos existentes.

![Lista de públicos-alvo](/help/main/c-intro/assets/audience-list.png)

Um público-alvo é um grupo de novatos em atividade semelhante que visualizam uma atividade direcionada. Um público-alvo é um grupo de pessoas com as mesmas características, como um novo visitante, um visitante recorrente ou visitantes recorrentes do meio-oeste. O recurso [!UICONTROL Audience] permite direcionar conteúdo e experiências diferentes para públicos-alvo específicos para otimizar o marketing digital ao exibir as mensagens certas para as pessoas certas, na hora certa. Se um visitante for identificado como parte de um público-alvo, o [!DNL Target] determinará qual experiência deve ser exibida com base nos critérios estabelecidos quando a atividade foi criada.

Consulte [Criar públicos-alvo](/help/main/c-target/c-audiences/create-audience.md) para obter informações detalhadas sobre os tipos de público-alvo em [!DNL Target] e saber mais sobre a interface do usuário da lista [!UICONTROL Audience].

## Ofertas

Clique na guia **[!UICONTROL Offers]** para exibir a lista [!UICONTROL Offers], onde é possível criar experiências e ofertas, além de gerenciar experiências e ofertas existentes.

![Lista de ofertas](/help/main/c-intro/assets/offers.png)

Uma experiência pode ser uma oferta, imagem, texto, botão, vídeo, combinação desses vários elementos em uma página, uma página da Web inteira ou um conjunto de páginas que talvez forme um funil de compra ou alguma outra sequência lógica de páginas. Também pode ser a resposta de um assistente de voz, um script de atendimento ao cliente ou até mesmo um sabor personalizado de uma máquina bebidas. Teste ou personalize experiências nas atividades do [!DNL Target].

Consulte [Ofertas](/help/main/c-experiences/c-manage-content/manage-content.md) para obter informações detalhadas sobre os tipos de ofertas em [!DNL Target] e para saber mais sobre a interface do usuário da lista [!UICONTROL Offer].

## Recommendations

Clique na guia **[!UICONTROL Recommendations]** para acessar [!DNL Target Recommendations].

>[!NOTE]
>
>As atividades do Recommendations estão disponíveis como parte da solução do [!DNL Target Premium]. Não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium]. Para obter mais informações, consulte o [Target Premium](/help/main/c-intro/intro.md#premium) em *Introdução ao Target*.

![Recommendations](/help/main/c-intro/assets/recommendations.png)

As atividades do [!UICONTROL Recommendations] exibem automaticamente produtos ou conteúdo que podem ser do interesse dos clientes com base em atividades do usuário anteriores. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.

Consulte [Recommendations](/help/main/c-recommendations/recommendations.md) para obter informações detalhadas sobre [!UICONTROL Recommendations] em [!DNL Target] e saber mais sobre a interface do usuário [!UICONTROL Recommendations].

## Administração

Clique na guia **[!UICONTROL Administration]** para acessar as páginas [!UICONTROL Administration].

![Páginas de administração](/help/main/c-intro/assets/administration.png)

As páginas [!UICONTROL Administration] permitem administrar o [!DNL Target], incluindo as definições de configuração do [!UICONTROL Visual Experience Composer] (VEC), relatórios, configuração do [!DNL Scene7], implementação, hosts, ambientes, tokens de resposta e usuários.

Consulte [Visão geral da administração do Target](/help/main/administrating-target/administrating-target.md) para obter informações detalhadas e saber mais sobre a interface do usuário.
