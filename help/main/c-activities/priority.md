---
keywords: configurações;priority
description: Saiba como o  [!DNL Adobe Target] determina qual atividade (ou quais atividades) mostrar em uma página de forma diferente, dependendo da interface do  [!DNL Target]  e da função de criação de atividade que você está usando.
title: Como o  [!DNL Target] atribui prioridade a atividades diferentes?
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: be6e45ff301f549eb5be24a65b05c4a9c1cd6089
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 37%

---

# Prioridade

[!DNL Adobe Target] determina qual atividade (ou quais atividades) mostrar em uma página de forma diferente, dependendo da interface do [!DNL Target] e da função de criação de atividade ([[!UICONTROL Visual Experience Composer (VEC)]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) ou [Experience Composer Baseado em Formulário](/help/main/c-experiences/form-experience-composer.md)) que você está usando.

## [!UICONTROL Visual Experience Composer] somente ou [!UICONTROL Form-Based Experience Composer] usando uma solicitação global [!DNL Target] somente {#section_4A0A317DFED345649B58B0CB5B410C8B}

Se sua empresa usa o VEC exclusivamente, o conteúdo de várias atividades pode ser retornado para a mesma chamada. As atividades são entregues por meio do seguinte fluxo de decisão:

1. A chamada do servidor [!DNL Target] vem para [!DNL Target] com informações sobre a URL.
1. [!DNL Target] extrai todas as atividades em execução nessa URL.
1. [!DNL Target] tentativas de combinar o visitante em atividades.

   Se o visitante já estiver em uma atividade [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test], ele corresponderá nessa atividade até que seja convertido. Se eles estavam anteriormente em uma atividade [!UICONTROL Experience Targeting], eles devem corresponder a ela novamente. Se atende às regras de público-alvo, o visitante é enquadrado nessas atividades e em experiências específicas.

1. O conteúdo de todas as atividades e experiências que o visitante corresponde é retornado à página.
1. Se o conteúdo de cada atividade fizer referência a [seletores de CSS](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337) diferentes, todo o conteúdo será exibido.

   Se houver uma sobreposição ou duplicação de seletor de CSS, então o conteúdo de atividade com maior prioridade é exibido. Os resultados de todas as atividades executadas na página são contados e refletidos nos relatórios.

   >[!IMPORTANT]
   >
   >[!DNL Target] retorna o conteúdo de todas as atividades na página, começando com o conteúdo de prioridade mais baixa, que é substituído em seguida por cada atividade, da prioridade mais baixa até a mais alta. Normalmente, isso resulta na exibição do conteúdo de prioridade mais alta. No entanto, se uma atividade de prioridade mais baixa alterar a estrutura do DOM para a página, é possível que a atividade de prioridade mais alta não reconheça a estrutura da página, de modo que o conteúdo de prioridade mais baixa seja exibido. Os resultados de todas as atividades executadas na página são contados e refletidos nos relatórios.

1. Se várias atividades compartilharem o nível de prioridade, há dois fatores que quebram os níveis:

   * Se apenas uma atividade tem direcionamento de público-alvo, essa atividade é exibida.
   * Se todos ou nenhum tiver direcionamento, a atividade que foi aprovada primeiro será exibida.

## [!UICONTROL Form-Based Experience Composer] e [!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

Se sua empresa usa o [!UICONTROL Form-Based Experience Composer] *e* o VEC, o conteúdo de várias atividades do [!UICONTROL Form-Based Experience Composer] e do VEC poderá ser entregue. Anteriormente, somente uma atividade do fluxo de trabalho baseado em formulário podia fornecer. Não há mais um limite para o número de atividades baseadas em formulário que podem ser entregues.

A entrega da atividade é determinada por meio do seguinte fluxo de decisão:

1. A chamada de servidor [!DNL Target] chega a [!DNL Target] com informações sobre a solicitação [!DNL Target] e a URL.
1. [!DNL Target] extrai cada atividade em execução nessa solicitação [!DNL Target].
1. [!DNL Target] tentativas de combinar o visitante em atividades.

   Se o visitante já estiver em uma atividade [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test], ele corresponderá nesse teste até que seja convertido. Se eles estavam anteriormente em uma atividade [!UICONTROL Experience Targeting], eles devem corresponder a ela novamente. Se atende às regras de público-alvo, o visitante é enquadrado nessas atividades e em experiências específicas.

