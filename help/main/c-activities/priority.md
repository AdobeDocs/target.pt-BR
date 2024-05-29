---
keywords: configurações;priority
description: Saiba como [!DNL Adobe Target] determina qual atividade (ou quais atividades) mostrar em uma página de forma diferente, dependendo de qual [!DNL Target] e qual função de criação de atividade você está usando.
title: Como o [!DNL Target] Atribuir prioridade a atividades diferentes?
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
source-git-commit: f935b963d8686ca8991544a96720adfc32b1083e
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 33%

---

# Prioridade

[!DNL Adobe Target] determina qual atividade (ou quais atividades) mostrar em uma página de forma diferente, dependendo de qual [!DNL Target] e qual função de criação de atividade ([[!UICONTROL Visual Experience Composer (VEC)]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) ou [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md)) você está usando.

## [!DNL Target Standard/Premium] [!UICONTROL Visual Experience Composer] somente ou [!UICONTROL Form-Based Experience Composer] usar uma global [!DNL Target] somente solicitação {#section_4A0A317DFED345649B58B0CB5B410C8B}

Se sua empresa usar [!DNL Target Standard/Premium] e o VEC exclusivamente, o conteúdo de várias atividades pode ser retornado para a mesma chamada. As atividades são entregues por meio do seguinte fluxo de decisão:

1. A variável [!DNL Target] chamada de servidor recebida em [!DNL Target] com informações sobre o URL.
1. [!DNL Target] O extrai cada atividade executada nesse URL.
1. [!DNL Target] O tenta direcionar o visitante às atividades.

   Se o visitante já estiver em uma [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test] atividade, elas correspondem a essa atividade até a conversão. Se estavam anteriormente em uma [!UICONTROL Experience Targeting] atividade, eles devem corresponder a ela novamente. Se atende às regras de público-alvo, o visitante é enquadrado nessas atividades e em experiências específicas.

1. O conteúdo de todas as atividades e experiências que o visitante corresponde é retornado à página.
1. Se o conteúdo de cada atividade fizer referência a [Seletores de CSS](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337), então todo o conteúdo é exibido.

   Se houver uma sobreposição ou duplicação de seletor de CSS, então o conteúdo de atividade com maior prioridade é exibido. Os resultados de todas as atividades executadas na página são contados e refletidos nos relatórios.

   >[!IMPORTANT]
   >
   >[!DNL Target] retorna o conteúdo de todas as atividades na página, começando com o conteúdo de prioridade mais baixa, que é substituído em seguida por cada atividade, da prioridade mais baixa até a mais alta. Normalmente, isso resulta na exibição do conteúdo de prioridade mais alta. No entanto, se uma atividade de prioridade mais baixa alterar a estrutura do DOM para a página, é possível que a atividade de prioridade mais alta não reconheça a estrutura da página, de modo que o conteúdo de prioridade mais baixa seja exibido. Os resultados de todas as atividades executadas na página são contados e refletidos nos relatórios.

1. Se várias atividades compartilharem o nível de prioridade, há dois fatores que quebram os níveis:

   * Se apenas uma atividade tem direcionamento de público-alvo, essa atividade é exibida.
   * Se todos ou nenhum tiver direcionamento, a atividade que foi aprovada primeiro será exibida.

## [!DNL Target Standard/Premium] [!UICONTROL Form-Based Experience Composer] e [!DNL Target Standard/Premium] [!UICONTROL Visual Experience Composer] {#section_4620253E1CE942DD830724C7822B175F}

>[!NOTE]
>
>Essas informações também se aplicam a todas as atividades que foram criadas em [!DNL Target Classic].

Se sua empresa usar o [!UICONTROL Form-Based Experience Composer] *e* o VEC, conteúdo de vários [!UICONTROL Form-Based Experience Composer] e VEC podem fornecer. Anteriormente, somente uma atividade do fluxo de trabalho baseado em formulário podia fornecer. Não há mais um limite para o número de atividades baseadas em formulário que podem ser entregues.

A entrega da atividade é determinada por meio do seguinte fluxo de decisão:

1. [!DNL Target] chamada de servidor recebida em [!DNL Target] com informações sobre o [!DNL Target] solicitação e URL.
1. [!DNL Target Standard/Premium] O extrai cada atividade em execução nesse [!DNL Target] solicitação.
1. [!DNL Target] O tenta direcionar o visitante às atividades.

   Se o visitante já estiver em uma [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test] atividade, elas correspondem nesse teste até a conversão. Se estavam anteriormente em uma [!UICONTROL Experience Targeting] atividade, eles devem corresponder a ela novamente. Se atende às regras de público-alvo, o visitante é enquadrado nessas atividades e em experiências específicas.

1. Se uma atividade baseada em formulário for a prioridade mais alta, esse conteúdo de atividade será retornado junto com todo o conteúdo de atividade correspondente das atividades do VEC.
1. Se uma atividade do VEC tiver a prioridade mais alta, o conteúdo de todas as atividades do VEC correspondentes será retornado, mas nenhuma [!DNL Target Classic] ou o conteúdo da atividade baseada em formulário é retornado.

   Os resultados de todas as atividades executadas na página são contados e refletidos nos relatórios.

