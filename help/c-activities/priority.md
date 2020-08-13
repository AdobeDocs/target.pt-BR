---
keywords: settings;priority
description: A Adobe Target determina qual atividade (ou atividade) deve ser entregue para uma página de forma diferente, dependendo da interface do Público alvo e da função de criação da atividade (Visual Experience Composer ou Criador baseado em forma) que você está usando.
title: Prioridade no Adobe Target
feature: activities
topic: Standard
uuid: 114cd625-2716-4c4c-983b-a7f677717b07
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 88%

---


# Prioridade{#priority}

O Target determina qual atividade (ou quais atividades) mostrar em uma página de maneira diferente, dependendo da interface do Target e da função de criação de atividade (Visual Experience Composer ou Compositor baseado em formulário) que você está usando.

## Target Standard/Premium Visual Experience Composer Only or Form-Based Composer Using Global Target Request Only {#section_4A0A317DFED345649B58B0CB5B410C8B}

Se a sua empresa usa exclusivamente o Target Standard/Premium e o Visual Experience Composer, então o conteúdo de várias atividades pode ser retornado para a mesma chamada. As atividades são entregues por meio do seguinte fluxo de decisão:

1. A chamada do servidor do Target chega ao Target com informações sobre o URL.
1. O Target extrai todas as atividades em execução nesse URL.
1. O Target tenta corresponder o visitante às atividades.

   Se o visitante já está em um teste A/B ou em um teste multivariado, será feita a correlação nesse teste até a conversão. Se anteriormente ele estava em uma atividade de direcionamento de experiência, a correlação deve ser feita novamente. Se atende às regras de público-alvo, o visitante é enquadrado nessas atividades e em experiências específicas.

1. O conteúdo de todas as atividades e experiências que o visitante corresponde é retornado à página.
1. Se o conteúdo de cada atividade fizer referencia a  [seletores CSS diferentes](../c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337), então todo o conteúdo é exibido.

   Se houver uma sobreposição ou duplicação de seletor de CSS, então o conteúdo de atividade com maior prioridade é exibido. Os resultados de todas as atividades executadas na página são contados e refletidos nos relatórios.

   >[!IMPORTANT]
   >
   >O Target retorna o conteúdo de todas as atividades na página, começando com o conteúdo de prioridade mais baixa, que é substituído em seguida a cada atividade, da prioridade mais baixa até a mais alta. Na maioria dos casos, isso resulta na exibição do conteúdo de prioridade mais alta. No entanto, se uma atividade de prioridade mais baixa alterar a estrutura do DOM para a página, será possível que a atividade de prioridade mais alta não reconheça a estrutura da página, de modo que o conteúdo de prioridade mais baixa será exibido. Os resultados de todas as atividades executadas na página são contados e refletidos nos relatórios.

1. Se várias atividades compartilham o mesmo nível de prioridade, há dois pontos decisivos:

   * Se apenas uma atividade tem direcionamento de público-alvo, essa atividade é exibida.
   * Se há direcionamento em todas ou nenhuma, a atividade que foi aprovada primeiro é exibida.

## Composer baseado em formulário do Target Standard/Premium e Visual Experience Composer do Target Standard/Premium  {#section_4620253E1CE942DD830724C7822B175F}

>[!NOTE]
>
>Essas informações também se aplicam a todas as campanhas que foram criadas em [!DNL Target Classic].

Se a sua empresa usa um Composer baseado em formulário no Target Standard/Premium e o Visual Experience Composer do Target Standard/Premium, então o conteúdo de várias atividades do Visual Experience Composer podem ser entregues, mas somente uma atividade do fluxo de trabalho baseado em formulário. A entrega da atividade é determinada por meio do seguinte fluxo de decisão:

1. Target server call comes to Target with information about the [!DNL Target] request and URL.
1. Target Classic and Standard pull every activity running in that [!DNL Target] request.
1. O Target tenta corresponder o visitante às atividades.

   Se o visitante já está em um teste A/B ou em um teste multivariado, será feita a correlação nesse teste até a conversão. Se anteriormente ele estava em uma atividade de direcionamento de experiência, a correlação deve ser feita novamente. Se atende às regras de público-alvo, o visitante é enquadrado nessas atividades e em experiências específicas.

1. Se uma atividade baseada em formulário tiver prioridade mais alta, então o conteúdo dela é retornado juntamente com todo o conteúdo de atividade correspondente das atividades do Visual Experience Composer.
1. Se uma atividade do Visual Experience Composer tiver prioridade mais alta, então o conteúdo de todas as atividades correspondentes do Visual Experience Composer são retornadas, mas nenhum conteúdo do Target Classic ou da atividade baseada em formulário é retornada.

   Os resultados de todas as atividades executadas na página são contados e refletidos nos relatórios.

**Exemplo**

