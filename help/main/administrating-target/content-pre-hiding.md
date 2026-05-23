---
keywords: cintilação,pré-ocultação,pré-ocultação,personalização,implementação,anti-cintilação,VEC,visual experience composer
description: Saiba como a pré-ocultação de conteúdo reduz a cintilação ao ocultar apenas as regiões que a personalização ativa do Adobe Target mudará, usando uma configuração no nível da conta, uma biblioteca de páginas leve e controles por atividade.
title: Pré-ocultação de conteúdo para experiências personalizadas
feature: Administration & Configuration
role: Admin
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#beta newtab=true" tooltip="O que são recursos beta no  [!DNL Adobe Target]."
hide: true
source-git-commit: 77741253fdfb007d0eda0c57fe293df2f9c638a2
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 3%

---

# Pré-ocultação de conteúdo para experiências personalizadas

>[!AVAILABILITY]
>
>A pré-ocultação de conteúdo personalizado está disponível como um recurso **beta**.

Quando um visitante carrega uma página, o conteúdo padrão pode aparecer brevemente e ser substituído por conteúdo personalizado de [!DNL Adobe Target]. Essa opção visível geralmente é chamada de **cintilação**, e é um problema comum de experiência para programas de personalização.

Com a pré-ocultação de conteúdo, é possível gerenciar a cintilação ocultando apenas as partes da página que suas atividades personalizam durante o carregamento da página, para que seus clientes vejam menos cintilação e menos tempo de tela vazio.

Veja como funciona a pré-ocultação de conteúdo, desde o padrão da conta até a implementação da página e as opções por atividade.

1. Ative a pré-ocultação de conteúdo para sua conta para definir o padrão global. Ela está desativada por padrão. [Saiba mais](#content-pre-hiding-enable-account)

1. Adicione a biblioteca de pré-ocultação de conteúdo à `<head>` de todas as páginas em que você executa atividades de personalização.

1. [!DNL Target] cria um conjunto de regras a partir de atividades [!UICONTROL Visual Experience Composer] e [!UICONTROL Enhanced Experience Composer] ativas. O conjunto de regras lista os seletores e regiões que o delivery pode alterar.

   Observe que não há suporte para [!UICONTROL Form-Based Composer] atividades.

1. A biblioteca busca esse conjunto de regras da CDN do Adobe e pré-oculta os elementos correspondentes apenas enquanto o conteúdo personalizado ainda está carregando.

1. Em **[!UICONTROL Goals & Settings]**, você pode desabilitar **[!UICONTROL Content pre-hiding]** para atividades individuais, mas somente se estiver habilitado no nível da conta. [Saiba mais](#content-pre-hiding-activity)

## Ativar a pré-ocultação de conteúdo para sua instância {#content-pre-hiding-enable-account}

>[!IMPORTANT]
>
>Para habilitar a pré-ocultação de conteúdo para a instância, você deve ser um **Administrador**.

A pré-ocultação de conteúdo fica desativada para sua instância até que você a ative. Use o **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** para ativar o recurso, definir os padrões e acessar o download para a sua equipe de implementação.

1. Em [!DNL Target], clique em **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

1. No menu **[!UICONTROL Content pre-hiding]**, habilite a opção de pré-ocultação de Conteúdo.

   ![](assets/content-pre-hiding-1.png)

1. Se necessário, atualize o **[!UICONTROL Pre-hiding timeout]** em segundos.

1. Clique em **[!UICONTROL Save]**. Isso aplicará as configurações de gerenciamento de cintilação à sua instância.

1. Depois de habilitado, clique em **[!UICONTROL Download]** e adicione o arquivo à página `<head>` para que ele seja carregado antes de [!DNL at.js] ou [!DNL Web SDK]. Para obter instruções completas de implementação, consulte [Pré-ocultação de conteúdo do SDK](https://experienceleague.adobe.com/pt-br/docs/target-dev/developer/client-side/prehide-sdk).

   ![](assets/content-pre-hiding-2.png)

Sua instância agora usa as configurações de pré-ocultação e tempo limite do conteúdo salvo como padrão para atividades que aceitam.

## Ativar a pré-ocultação de conteúdo para sua atividade {#content-pre-hiding-activity}

Com a pré-ocultação habilitada para sua instância, escolha se cada atividade a usará no **[!UICONTROL Goals & Settings]**. As atividades para as quais você habilita a pré-ocultação são incluídas no comportamento direcionado quando estão ativas.

[!DNL Target] então cria um conjunto de regras leve a partir de atividades ativas criadas no [!UICONTROL Visual Experience Composer] (VEC) e no [!UICONTROL Form-Based Composer], descrevendo os seletores e as áreas que a entrega pode alterar.

Ao criar ou editar uma atividade:

1. Acesse a atividade que deseja ativar a opção de pré-ocultação.

1. Acesse o menu suspenso **[!UICONTROL Edit activity]** e selecione **[!UICONTROL Edit Goals & Settings]**.

   ![](assets/content-pre-hiding-3.png)

1. No menu **[!UICONTROL Content pre-hiding]**, ative a opção **[!UICONTROL Enable content pre-hiding]** para ativar ou desativar a pré-ocultação dessa atividade.

   ![](assets/content-pre-hiding-4.png)

1. Depois de concluído, clique em **[!UICONTROL Save & Close]**.

Depois de salvar e à medida que as atividades entram em vigor ou são desativadas, o conjunto de regras é atualizado para que a pré-ocultação permaneça alinhada com o que está realmente entregando, sem edições no código da página para cada inicialização.

No lado do visitante, a biblioteca recupera esse conjunto de regras da CDN da Adobe em cada carregamento de página e pré-oculta os elementos correspondentes somente quando necessário, até que o conteúdo personalizado esteja pronto.
