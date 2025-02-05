---
keywords: prioridade; criação de experiência; prioridade; experiência; público-alvo; experiência; troca de experiências; visual experience composer
description: Saiba como os visitantes podem alternar entre experiências em uma atividade  [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT) conforme seus perfis evoluem.
title: Os visitantes podem trocar experiências em uma atividade [!UICONTROL Experience Targeting]?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 43%

---

# Alternando experiências no [!UICONTROL Experience Targeting]

Com o [!UICONTROL Experience Targeting], você pode controlar quais experiências os visitantes verão à medida que seus perfis evoluírem.

A lista a seguir apresenta apenas alguns cenários nos quais os perfis dos visitantes podem evoluir e você pode apresentar conteúdo diferente com base nessas alterações:

| Cenário | Detalhes |
|--- |--- |
| Localização geográfica | Conforme os visitantes viajam a negócios ou a lazer, eles podem visualizar seu site ou aplicativo móvel em diferentes localizações geográficas. |
| Status do cliente | Os visitantes podem ser considerados clientes em potencial antes de criarem uma conta ou comprarem um produto. |
| Afinidade de categorias | O recurso [afinidade de categorias](/help/main/c-target/c-visitor-profile/category-affinity.md) em [!DNL Target] captura automaticamente a exibição de categorias de visitantes e calcula a afinidade de visitantes com a categoria para fins de direcionamento. Por exemplo, os visitantes que visualizaram vários artigos em seu site sobre um assunto específico são apresentados com conteúdo relacionado a esse assunto. |
| Dias da semana | À medida que o fim de semana se aproxima, você pode querer mostrar aos visitantes um conteúdo sobre filmes, refeições ou outras formas de entretenimento. |

Para usar esses recursos no [!DNL Target], é importante compreender as seguintes informações ao trabalhar com as atividades do [!UICONTROL Experience Targeting]:

* **A prioridade é controlada pela ordem das experiências, de cima para baixo.** Se um visitante se qualificar para mais de dois públicos-alvo, ele receberá conteúdo da experiência de prioridade mais alta.
* **Os visitantes alternarão entre experiências em uma atividade [!UICONTROL Experience Targeting] se começarem a se qualificar para o público-alvo de uma experiência de prioridade mais alta.**

  Por exemplo, na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a Alemanha e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante se qualificou para a Experiência A (visitante dos EUA). Após visualizar o seu site na Alemanha, esse visitante mudou para a Experiência B (visitante da Alemanha).

  ![Prioridade dos EUA > Alemanha](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

* **Os visitantes também alternarão entre experiências se deixarem de se qualificar para seu público atual, mas começarem a se qualificar para uma experiência de prioridade mais baixa.**
* **Se os visitantes deixarem de se qualificar para sua experiência atual e não se qualificarem para outra experiência, verão o conteúdo padrão.**

  Por exemplo, na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a França e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante se qualificou para a Experiência A (visitante dos EUA). Após visualizar o seu site na França, esse visitante permanece na experiência original.

  ![Prioridade dos EUA > Alemanha](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-refresh.png)

* **Uma experiência direcionada para &quot;Todos os visitantes&quot; pode ser usada como a última experiência na atividade [!UICONTROL Experience Targeting] para &quot;capturar&quot; todos os visitantes que não se qualificaram para nenhuma outra experiência. Se uma experiência direcionada para &quot;Todos os visitantes&quot; não for a última na ordem, outras experiências direcionadas listadas abaixo dessa experiência ainda serão avaliadas.**

  Por exemplo, na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a Alemanha e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante se qualificou para a Experiência A (visitante dos EUA). Após visualizar o seu site na Alemanha, esse visitante permanece na Experiência A (visitante dos EUA).

  ![Prioridade dos EUA > Todos os visitantes](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-refresh.png)

  Se isso não for desejado, você poderá criar um novo público-alvo que seja explicitamente definido como o inverso de seu público-alvo direcionado, conforme mostrado no exemplo a seguir:

  ![Prioridade dos EUA > Não EUA](/help/main/c-activities/t-experience-target/t-xt-create/assets/not-us.png)

* **Com uma atividade [!UICONTROL Experience Targeting] de experiência única, os visitantes permanecem em uma experiência mesmo que deixem de se qualificar para o público-alvo que os colocou nessa experiência.**

  Se isso não for desejado, você poderá criar outra experiência direcionada para o público-alvo inverso (por exemplo, &quot;Não dos Estados Unidos&quot;, em vez de &quot;Estados Unidos&quot;).

  Como outra opção, você pode criar uma atividade do [!UICONTROL A/B Test] direcionada para o seu público-alvo desejado com 100% de alocação de tráfego, conforme mostrado abaixo:

  ![Prioridade de uma experiência](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-refresh.png)

* **A prioridade das experiências é definida por sua ordem (de cima para baixo), conforme exibida na interface do usuário do [!DNL Target].**

  Isso é importante em cenários em que um visitante pode se qualificar para mais de um de seus públicos-alvo. Por exemplo, se você tiver duas experiências: uma direcionada para &quot;Estados Unidos&quot; e outra para &quot;Nova York&quot;, um visitante localizado em Nova York se qualifica para ambos os públicos-alvo. Portanto, você deve garantir que a experiência de &quot;Nova York&quot; seja definida antes da experiência de &quot;Estados Unidos&quot; na interface do usuário do [!DNL Target]. Essa prática garante que a experiência mais direcionada de &quot;Nova York&quot; tenha a prioridade mais alta, conforme mostrado no exemplo a seguir:

  ![Prioridade de NY > EUA](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-refresh.png)
