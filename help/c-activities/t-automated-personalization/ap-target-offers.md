---
keywords: personalização automatizada, ofertas, target, público-alvo, regras de direcionamento, direcionamento
description: Saiba como direcionar ofertas individuais para públicos-alvo específicos usando uma atividade de Automated Personalization (AP) no Adobe Target.
title: Como posso [!DNL Target] Ofertas do Automated Personalization?
feature: Personalização automatizada
solution: Target,Analytics
exl-id: 633308dd-437b-4525-a7f8-69656c7d89be
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 87%

---

# ![](/help/assets/premium.png) [!DNL Target] PREMIUMAofertas de personalização automatizada

Em uma atividade [!DNL Adobe Target] [!DNL Automated Personalization] (AP), é possível direcionar ofertas para públicos-alvo específicos.

Utilizar essa funcionalidade reduz o número de ofertas que um visitante específico está qualificado a visualizar. Por exemplo, considere uma atividade com três ofertas. A oferta 1 tem uma regra de direcionamento que limita a exposição somente para o Público-alvo A. Dois visitantes visualizaram essa atividade AP.

|  | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Qualificação do público-alvo | Público-alvo A | Público-alvo B |
| Pontuação do modelo de personalização da Oferta 1 do Target | 90 | 90º |
| Pontuação do modelo de personalização da Oferta 2 do Target | 50 | 70 |
| Pontuação do modelo de personalização da Oferta 3 do Target | 80 | 60 |

Neste cenário, o Visitante 1 veria a Oferta 1 (porque ele se qualifica como parte do Público-alvo A), que é a pontuação mais alta desse visitante. Entretanto, o Visitante 2 veria a Oferta 2 mesmo que sua pontuação mais alta seja para a Oferta 1, porque o Visitante 2 não faz parte do Público-alvo A. Este exemplo demonstra por que as regras de direcionamento devem ser usadas com moderação para atender às necessidades comerciais. Adicionar essas regras pode reduzir a eficiência dos modelos de personalização do Target.

## Configurar regras de direcionamento

1. Crie uma [atividade Personalização automatizada](/help/c-activities/t-automated-personalization/create-ap-activity.md) contendo as ofertas que deseja direcionar.
1. Depois de configurar as ofertas para a atividade no Visual Experience Composer, clique em **[!UICONTROL Gerenciar conteúdo]**.

   ![Gerenciar conteúdo](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   A caixa de diálogo Gerenciar conteúdo é aberta.

1. Clique na guia Ofertas.

   ![Página de ofertas](/help/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Selecione a(s) oferta(s) desejada(s) e escolha os públicos que deseja qualificar para ver essa oferta.

   Para configurar o direcionamento para uma única oferta, passe o mouse sobre a oferta desejada e clique no ícone **[!UICONTROL Direcionamento]**.

   Para configurar o direcionamento para várias ofertas, marque as caixas de seleção para as ofertas desejadas e clique no ícone**[!UICONTROL Direcionamento], que é exibido na parte superior direita da lista.

1. Na caixa de diálogo [!UICONTROL Escolher público-alvo] selecione o(s) público(s) desejado(s) para a(s) oferta(s) e clique em **[!UICONTROL Concluído]** para retornar à caixa de diálogo [!UICONTROL Gerenciar conteúdo].

   >[!NOTE]
   >
   >Além de selecionar um público-alvo existente, você pode combinar vários deles para criar públicos-alvo combinados ad hoc em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Clique em **[!UICONTROL Concluído]**.

>[!NOTE]
>
>Você pode configurar 50 locais e até 250 ofertas por local.
