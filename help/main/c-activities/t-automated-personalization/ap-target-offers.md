---
keywords: personalização automatizada;ofertas;direcionamento;público-alvo;regras de direcionamento;direcionamento
description: Descubra como direcionar ofertas individuais para públicos específicos usando atividades de [!UICONTROL Automated Personalization] (AP).
title: Como Posso Direcionar Ofertas Do [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
TQID: 'https://experienceleague.adobe.com/AVqyD-Von-gzuVXC09N9qHY5hEe1QLQwSavCE0mp7Ok'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 8%
---
# Ofertas do [!UICONTROL Automated Personalization] do Target {#target-ap-offers}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como direcionar ofertas individuais para públicos-alvo específicos em uma atividade do **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

Em uma atividade de [!DNL Adobe Target] **[!UICONTROL Automated Personalization]** (AP), as regras de direcionamento permitem limitar uma oferta a públicos específicos, para que somente os visitantes que pertencem a esses públicos possam visualizá-la. Use as regras de direcionamento com moderação e somente quando for necessário para uma empresa, pois elas reduzem o número de ofertas que um visitante se qualifica para ver e podem diminuir a eficácia dos modelos de personalização do [!DNL Target].

Por exemplo, considere uma atividade com três ofertas. A oferta 1 tem uma regra de direcionamento que limita a exposição ao Público-alvo A. Dois visitantes veem essa atividade.

| | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Qualificação de público-alvo | Público-alvo A | Público-alvo B |
| Pontuação do modelo de personalização da oferta 1 [!DNL Target] | 90 | 90 |
| Pontuação do modelo de personalização da oferta 2 [!DNL Target] | 50 | 70 |
| Pontuação do modelo de personalização da oferta 3 [!DNL Target] | 80 | 60 |

O Visitante 1 é qualificado como parte do Público-alvo A, portanto, esse visitante vê a Oferta 1, que tem a pontuação mais alta. O Visitante 2 não faz parte do Público-alvo A, portanto, esse visitante vê a Oferta 2, mesmo que a pontuação mais alta seja para a Oferta 1.

## Configurar regras de direcionamento {#set-up-targeting-rules}

<a id="task_F207ED7A41B84FD39BB6FCBFABF4B23E"></a>

As regras de direcionamento de público controlam quais visitantes podem ver cada oferta, o que permite atender a uma necessidade empresarial específica, como reservar uma oferta para um segmento de cliente. Cada regra restringe as opções do modelo de personalização, portanto, aplique regras somente às ofertas que exigirem elas.

1. Crie ou edite uma [atividade do Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity) que contenha as ofertas que você deseja direcionar.

   Você pode configurar 50 locais e até 250 ofertas por local.

1. Depois de configurar as ofertas para a atividade no **[!UICONTROL Visual Experience Composer]**, clique no ícone **[!UICONTROL Gerenciar conteúdo]** ( ![ícone Gerenciar conteúdo](/help/main/assets/icons/Experience.svg) ). A caixa de diálogo **[!UICONTROL Gerenciar Conteúdo]** é exibida.

   ![Ícone Gerenciar Conteúdo](../assets/ap-offers-1.png)

1. Clique na guia **[!UICONTROL Ofertas]**.

1. Escolha as ofertas para direcionar e escolha os públicos-alvo que se qualificam para vê-las.

   * Para configurar o direcionamento para uma única oferta, clique no ícone Mais Informações ( ![Mais Informações](/help/main/assets/icons/MoreSmallList.svg) ) ao lado da oferta e, em seguida, clique em **[!UICONTROL Público-Alvo]** para exibir a caixa de diálogo **[!UICONTROL Adicionar Públicos-Alvo]**.
   * Para configurar o direcionamento para várias ofertas, marque as caixas de seleção para as ofertas e clique no link **[!UICONTROL Público-alvo]**, que é exibido na parte inferior da lista.

   ![Ícone Gerenciar Conteúdo](../assets/ap-offers-2.png)

1. Na caixa de diálogo **[!UICONTROL Adicionar Públicos-alvo]**, selecione os públicos-alvo para as ofertas e clique em **[!UICONTROL Atribuir Público-alvo]** para retornar à caixa de diálogo **[!UICONTROL Gerenciar Conteúdo]**.

   >[!NOTE]
   >
   >Em vez de criar um novo público-alvo, você pode combinar vários públicos-alvo com os existentes para criar públicos-alvo combinados sob demanda. Para obter mais informações, consulte [Combinar vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Clique em **[!UICONTROL Concluído]**.

As regras de direcionamento agora se aplicam às ofertas selecionadas, para que somente os visitantes que pertencem aos públicos atribuídos possam vê-las.