1. Se uma atividade baseada em formulário for a prioridade mais alta, esse conteúdo de atividade será retornado junto com todo o conteúdo de atividade correspondente das atividades do VEC.
1. Se uma atividade do VEC for a prioridade mais alta, o conteúdo de todas as atividades do VEC correspondentes será retornado, mas nenhum conteúdo de atividade baseada em formulário será retornado.

   Os resultados de todas as atividades executadas na página são contados e refletidos nos relatórios.

**Exemplo**

Se você tiver duas atividades, uma direcionada à palavra-chave de pesquisa de marca &quot;Nike&quot; e a segunda direcionada à palavra-chave não de marca &quot;tênis&quot;, as prioridades de ambas as atividades serão verificadas. Se a atividade Nike tiver uma prioridade mais alta, esse conteúdo será exibido. Se a atividade tênis tiver uma prioridade mais alta, seu conteúdo será exibido.

Se ambas as atividades direcionadas tiverem a mesma prioridade, a atividade que foi mais recentemente visualizada é exibida. Se o visitante for novo na página, a atividade ativada por último será exibida.

## [!UICONTROL Form-Based Experience Composer] com solicitações [!DNL Target] não globais {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

Se sua empresa usa solicitações [!DNL Target] diferentes da solicitação global [!DNL Target] no compositor baseado em formulário, o conteúdo de apenas uma atividade pode ser retornado por chamada. A entrega da atividade é determinada por meio do seguinte fluxo de decisão:

1. A chamada do servidor [!DNL Target] vem para [!DNL Target] com informações sobre a solicitação [!DNL Target] e a URL.
1. [!DNL Target] extrai cada atividade em execução nessa solicitação [!DNL Target].
1. [!DNL Target] tenta fazer a correspondência do visitante com a atividade de prioridade mais alta.

   Se o visitante já estiver em uma atividade [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test], ele corresponderá nessa atividade até que seja convertido. Se eles estavam anteriormente em uma atividade [!UICONTROL Experience Targeting], eles devem corresponder a ela novamente. Se atende às regras de público-alvo, o visitante é enquadrado nessas atividades e em experiências específicas.

1. Se várias atividades compartilharem o nível de prioridade, há dois fatores que quebram os níveis:

   * Se apenas uma atividade tem direcionamento de público-alvo, essa atividade é exibida.
   * Se todos ou nenhum tiver direcionamento, a atividade que foi aprovada primeiro será exibida.

## Exemplos {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Dependendo das configurações, os valores de prioridade variam. Você pode usar as configurações herdadas de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou pode habilitar prioridades otimizadas de 0 a 999. Para obter mais informações, consulte [Configurações da atividade](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

Resposta: offer1

**Duas atividades usam somente ofertas criadas em [!UICONTROL Visual Experience Composer] para seletores diferentes**

* Atividade 1: target-global-mbox, selector1, visualExpCompOffer1, prioridade baixa
* Atividade 2: target-global-mbox, selector2, visualExpCompOffer2, prioridade alta

Resposta: visualExpCompOffer1, visualExpCompOffer2

**Duas atividades usam somente ofertas criadas no [!UICONTROL Visual Experience Composer] para o mesmo seletor**

* Atividade 1: target-global-mbox, selector1, visualExpCompOffer1, prioridade baixa
* Atividade 2: target-global-mbox, selector1, visualExpCompOffer2, prioridade alta

Resposta: visualExpCompOffer1, visualExpCompOffer2

## Vídeo de treinamento: configurações da atividade (3:02)

Este vídeo inclui informações sobre as configurações da atividade.

* Inserir um objetivo para a atividade
* Definir o nível de prioridade das atividades
* Programar as horas de início e término da atividade
* Adicionar públicos-alvo para relatórios a fim de criar filtros de relatórios
* Inserir observações para a atividade

>[!VIDEO](https://video.tv.adobe.com/v/17381)
