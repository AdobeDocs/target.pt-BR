---
keywords: audience;audience rules;create audience;creating audience
description: Você pode criar públicos-alvo personalizados e salvá-los na biblioteca do Target para usar nas atividades. Agora é possível copiar um público-alvo existente, que pode ser editado para criar um público-alvo semelhante.
title: Criar públicos no Target
feature: audiences
topic: Advanced,Standard,Classic
uuid: 496dbb9d-cb13-47ee-88bd-ba5920b2ca1c
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 99%

---


# Criar públicos no Target{#build-audiences-in-target}

Você pode criar públicos-alvo personalizados e salvá-los na biblioteca do Target para usar nas atividades. Agora é possível copiar um público-alvo existente, que pode ser editado para criar um público-alvo semelhante.

## Visão geral do público

Os públicos-alvo são definidos por regras que determinam quem está incluso ou foi excluído de uma atividade no [!DNL Target]. A definição de um público-alvo pode incluir várias regras e cada regra pode incluir vários parâmetros. Definições complexas de público-alvo usam os operadores booleanos E e OU para combinar regras e parâmetros para que você tenha controle detalhado sobre quais visitantes do site sejam contados como participantes da atividade.

Quando você combina regras e parâmetros com E, qualquer membro em potencial do público-alvo deve atender *todas* condições definidas para ser incluído como participante. Por exemplo, se você definir uma regra de sistema operacional e uma regra de navegador com E, somente visitantes usando o sistema operacional *e* o navegador definidos serão incluídos na atividade.

Quando você combina regras e parâmetros com OU, qualquer membro em potencial do público-alvo só precisa atender uma única condição definida para ser incluído como participante. Por exemplo, se você definir várias regras móveis conectadas por OU, visitantes que atendam *qualquer* dos critérios definidos são incluídos na atividade.

Você pode misturar operadores booleanos para criar regras complexas; no entanto, operadores no mesmo nível da regra devem ser compatíveis. A interface de usuário aplica o operador correto automaticamente.

Por exemplo, a seguinte regra busca visitantes que estão usando Chrome *ou* Firefox em um computador com Windows:

![Criar público-alvo](assets/audience_create.png)

>[!NOTE]
>
>Tenha cuidado para evitar criar regras que excluem todos membros em potencial do público-alvo. Por exemplo, não é possível alguém visitar sua página usando o Chrome *e* o Firefox simultaneamente.

## Criar um novo público

1. Clique em **[!UICONTROL Públicos-alvo]** na barra de menu no topo.

   ![](assets/audiences_list.png)

1. Na lista [!UICONTROL Públicos-alvo], clique em **[!UICONTROL + Criar públicos-alvo]**.

   Ou

   Para copiar um público-alvo existente, na lista de [!UICONTROL Públicos-alvo], passe com o mouse sobre o público-alvo desejado e clique no ícone **[!UICONTROL Copiar]**. Você pode editar o público-alvo para criar um público-alvo semelhante.

1. Digite um nome de público-alvo descritivo e exclusivo.
1. Clique em **[!UICONTROL + Adicionar regra]**.

   As regras possibilitam a limitação do seu público-alvo a um subconjunto dos visitantes do seu site.
1. Selecione um tipo de regra.

   Cada tipo de regra tem seus próprios parâmetros. Consulte [Categorias para públicos-alvo](../../c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) para mais informações sobre a configuração de cada tipo de regra de público-alvo.
1. Defina os parâmetros da regra.
1. Clique em **[!UICONTROL Salvar]**.

   Públicos-alvo criados recentemente aparecem na lista após alguns segundos de processamento. Se o público-alvo não aparecer imediatamente na lista, tente procurar pelo público-alvo ou atualizar a lista.

## Vídeo de treinamento: Criação de públicos-alvo ![Etiqueta de visão geral](/help/assets/overview.png)

Este vídeo inclui informações sobre a criação de públicos-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)