---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; provisionamento; provisionamento; adobe Experience Cloud
description: Encontre respostas para perguntas frequentes sobre o provisionamento do Analytics para [!DNL Target] (A4T), que permite usar os relatórios do Analytics para [!DNL Target] atividades.
title: Onde posso encontrar informações sobre o Provisionamento inicial do A4T?
feature: Analytics for Target (A4T)
exl-id: 4b098444-3e5b-45e3-b635-1857c2c8d183
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 47%

---

# Provisionamento inicial - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre o provisionamento [!DNL Adobe Analytics] como fonte de relatórios para [!DNL Adobe Target] (A4T).

## Como posso configurar uma atividade de várias páginas do A4T?

+++Resposta Para implementar um caso de uso básico de várias páginas do A4T:

* Implemente as bibliotecas do JavaScript para Target e Analytics no URL/página de aterrissagem da atividade. A implementação de ambas as soluções une os dados do Target com os do Analytics de cada visitante. Esses dados permanecem no Analytics até que expirem e a validade padrão é definida como 90 dias.

* Para as páginas restantes no site, onde apenas as métricas do Analytics devem ser rastreadas, implemente o Analytics nessas páginas. Não é necessário implementar o Target nessas páginas. As métricas do Analytics capturadas nessas páginas se unem automaticamente à atividade do Target para a qual o usuário foi qualificado inicialmente, com base nas informações do Target anexadas a esse visitante na etapa anterior.

+++

## Como posso saber se o A4T está ativado no meu [!DNL Target] conta? {#section_4437D284448F4313BF953D4B6EDBACA6}

+++Resposta Antes que um conjunto de relatórios possa ser selecionado ao definir uma atividade do Analytics, você precisa de uma conta de usuário do Analytics e de uma conta de usuário do Target. Suas contas de usuário devem ser configuradas conforme descrito na documentação. Consulte [Exigências de permissão do usuário](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083).

Depois que você for membro de um ou mais grupos do Experience Cloud que têm acesso ao Analytics e ao Target e tiver acesso a todos os conjuntos de relatórios, deverá ver a opção de criar um teste A/B usando o Analytics em **[!UICONTROL Criar atividade]**.

Se ocorrerem problemas de provisionamento, verifique se o A4T está provisionado corretamente.

+++

## Por que meus conjuntos de relatórios não estão carregando?  {#section_6CC8B2B3568A46C499895EB9811FDC2E}

+++Answer Verifique o seguinte se algum desses problemas ocorrer:

* Verifique se as contas do Analytics e do Target estão vinculadas no Experience Cloud.
* Alguns clientes usam vários logons de empresa do Analytics na mesma empresa do Experience Cloud. Se você usar vários logons, verifique se a última empresa do Analytics na qual você fez logon é aquela vinculada à conta do Target para a integração.
* Se você fez login no Experience Cloud por várias horas, às vezes a sessão do Analytics pode expirar. Saia e faça login novamente para tentar de novo.

+++

## Por que não vejo as opções do Analytics no Target?  {#section_EDD996AFB08B4DB196DD934BE55BF48D}

+++Resposta Consulte &quot;Por que meus conjuntos de relatórios não estão carregando?&quot; Acima de. A causa raiz deste problema é a mesma.

+++

## Por que não vejo os relatórios do A4T no Analytics?  {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

+++Resposta Consulte &quot;Por que meus conjuntos de relatórios não estão carregando?&quot; acima. A causa raiz deste problema é a mesma.

+++

## Por que meus relatórios em [!DNL Target] vazio? {#section_3837104757464CB488C5A83014A669A1}

+++Resposta Consulte &quot;Por que meus conjuntos de relatórios não estão carregando?&quot; acima. A causa raiz deste problema é a mesma.

+++