**Exemplo**

Se você tiver duas atividades, uma direcionada à palavra-chave de pesquisa de marca &quot;Nike&quot; e a segunda direcionada à palavra-chave não de marca &quot;tênis&quot;, as prioridades de ambas as atividades serão verificadas. Se a atividade Nike tiver uma prioridade mais alta, esse conteúdo será exibido. Se a atividade tênis tiver uma prioridade mais alta, seu conteúdo será exibido.

Se ambas as atividades direcionadas tiverem a mesma prioridade, a atividade que foi mais recentemente visualizada é exibida. Se o visitante for novo na página, a atividade ativada por último será exibida.

## [!DNL Target Standard/Premium] [!UICONTROL Form-Based Experience Composer] com propriedades não globais [!DNL Target] solicitações {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

>[!NOTE]
>
>Essas informações também se aplicam a todas as atividades que foram criadas em [!DNL Target Classic].

Se sua empresa usar [!DNL Target] solicitações que não sejam a global [!DNL Target] solicitação no compositor baseado em formulário, o conteúdo de apenas uma atividade pode ser retornado por chamada. A entrega da atividade é determinada por meio do seguinte fluxo de decisão:

1. A variável [!DNL Target] chamada de servidor recebida em [!DNL Target] com informações sobre o [!DNL Target] solicitação e URL.
1. [!DNL Target] O extrai cada atividade em execução nesse [!DNL Target] solicitação.
1. [!DNL Target] O tenta direcionar o visitante à atividade de prioridade mais alta.

   Se o visitante já estiver em uma [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test] atividade, elas correspondem a essa atividade até a conversão. Se estavam anteriormente em uma [!UICONTROL Experience Targeting] atividade, eles devem corresponder a ela novamente. Se atende às regras de público-alvo, o visitante é enquadrado nessas atividades e em experiências específicas.

1. Se várias atividades compartilharem o nível de prioridade, há dois fatores que quebram os níveis:

   * Se apenas uma atividade tem direcionamento de público-alvo, essa atividade é exibida.
   * Se todos ou nenhum tiver direcionamento, a atividade que foi aprovada primeiro será exibida.

## Exemplos {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Dependendo das configurações, os valores de prioridade variam. É possível usar as configurações herdadas de [!UICONTROL Low], [!UICONTROL Medium]ou [!UICONTROL High]ou você pode ativar as prioridades otimizadas de 0 a 999. Para obter mais informações, consulte [Configurações de atividade](/help/main/c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

**Dois [!DNL Target Classic] atividades usam não globais [!DNL Target] solicitações**

* Atividade 1: homePageHero, offer1, priority high
* Atividade 2: homePageHero, offer2, priority low

Resposta: offer1

**Duas atividades usam somente ofertas criadas no [!UICONTROL Visual Experience Composer] para seletores diferentes**

* Atividade 1: target-global-mbox, selector1, visualExpCompOffer1, prioridade baixa
* Atividade 2: target-global-mbox, selector2, visualExpCompOffer2, prioridade alta

Resposta: visualExpCompOffer1, visualExpCompOffer2

**Duas atividades usam somente ofertas criadas no [!UICONTROL Visual Experience Composer] para o mesmo seletor**

* Atividade 1: target-global-mbox, selector1, visualExpCompOffer1, prioridade baixa
* Atividade 2: target-global-mbox, selector1, visualExpCompOffer2, prioridade alta

Resposta: visualExpCompOffer1, visualExpCompOffer2

>[!NOTE]
>
>Essa é a mesma resposta do segundo caso de uso acima, pois [!DNL Target Classic] não tratou colisões de seletores. [!DNL Target Standard/Premium] O captura esse comportamento e outros casos de uso quando os seletores podem colidir no DOM e visualmente (geralmente feito no nível do editor de experiência ou no modo de simulação de atividade).

**Duas atividades usam ofertas criadas no [!UICONTROL Visual Experience Composer] e dois [!DNL Target Classic] atividades**

* Atividade 1: target-global-mbox, selector1, visualExpCompOffer1, prioridade média
* Atividade 2: target-global-mbox, selector2, visualExpCompOffer2, prioridade baixa
* Atividade 1: target-global-mbox, offer1, priority high
* Atividade 2: target-global-mbox, offer2, priority low

Resposta: offer1, visualExpCompOffer2, visualExpCompOffer1

>[!NOTE]
>
>A ordem das respostas combinadas é que [!DNL Target Classic] o conteúdo vem primeiro. Somente um [!DNL Target Classic] a resposta é atendida como no caso de uso 1 e, em seguida, [!UICONTROL Visual Experience Composer] respostas de oferta ordenadas por prioridade invertida.

## Vídeo de treinamento: configurações da atividade (3:02)

Este vídeo inclui informações sobre as configurações da atividade.

* Inserir um objetivo para a atividade
* Definir o nível de prioridade das atividades
* Programar as horas de início e término da atividade
* Adicionar públicos-alvo para relatórios a fim de criar filtros de relatórios
* Inserir observações para a atividade

>[!VIDEO](https://video.tv.adobe.com/v/17381)
