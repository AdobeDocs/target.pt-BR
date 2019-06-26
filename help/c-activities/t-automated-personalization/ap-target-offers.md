---
description: Em uma atividade de Automated Personalization, você pode direcionar ofertas a públicos específicos.
seo-description: Em uma atividade de Automated Personalization, você pode direcionar ofertas a públicos específicos.
seo-title: Ofertas de Personalização automatizada do Target
solution: Target,Analytics
title: Ofertas de Personalização automatizada do Target
title-outputclass: premium
uuid: 4ee30e1a-bfda-4b20-9313-99e32dcf60ac
badge: premium
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![PREMIUM](/help/assets/premium.png) Ofertas de personalização automatizada do Target{#target-automated-personalization-offers}

Em uma atividade de Personalização automatizada (AP), você pode direcionar ofertas a públicos-alvo específicos.

Utilizar essa funcionalidade reduz o número de ofertas que um visitante específico está qualificado a visualizar. Por exemplo, considere uma atividade AP com três ofertas. A oferta 1 tem uma regra de definição de metas que limita sua exposição ao Público A. Dois visitantes viram essa atividade AP.

|  | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Qualificação do público-alvo | Público-alvo A | Público-alvo B |
| Pontuação do modelo de personalização da Oferta 1 do Target | 90 | 90 |
| Pontuação do modelo de personalização sa Oferta 2 do Target | 50 | 70 |
| Pontuação do modelo de personalização sa Oferta 3 do Target | 80 | 60 |

Neste cenário, o Visitante 1 veria a Oferta 1 (porque ele se qualifica como parte do Público-alvo A), que é a pontuação mais alta desse visitante. Entretanto, o Visitante 2 veria a Oferta 2 mesmo que sua pontuação mais alta seja para a Oferta 1, porque o Visitante 2 não faz parte do Público-alvo A. Este exemplo demonstra por que as regras de direcionamento devem ser usadas com moderação para atender às necessidades comerciais. Adicionar essas regras pode reduzir a eficiência dos modelos de personalização do Target.

## Configurar regras de definição de metas

1. Create an [Automated Personalization activity](/help/c-activities/t-automated-personalization/create-ap-activity.md) containing the offers you want to target.
1. After setting up the offers for the activity in the Visual Experience Composer, click **[!UICONTROL Manage Content]**.

   ![Gerenciar conteúdo](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   A caixa de diálogo Gerenciar conteúdo é aberta.

1. Clique na guia Ofertas.

   ![Página de ofertas](/help/c-activities/t-automated-personalization/assets/manage-content-offers.png)

1. Selecione a (s) oferta (s) desejada (s) e escolha os públicos-alvo que deseja qualificar para ver essa oferta.

   To set up targeting for a single offer, hover over the desired offer, then click the **[!UICONTORL Targeting]** icon.

   To set up targeting for multiple offers, select the checkboxes for the desired offers, then click the **[!UICONTROL Targeting] icon that displays at the top right of the list.

1. In the [!UICONTROL Choose Audience] dialog box, select the desired audience(s) for the offer(s), then click **[!UICONTROL Done]** to return to the [!UICONTROL Manage Content] dialog box.

   >[!NOTE]
   >
   >Além de selecionar um público-alvo existente, você pode combinar vários deles para criar públicos-alvo combinados ad hoc em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Clique em **[!UICONTROL Concluído]**.

>[!NOTE]
>
>Você pode configurar 50 locais e até 250 ofertas por local.
