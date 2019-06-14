---
description: Informações sobre como visitantes podem alternar entre experiências em uma atividade de Direcionamento de experiência (XT) conforme seus perfis evoluem.
keywords: prioridade; criação de experiência; prioridade; experiência; público-alvo; experiência; troca de experiências; visual experience composer
seo-description: Informações sobre como visitantes podem alternar entre experiências em uma atividade de Direcionamento de experiência (XT) conforme seus perfis evoluem.
seo-title: Troca de experiências no Direcionamento de experiência
solution: Target
title: Troca de experiências no Direcionamento de experiência
topic: Advanced,Standard,Classic
uuid: a4fa4cf0-509c-4c31-a778-09c5edacc9b0
translation-type: tm+mt
source-git-commit: ca9639ccca286dac182728f7bbd43fac78217209

---


# Alternar experiências em direcionamento de experiência{#switching-experiences-in-experience-targeting}

Informações sobre como visitantes podem alternar entre experiências em uma atividade de Direcionamento de experiência (XT) conforme seus perfis evoluem.

>[!NOTE]
>
>**21 de setembro de 2017**
>
>Com o lançamento em 21 de setembro de 21 17, o Target alterou a maneira como os usuários são colocados em experiências nas atividades de direcionamento de experiência (XT) (campanhas de página de aterrissagem no Target Classic). Para todas as atividades novas e existentes, os usuários devem atender às regras de direcionamento da experiência em cada impressão para continuar a ver o conteúdo da experiência e serem contados nos relatórios. Anteriormente, se o usuário não se qualificasse mais para alguma experiência, ele continuaria a ver o conteúdo e a ser contabilizado nos relatórios para a última experiência pela qual se qualificou.
>
>Essa alteração ocorria automaticamente como parte da versão de todas as atividades existentes e para quaisquer atividades novas criadas após a publicação. Se o método anterior (anterior a 21 de setembro) for desejado, você poderá criar públicos-alvo usando scripts de perfil; assim, um usuário só precisa atender a uma condição uma vez para continuar a se enquadrar nesse público-alvo no futuro. Em seguida, use esses públicos-alvo para cada experiência na atividade.

Com o Direcionamento de experiência, você pode controlar qual experiência é vista pelos visitantes, à medida que seus perfis evoluem. A lista a seguir apresenta apenas alguns cenários em que os perfis dos visitantes podem evoluir e você pode querer apresentar um conteúdo diferente:

| Cenário | Detalhes |
|--- |--- |
| Localização geográfica | Conforme os visitantes viajam a negócios ou a lazer, eles podem visualizar seu site ou aplicativo móvel em diferentes localizações geográficas. |
| Status do cliente | Os visitantes podem ser considerados clientes em potencial antes de criarem uma conta ou comprarem um produto. |
| Afinidade de categorias | A configuração [o recurso afinidade de categorias](/help/c-target/c-visitor-profile/category-affinity.md) no Target captura automaticamente as categorias visitadas pelos usuários e calcula as afinidades do usuário com a categoria para fins de direcionamento. Por exemplo, os visitantes que visualizaram vários artigos no seu site sobre um assunto específico poderiam receber um conteúdo relacionado a esse assunto. |
| Dias da semana | À medida que o fim de semana se aproxima, você pode querer mostrar aos visitantes um conteúdo sobre filmes, refeições ou outras formas de entretenimento. |

Para aproveitar esses recursos no [!DNL Target], é importante compreender as seguintes informações ao trabalhar com as atividades do XT:

* **A prioridade é controlada pela ordem das experiências, de cima para baixo.** Se um visitante se qualificar para mais de dois públicos-alvo, ele receberá um conteúdo da experiência com prioridade mais alta.
* **Caso os visitantes comecem a se qualificar para o público-alvo de uma experiência com prioridade mais alta, eles alternarão entre experiências em uma atividade do XT.**

   Por exemplo, na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a Alemanha e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante qualificado para Experiência A (visitantes dos EUA). Após visualizar seu site da Alemanha, este visitante alternou para a Experiência B (visitantes alemães).

   ![Prioridade dos EUA &gt; Alemanha](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Os visitantes também alternarão entre experiências se deixarem de se qualificar para o seu público-alvo atual, mas começarem a se qualificar para uma experiência com baixa prioridade.**
* **Se os visitantes deixarem de se qualificar para a experiência atual e não se qualificarem para outra experiência, eles verão o conteúdo padrão.**

   Por exemplo, na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a França e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante qualificado para Experiência A (visitantes dos EUA). Após visualizar o seu website da França, esse visitante permanecerá na experiência original.

   ![Prioridade dos EUA &gt; Alemanha](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_germany-new.png)

* **Uma experiência direcionada para &quot;Todos os visitantes&quot; pode ser usada como a última experiência na atividade de direcionamento de experiência para &quot;capturar&quot; todos os visitantes que não se enquadram em nenhuma outra experiência. Se uma experiência direcionada para &quot;Todos os visitantes&quot; não for a última na ordem, outras experiências direcionadas, listadas abaixo dessa, ainda serão avaliadas.**

   Por exemplo, na configuração de atividade a seguir, um visitante acessou o seu site dos Estados Unidos e depois viajou para a Alemanha e visitou o seu site uma segunda vez. Durante a primeira visita, este visitante qualificado para Experiência A (visitantes dos EUA). Depois de visualizar seu site da Alemanha, este visitante permanecerá na Experiência A (visitantes dos EUA).

   ![Prioridade dos EUA &gt; Todos os visitantes](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_all_visitors-new.png)

   Se isso não for desejado, você poderá criar um novo público-alvo que seja explicitamente definido como o inverso de seu público-alvo direcionado, conforme mostrado no exemplo a seguir:

   ![Prioridade US &gt; Não US](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_us_not_us-new.png)

* **Com uma atividade do XT de experiência única, os visitantes permanecerão em uma experiência, mesmo que deixem de se qualificar para o público-alvo que os colocou nessa experiência.**

   Se isso não for desejado, você poderá criar outra experiência direcionada para o público-alvo inverso (por exemplo, &quot;Não dos Estados Unidos&quot;, em vez de &quot;Estados Unidos&quot;).

   Como outra opção, você pode criar uma atividade de A/B direcionada para o seu público-alvo desejado com 100% de alocação de tráfego, conforme mostrado abaixo:

   ![Prioridade uma experiência](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_one_experience-new.png)

* **A prioridade das experiências é definida por sua ordem (de cima para baixo), conforme exibida na interface do usuário do Target.**

   Isso é importante em cenários em que um visitante pode se qualificar para mais de um de seus públicos-alvo. Por exemplo, se você tiver duas experiências: uma direcionada para os &quot;Estados Unidos&quot; e outra para &quot;Nova York&quot;, um visitante localizado em Nova York se qualificará para os dois públicos-alvo. Portanto, você deve garantir que a experiência de &quot;Nova York&quot; seja definida antes da experiência de &quot;Estados Unidos&quot; na interface do usuário do Target. Isso garante que quanto mais segmentada é a experiência de &quot;Nova York&quot;, mas alta é a prioridade, conforme mostrado no exemplo a seguir:

   ![Priority NY &gt; US](/help/c-activities/t-experience-target/t-xt-create/assets/xt_priority_ny_us-new.png)

