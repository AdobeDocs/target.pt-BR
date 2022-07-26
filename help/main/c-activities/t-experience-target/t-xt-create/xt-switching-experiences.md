---
keywords: prioridade; criação de experiência; prioridade; experiência; público-alvo; experiência; troca de experiências; visual experience composer
description: Saiba como os visitantes podem alternar entre experiências em um Adobe [!DNL Target] Atividade de Direcionamento de experiência (XT) conforme seus perfis evoluem.
title: Os visitantes podem trocar experiências em uma atividade de direcionamento de experiência?
feature: Experience Targeting
exl-id: 8d931764-8ba7-4eac-99db-60659086b8be
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 97%

---

# Troca de experiências no Direcionamento de experiência

Informações sobre como visitantes podem alternar entre experiências em uma atividade de Direcionamento de experiência (XT) conforme seus perfis evoluem.

>[!NOTE]
>
>**21 de setembro de 2017**
>
>Com o lançamento em 21 de setembro de 2017, o Target mudou a maneira como os usuários são adicionados às experiências nas atividades de Direcionamento de experiência (XT) (campanhas de landing page no Target Classic). Para todas as atividades novas e existentes, os usuários devem atender às regras de direcionamento de experiência em todas as impressões para continuarem visualizando o conteúdo da experiência e serem contabilizados nos relatórios. Anteriormente, se o usuário não se qualificasse mais para alguma experiência, ele continuaria a ver o conteúdo e a ser contabilizado nos relatórios para a última experiência pela qual se qualificou.
>
>Essa alteração ocorreu automaticamente como parte da versão para todas as atividades existentes e para quaisquer novas atividades criadas após o lançamento. Se o método anterior (anterior a 21 de setembro) for desejado, você poderá criar públicos-alvo usando scripts de perfil; assim, um usuário só precisa atender a uma condição uma vez para continuar a se enquadrar nesse público-alvo no futuro. Em seguida, use esses públicos-alvo para cada experiência na atividade.

Com o Direcionamento de experiência, você pode controlar qual experiência é vista pelos visitantes, à medida que seus perfis evoluem. A lista a seguir apresenta apenas alguns cenários em que os perfis dos visitantes podem evoluir e você pode querer apresentar um conteúdo diferente:

| Cenário | Detalhes |
|--- |--- |
| Localização geográfica | Conforme os visitantes viajam a negócios ou a lazer, eles podem visualizar seu site ou aplicativo móvel em diferentes localizações geográficas. |
| Status do cliente | Os visitantes podem ser considerados clientes em potencial antes de criarem uma conta ou comprarem um produto. |
| Afinidade de categorias | A configuração [o recurso afinidade de categorias](/help/main/c-target/c-visitor-profile/category-affinity.md) no Target captura automaticamente as categorias visitadas pelos usuários e calcula as afinidades do usuário com a categoria para fins de direcionamento. Por exemplo, os visitantes que visualizaram vários artigos no seu site sobre um assunto específico poderiam receber um conteúdo relacionado a esse assunto. |
| Dias da semana | À medida que o fim de semana se aproxima, você pode querer mostrar aos visitantes um conteúdo sobre filmes, refeições ou outras formas de entretenimento. |

Para aproveitar esses recursos no [!DNL Target], é importante compreender as seguintes informações ao trabalhar com as atividades do XT:

* **A prioridade é controlada pela ordem das experiências, de cima para baixo.** Se um visitante se qualificar para mais de dois públicos-alvo, ele receberá um conteúdo da experiência com prioridade mais alta.
* **Caso os visitantes comecem a se qualificar para o público-alvo de uma experiência com prioridade mais alta, eles alternarão entre experiências em uma atividade do XT.**

   Por exemplo, na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a Alemanha e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante se qualificou para a Experiência A (visitante dos EUA). Após visualizar o seu site na Alemanha, esse visitante mudou para a Experiência B (visitante da Alemanha).

   ![Prioridade dos EUA > Alemanha](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Os visitantes também alternarão entre experiências se deixarem de se qualificar para o seu público-alvo atual, mas começarem a se qualificar para uma experiência com baixa prioridade.**
* **Se os visitantes deixarem de se qualificar para a experiência atual e não se qualificarem para outra experiência, eles verão o conteúdo padrão.**

   Por exemplo, na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a França e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante se qualificou para a Experiência A (visitante dos EUA). Após visualizar o seu website da França, esse visitante permanecerá na experiência original.

   ![Prioridade dos EUA > Alemanha](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Uma experiência direcionada para &quot;Todos os visitantes&quot; pode ser usada como a última experiência na atividade de direcionamento de experiência para &quot;capturar&quot; todos os visitantes que não se enquadram em nenhuma outra experiência. Se uma experiência direcionada para &quot;Todos os visitantes&quot; não for a última na ordem, outras experiências direcionadas, listadas abaixo dessa, ainda serão avaliadas.**

   Por exemplo, na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a Alemanha e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante se qualificou para a Experiência A (visitante dos EUA). Após visualizar o seu site na Alemanha, esse visitante permanecerá na Experiência A (visitante dos EUA).

   ![Prioridade dos EUA > Todos os visitantes](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

   Se isso não for desejado, você poderá criar um novo público-alvo que seja explicitamente definido como o inverso de seu público-alvo direcionado, conforme mostrado no exemplo a seguir:

   ![Prioridade dos EUA > Não EUA](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **Com uma atividade do XT de experiência única, os visitantes permanecerão em uma experiência, mesmo que deixem de se qualificar para o público-alvo que os colocou nessa experiência.**

   Se isso não for desejado, você poderá criar outra experiência direcionada para o público-alvo inverso (por exemplo, &quot;Não dos Estados Unidos&quot;, em vez de &quot;Estados Unidos&quot;).

   Como outra opção, você pode criar uma atividade de A/B direcionada para o seu público-alvo desejado com 100% de alocação de tráfego, conforme mostrado abaixo:

   ![Prioridade de uma experiência](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **A prioridade das experiências é definida por sua ordem (de cima para baixo), conforme exibida na interface do usuário do Target.**

   Isso é importante em cenários em que um visitante pode se qualificar para mais de um de seus públicos-alvo. Por exemplo, se você tiver duas experiências: uma direcionada para os &quot;Estados Unidos&quot; e outra para &quot;Nova York&quot;, um visitante localizado em Nova York se qualificará para os dois públicos-alvo. Portanto, você deve garantir que a experiência de &quot;Nova York&quot; seja definida antes da experiência de &quot;Estados Unidos&quot; na interface do usuário do Target. Isso garante que quanto mais segmentada é a experiência de &quot;Nova York&quot;, mas alta é a prioridade, conforme mostrado no exemplo a seguir:

   ![Prioridade de NY > EUA](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)
