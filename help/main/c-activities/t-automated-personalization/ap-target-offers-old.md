---
keywords: personalização automatizada;ofertas;direcionamento;público-alvo;regras de direcionamento;direcionamento
description: Saiba como direcionar ofertas individuais para públicos-alvo específicos usando uma atividade do [!UICONTROL Automated Personalization] (AP) no [!DNL Adobe Target].
title: Como Posso Direcionar Ofertas Do [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 26%

---

# Ofertas do [!UICONTROL Automated Personalization] do Target

Em uma atividade de [!DNL Adobe Target] [!DNL Automated Personalization] (AP), você pode direcionar ofertas a públicos específicos.

Utilizar essa funcionalidade reduz o número de ofertas que um visitante específico está qualificado a visualizar. Por exemplo, considere uma atividade [!UICONTROL Automated Personalization] que tenha três ofertas. A oferta 1 tem uma regra de direcionamento que limita a exposição ao Público-alvo A. Dois visitantes viram essa atividade.

| | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Qualificação de público-alvo | Público-alvo A | Público-alvo B |
| Pontuação do modelo de personalização da Oferta 1 do Target | 90 | 90 |
| Pontuação do modelo de personalização da Oferta 2 do Target | 50 | 70 |
| Pontuação do modelo de personalização da Oferta 3 do Target | 80 | 60 |

Nesse cenário, o Visitante 1 vê a Oferta 1 (porque esse visitante se qualifica como parte do Público-alvo A), que é a pontuação mais alta desse visitante. No entanto, o Visitante 2 vê a Oferta 2, mesmo que a pontuação mais alta seja para a Oferta 1, porque o Visitante 2 não faz parte do Público-alvo A. Este exemplo demonstra por que as regras de direcionamento devem ser usadas com moderação para atender às necessidades da empresa. A adição dessas regras pode reduzir a eficácia de [!DNL Target] modelos de personalização.

## Configurar regras de direcionamento

1. Crie uma [atividade do Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) contendo as ofertas que deseja direcionar.
1. Depois de configurar as ofertas para a atividade no [!UICONTROL Visual Experience Composer], clique em **[!UICONTROL Gerenciar conteúdo]**.

   ![Gerenciar conteúdo](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   A caixa de diálogo [!UICONTROL Gerenciar Conteúdo] é exibida.

1. Clique na guia **[!UICONTROL Ofertas]**.

   ![Página de ofertas](/help/main/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Selecione as ofertas desejadas e escolha os públicos que deseja qualificar para ver essa oferta.

   Para configurar o direcionamento para uma única oferta, passe o mouse sobre a oferta desejada e clique no ícone **[!UICONTROL Direcionamento]**.

   Para configurar o direcionamento para várias ofertas, marque as caixas de seleção para as ofertas desejadas e clique no ícone **[!UICONTROL Direcionamento]**, que é exibido na parte superior direita da lista.

1. Na caixa de diálogo [!UICONTROL Escolher público-alvo], selecione os públicos-alvo desejados para as ofertas e clique em **[!UICONTROL Concluído]** para retornar à caixa de diálogo [!UICONTROL Gerenciar conteúdo].

   >[!NOTE]
   >
   >Além de selecionar um público-alvo existente, você pode combinar vários deles para criar públicos-alvo combinados ad hoc em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Clique em **[!UICONTROL Concluído]**.

>[!NOTE]
>
>Você pode configurar 50 locais e até 250 ofertas por local.
