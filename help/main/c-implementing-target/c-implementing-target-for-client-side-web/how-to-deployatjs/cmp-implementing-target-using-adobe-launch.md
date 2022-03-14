---
keywords: implement;implementing;implementation;adobe launch;launch;race;redirect;experience platform launch;platform launch;tags;adobe platform
description: Saiba como implementar o [!DNL Adobe Target] biblioteca da at.js usando [!DNL Adobe Experience Platform], o método preferido para implementar [!DNL Target].
title: Como implementar o  [!DNL Target]  usando a  [!DNL Adobe Experience Platform]?
feature: Implement Server-side
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 96%

---

# Implementar o [!DNL Target]usando a [!DNL Adobe Experience Platform]

As tags na [!DNL Adobe Experience Platform] são a próxima geração de recursos de gerenciamento de tags da [!DNL Adobe]. As tags oferecem aos clientes uma forma simples de implantar e gerenciar as tags de análise, marketing e anúncios necessárias para potencializar experiências relevantes do cliente.

>[!NOTE]
>
>O [!DNL Adobe Experience Platform Launch] foi reformulado como um conjunto de tecnologias de coleção de dados na [!DNL Adobe Experience Platform]. Como resultado, várias alterações de terminologia foram implementadas na documentação do produto. Consulte o seguinte [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=pt-BR) para obter uma referência consolidada das alterações de terminologia.

A tabela a seguir lista as diversas fontes para obter mais informações:

| Recurso | Detalhes |
|--- |--- |
| [Adicionar [!UICONTROL Adobe Target]](https://experienceleague.adobe.com/docs/launch-learn/implementing-in-websites-with-launch/implement-solutions/target.html?lang=pt-BR#implement-solutions) | Esse tutorial fornece o passo a passo para implementar o [!DNL Target] em um site com tags na [!DNL Adobe Experience Platform]. Os tópicos incluem a adição da biblioteca do JavaScript at.js, o acionamento da mbox global, a adição de parâmetros e a integração com outras soluções. Este artigo faz parte de um tutorial maior que mostra como implementar a [!DNL Adobe Experience Platform] e outras soluções da [!DNL Adobe Experience Cloud]. |
| [Guia de início rápido](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=pt-BR) | Informações sobre implantação e gerenciamento das tags de análise, marketing e anúncio para potencialização de experiências relevantes do cliente. |
| [Visão geral da extensão da Adobe  [!DNL Target] ](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/target/overview.html?lang=pt-BR) | Informações sobre como implementar o [!DNL Target] usando a [!DNL Adobe Experience Platform]. |

## Vantagens de implementar a at.js utilizando a extensão do [!DNL Target] {#section_48B3F938B6F8491DAF798E0DB54EF304}

As seguintes vantagens se aplicam apenas se você usar tags na [!DNL Adobe Experience Platform] para implementar a at.js. Por isso, a [!DNL Adobe] recomenda que você use tags na [!DNL Adobe Experience Platform], em vez de implementar manualmente a at.js.

* **Soluciona a condição de corrida do [!DNL Adobe Analytics] e do [!DNL Target]:** visto que a chamada do [!DNL Analytics] pode ser disparada antes da chamada do [!DNL Target], a chamada do [!DNL Target] não é anexada à chamada do [!DNL Analytics]. Este sequenciamento pode levar a dados incorretos. A extensão do [!DNL Target] garante que a chamada de sinal do [!DNL Analytics] espere até que a chamada do [!DNL Target] seja concluída, com ou sem êxito. Usar tags na [!DNL Adobe Experience Platform] resolve a inconsistência de dados que pode ocorrer com os clientes ao implementar manualmente.

   >[!NOTE]
   >
   >Use a ação [!UICONTROL Enviar sinal] na extensão do [!DNL Adobe Analytics] para que a chamada do [!DNL Analytics] aguarde a chamada do [!DNL Target]. Se você chamar `s.t()` ou `s.tl()` diretamente, usando um código personalizado, as chamadas do [!DNL Analytics] não irão esperar até que as chamadas do [!DNL Target] sejam concluídas.

* **Impede o tratamento incorreto da oferta de redirecionamento:** se você tiver o [!DNL Target] e o [!DNL Analytics] na página e uma oferta de redirecionamento for executada pelo [!DNL Target], você pode se deparar com uma situação em que o rastreador do [!DNL Analytics] dispara uma solicitação quando não deveria (porque o usuário está sendo redirecionado para um URL diferente). Se implementar o [!DNL Target] e o [!DNL Analytics] por meio de tags na [!DNL Adobe Experience Platform], você não experienciará esse problema. Ao usar tags na [!DNL Adobe Experience Platform], o [!DNL Target] instrui o [!DNL Analytics] a suspender a solicitação de sinal do [!DNL Analytics].