Por exemplo, se você tiver duas atividades, uma definindo as metas da palavra-chave de pesquisa de marca conhecida Nike e outra definindo a palavra-chave de marca não conhecida tênis, as prioridades de ambas as atividades serão verificadas. Se a atividade Nike tiver uma prioridade mais alta, esse conteúdo será exibido. Se a atividade tênis tiver uma prioridade mais alta, seu conteúdo será exibido.

Se ambas as atividades direcionadas tiverem a mesma prioridade, a atividade que foi mais recentemente visualizada é exibida. Se o visitante for novo na página, a atividade ativada por último será exibida.

## Target Standard/Premium Form-Based Composer with Non-Global Target Requests {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

>[!NOTE]
>
>Essas informações também se aplicam a todas as campanhas que foram criadas no Target Classic.

If your company uses [!DNL Target] requests other than the global [!DNL Target] request in the form-based composer, content from only one activity can be returned per call. A entrega da atividade é determinada por meio do seguinte fluxo de decisão:

1. The [!DNL Target] server call comes to [!DNL Target] with information about the [!DNL Target] request and URL.
1. [!DNL Target] puxa cada atividade em execução nessa [!DNL Target] solicitação.
1. [!DNL Target]O tenta corresponder o visitante à atividades com prioridade mais alta.

   Se o visitante já está em um teste A/B ou em um teste multivariado, será feita a correlação nesse teste até a conversão. Se anteriormente ele estava em uma atividade de direcionamento de experiência, a correlação deve ser feita novamente. Se atende às regras de público-alvo, o visitante é enquadrado nessas atividades e em experiências específicas.

1. Se várias atividades compartilham o mesmo nível de prioridade, há dois pontos decisivos:

   * Se apenas uma atividade tem direcionamento de público-alvo, essa atividade é exibida.
   * Se há direcionamento em todas ou nenhuma, a atividade que foi aprovada primeiro é exibida.

## Exemplos {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Dependendo das configurações, os valores de prioridade variam. É possível usar as configurações herdadas de Baixo, Médio ou Alto, ou pode ativar as prioridades otimizadas de 0 a 999. Para obter mais informações, consulte [Configurações da atividade](../c-activities/activity-settings.md#task_C6B2FF8374724933BE79A83549B9CD02).

**Duas campanhas Públicos alvos clássicas usam solicitações de Público alvo não globais**

* Campanha 1: homePageHero, offer1, prioridade alta
* Campanha 2: homePageHero, offer2, prioridade baixa

Resposta: offer1

**Duas atividades usam somente ofertas criadas no Visual Experience Composer para seletores diferentes**

* Atividade 1: target-global-mbox, selector1, visualExpCompOffer1, prioridade baixa
* Atividade 2: target-global-mbox, selector2, visualExpCompOffer2, prioridade alta

Resposta: visualExpCompOffer1, visualExpCompOffer2

**Duas atividades usam somente ofertas criadas no Visual Experience Composer para o mesmo seletor**

* Atividade 1: target-global-mbox, selector1, visualExpCompOffer1, prioridade baixa
* Atividade 2: target-global-mbox, selector1, visualExpCompOffer2, prioridade alta

Resposta: visualExpCompOffer1, visualExpCompOffer2

>[!NOTE]
>
>Essa é a mesma resposta do segundo caso de uso acima, pois o Target Classic não processa conflitos do seletor. O Target Standard detecta tal comportamento e outros casos de uso, quando os seletores podem entrar em conflito no DOM e visualmente (normalmente, feito no nível de editor de experiência ou no modo de simulação da campanha).

**Duas atividades usam ofertas criadas no Visual Experience Composer e duas campanhas do Target Classic**

* Atividade 1: target-global-mbox, selector1, visualExpCompOffer1, prioridade média
* Atividade 2: target-global-mbox, selector2, visualExpCompOffer2, prioridade baixa
* Campanha 1: target-global-mbox, offer1, prioridade alta
* Campanha 2: target-global-mbox, offer2, prioridade baixa

Resposta: offer1, visualExpCompOffer2, visualExpCompOffer1

>[!NOTE]
>
>A ordem das respostas combinadas é o conteúdo do Classic em primeiro (somente uma resposta do Classic será atendida, como no caso de uso 1) e, em seguida, as respostas de oferta do Visual Experience Composer ordenadas por prioridade invertida.

## Vídeo de treinamento: configurações da atividade (3:02)

Este vídeo inclui informações sobre as configurações da atividade.

* Inserir um objetivo para a atividade
* Definir o nível de prioridade das atividades
* Programar as horas de início e término da atividade
* Adicionar públicos-alvo para relatórios a fim de criar filtros de relatórios
* Inserir observações para a atividade

>[!VIDEO](https://video.tv.adobe.com/v/17381)