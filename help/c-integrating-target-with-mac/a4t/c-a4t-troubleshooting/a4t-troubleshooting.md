---
keywords: servidor de rastreamento de análises; A4T; segmentos de análise; conjuntos de relatórios; dados incorretos; órfão; sdid; VisitorAPI.js; mboxMCSDID; fictício; não especificado
description: Explore problemas comuns que os clientes encontraram ao usar o Analytics for Target (A4T).
title: Como soluciono problemas na integração do Analytics e do Target (A4T)
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: f48c54eb12a416312c3ceb6c1b36c3fc43496e78
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 42%

---


# Solução de problemas de integração do Analytics e do Target (A4T)

Este tópico aborda alguns problemas comuns encontrados ao usar [!DNL Adobe Analytics] como a fonte de relatórios para [!DNL Adobe Target] (A4T).

## As atividades não mostram dados no Analytics, mas são listadas como &quot;não especificadas&quot;.{#unspecified}

Há vários motivos pelos quais dados exibidos como &quot;não especificados&quot; podem ocorrer:

* A classificação no [!DNL Target] não foi completamente processada.

   A classificação geralmente leva de 24 a 72 horas para relatórios após a primeira gravação.

* O conjunto de relatórios não contém nenhum dado, mas o [!DNL Target] tentou classificar os hits. O [!DNL Target] não pode classificar os dados até que o primeiro hit ocorra.

   Verifique se o conjunto de relatórios teve pelo menos um hit.

