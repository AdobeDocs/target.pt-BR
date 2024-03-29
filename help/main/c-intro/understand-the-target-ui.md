---
keywords: interface do usuário do target, interface do usuário, iu;anúncios;eventos;notificações
description: Familiarize-se com a interface do usuário e encontre links para informações mais detalhadas para ajudar você a aproveitar ao máximo o [!DNL Target].
title: Como faço para usar a interface do [!DNL Target] ?
feature: Overview
exl-id: ce4c72b2-b635-406b-9830-650816445a64
source-git-commit: 6bef27637c06f39ffc0e755f19e8a0870ec749e5
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 49%

---

# Compreensão da interface do [!DNL Target]

A interface do usuário é organizada em um formato lógico e amigável para ajudar você o a aproveitar ao máximo o [!DNL Adobe Target]. A breve visão geral a seguir ajuda você a se familiarizar com o [!DNL Target] e fornece links para informações mais detalhadas e instruções passo a passo.

O cabeçalho na parte superior do [!DNL Target] A interface do usuário contém guias e opções para ajudar você a navegar pelos diferentes recursos da solução. Você também pode trocar organizações e [!DNL Adobe Experience Cloud] soluções, obter ajuda e notificações, gerenciar o [!DNL Adobe] perfil e faça logout do [!DNL Target].

![Cabeçalho do Target](/help/main/c-intro/assets/target-header.png)

As guias no lado esquerdo permitem que você acesse os vários recursos do [!DNL Target], que será discutido posteriormente. Vamos começar discutindo as opções no lado direito antes de abordar as guias.

## Organizações

Uma *organização* é a entidade que permite a um administrador configurar grupos e usuários, além de controlar o logon único na [!DNL Adobe Experience Cloud]. A organização funciona como uma empresa para logon que abrange os produtos e as soluções da [!DNL Experience Cloud]. Frequentemente, a organização é o nome da empresa. Contudo, uma empresa pode ter muitas organizações.

Selecione a organização desejada na lista suspensa [!UICONTROL Organização] caso sua empresa tenha várias organizações:

![Lista suspensa de organização](/help/main/c-intro/assets/organizations.png)

## Aplicativos

O seletor de aplicativos permite acessar rapidamente as soluções da [!DNL Adobe Experience Cloud] às quais você tem acesso.

![Seletor de aplicativos](/help/main/c-intro/assets/apps.png)

## Ajuda

O ícone Ajuda permite acessar informações, vídeos, blogs e muito mais para ajudar você a usar o [!DNL Target] com mais eficiência. Você pode criar um tíquete de suporte, encontrar números de telefone de suporte, fazer perguntas pelo Twitter ou fornecer feedback sobre [!DNL Target] para nos informar como a [!DNL Target] A equipe está fazendo.

![Ajuda ](/help/main/c-intro/assets/help.png)

## Notificações e anúncios {#notifications-announcements}

Os painéis [!UICONTROL Notificações] e [!UICONTROL Anúncios] ajudam a manter você atualizado sobre tudo do [!DNL Adobe Target]. As notificações proativas ajudam a manter você informado sobre o status da [!DNL Adobe Experience Cloud] soluções e [!DNL Target] eventos. As notificações proativas alertam você sobre eventos de interrupção e manutenção.

Clique no ícone de sino no cabeçalho para exibir as notificações:

![Ícone de sino para notificações e anúncios](assets/bell-icon.png)

O painel contém guias para [!UICONTROL Notificação] e [!UICONTROL Anúncios].

![Notificações](assets/notifications.png)

As seções a seguir contêm informações sobre cada guia e como configurar notificações e anúncios:

### Notificações {#notifications}

[!DNL Target] as notificações de eventos incluem o seguinte:

* **Atividades**: notificações para todos os tipos de atividade quando uma atividade é aprovada ou desativada manualmente ou quando atinge sua data inicial ou final. A notificação inclui o nome da atividade com um link para a página de visão geral da atividade.

   As notificações são configuráveis e recebidas, por padrão, por administradores de produtos, editores e aprovadores no espaço de trabalho da atividade para [!DNL Target Premium] contas. Para [!DNL Target Standard] contas, as notificações são recebidas por todos os editores e aprovadores.

   As notificações são formatadas como os seguintes exemplos:

   * `Activity {target.activity.name} has been activated`

   * `Activity {target.activity.name} has been deactivated`

