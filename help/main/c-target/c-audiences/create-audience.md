---
keywords: público-alvo, regras de público-alvo, criar público-alvo, criação de público-alvo
description: Saiba como criar públicos-alvo personalizados e salvá-los na biblioteca  [!DNL Adobe Target] [!UICONTROL Audiences] para uso em atividades.
title: Como Construir Públicos?
feature: Audiences
exl-id: 59057461-d958-4d38-9725-53aacbe1f7eb
source-git-commit: 19d2b14f137fe4dbf95e9f9f9b84f80b93d1e281
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 48%

---

# Criar públicos em [!DNL Target]

Crie públicos-alvo personalizados e salve-os na biblioteca [!DNL Adobe Target] [!UICONTROL Audiences] para usar em suas atividades. Você também pode copiar um público-alvo existente que poderá editar para criar um público-alvo semelhante e combinar vários públicos-alvo.

## Visão geral do público

Os públicos-alvo são definidos por regras que determinam quem está incluso ou foi excluído de uma atividade no [!DNL Target]. A definição de um público-alvo pode incluir várias regras e cada regra pode incluir vários parâmetros. Definições complexas de público-alvo usam os operadores booleanos E e OU para combinar regras e parâmetros para que você tenha controle detalhado sobre quais visitantes do site sejam contados como participantes da atividade.

Quando você combina regras ou parâmetros com AND, qualquer membro em potencial do público-alvo deve atender a *todos* condições definidas para ser incluído como um participante. Por exemplo, se você definir uma regra de sistema operacional e uma regra de navegador com E, somente visitantes usando o sistema operacional *e* o navegador definidos serão incluídos na atividade.

Quando você combina regras e parâmetros com OU, qualquer membro em potencial do público-alvo só precisa atender uma única condição definida para ser incluído como participante. Por exemplo, se você definir várias regras móveis conectadas por OU, visitantes que atendam *qualquer* dos critérios definidos são incluídos na atividade.

Você pode misturar operadores booleanos para criar regras complexas; no entanto, operadores no mesmo nível da regra devem ser compatíveis. A interface de usuário aplica o operador correto automaticamente.

Por exemplo, a regra a seguir é direcionada a visitantes que usam [!DNL Chrome] *ou* [!DNL Firefox] em um computador [!DNL Windows]:

![Criar público-alvo](assets/audience_create.png)

>[!NOTE]
>
>Tenha cuidado para evitar criar regras que excluem todos membros em potencial do público-alvo. Por exemplo, não é possível alguém visitar sua página usando [!DNL Chrome] *e* [!DNL Firefox] simultaneamente.

## Criar um público-alvo

1. Clique em **[!UICONTROL Audiences]** na barra de menu superior.

   ![imagem de audiences_list](assets/audiences_list.png)

1. Na lista [!UICONTROL Audiences], clique em **[!UICONTROL Create Audience]**.

   Ou

   Para copiar um público-alvo existente, na lista [!UICONTROL Audiences], clique no ícone **[!UICONTROL More Actions]** ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmallListVert.svg) ) do público-alvo que você deseja copiar e clique em **[!UICONTROL Duplicate]**. Você pode editar o público-alvo para criar um público-alvo semelhante.

1. Digite um nome de público-alvo descritivo e exclusivo e uma descrição opcional.

   Os nomes de públicos-alvo não podem começar com os seguintes caracteres:

   `=  +  -  !  @`

   Os nomes de públicos-alvo não podem conter nenhuma das sequências de caracteres a seguir:

   `;=  ;+  ;-  ;@  ,=  ,+  ,-  ,@  ["  "]  ['  ]'`

1. Arraste e solte os atributos desejados da lista **[!UICONTROL Attributes]** à esquerda do painel do audience builder.

   ![Arrastar e soltar atributos](assets/drag-attribute.png)

   Cada tipo de regra tem seus próprios parâmetros. Consulte [Categorias para públicos-alvo](/help/main/c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) para obter mais informações sobre a configuração de cada tipo de regra de público-alvo.

1. Defina os parâmetros da regra.

   Por exemplo, o público-alvo a seguir é direcionado aos visitantes de Utah que usam o sistema operacional [!DNL Macintosh].

   ![Público de Utah/Macintosh](assets/adience-builder.png)

1. (Condicional) Continue a adicionar e definir os atributos desejados.

   Para criar outro contêiner, clique em **[!UICONTROL Add container]** ou simplesmente arraste outro atributo para o painel do Audience Builder. Em seguida, você pode ajustar o operador (AND ou OR) usando a lista suspensa.

1. Clique em **[!UICONTROL Done]**.

   Públicos-alvo criados recentemente aparecem na lista após alguns segundos de processamento. Se o público-alvo não aparecer imediatamente na lista, tente procurar pelo público-alvo ou atualizar a lista.

## Vídeo de treinamento: Criando públicos-alvo ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo inclui informações sobre a criação de públicos-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)
