---
keywords: api;apis;admin api;delivery api;relatórios api;perfil api;api
description: Informações sobre as APIs da Adobe Target, incluindo as APIs de Admin, Delivery, Relatórios e Perfil.
title: Visão geral da API do Adobe Target
feature: APIs/SDKs
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---


# Visão geral da API Adobe Target

[!DNL Adobe Target] As APIs podem ser agrupadas de acordo com o tipo: APIs de administração, Delivery, Relatórios e Perfil.

| Tipo de API | O que ele permite fazer | Link de download | Outros links úteis |
| --- | --- | --- |--- |
| Admin | Crie, modifique e exclua atividades, audiências, ofertas e outros objetos (incluindo [!DNL Recommendations] entidades, critérios, designs e assim por diante). As APIs [!DNL Recommendations] são um tipo de API de administração.) | <UL><li>[Coleção Postman da API do administrador do público alvo](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Coleção Recommendations API Postman](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Usar Recommendations ](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) APIs em Tutorials  *Adobe Target* |
| Entrega | Recupere conteúdo otimizado e personalizado de [!DNL Target] para delivery para um usuário final. | [Coleção Postman da API do Delivery do público alvo](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| Relatório | Exporte os resultados da atividade e outros resultados do relatórios. | As APIs de relatórios estão incluídas na [coleção do Postman da API de administração de Públicos alvos](https://developers.adobetarget.com/api/#admin-postman-collection). |  |
| Perfil | Recupere e modifique perfis de usuário armazenados no Adobe Target. | [Coleção Postman da API do Perfil do público alvo](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>Há distinções importantes entre [!DNL Target] APIs de administração (incluindo [!DNL Recommendations] APIs) e [!DNL Target] APIs de Delivery:
>
>* As APIs administrativas permitem configurar vários aspectos de [!DNL Target] que também podem ser configurados na interface do usuário [!DNL Target]. As APIs administrativas exigem autenticação.
   >
   >
* As APIs de delivery permitem recuperar conteúdo. As APIs de delivery não exigem autenticação.
>
>
Para usar [!DNL Target] APIs de administração, primeiro é necessário configurar a autenticação usando o Adobe I/O. Para obter mais informações, consulte [Configurar autenticação](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html) em *Adobe Target Tutorials*.