* **Scripts de perfil**: notificações quando um script de perfil é ativado ou desativado manualmente ou pelo [!DNL Target].

   As notificações podem ser configuradas e são recebidas, por padrão, por administradores de produtos e aprovadores para ambos [!DNL Target Premium] e [!DNL Target Standard] contas.

   As notificações são formatadas como os seguintes exemplos:

   * `Profile Script {target.profileScript.name} has been activated`
   * `Profile Script {target.profileScript.name} has been deactivated`

* **Feeds do**[!DNL Recommendations]: notificações quando um feed do Recommendations é ativado ou desativado manualmente ou pelo [!DNL Target]. Também são enviadas notificações quando uma [!DNL Recommendations] falha no feed.

   As notificações podem ser configuradas e são recebidas, por padrão, por administradores de produtos e aprovadores de [!DNL Target Premium] contas. [!DNL Recommendations] é um [!DNL Target Premium] e não está disponível no [!DNL Target Standard].

   As notificações são formatadas como os seguintes exemplos:

   * `Feed  {target.feed.name} has been activated`
   * `Feed {target.feed.name} has been deactivated`
   * `Feed {target.feed.name} has failed`
   * `Feed {target.feed.name} has failed to import from source`

Você pode marcar as notificações individuais como lidas, passando o mouse sobre a notificação desejada e clicando na marca de seleção. Você pode marcar todas as notificações como lidas ou exibir todas as notificações clicando em [!UICONTROL &quot;Marcar como lido&quot;] ou [!UICONTROL &quot;Exibir tudo&quot;] na parte inferior do painel.

Você também pode definir um lembrete para ser notificado novamente, passando o mouse sobre uma notificação e clicando no ícone &quot;[!UICONTROL Lembre-me]&quot; e selecionando quando você deseja ser notificado: 5 minutos, 15 minutos, uma hora ou amanhã.

### Anúncios

As notificações proativas alertam você sobre eventos de interrupção e manutenção.

