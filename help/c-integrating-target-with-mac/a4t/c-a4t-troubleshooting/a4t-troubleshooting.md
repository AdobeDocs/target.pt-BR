---
keywords: analytics tracking server;A4T;analytics segments;report suites;incorrect data;orphaned;sdid;VisitorAPI.js;mboxMCSDID;phantom;unspecified
description: Este tópico aborda alguns problemas comuns encontrados durante o uso do Analytics como a fonte de geração de relatórios para o Target (A4T).
title: Solução de problemas de integração do Analytics e do Target (A4T)
feature: a4t troubleshooting
subtopic: Multivariate Test
topic: Standard
uuid: a5aa3be5-68a2-4f12-8226-f32a76136bbd
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 100%

---


# Solução de problemas na integração do Analytics e do Target (A4T){#troubleshoot-the-analytics-and-target-integration-a-t}

Este tópico aborda alguns problemas comuns encontrados durante o uso do Analytics como a fonte de geração de relatórios para o Target (A4T).

## As atividades não mostram dados no Analytics, mas são listadas como &quot;não especificadas&quot;.{#unspecified}

Existem várias razões pelas quais isso pode acontecer:

* A classificação no [!DNL Target] não foi completamente processada.

   A classificação geralmente leva entre 24 e 72 horas para relatórios após a primeira gravação.

* O conjunto de relatórios não contém nenhum dado, mas o [!DNL Target] tentou classificar os hits. O [!DNL Target] não pode classificar os dados até que o primeiro hit ocorra.

   Verifique se o conjunto de relatórios teve pelo menos um hit.

* Houve falha na chamada de classificação do [!DNL Target] para o [!DNL Analytics].

   [Entre em contato com o Atendimento ao cliente](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para obter assistência.

>[!NOTE]
>
>Às vezes, os dados são exibidos corretamente nos relatórios, mas depois são revertidos para &quot;não especificados&quot; porque foi adicionada uma nova atividade que não concluiu a classificação. Lembre-se de que a classificação geralmente leva entre 24 e 72 horas para relatórios após a primeira gravação.
>
>Nenhum dado é perdido quando listado como &quot;não especificado&quot;. Os dados são adequadamente atribuídos à atividade ou experiência apropriada após a execução da classificação.

## Meus dados do Analytics mostram uma contagem aumentada de visitas ou visitantes desde o início do A4T.  {#section_4BE374E573D44FB7918611699B74F58E}

Para obter mais informações, consulte [Redução de visitas aumentadas e contagem de visitantes em A4T](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## O aumento estimado na métrica da receita não está mostrando os dados corretos. {#section_35D766E5E4D347C39E15D08AA883FBB0}

Os detalhes de incentivo e confiança não estão disponíveis no Analytics. No entanto, eles estão disponíveis nos relatórios do Target.

## As atividades não aparecem nos relatórios do Analytics.  {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

As atividades do A4T exigem que um servidor de rastreamento de análise seja especificado. Consulte [Uso do Servidor de rastreamento de análise](../../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para certificar-se de que seu Servidor de rastreamento de análise está configurado corretamente.

>[!NOTE]
>
>Se você usar o Adobe Analytics como a fonte de relatórios da sua atividade, não será necessário especificar um servidor de rastreamento durante a criação da atividade usando a mbox.js versão 61 (ou posterior) ou a at.js versão 0.9.1 (ou posterior). A biblioteca mbox.js ou at.js envia automaticamente os valores do servidor de rastreamento ao [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Servidor de rastreamento] em branco na página [!UICONTROL Metas e configurações].

## Meus segmentos do Analytics não aparecem no Target.  {#section_DEE87F1557834F448E99381D3D02EEEF}

Verifique se você tem as permissões certas antes de começar a criar atividades do A4T:

* Você deve fazer parte do grupo de acesso a serviços da Web no Adobe Analytics para usar o Analytics como a fonte de geração de relatórios para o Target.
* Você deve ser um membro de um ou mais grupos da Experience Cloud com acesso ao Analytics e Target.
* Verifique se o Analytics e Target são exibidos na seção Marketing Apps da navegação à esquerda.

## Taxas de rejeição, rejeições e métricas de saída aparecem como positivas nos relatórios.  {#section_B5C3D56EF0344407AE67ABEB93037F5A}

Esse é um problema conhecido.

Apesar de essas métricas serem negativas, o incentivo é mostrado como se elas fossem positivas nos relatórios do Target. Por exemplo, mesmo que você queira uma taxa de rejeição mais baixa, a taxa de rejeição mais alta é mostrada como vencedora com o maior incentivo. Considere essas métricas de métricas semelhantes, bem como sua preferência por diminuir ou aumentar os números, ao tomar decisões baseadas nos relatórios.

## O conjunto de relatórios de que preciso não aparece.  {#section_BD8F956E41D6475B98B7BF0C74CC387C}

A lista de conjuntos de relatórios que aparece no Target Standard/Premium é a lista de conjuntos de relatórios que foram configurados para o Analytics com a fonte de geração de relatórios para o Target. Isso significa que você pode não ver todos os seus conjuntos de relatórios. Caso não veja o conjunto de relatórios que você está procurando, entre em contato com o Atendimento ao cliente para ativá-lo.

## Não vejo tantos dados nos relatórios quanto esperado.  {#section_75002584FA63456D8D9086172925DD8D}

Revise sua implementação, especialmente em páginas nas quais seus visitantes se qualificam para experiências e garanta que as IDs de dados complementares correspondam às chamadas do [!DNL Target] e do [!DNL Analytics]. Na chamada do [!DNL Target], a ID complementar está contida no parâmetro `mboxMCSDID`. Na chamada do [!DNL Analytics], a ID complementar está contida no parâmetro `sdid`.

Se não houver uma ID de dados complementar na chamada do [!DNL Target], confirme se o arquivo [!DNL VisitorAPI.js] foi carregado antes da [!DNL at.js] ou da [!DNL mbox.js]. Se não houver uma ID de dados complementar na chamada do [!DNL Analytics], confirme se a chamada do [!DNL Target] é acionada antes da chamada do [!DNL Analytics].

Para obter mais informações, consulte [Implementação do Analytics para Target](../../../c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A) ou entre em contato com o [Atendimento ao cliente](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).