---
description: O Launch é a plataforma de gerenciamento de tags da Adobe de próxima geração, sendo o método preferido para implementar o Adobe Target. Ele oferece aos clientes uma forma simples de implantar e gerenciar todas as tags de análise, de marketing e de anúncios necessárias para potencializar experiências de cliente relevantes.
keywords: implementar; implementação; implementação; adobe launch; launch; raça; redirecionar
seo-description: O Launch é a plataforma de gerenciamento de tags da Adobe de próxima geração, sendo o método preferido para implementar o Adobe Target. Ele oferece aos clientes uma forma simples de implantar e gerenciar todas as tags de análise, de marketing e de anúncios necessárias para potencializar experiências de cliente relevantes.
seo-title: Implementação do Target usando o Adobe Launch
title: Implementação do Target usando o Adobe Launch
uuid: c8cd855b-bed1-4fc2-a0e3-f1ea6ab620e6
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Implementação do Target usando o Adobe Launch{#implement-target-using-adobe-launch}

O Launch é a plataforma de gerenciamento de tags da Adobe de próxima geração, sendo o método preferido para implementar o Adobe Target. Ele oferece aos clientes uma forma simples de implantar e gerenciar todas as tags de análise, de marketing e de anúncios necessárias para potencializar experiências de cliente relevantes.

## Implementação do Target usando o Adobe Launch {#topic_5234DDAEB0834333BD6BA1B05892FC25}

O Launch é a plataforma de gerenciamento de tags da Adobe de próxima geração, sendo o método preferido para implementar o Adobe Target. Ele oferece aos clientes uma forma simples de implantar e gerenciar todas as tags de análise, de marketing e de anúncios necessárias para potencializar experiências de cliente relevantes.

A tabela a seguir lista as diversas fontes em que você pode obter mais informações sobre o Launch:

| Recurso | Detalhes |
|--- |--- |
| [Implementação do Target usando o Tutorial de extensão do Adobe Target](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-websites-with-launch/implement-solutions/target.html) | Esse tutorial fornece instruções passo a passo para implementar o Adobe Target em um site com o Launch. Os tópicos incluem a adição da biblioteca do JavaScript at.js, o acionamento da mbox global, a adição de parâmetros e a integração com outras soluções. Este artigo faz parte de um tutorial maior que mostra como implementar o Adobe Launch, bem como as outras soluções da Adobe Experience Cloud. |
| [Documentação do Adobe Launch](https://docs.adobelaunch.com/getting-started) | Informações sobre implementação e gerenciamento de todas as análises, marketing e marcas de anúncio para aprimorar experiências de cliente relevantes. |
| [Documentação de extensão do Adobe Target](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension) | Informações sobre como implementar o Target utilizando o Launch. |

## Vantagens de implementar o at.js utilizando a extensão Launch do Target {#section_48B3F938B6F8491DAF798E0DB54EF304}

As seguintes vantagens se aplicam apenas se você usar o Adobe Launch para implementar o at.js. Por essa razão, recomendamos usar o Adobe Launch em vez do DTM ou uma implementação manual da at.js.

* **Solta o Analytics e a Condição de raça do Target:** Como a chamada do Analytics pode ser acionada antes da chamada do Target, a chamada do Target não é encadeada para a chamada do Analytics. Isso pode levar a dados incorretos. A partir de 0.6.0, a extensão do Target Launch garante que a chamada de beacon do Analytics aguarde até que a chamada Target seja concluída, com êxito ou não. Isso deve solucionar a inconsistência de dados os que os clientes podem ter encontrado.
* **Impede o tratamento incorreto da oferta de redirecionamento:** Se você tiver o Target e o Analytics na página e houver uma oferta de redirecionamento executada pelo Target, poderá enfrentar uma situação na qual o rastreador do Analytics aciona uma solicitação quando ela não deveria ser executada (porque o usuário está sendo redirecionado para um URL diferente). Se implementar o Target e o Analytics via Launch, você não vai enfrentar esse problema. Usando o Launch, o Target instrui o Analytics a suspender a solicitação de beacon do Analytics.