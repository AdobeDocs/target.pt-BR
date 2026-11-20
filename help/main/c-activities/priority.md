---
keywords: configurações;priority
description: Saiba como o [!DNL Adobe Target] determina qual atividade (ou quais atividades) mostrar em uma página de forma diferente, dependendo da interface do [!DNL Target] e da função de criação de atividade que você está usando.
title: Como o [!DNL Target] atribui prioridade a atividades diferentes?
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
TQID: 'https://experienceleague.adobe.com/KSkJ1CDkd4hgwnLQ1RKn8l8r2MDIO-6flcHcdN0c0oQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 7eede3484d524e87127de9147aa786484fc87c7d
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 19%
---
# Prioridade {#priority}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como o [!DNL Adobe Target] decide quais atividades serão entregues a uma página, dependendo do compositor de experiências e do tipo de solicitação [!DNL Target] em uso.

>[!ENDSHADEBOX]

[!DNL Adobe Target] determina qual atividade (ou quais atividades) mostrar em uma página de forma diferente, dependendo da interface do [!DNL Target] e da função de criação de atividade ([**[!UICONTROL Visual Experience Composer (VEC)]**](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) ou [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md)) que você está usando. A tabela a seguir resume os três casos, que são detalhados nas seções abaixo.

| Cenário | Atividades que podem fornecer | Conteúdo retornado |
|---|---|---|
| **[!UICONTROL Visual Experience Composer]** somente ou **[!UICONTROL Experience Composer baseado em formulário]** somente com uma solicitação global [!DNL Target] | Vários | Conteúdo de todas as atividades correspondentes. Se os seletores se sobrepuserem, o conteúdo da atividade de prioridade mais alta será exibido. |
| **[!UICONTROL Experience Composer baseado em formulário]** e **[!UICONTROL Visual Experience Composer]** | Vários | Se uma atividade baseada em formulário tiver a prioridade mais alta, seu conteúdo e o conteúdo de todas as atividades de VEC correspondentes. Se uma atividade do VEC tiver a prioridade mais alta, o conteúdo de todas as atividades do VEC correspondentes será exibido somente. |
| **[!UICONTROL Experience Composer baseado em formulário]** com solicitações [!DNL Target] não globais | Um por chamada | Conteúdo da atividade de correspondência de maior prioridade. |

## VEC ou [!UICONTROL Experience Composer baseado em formulário] com uma solicitação global {#section_4A0A317DFED345649B58B0CB5B410C8B}

Se sua empresa usa o VEC exclusivamente, o conteúdo de várias atividades pode ser retornado para a mesma chamada. As atividades são entregues por meio do seguinte fluxo de decisão:

1. A chamada do servidor [!DNL Target] atinge [!DNL Target]. A chamada transporta informações sobre o URL da página solicitada.
1. [!DNL Target] extrai cada atividade que está sendo executada nessa URL. Essas atividades são as candidatas para delivery.
1. [!DNL Target] tenta fazer a correspondência do visitante às atividades candidatas.

   {{visitor-matching}}

1. O conteúdo de todas as atividades e experiências que o visitante corresponde é retornado à página, para que o conteúdo de várias atividades possa ser entregue para a mesma chamada.
1. [!DNL Target] compara os [seletores de CSS](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md) aos quais o conteúdo de cada atividade faz referência. Se as atividades referenciarem seletores diferentes, todo o conteúdo será exibido.
1. Se um seletor se sobrepõe ou é duplicado, o conteúdo da atividade de maior prioridade é exibido.

   >[!IMPORTANT]
   >
   >[!DNL Target] retorna o conteúdo de todas as atividades na página, começando com o conteúdo de prioridade mais baixa, que é substituído em seguida por cada atividade, da prioridade mais baixa até a mais alta. Normalmente, isso resulta na exibição do conteúdo de prioridade mais alta. No entanto, se uma atividade de prioridade mais baixa alterar a estrutura do DOM para a página, a atividade de prioridade mais alta pode não reconhecer a estrutura da página, portanto, o conteúdo de prioridade mais baixa é exibido.

