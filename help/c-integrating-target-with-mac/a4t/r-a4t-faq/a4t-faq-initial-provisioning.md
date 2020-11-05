---
keywords: faq;frequently asked questions;analytics for target;a4t;provisioning;provisioning;adobe Experience Cloud
description: Este tópico contém respostas a perguntas frequentes sobre o provisionamento do Analytics como a fonte de geração de relatórios para o Target (A4T).
title: Provisionamento inicial - Perguntas frequentes sobre o A4T
feature: a4t troubleshooting
topic: Standard
uuid: cc80f879-ad2a-46d6-adc2-df616e8ab0b5
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 100%

---


# Provisionamento inicial - Perguntas frequentes sobre o A4T{#initial-provisioning-a-t-faq}

Este tópico contém respostas a perguntas frequentes sobre o provisionamento do Analytics como a fonte de geração de relatórios para o Target (A4T).

## Como posso configurar uma atividade de várias páginas do A4T?

Para implementar um caso de uso básico de várias páginas do A4T:

* Implemente as bibliotecas do JavaScript para o Target (at.js ou mbox.js) e o Analytics na landing page/URL da atividade. A implementação de ambas as soluções une os dados do Target com os do Analytics de cada visitante. Esses dados permanecem no Analytics até que expirem e a validade padrão é definida como 90 dias.

* Para as páginas restantes no site, onde apenas as métricas do Analytics devem ser rastreadas, implemente o Analytics nessas páginas. Não é necessário implementar o Target nessas páginas. As métricas do Analytics capturadas nessas páginas se unem automaticamente à atividade do Target para a qual o usuário foi qualificado inicialmente, com base nas informações do Target anexadas a esse visitante na etapa anterior.

## Como posso saber se o A4T está ativado na minha conta Target? {#section_4437D284448F4313BF953D4B6EDBACA6}

Para poder selecionar um conjunto de relatórios ao definir uma atividade do Analytics, você precisa de uma conta de usuário do Analytics e de uma conta de usuário do Target. Suas contas de usuário devem ser configuradas conforme descrito na documentação. Consulte [Exigências de permissão do usuário](/help/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083).

Quando você for membro de um ou mais grupos da Experience Cloud que têm acesso ao Analytics e ao Target e tiver acesso a todos os conjuntos de relatórios, deverá ver a opção de criar um teste A/B usando o Analytics em **[!UICONTROL Criar atividade]**.

Se ocorrerem problemas de provisionamento, verifique se o A4T está provisionado corretamente.

## Por que meus conjuntos de relatórios não estão carregando?  {#section_6CC8B2B3568A46C499895EB9811FDC2E}

Verifique o seguinte se algum destes problemas ocorrer:

* Certifique-se de que suas contas do Analytics e do Target estejam vinculadas no Experience Cloud.
* Se você estiver usando vários logins da empresa do Analytics na mesma empresa Experience Cloud, verifique se a última empresa do Analytics na qual você fez login é aquela vinculada à conta do Target para a integração.
* Se você fez login no Experience Cloud por várias horas, às vezes a sessão do Analytics pode expirar. Saia e faça login novamente para tentar de novo.

## Por que não vejo as opções do Analytics no Target?  {#section_EDD996AFB08B4DB196DD934BE55BF48D}

Consulte &quot;Por que meus conjuntos de relatórios não estão carregando?&quot; acima. A causa raiz deste problema é a mesma.

## Por que não vejo os relatórios do A4T no Analytics?  {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

Consulte &quot;Por que meus conjuntos de relatórios não estão carregando?&quot; acima. A causa raiz deste problema é a mesma.

## Por que meus relatórios no Target estão vazios?  {#section_3837104757464CB488C5A83014A669A1}

Consulte &quot;Por que meus conjuntos de relatórios não estão carregando?&quot; acima. A causa raiz deste problema é a mesma.
