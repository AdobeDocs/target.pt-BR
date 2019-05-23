---
description: Em uma atividade de Automated Personalization, você pode direcionar ofertas a públicos específicos.
seo-description: Em uma atividade de Automated Personalization, você pode direcionar ofertas a públicos específicos.
seo-title: Ofertas de Automated Personalization do Target
solution: Target,Analytics
title: Ofertas de Automated Personalization do Target
title-outputclass: premium
uuid: 4ee30e1a-bfda-4b20-9313-99e32dcf60ac
badge: premium
translation-type: tm+mt
source-git-commit: 2baa75b6020b2f9229db68667c2e19a698954231

---


# ![PREMIUM](/help/assets/premium.png) Ofertas de personalização automatizada do Target{#target-automated-personalization-offers}

Em uma atividade de Automated Personalization, você pode direcionar ofertas a públicos específicos.

Utilizar essa funcionalidade reduz o número de ofertas que um visitante específico está qualificado a visualizar. Por exemplo, considere uma atividade de Personalização automatizada (AP) com três ofertas. A oferta 1 tem uma regra de direcionamento que limita a exposição somente para o Público-alvo A. Dois visitantes visualizaram essa atividade AP.

|  | Visitante 1 | Visitante 2 |
|--- |--- |--- |
| Qualificação do público-alvo | Público-alvo A | Público-alvo B |
| Pontuação do modelo de personalização da Oferta 1 do Target | 90 | 90 |
| Pontuação do modelo de personalização sa Oferta 2 do Target | 50 | 70 |
| Pontuação do modelo de personalização sa Oferta 3 do Target | 80 | 60 |

Neste cenário, o Visitante 1 veria a Oferta 1 (porque ele se qualifica como parte do Público-alvo A), que é a pontuação mais alta desse visitante. Entretanto, o Visitante 2 veria a Oferta 2 mesmo que sua pontuação mais alta seja para a Oferta 1, porque o Visitante 2 não faz parte do Público-alvo A. Este exemplo demonstra por que as regras de direcionamento devem ser usadas com moderação para atender às necessidades comerciais. Adicionar essas regras pode reduzir a eficiência dos modelos de personalização do Target.

## Configurar regras de definição de metas

1. Crie uma atividade de Personalização automatizada contendo as ofertas que deseja direcionar.
1. Depois de configurar as ofertas para a atividade no Visual Experience Composer, clique em **[!UICONTROL Conteúdo]**.

   A caixa de diálogo Gerenciar conteúdo é aberta.

   ![](assets/ap_content.png)

   >[!NOTE]
   >
   >Você pode configurar 50 locais e até 250 ofertas por local.

1. Na coluna **[!UICONTROL Conteúdo]**, selecione a oferta, clique em **[!UICONTROL Definição de metas]** e escolha os públicos-alvo que deseja qualificar para ver essa oferta.

   Somente os públicos-alvo selecionados serão apresentados nessa oferta.

   >[!NOTE]
   >
   >Além de selecionar um público-alvo existente, você pode combinar vários deles para criar públicos-alvo combinados ad hoc em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Clique em **[!UICONTROL Concluído]**.
