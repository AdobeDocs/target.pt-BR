---
keywords: personalização automatizada;ofertas;direcionamento;público-alvo;regras de direcionamento;direcionamento
description: Descubra como direcionar ofertas individuais para públicos específicos usando atividades de [!UICONTROL Automated Personalization] (AP).
title: Como Posso Direcionar Ofertas De [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 19%

---

# Ofertas do Target [!UICONTROL Automated Personalization]

Em uma atividade de [!DNL Adobe Target] [!DNL Automated Personalization] (AP), você pode direcionar ofertas a públicos específicos.

Utilizar essa funcionalidade reduz o número de ofertas que um visitante específico está qualificado a visualizar. Por exemplo, considere uma atividade [!UICONTROL Automated Personalization] que tenha três ofertas. A oferta 1 tem uma regra de direcionamento que limita a exposição ao Público-alvo A. Dois visitantes viram essa atividade.

| | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Qualificação de público | Público-alvo A | Público-alvo B |
| Pontuação do modelo de personalização da Oferta 1 do Target | 90 | 90 |
| Pontuação do modelo de personalização da Oferta 2 do Target | 50 | 70 |
| Pontuação do modelo de personalização da Oferta 3 do Target | 80 | 60 |

Nesse cenário, o Visitante 1 vê a Oferta 1 (porque esse visitante se qualifica como parte do Público-alvo A), que é a pontuação mais alta desse visitante. No entanto, o Visitante 2 vê a Oferta 2, mesmo que a pontuação mais alta seja para a Oferta 1, porque o Visitante 2 não faz parte do Público-alvo A. Este exemplo demonstra por que as regras de direcionamento devem ser usadas com moderação para atender às necessidades da empresa. A adição dessas regras pode reduzir a eficácia de [!DNL Target] modelos de personalização.

## Configurar regras de direcionamento

1. Crie ou edite uma [atividade do Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) contendo as ofertas que deseja direcionar.
1. Depois de configurar as ofertas para a atividade no [!UICONTROL Visual Experience Composer], clique no ícone **[!UICONTROL Manage Content]** ( ![Ícone Gerenciar Conteúdo](/help/main/assets/icons/Experience.svg) ).

   A caixa de diálogo [!UICONTROL Manage Content] é exibida.

1. Clique na guia **[!UICONTROL Offers]**.

1. Selecione as ofertas desejadas e escolha os públicos que deseja qualificar para ver essa oferta.

   Para configurar o direcionamento para uma única oferta, clique no ícone Mais Informações ( ![Mais Informações](/help/main/assets/icons/MoreSmallList.svg) ) ao lado da oferta desejada e, em seguida, clique em **[!UICONTROL Target Audience]** para exibir a caixa de diálogo [!UICONTROL Add Audiences].

   Para configurar o direcionamento para várias ofertas, marque as caixas de seleção para as ofertas desejadas e clique no link **[!UICONTROL Target Audience]**, que é exibido na parte inferior da lista.

1. Na caixa de diálogo [!UICONTROL Add Audiences], selecione os públicos desejados para as ofertas e clique em **[!UICONTROL Assign Audience]** para retornar à caixa de diálogo [!UICONTROL Manage Content].

   >[!NOTE]
   >
   >Além de selecionar um público existente, você pode combinar vários deles para criar públicos combinados sob demanda em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Clique em **[!UICONTROL Done]**.

>[!NOTE]
>
>Você pode configurar 50 locais e até 250 ofertas por local.
