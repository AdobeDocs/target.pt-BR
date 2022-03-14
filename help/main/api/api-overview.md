---
keywords: api, apis, api de administrador, api de entrega, api de relatórios, api de perfil
description: Encontrar Adobe [!DNL Target] APIs, incluindo Admin, Delivery, Relatórios e APIs de perfil.
title: Onde posso encontrar [!DNL Target] Documentação da API e do SDK?
feature: APIs/SDKs
role: Developer
exl-id: 2a0232cc-9a6a-42f4-afb6-4b3e2b13939c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# Adobe [!DNL Target] Visão geral da API

[!DNL Adobe Target] As APIs podem ser agrupadas de acordo com o tipo: Admin, delivery, relatórios e APIs de perfil.

| Tipo de API | O que ele permite fazer | Link de download | Outros links úteis |
| --- | --- | --- |--- |
| Admin | Criar, modificar e excluir atividades, públicos-alvo, ofertas e outros objetos (incluindo [!DNL Recommendations] entidades, critérios, designs e assim por diante. O [!DNL Recommendations] As APIs são um tipo de API de administrador.) | <UL><li>[Coleção de postman da API de administrador do Target](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Coleção de postman da API do Recommendations](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Usar APIs do Recommendations](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) em *Adobe Target Tutorials* |
| Entrega | Recuperar conteúdo otimizado e personalizado do [!DNL Target] para entrega a um usuário final. | [Coleção de postman da API de entrega do Target](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| Relatório | Exportar resultados da atividade e outros resultados do relatório. | As APIs de relatórios são incluídas na variável [Coleção de Postman da API de administrador do Target](https://developers.adobetarget.com/api/#admin-postman-collection). |  |
| Perfil | Recupere e modifique perfis de usuário armazenados no Adobe Target. | [Coleção de postman da API de perfil do Target](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>Existem distinções importantes entre [!DNL Target] APIs de administrador (incluindo a variável [!DNL Recommendations] APIs) e [!DNL Target] APIs de entrega:
>
>* As APIs de administrador permitem configurar vários aspectos de [!DNL Target] que você também pode configurar no [!DNL Target] IU. As APIs de administrador exigem autenticação.
>
>* As APIs de entrega permitem recuperar conteúdo. As APIs de entrega não exigem autenticação.
>
>Para usar [!DNL Target] APIs de administrador, primeiro é necessário configurar a autenticação usando o Adobe I/O. Para obter mais informações, consulte [Configurar autenticação](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html) em *Adobe Target Tutorials*.