Informações mais detalhadas podem ser encontradas na página [Status dao Adobe.](https://status.adobe.com/)

### Configurar notificações e anúncios

Para editar suas preferências de notificações:

1. Clique no ícone de engrenagem e clique em **[!UICONTROL Notificação]**.
1. Em **[!UICONTROL Target]**, clique em **[!UICONTROL Personalizar]**.
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
   >As &quot;Novas versões&quot; e &quot;Atualizações de conteúdo&quot; são as únicas categorias de notificação que se aplicam a [!DNL Target]. As outras categorias se aplicam a outras soluções de Adobe.


1. Selecione as categorias que você deseja que sejam consideradas de alta prioridade.
1. Selecione as notificações para as quais deseja que os alertas sejam exibidos no navegador.

   Esses alertas são exibidos no canto superior direito do navegador por alguns segundos. Você pode optar por ver categorias de alta prioridade, todas as categorias ou ocultar todos os pop-ups de notificação. Você também pode configurar se deseja que as notificações permaneçam visíveis até que você as ignore ou pode configurar a duração da notificação.

1. Selecione a frequência com que deseja receber emails de notificação:

   * Não enviar emails
   * Notificações instantâneas
   * Resumo diário
   * Resumo semanal

## Perfil

Clique no avatar do seu perfil para editar suas preferências da [!DNL Adobe Experience Cloud] ou para fazer logoff do [!DNL Target]. Você também pode acessar ou editar seu perfil da [!DNL Adobe].

![Avatar do perfil](/help/main/c-intro/assets/change-language.png)

Agora vamos discutir as guias no lado esquerdo do cabeçalho do [!DNL Target].

## Atividades

A lista de **[!UICONTROL Atividades]** é a exibição padrão ao abrir o [!DNL Target]. Você pode criar atividades nesta página e gerenciar atividades existentes.

![Lista de atividades](/help/main/c-intro/assets/activities-list.png)

Consulte [Atividades](/help/main/c-activities/activities.md) para obter informações detalhadas sobre os tipos de atividades disponíveis no [!DNL Target] e para saber mais sobre a interface do usuário da lista [!UICONTROL Atividade].

## Públicos-alvo

Clique em **[!UICONTROL Públicos-alvo]** para exibir a [!UICONTROL Públicos-alvo] uma lista onde é possível criar públicos e gerenciar públicos existentes.

![Lista de públicos-alvo](/help/main/c-intro/assets/audience-list.png)

Um público-alvo é um grupo de novatos em atividade semelhante que visualizam uma atividade direcionada. Um público-alvo é um grupo de pessoas com as mesmas características, como um novo visitante, um visitante recorrente ou visitantes recorrentes do meio-oeste. O recurso [!UICONTROL Público-alvo] permite direcionar conteúdo e experiências diferentes para públicos-alvo específicos para otimizar o marketing digital ao exibir as mensagens certas para as pessoas certas, na hora certa. Se um visitante for identificado como parte de um público-alvo, o [!DNL Target] determinará qual experiência deve ser exibida com base nos critérios estabelecidos quando a atividade foi criada.

Consulte [Criar públicos-alvo](/help/main/c-target/c-audiences/create-audience.md) para obter informações detalhadas sobre os tipos de público-alvo no [!DNL Target] e para saber mais sobre a interface do usuário da lista [!UICONTROL Público-alvo].

## Ofertas

Clique em **[!UICONTROL Ofertas]** para exibir a [!UICONTROL Ofertas] lista onde você pode criar experiências e ofertas e gerenciar experiências e ofertas existentes.

![Lista de ofertas](/help/main/c-intro/assets/offers.png)

Uma experiência pode ser uma oferta, imagem, texto, botão, vídeo, combinação desses vários elementos em uma página, uma página da Web inteira ou um conjunto de páginas que talvez forme um funil de compra ou alguma outra sequência lógica de páginas. Também pode ser a resposta de um assistente de voz, um script de atendimento ao cliente ou até mesmo um sabor personalizado de uma máquina bebidas. Teste ou personalize experiências nas atividades do [!DNL Target].

Consulte [Ofertas](/help/main/c-experiences/c-manage-content/manage-content.md) para obter informações detalhadas sobre os tipos de oferta no [!DNL Target] e para saber mais sobre a interface do usuário da lista [!UICONTROL Oferta].

## Recommendations

Clique na guia **[!UICONTROL Recommendations]** para acessar o [!DNL Target Recommendations].

>[!NOTE]
>
>As atividades do Recommendations estão disponíveis como parte da solução do [!DNL Target Premium]. Não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium]. Para obter mais informações, consulte o [Target Premium](/help/main/c-intro/intro.md#premium) em *Introdução ao Target*.

![Recommendations](/help/main/c-intro/assets/recommendations.png)

As atividades do [!UICONTROL Recommendations] exibem automaticamente produtos ou conteúdo que podem ser do interesse dos clientes com base em atividades do usuário anteriores. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.

Consulte [Recommendations](/help/main/c-recommendations/recommendations.md) para obter informações detalhadas sobre o [!UICONTROL Recommendations] em [!DNL Target] e para saber mais sobre a interface do usuário do [!UICONTROL Recommendations].

## Administração

Clique na guia **[!UICONTROL Administração]** para acessar as páginas de [!UICONTROL Administração].

![Páginas de administração](/help/main/c-intro/assets/administration.png)

As páginas de [!UICONTROL Administração] permitem administrar o [!DNL Target], incluindo configurações para o [!UICONTROL Visual Experience Composer] (VEC), relatórios, configuração do [!DNL Scene7], implementação, hosts, ambientes, tokens de resposta e usuários.

Consulte [Visão geral da administração do Target](/help/main/administrating-target/administrating-target.md) para obter informações detalhadas e saber mais sobre a interface do usuário.
