---
keywords: público-alvo, regras de público-alvo, criar público-alvo, criação de público-alvo
description: Saiba como criar públicos-alvo personalizados e salvá-los na [!DNL Adobe Target] [!UICONTROL Públicos-alvo] biblioteca para uso em atividades.
title: Como Construir Públicos?
feature: Audiences
exl-id: 59057461-d958-4d38-9725-53aacbe1f7eb
source-git-commit: a185edee86f6d07b488cf5dd3fe7e5dc3f4e87b3
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 56%

---

# Criar públicos-alvo no [!DNL Target]

Você pode criar públicos-alvo personalizados e salvá-los na [!DNL Adobe Target] [!UICONTROL Públicos-alvo] para uso em suas atividades. Você também pode copiar um público-alvo existente que poderá editar para criar um público-alvo semelhante e combinar vários públicos-alvo.

## Visão geral do público

Os públicos-alvo são definidos por regras que determinam quem está incluso ou foi excluído de uma atividade no [!DNL Target]. A definição de um público-alvo pode incluir várias regras e cada regra pode incluir vários parâmetros. Definições complexas de público-alvo usam os operadores booleanos E e OU para combinar regras e parâmetros para que você tenha controle detalhado sobre quais visitantes do site sejam contados como participantes da atividade.

Quando você combina regras ou parâmetros com AND, qualquer membro em potencial do público-alvo deve atender *all* condições definidas para serem incluídas como um participante. Por exemplo, se você definir uma regra de sistema operacional e uma regra de navegador com E, somente visitantes usando o sistema operacional *e* o navegador definidos serão incluídos na atividade.

Quando você combina regras e parâmetros com OU, qualquer membro em potencial do público-alvo só precisa atender uma única condição definida para ser incluído como participante. Por exemplo, se você definir várias regras móveis conectadas por OU, visitantes que atendam *qualquer* dos critérios definidos são incluídos na atividade.

Você pode misturar operadores booleanos para criar regras complexas; no entanto, operadores no mesmo nível da regra devem ser compatíveis. A interface de usuário aplica o operador correto automaticamente.

Por exemplo, a seguinte regra busca visitantes que estão usando Chrome *ou* Firefox em um computador com Windows:

![Criar público-alvo](assets/audience_create.png)

>[!NOTE]
>
>Tenha cuidado para evitar criar regras que excluem todos membros em potencial do público-alvo. Por exemplo, não é possível alguém visitar sua página usando o Chrome *e* o Firefox simultaneamente.

## Criar um público-alvo

1. Clique em **[!UICONTROL Públicos-alvo]** na barra de menu no topo.

   ![imagem audiences_list](assets/audiences_list.png)

1. No [!UICONTROL Públicos-alvo] clique em **[!UICONTROL Criar público-alvo]**.

   Ou

   Para copiar um público-alvo existente, da variável [!UICONTROL Públicos-alvo] clique na guia **[!UICONTROL Mais ações]** (o ícone de reticências) e clique em **[!UICONTROL Duplicar]**. Você pode editar o público-alvo para criar um público-alvo semelhante.

1. Digite um nome de público-alvo descritivo e exclusivo e uma descrição opcional.

   Os nomes de públicos-alvo não podem começar com os seguintes caracteres:

   `=  +  -  !  @`

   Os nomes de públicos-alvo não podem conter nenhuma das sequências de caracteres a seguir:

   `;=  ;+  ;-  ;@  ,=  ,+  ,-  ,@  ["  "]  ['  ]'`

1. Arraste e solte os atributos desejados da **[!UICONTROL Atributos]** à direita do painel do audience builder.

   ![Arrastar e soltar atributos](assets/drag-attribute.png)

   Cada tipo de regra tem seus próprios parâmetros. Consulte [Categorias para públicos](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) para obter mais informações sobre como configurar cada tipo de regra de público-alvo.

1. Defina os parâmetros da regra.

   Por exemplo, o público-alvo a seguir é direcionado a visitantes de Utah que usam o sistema operacional Macintosh.

   ![Público de Utah/Macintosh](assets/adience-builder.png)

1. (Condicional) Continue a adicionar e definir os atributos desejados.

   Para criar outro container, clique em **[!UICONTROL Adicionar contêiner]** ou simplesmente arraste outro atributo para o painel do Audience Builder. Em seguida, você pode ajustar o operador (AND ou OR) usando a lista suspensa.

1. Clique em **[!UICONTROL Concluído]**.

   Públicos-alvo criados recentemente aparecem na lista após alguns segundos de processamento. Se o público-alvo não aparecer imediatamente na lista, tente procurar pelo público-alvo ou atualizar a lista.

## Vídeo de treinamento: Criação de públicos-alvo ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo inclui informações sobre a criação de públicos-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)
