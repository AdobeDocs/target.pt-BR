---
keywords: implementar; implementação; implementação; adobe launch; launch; raça; redirecionar; platform launch da experiência
description: Saiba como implementar a biblioteca Adobe [!DNL Target] at.js usando o Adobe Experience Platform Launch, o método preferido para implementar o Adobe [!DNL Target].
title: Como implementar [!DNL Target] usando o Adobe Launch?
feature: Implementar o lado do servidor
role: Developer
exl-id: 7cc1d3ab-4a68-4454-95b0-04fa547a6d9e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 75%

---

# Implementar [!DNL Target] usando o Adobe Launch

O Adobe Experience Platform Launch é a plataforma de gerenciamento de tags de última geração do Adobe e é o método preferido para implementar o Adobe Target. Ele oferece aos clientes uma forma simples de implantar e gerenciar todas as tags de análise, de marketing e de anúncios necessárias para potencializar experiências de cliente relevantes.

## Implementar [!DNL Target] usando o Adobe Launch {#topic_5234DDAEB0834333BD6BA1B05892FC25}

O Launch é a plataforma de gerenciamento de tags da Adobe de próxima geração, sendo o método preferido para implementar o Adobe Target. Ele oferece aos clientes uma forma simples de implantar e gerenciar todas as tags de análise, de marketing e de anúncios necessárias para potencializar experiências de cliente relevantes.

A tabela a seguir lista as diversas fontes em que você pode obter mais informações sobre o Launch:

| Recurso | Detalhes |
|--- |--- |
| [Implementação do Target usando o tutorial de extensões do Adobe Target](https://experienceleague.adobe.com/docs/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | Esse tutorial fornece instruções passo a passo para implementar o Adobe Target em um site com o Launch. Os tópicos incluem a adição da biblioteca do JavaScript at.js, o acionamento da mbox global, a adição de parâmetros e a integração com outras soluções. Este artigo faz parte de um tutorial maior que mostra como implementar o Adobe Launch, bem como as outras soluções da Adobe Experience Cloud. |
| [Documentação do Adobe Launch](https://experienceleague.adobe.com/docs/launch/using/intro/get-started/quick-start.html) | Informações sobre implementação e gerenciamento de todas as análises, marketing e marcas de anúncio para aprimorar experiências de cliente relevantes. |
| [Documentação da extensão do Adobe Target](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/target-extension/overview.html) | Informações sobre como implementar o Target utilizando o Launch. |

## Vantagens de implementar a at.js usando a extensão [!DNL Target] do Launch {#section_48B3F938B6F8491DAF798E0DB54EF304}

As seguintes vantagens se aplicam apenas se você usar o Adobe Launch para implementar o at.js. Por essa razão, recomendamos usar o Adobe Launch em vez do DTM ou uma implementação manual da at.js.

* **Soluciona condição de corrida do Analytics e do Target:** como a chamada do Analytics pode ser acionada antes da chamada do Target, a chamada do Target não é anexada à chamada do Analytics. Isso pode levar a dados incorretos. A partir do 0.6.0, a extensão Launch do Target garante que a chamada de beacon do Analytics espere até que a chamada do Target seja concluída com sucesso ou não. Isso deve solucionar a inconsistência de dados os que os clientes podem ter encontrado.
* **Impede o tratamento incorreto da oferta de redirecionamento** Se você tiver o Target e o Analytics na página e uma oferta de redirecionamento for executada pelo Target, você pode se deparar com uma situação em que o rastreador do Analytics aciona uma solicitação quando não deveria (porque o usuário está sendo redirecionado para um URL diferente). Se implementar o Target e o Analytics por meio do Launch, você não enfrentará esse problema. Usando o Launch, o Target instrui o Analytics a suspender a solicitação de beacon do Analytics.