* Houve falha na chamada de classificação do [!DNL Target] para o [!DNL Analytics].

   [Entre em contato com o Atendimento ao cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para obter assistência.

Se você analisar a linha &quot;não especificado&quot; pela dimensão &quot;Analytics for Target&quot; e ela não consistir em IDs de atividade, significa que tudo está classificado corretamente. Se as ids de atividade estiverem listadas lá, elas servirão como indicação para um problema de classificação.

>[!NOTE]
>
>Às vezes, os dados são exibidos corretamente nos relatórios, mas depois são revertidos para &quot;não especificados&quot; porque foi adicionada uma nova atividade que não concluiu a classificação. Lembre-se de que geralmente leva de 24 a 72 horas para classificar relatórios após a primeira gravação.
>
>Nenhum dado é perdido quando listado como &quot;não especificado&quot;. Os dados são adequadamente atribuídos à atividade ou experiência apropriada após a execução da classificação.

## Os relatórios de atividade do A4T incluem uma linha com muitos eventos &quot;não especificados&quot;. {#added_unspecified_events}

Pode haver uma linha de eventos &quot;[!UICONTROL Não especificado]&quot; mostrada no relatório, dependendo da métrica usada para exibir seus dados.

Normalmente, essa linha é exibida se você escolher uma métrica comum no relatório que não seja [!DNL Target] específica (por exemplo, [!UICONTROL Exibições de página], [!UICONTROL Visitas], [!UICONTROL Visitantes únicos] e assim por diante). Nesse caso, a linha [!UICONTROL &quot;Não especificado&quot;] inclui todas as [!UICONTROL Exibições de página], [!UICONTROL Visitas] e [!UICONTROL Visitantes únicos] que não estão associados a atividades [!DNL Target].

Essa linha não terá nenhuma informação [!DNL Target] associada (por exemplo, nenhum visitante, visita ou impressões). Para obter mais informações, consulte [&quot;Não especificado&quot;, &quot;Nenhum&quot;, &quot;Outros&quot; e &quot;Desconhecido&quot; no relatório](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=en) nas *Notas técnicas do Analytics*.

Se você escolher uma métrica específica de [!DNL Target] no relatório, essa linha [!UICONTROL &quot;Não especificado&quot;] não será exibida. A única maneira de evitar tê-lo no relatório é definir uma chamada [!DNL Target] em cada solicitação enviada dessa página, o que não é comum ou necessário.

## Meus dados do Analytics mostram uma contagem aumentada de visitas ou visitantes desde o início do A4T.   {#section_4BE374E573D44FB7918611699B74F58E}

Para obter mais informações, consulte [Redução de visitas aumentadas e contagem de visitantes em A4T](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## O aumento estimado na métrica da receita não está mostrando os dados corretos. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Os detalhes de incentivo e confiança não estão disponíveis no Analytics. No entanto, eles estão disponíveis nos relatórios do Target.

## As atividades não aparecem nos relatórios do Analytics.   {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

As atividades do A4T exigem que um servidor de rastreamento de análise seja especificado. Consulte  [Usar um ](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) servidor de rastreamento do Analytics para certificar-se de que seu servidor de rastreamento do Analytics está configurado corretamente.

>[!NOTE]
>
>Você não precisa especificar um servidor de rastreamento durante a criação da atividade se estiver usando a mbox.js versão 61 (ou posterior) ou a at.js versão 0.9.1 (ou posterior). A biblioteca mbox.js ou at.js envia automaticamente os valores do servidor de rastreamento ao [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Servidor de rastreamento] em branco na página [!UICONTROL Metas e configurações].

## Meus segmentos do Analytics não aparecem no Target.   {#section_DEE87F1557834F448E99381D3D02EEEF}

Verifique se você tem as permissões certas antes de começar a criar atividades do A4T:

* Pertencer ao grupo de acesso a serviços da Web no Adobe Analytics para poder usar o Analytics como a fonte de relatórios do Target
* Ser membro de um ou mais grupos da Experience Cloud que têm acesso ao Analytics e ao Target.
* Verifique se o Analytics e Target são exibidos na seção Marketing Apps da navegação à esquerda.

## Taxas de rejeição, rejeições e métricas de saída aparecem como positivas nos relatórios.   {#section_B5C3D56EF0344407AE67ABEB93037F5A}

Essas métricas que aparecem como positivas nos relatórios são um problema conhecido.

Apesar de essas métricas serem negativas, o incentivo é mostrado como se elas fossem positivas nos relatórios do Target. Por exemplo, mesmo que você queira uma taxa de rejeição mais baixa, a taxa de rejeição mais alta é mostrada como vencedora com o maior incentivo. Considere essas métricas de métricas semelhantes, bem como sua preferência por diminuir ou aumentar os números, ao tomar decisões baseadas nos relatórios.

## O conjunto de relatórios de que preciso não é exibido. {#section_BD8F956E41D6475B98B7BF0C74CC387C}

A lista de conjuntos de relatórios que aparece em [!DNL Target Standard/Premium] é a lista de conjuntos de relatórios que foram configurados para [!DNL Analytics] como fonte de relatórios para [!DNL Target] (A4T). Talvez você não veja todos os conjuntos de relatórios que possui.

Se você estiver usando várias fontes de relatórios, os conjuntos de relatórios também deverão estar presentes na fonte de relatórios padrão definida em [!DNL Target]. Se os conjuntos de relatórios não estiverem na fonte de relatórios padrão, eles não serão exibidos.

Se você ainda não vir o conjunto de relatórios que está procurando, entre em contato com o [Atendimento ao cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para ativá-lo.

## Não vejo tantos dados nos relatórios quanto esperado.   {#section_75002584FA63456D8D9086172925DD8D}

Revise sua implementação, especialmente em páginas nas quais seus visitantes se qualificam para experiências e garanta que as IDs de dados complementares correspondam às chamadas do [!DNL Target] e do [!DNL Analytics]. 

* **at.js 1.x**: Na  [!DNL Target] chamada do , a ID complementar está contida no  `mboxMCSDID` parâmetro . Na chamada do [!DNL Analytics], a ID complementar está contida no parâmetro `sdid`.
* **at.js 2.x**: Na  [!DNL Target] chamada , a ID complementar é retornada no cabeçalho HTTP como o valor de  `experienceCloud.analytics.supplementalDataId`. Na chamada do [!DNL Analytics], a ID complementar está contida no parâmetro `sdid`.

A maneira mais fácil de examinar a ID complementar é usando o Adobe Experience Platform Debugger.

Se você não tiver instalado o depurador, consulte [Introdução ao Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

![Depurador](/help/c-integrating-target-with-mac/a4t/assets/debugger.png)

Se não houver uma ID de dados complementar na chamada do [!DNL Target], confirme se o arquivo [!DNL VisitorAPI.js] foi carregado antes da [!DNL at.js] ou da [!DNL mbox.js]. Se não houver uma ID de dados complementar na chamada do [!DNL Analytics], confirme se a chamada do [!DNL Target] é acionada antes da chamada do [!DNL Analytics].

Para obter mais informações, consulte [Implementação do Analytics para Target](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) ou entre em contato com o [Atendimento ao cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
