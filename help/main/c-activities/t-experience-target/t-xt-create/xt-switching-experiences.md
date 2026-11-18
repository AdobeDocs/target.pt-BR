---
keywords: prioridade; criação de experiência; prioridade; experiência; público-alvo; experiência; troca de experiências; visual experience composer
description: Saiba como os visitantes podem alternar entre experiências em uma atividade de [!DNL Adobe Target] [!UICONTROL Direcionamento de experiência] (XT) conforme seus perfis evoluem.
title: Os visitantes podem trocar experiências em uma atividade de [!UICONTROL Direcionamento de experiência]?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
TQID: 'https://experienceleague.adobe.com/4bBukCristluFUClhewMcSsNMTPjLjXEqM1QyyropKU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: b6f5758b-84f7-4943-8b05-1297a046943c
    internal-label: Experience target
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: aaa094f4f36b6088ca180637d8054b6d5ff59d60
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 20%
---
# Alternando experiências no [!UICONTROL Direcionamento de experiência] {#switching-experiences}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como a prioridade funciona em uma atividade **[!UICONTROL de Direcionamento de experiência]** e quando os visitantes alternam entre experiências à medida que seus perfis evoluem.

>[!ENDSHADEBOX]

Com o **[!UICONTROL Direcionamento de experiência]**, você pode controlar quais visitantes de experiência verão à medida que seus perfis evoluírem. O perfil de um visitante pode mudar de várias maneiras, e você pode querer apresentar conteúdo diferente com base nessas alterações. A tabela a seguir lista alguns exemplos:

| Cenário | Detalhes |
|--- |--- |
| Localização geográfica | Conforme os visitantes viajam a negócios ou a lazer, eles podem visualizar seu site ou aplicativo móvel em diferentes localizações geográficas. |
| Status do cliente | Os visitantes podem ser considerados clientes em potencial antes de criarem uma conta ou comprarem um produto. |
| Afinidade de categorias | O recurso [afinidade de categorias](/help/main/c-target/c-visitor-profile/category-affinity.md) em [!DNL Target] captura automaticamente as categorias que os visitantes visualizam e calcula a afinidade dos visitantes para cada categoria para fins de direcionamento. Por exemplo, os visitantes que visualizaram vários artigos em seu site sobre um assunto específico são apresentados com conteúdo relacionado a esse assunto. |
| Dias da semana | À medida que o fim de semana se aproxima, você pode querer mostrar aos visitantes um conteúdo sobre filmes, refeições ou outras formas de entretenimento. |

Para usar esses recursos no [!DNL Target], é importante entender as informações a seguir ao trabalhar com as atividades de **[!UICONTROL Direcionamento de experiência]**.

## Como os visitantes são atendidos {#how-visitors-are-served}

A ordem das experiências na interface do usuário do [!DNL Target], de cima para baixo, controla sua prioridade, portanto, defina a experiência mais direcionada antes da mais ampla. A tabela a seguir resume o que os visitantes veem em cada situação.

| Situação | O que o visitante vê |
|--- |--- |
| O visitante se qualifica para mais de um público-alvo. | O conteúdo da experiência que tem a prioridade mais alta. |
| O visitante começa a se qualificar para o público-alvo de uma experiência de prioridade mais alta. | O visitante alterna para a experiência de prioridade mais alta. |
| O visitante para de se qualificar para o público-alvo atual, mas começa a se qualificar para uma experiência de prioridade mais baixa. | O visitante alterna para a experiência de prioridade mais baixa. |
| O visitante para de se qualificar para a experiência atual e não se qualifica para outra experiência. | Conteúdo padrão. |
| O visitante não se qualificou para nenhuma outra experiência e a última experiência é direcionada para &quot;Todos os visitantes&quot;. | A experiência &quot;Todos os visitantes&quot;. Essa experiência &quot;captura&quot; os visitantes que não se qualificaram para nenhuma outra experiência. |
| Uma experiência direcionada para &quot;Todos os visitantes&quot; não é a última no pedido. | As experiências direcionadas listadas abaixo da experiência &quot;Todos os visitantes&quot; ainda são avaliadas. |
| A atividade tem uma única experiência e o visitante deixa de se qualificar para seu público-alvo. | O visitante permanece na experiência. |

## Exemplos {#examples}

Os exemplos a seguir ilustram essas situações.

### Prioridade: Nova York e Estados Unidos

Se você tiver duas experiências, uma direcionada para &quot;Estados Unidos&quot; e outra para &quot;Nova York&quot;, um visitante localizado em Nova York se qualifica para ambos os públicos-alvo. Portanto, você deve definir a experiência de &quot;Nova York&quot; antes da experiência de &quot;Estados Unidos&quot; na interface do usuário do [!DNL Target]. Essa prática garante que a experiência mais direcionada de &quot;Nova York&quot; tenha a prioridade mais alta, conforme mostrado no exemplo a seguir:

![Prioridade de NY > EUA](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-refresh.png)

### Mudança para uma experiência de prioridade mais alta: Estados Unidos para Alemanha

Na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a Alemanha e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante se qualificou para a Experiência A (visitante dos EUA). Após visualizar o seu site na Alemanha, esse visitante mudou para a Experiência B (visitante da Alemanha).

![Prioridade dos EUA > Alemanha](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

### Deixando a audiência: Estados Unidos para a França

Na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a França e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante se qualificou para a Experiência A (visitante dos EUA). Após visualizar o seu site na França, esse visitante permanece na experiência original.

![Prioridade dos EUA > Alemanha, visitante da França](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

### Experiência direcionada para todos os visitantes

Na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a Alemanha e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante se qualificou para a Experiência A (visitante dos EUA). Após visualizar o seu site na Alemanha, esse visitante permanece na Experiência A (visitante dos EUA).

![Prioridade dos EUA > Todos os visitantes](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-refresh.png)

Se isso não for desejado, você poderá criar um novo público-alvo que seja explicitamente definido como o inverso de seu público-alvo direcionado, conforme mostrado no exemplo a seguir:

![Prioridade dos EUA > Não EUA](/help/main/c-activities/t-experience-target/t-xt-create/assets/not-us.png)

### Atividade de experiência única

Com uma atividade de experiência única **[!UICONTROL Direcionamento de experiência]**, os visitantes permanecem em uma experiência mesmo que deixem de se qualificar para o público-alvo que os colocou nessa experiência. Se isso não for desejado, você poderá criar outra experiência direcionada para o público-alvo inverso (por exemplo, &quot;Não dos Estados Unidos&quot;, em vez de &quot;Estados Unidos&quot;). Como outra opção, você pode criar uma atividade de **[!UICONTROL Teste A/B]** direcionada ao seu público-alvo desejado com 100% de alocação de tráfego, como mostrado no exemplo a seguir:

![Prioridade de uma experiência](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-refresh.png)
