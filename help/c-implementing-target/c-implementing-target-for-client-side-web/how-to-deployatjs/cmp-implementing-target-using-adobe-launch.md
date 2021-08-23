---
keywords: implementar; implementação; implementação; adobe launch; launch; raça; redirecionar; experience platform launch; platform launch
description: Saiba como implementar a biblioteca Adobe [!DNL Target] at.js usando o Adobe Experience Platform Launch, o método preferido para implementar o Adobe [!DNL Target].
title: Como implementar [!DNL Target] usando o Adobe Launch?
feature: Implementar o lado do servidor
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: fd7d3900f9e5d1a6c3d13fd2452de8528f8fd248
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 9%

---

# Implemente [!DNL Target] usando [!DNL Adobe Platform Launch]

[!DNL Adobe Experience Platform Launch] O é a plataforma de gerenciamento de tags de última geração do  [!DNL Adobe] e o é o método preferido para implementar o  [!DNL Adobe Target]. [!DNL Platform Launch] O oferece aos clientes uma forma simples de implantar e gerenciar as tags de análise, marketing e anúncios necessárias para potencializar experiências de cliente relevantes.

## Implemente [!DNL Target] usando [!DNL Platform Launch] {#topic_5234DDAEB0834333BD6BA1B05892FC25}

A tabela a seguir lista as diversas fontes em que você pode obter mais informações sobre o [!DNL Platform Launch]:

| Recurso | Detalhes |
|--- |--- |
| [ [!DNL Target] Implementação do uso do tutorial de extensões do  [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | Este tutorial fornece instruções passo a passo para implementar [!DNL Target] em um site com [!DNL Platform Launch]. Os tópicos incluem a adição da biblioteca do JavaScript at.js, o acionamento da mbox global, a adição de parâmetros e a integração com outras soluções. Este artigo faz parte de um tutorial maior que mostra como implementar [!DNL Platform Launch] e outras soluções [!DNL Adobe Experience Cloud]. |
| [Guia de início rápido para tags no Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | Informações sobre a implantação e o gerenciamento de tags de análise, marketing e publicidade necessárias para potencializar experiências de cliente relevantes. |
| [ [!DNL Target] Documentação do AdobeExtension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | Informações sobre como implementar [!DNL Target] usando [!DNL Platform Launch]. |

## Vantagens de implementar a at.js usando a extensão [!DNL Target] [!DNL Platform Launch] {#section_48B3F938B6F8491DAF798E0DB54EF304}

As seguintes vantagens se aplicam somente se você usar [!DNL Platform Launch] para implementar a at.js. Por isso, [!DNL Adobe] sugere que você use [!DNL Platform Launch] em vez de uma implementação manual da at.js.

* **Soluções  [!DNL Adobe Analytics] e condições de  [!DNL Target] corrida:** como a  [!DNL Analytics] chamada pode ser acionada antes da  [!DNL Target] chamada do , a  [!DNL Target] chamada do não é anexada à  [!DNL Analytics] chamada do . Essa sequência pode levar a dados incorretos. A partir do 0.6.0, a extensão [!DNL Platform Launch] garante que a chamada de beacon [!DNL Analytics] espere até que a chamada [!DNL Target] seja concluída com êxito ou não. Usar [!DNL Platform Launch] resolve a inconsistência de dados que os clientes podem experimentar ao implementar manualmente.
* **Impede o tratamento incorreto da oferta de redirecionamento:** se você tiver  [!DNL Target] e  [!DNL Analytics] na página e houver uma oferta de redirecionamento executada pelo  [!DNL Target], você poderá enfrentar uma situação em que o  [!DNL Analytics] rastreador aciona uma solicitação quando não deveria (porque o usuário está sendo redirecionado para um URL diferente). Se implementar [!DNL Target] e [!DNL Analytics] por meio de [!DNL Platform Launch], você não enfrentará esse problema. Usando [!DNL Platform Launch], [!DNL Target] instrui [!DNL Analytics] para suspender a solicitação de beacon [!DNL Analytics].