1. Se várias atividades compartilharem um nível de prioridade, um tiebreaker será aplicado. Se apenas uma das atividades tiver direcionamento de público-alvo, essa atividade será exibida. Se todas ou nenhuma das atividades tiver direcionamento, a atividade que foi aprovada primeiro será exibida.
1. Os resultados de todas as atividades executadas na página são contados e refletidos nos relatórios.

## [!UICONTROL Experience Composer baseado em formulário] e VEC {#section_4620253E1CE942DD830724C7822B175F}

Se sua empresa usa o [!UICONTROL Experience Composer baseado em formulário] *e* o VEC, o conteúdo de vários [!UICONTROL Experience Composer baseado em formulário] e atividades de VEC poderá ser entregue. Anteriormente, somente uma atividade do fluxo de trabalho baseado em formulário podia fornecer. Não há mais um limite para o número de atividades baseadas em formulário que podem ser entregues.

A entrega da atividade é determinada por meio do seguinte fluxo de decisão:

1. A chamada do servidor [!DNL Target] atinge [!DNL Target]. A chamada transporta informações sobre a solicitação [!DNL Target] e a URL.
1. [!DNL Target] extrai cada atividade que está sendo executada nessa solicitação [!DNL Target]. Essas atividades são as candidatas para delivery.
1. [!DNL Target] tenta fazer a correspondência do visitante às atividades candidatas.

   {{visitor-matching}}

1. O [!DNL Target] verifica qual das atividades correspondentes tem a prioridade mais alta e se essa atividade foi criada no [!UICONTROL Experience Composer baseado em formulário] ou no VEC.
1. Se uma atividade baseada em formulário tiver a prioridade mais alta, seu conteúdo será retornado junto com o conteúdo de todas as atividades de VEC correspondentes.
1. Se uma atividade do VEC tiver a prioridade mais alta, o conteúdo de todas as atividades do VEC correspondentes será retornado, mas nenhum conteúdo de atividade baseada em formulário será retornado.
1. Os resultados de todas as atividades executadas na página são contados e refletidos nos relatórios.

**Exemplo**

Existem duas atividades: uma direcionada à palavra-chave de pesquisa de marca &quot;Nike&quot; e a outra direcionada à palavra-chave de marca &quot;tênis&quot;. As prioridades de ambas as atividades são verificadas. Se a atividade Nike tiver uma prioridade mais alta, seu conteúdo será exibido. Se a atividade tênis tiver uma prioridade mais alta, seu conteúdo será exibido.

Se ambas as atividades direcionadas tiverem a mesma prioridade, a atividade que foi mais recentemente visualizada é exibida. Se o visitante for novo na página, a atividade ativada por último será exibida.

## [!UICONTROL Experience Composer baseado em formulário] com solicitações não globais {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

Se sua empresa usa solicitações [!DNL Target] diferentes da solicitação global [!DNL Target] no compositor baseado em formulário, o conteúdo de apenas uma atividade pode ser retornado por chamada. A entrega da atividade é determinada por meio do seguinte fluxo de decisão:

1. A chamada do servidor [!DNL Target] atinge [!DNL Target]. A chamada transporta informações sobre a solicitação [!DNL Target] e a URL.
1. [!DNL Target] extrai cada atividade que está sendo executada nessa solicitação [!DNL Target]. Essas atividades são as candidatas para delivery.
1. [!DNL Target] tenta fazer a correspondência do visitante com a atividade de prioridade mais alta do candidato.

   {{visitor-matching}}

1. Se várias atividades compartilharem um nível de prioridade, um tiebreaker será aplicado. Se apenas uma das atividades tiver direcionamento de público-alvo, essa atividade será exibida. Se todas ou nenhuma das atividades tiver direcionamento, a atividade que foi aprovada primeiro será exibida.
1. O conteúdo dessa única atividade é retornado para a página.

## Exemplos {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Dependendo das configurações, os valores de prioridade variam. Você pode usar as configurações herdadas de **[!UICONTROL Baixo]**, **[!UICONTROL Medium]** ou **[!UICONTROL Alto]**, ou pode habilitar prioridades otimizadas de 0 a 999. Para obter mais informações, consulte [Configurações da atividade](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC).

**Duas atividades usam somente ofertas criadas no [!UICONTROL Visual Experience Composer] para seletores diferentes**

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
