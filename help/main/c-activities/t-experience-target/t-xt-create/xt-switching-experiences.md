---
keywords: prioridade; criação de experiência; prioridade; experiência; público-alvo; experiência; troca de experiências; visual experience composer
description: Saiba como os visitantes podem alternar entre experiências em uma [!DNL Adobe Target] [!UICONTROL Direcionamento de experiência] (XT) à medida que seus perfis evoluem.
title: Os visitantes podem alternar experiências em um [!UICONTROL Direcionamento de experiência] Atividade?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: 0dfdd995c00961ed2aed91ec03406e8493292af7
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 44%

---

# Troca de experiências no [!UICONTROL Direcionamento de experiência]

Com [!UICONTROL Direcionamento de experiência], você pode controlar quais experiências os visitantes verão à medida que seus perfis evoluírem.

A lista a seguir apresenta apenas alguns cenários nos quais os perfis dos visitantes podem evoluir e você pode apresentar conteúdo diferente com base nessas alterações:

| Cenário | Detalhes |
|--- |--- |
| Localização geográfica | Conforme os visitantes viajam a negócios ou a lazer, eles podem visualizar seu site ou aplicativo móvel em diferentes localizações geográficas. |
| Status do cliente | Os visitantes podem ser considerados clientes em potencial antes de criarem uma conta ou comprarem um produto. |
| Afinidade de categorias | A configuração [afinidade de categorias](/help/main/c-target/c-visitor-profile/category-affinity.md) recurso no [!DNL Target] captura automaticamente a visualização de categorias de visitantes e calcula a afinidade dos visitantes com a categoria para fins de direcionamento. Por exemplo, os visitantes que visualizaram vários artigos em seu site sobre um assunto específico são apresentados com conteúdo relacionado a esse assunto. |
| Dias da semana | À medida que o fim de semana se aproxima, você pode querer mostrar aos visitantes um conteúdo sobre filmes, refeições ou outras formas de entretenimento. |

Para usar esses recursos no [!DNL Target], é importante compreender as seguintes informações ao trabalhar com o [!UICONTROL Direcionamento de experiência] atividades:

* **A prioridade é controlada pela ordem das experiências, de cima para baixo.** Se um visitante se qualificar para mais de dois públicos-alvo, ele receberá conteúdo da experiência de prioridade mais alta.
* **Os visitantes alternam entre experiências em um [!UICONTROL Direcionamento de experiência] atividade se começarem a se qualificar para o público-alvo de uma experiência de prioridade mais alta.**

  Por exemplo, na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a Alemanha e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante se qualificou para a Experiência A (visitante dos EUA). Após visualizar o seu site na Alemanha, esse visitante mudou para a Experiência B (visitante da Alemanha).

  ![Prioridade dos EUA > Alemanha](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Os visitantes também alternam entre experiências se deixarem de se qualificar para seu público-alvo atual, mas começarem a se qualificar para uma experiência de prioridade mais baixa.**
* **Se os visitantes deixarem de se qualificar para sua experiência atual e não se qualificarem para outra experiência, verão o conteúdo padrão.**

  Por exemplo, na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a França e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante se qualificou para a Experiência A (visitante dos EUA). Após visualizar o seu site na França, esse visitante permanece na experiência original.

  ![Prioridade dos EUA > Alemanha](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Uma experiência direcionada para &quot;Todos os visitantes&quot; pode ser usada como a última experiência no [!UICONTROL Direcionamento de experiência] atividade para &quot;capturar&quot; todos os visitantes que não se qualificaram para nenhuma outra experiência. Se uma experiência direcionada para &quot;Todos os visitantes&quot; não for a última na ordem, outras experiências direcionadas listadas abaixo dessa experiência ainda serão avaliadas.**

  Por exemplo, na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a Alemanha e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante se qualificou para a Experiência A (visitante dos EUA). Após visualizar o seu site na Alemanha, esse visitante permanece na Experiência A (visitante dos EUA).

  ![Prioridade dos EUA > Todos os visitantes](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

  Se isso não for desejado, você poderá criar um novo público-alvo que seja explicitamente definido como o inverso de seu público-alvo direcionado, conforme mostrado no exemplo a seguir:

  ![Prioridade dos EUA > Não EUA](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **Com uma única experiência [!UICONTROL Direcionamento de experiência] atividade, os visitantes permanecem em uma experiência mesmo que deixem de se qualificar para o público-alvo que os colocou nessa experiência.**

  Se isso não for desejado, você poderá criar outra experiência direcionada para o público-alvo inverso (por exemplo, &quot;Não dos Estados Unidos&quot;, em vez de &quot;Estados Unidos&quot;).

  Como outra opção, você pode criar um [!UICONTROL Teste A/B] atividade direcionada para o público-alvo desejado com 100% de alocação de tráfego, conforme mostrado abaixo:

  ![Prioridade de uma experiência](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **[!DNL Target]A prioridade das experiências é definida por sua ordem (de cima para baixo), conforme exibida na interface do usuário do .**

  Isso é importante em cenários em que um visitante pode se qualificar para mais de um de seus públicos-alvo. Por exemplo, se você tiver duas experiências: uma direcionada para &quot;Estados Unidos&quot; e outra para &quot;Nova York&quot;, um visitante localizado em Nova York se qualifica para ambos os públicos-alvo. Portanto, você deve garantir que a experiência de &quot;Nova York&quot; seja definida antes da experiência dos &quot;Estados Unidos&quot; na [!DNL Target] IU. Essa prática garante que a experiência mais direcionada de &quot;Nova York&quot; tenha a prioridade mais alta, conforme mostrado no exemplo a seguir:

  ![Prioridade de NY > EUA](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)
