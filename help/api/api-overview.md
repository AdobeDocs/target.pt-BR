---
keywords: api, apis, api de administrador, api de entrega, api de relatórios, api de perfil
description: Encontre as APIs do Adobe [!DNL Target] , incluindo as APIs de Administração, Entrega, Relatório e Perfil.
title: Onde posso encontrar [!DNL Target] Documentação da API e do SDK?
feature: APIs/SDKs
role: Developer
exl-id: 2a0232cc-9a6a-42f4-afb6-4b3e2b13939c
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 1%

---

# Visão geral da API do Adobe [!DNL Target]

[!DNL Adobe Target] As APIs podem ser agrupadas de acordo com o tipo: Admin, delivery, relatórios e APIs de perfil.

| Tipo de API | O que ele permite fazer | Link de download | Outros links úteis |
| --- | --- | --- |--- |
| Admin | Crie, modifique e exclua atividades, públicos-alvo, ofertas e outros objetos (incluindo [!DNL Recommendations] entidades, critérios, designs e assim por diante. As APIs [!DNL Recommendations] são um tipo de API de administrador.) | <UL><li>[Coleção de postman da API de administrador do Target](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Coleção de postman da API do Recommendations](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Usar a ](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) API do Recommendations no  *Adobe Target Tutorials* |
| Entrega | Recupere conteúdo otimizado e personalizado de [!DNL Target] para entrega a um usuário final. | [Coleção de postman da API de entrega do Target](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| Relatório | Exportar resultados da atividade e outros resultados do relatório. | As APIs de relatórios são incluídas na [coleção Postman da API de administrador do Target](https://developers.adobetarget.com/api/#admin-postman-collection). |  |
| Perfil | Recupere e modifique perfis de usuário armazenados no Adobe Target. | [Coleção de postman da API de perfil do Target](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>Há distinções importantes entre [!DNL Target] APIs de administração (incluindo as [!DNL Recommendations] APIs) e [!DNL Target] APIs de entrega:
>
>* As APIs de administrador permitem configurar vários aspectos de [!DNL Target] que também podem ser configurados na interface do usuário [!DNL Target]. As APIs de administrador exigem autenticação.
   >
   >
* As APIs de entrega permitem recuperar conteúdo. As APIs de entrega não exigem autenticação.
>
>
Para usar [!DNL Target] APIs de administrador, primeiro é necessário configurar a autenticação usando o Adobe I/O. Para obter mais informações, consulte [Configurar autenticação](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html) em *Adobe Target Tutorials*.
