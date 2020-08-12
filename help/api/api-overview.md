---
keywords: api;apis;admin api;delivery api;reporting api;profile api
description: Informações sobre as APIs da Adobe Target, incluindo as APIs de Admin, Delivery, Relatórios e Perfil.
title: Visão geral da API Adobe Target
feature: null
topic: APIs
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 1%

---


# Visão geral da API Adobe Target

[!DNL Adobe Target] As APIs podem ser agrupadas de acordo com o tipo.

| Tipo de API | O que ele permite fazer | Link de download | Outros links úteis |
| --- | --- | --- |--- |
| Admin | Crie, modifique e exclua atividades, audiências, ofertas e outros objetos (incluindo [!DNL Recommendations] entidades, critérios, designs e assim por diante). As [!DNL Recommendations] APIs são um tipo de API de administração.) | <UL><li>[Coleção Postman da API do administrador do público alvo](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Coleção Recommendations API Postman](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Usar APIs](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html) Recommendations em Tutorials *Adobe Target* |
| Entrega | Recupere conteúdo otimizado e personalizado de [!DNL Target] delivery para usuário final. | [Coleção Postman da API do Delivery do público alvo](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| Relatório | Exporte os resultados da atividade e outros resultados do relatórios. | As APIs de relatórios estão incluídas na coleção [Postman da API de administração de](https://developers.adobetarget.com/api/#admin-postman-collection)Públicos alvos. |  |
| Perfil | Recupere e modifique perfis de usuário armazenados no Adobe Target. | [Coleção Postman da API do Perfil do público alvo](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>Há distinções importantes entre [!DNL Target] as APIs de administração (incluindo as [!DNL Recommendations] APIs) e as APIs de [!DNL Target] Delivery:
>
>* As APIs de administração permitem configurar vários aspectos dos [!DNL Target] quais você também pode configurar na [!DNL Target] interface do usuário. As APIs administrativas exigem autenticação.
   >
   >
* As APIs de delivery permitem recuperar conteúdo. As APIs de delivery não exigem autenticação.
>
>
Para usar [!DNL Target] as APIs de administração, primeiro é necessário configurar a autenticação usando E/S de Adobe. Para obter mais informações, consulte [Configurar autenticação](https://docs.adobe.com/content/help/en/target-learn/tutorials/apis/configure-io-target-integration.html) em Tutorials ** Adobe Target.
