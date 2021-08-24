---
keywords: implementar; implementação; implementação; adobe launch; launch; raça; redirecionar; experience platform launch; platform launch; tags; adobe platform
description: Saiba como implementar a biblioteca Adobe [!DNL Target] at.js usando o Adobe Experience Platform Launch, o método preferido para implementar o Adobe [!DNL Target].
title: Como implementar [!DNL Target] usando o Adobe Launch?
feature: Implementar o lado do servidor
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: 82629fb4c543220796fc99d9c034ebb725e1a645
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 5%

---

# Implemente [!DNL Target] usando [!DNL Adobe Experience Platform]

As tags em [!DNL Adobe Experience Platform] são a próxima geração de recursos de gerenciamento de tags de [!DNL Adobe]. As tags oferecem aos clientes uma forma simples de implantar e gerenciar as tags de análise, marketing e anúncios necessárias para potencializar experiências de cliente relevantes.

>[!NOTE]
>
>[!DNL Adobe Experience Platform Launch] A foi reformulada como um conjunto de tecnologias de coleta de dados no  [!DNL Adobe Experience Platform]. Como resultado, várias alterações de terminologia foram implementadas na documentação do produto. Consulte o seguinte [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) para obter uma referência consolidada das alterações de terminologia.

A tabela a seguir lista as várias fontes onde você pode obter mais informações:

| Recurso | Detalhes |
|--- |--- |
| [Adicionar  [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html#implement-solutions) | Este tutorial fornece instruções passo a passo para implementar [!DNL Target] em um site com tags em [!DNL Adobe Experience Platform]. Os tópicos incluem a adição da biblioteca do JavaScript at.js, o acionamento da mbox global, a adição de parâmetros e a integração com outras soluções. Este artigo faz parte de um tutorial maior que mostra como implementar [!DNL Adobe Experience Platform] e outras soluções [!DNL Adobe Experience Cloud]. |
| [Guia de início rápido](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html) | Informações sobre a implantação e o gerenciamento de tags de análise, marketing e publicidade necessárias para potencializar experiências de cliente relevantes. |
| [ [!DNL Target] Visão geral da Adobe Extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html) | Informações sobre como implementar [!DNL Target] usando [!DNL Adobe Experience Platform]. |

## Vantagens de implementar a at.js usando a extensão [!DNL Target] {#section_48B3F938B6F8491DAF798E0DB54EF304}

As seguintes vantagens se aplicam somente se você usar tags em [!DNL Adobe Experience Platform] para implementar a at.js. Por isso, [!DNL Adobe] sugere que você use tags em [!DNL Adobe Experience Platform] em vez de uma implementação manual da at.js.

* **Soluções  [!DNL Adobe Analytics] e condições de  [!DNL Target] corrida:** como a  [!DNL Analytics] chamada pode ser acionada antes da  [!DNL Target] chamada do , a  [!DNL Target] chamada do não é anexada à  [!DNL Analytics] chamada do . Essa sequência pode levar a dados incorretos. A extensão [!DNL Target] garante que a chamada de beacon [!DNL Analytics] espere até que a chamada [!DNL Target] seja concluída com êxito ou não. Usar tags em [!DNL Adobe Experience Platform] resolve a inconsistência de dados que os clientes podem experimentar ao implementar manualmente.
* **Impede o tratamento incorreto da oferta de redirecionamento:** se você tiver  [!DNL Target] e  [!DNL Analytics] na página e houver uma oferta de redirecionamento executada pelo  [!DNL Target], você poderá enfrentar uma situação em que o  [!DNL Analytics] rastreador aciona uma solicitação quando não deveria (porque o usuário está sendo redirecionado para um URL diferente). Se você implementar [!DNL Target] e [!DNL Analytics] por meio de tags em [!DNL Adobe Experience Platform], você não enfrentará esse problema. Usando tags em [!DNL Adobe Experience Platform], [!DNL Target] instrui [!DNL Analytics] a suspender a solicitação de beacon [!DNL Analytics].
