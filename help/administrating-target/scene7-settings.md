---
description: O Target Standard pode ser integrado com o Adobe Dynamic Media Classic (anteriormente Adobe Scene7) para fornecer gerenciamento de ativos digitais (DAM) na biblioteca de conteúdo.
title: Integração com o Dynamic Media Classic integração de configuração
feature: null
subtopic: Getting Started
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 36%

---


# Configuração Scene7 {#scene-settings}

Target can be integrated with [!DNL Adobe Dynamic Media Classic] (formerly [!DNL Scene7]) to provide Digital Asset Management (DAM) in the Content Library.

>[!NOTE]
>
>Integrating [!DNL Target] with [!DNL Dynamic Media Classic] enables delivery of assets (as part of activities) uploaded to the [!DNL Adobe Experience Cloud] assets folder. This integration does not enable access to all assets uploaded in [!DNL Dynamic Media Classic] for delivery in [!DNL Target] activities.

If you already have a [!DNL Dynamic Media] account, you can supply your existing credentials. If you do not have an account, you can request a restricted-use [!DNL Dynamic Media Classic] account at no additional charge from your [!DNL Adobe] representative. This account can be used for purposes restricted for use in [!DNL Target] only. Este serviço está disponível para cliente com fluxos de trabalho que precisam de funcionalidade de troca de imagem.

If this setting is not configured, the [!UICONTROL Swap Image offer] option within the activity creation workflow is not available. Após está configuração estar definida, a opção de trocar imagens de oferta ficará disponível no  [Visual Experience Composer (VEC) e no Experience Composer baseado em formulários](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). You can then leverage image offers with images that have been uploaded from the [!DNL Adobe Experience Cloud] for use in [!DNL Target] activities.

Se você quer referenciar um URL de imagem pública diretamente em uma oferta ou código personalizado durante a criação da atividade, você deve implantar a imagem em seu próprio servidor web e usar seu próprio URL no código. There is no way to obtain the published URL of an image uploaded into the [!DNL Experience Cloud] to consume directly or outside of targeting workflows using [!DNL Target]. Esta funcionalidade não é permitida, de acordo com o contrato.

Note that the storage URL and the final publish URLs of images from [!DNL Dynamic Media] are different and one must *NOT* create offers using the storage link of images as delivery will not work in such cases. Você deve usar o recurso ofertas de imagem, conforme explicado em nossa documentação de ajuda.

To integrate with [!DNL Dynamic Media Classic] ([!DNL Scene7]), you need to specify the following information.

1. Clique em **[!UICONTROL Administração]** > Configuração **** Scene7.

   ![Página do Scene7](/help/administrating-target/assets/scene7.png)

1. Specify the following [!DNL Dynamic Media Classic] account information:

   **Região:**[!DNL Dynamic Media] A região de sua conta do : América do Norte, Europa ou Ásia.

   **Pasta adhoc:** O local do conteúdo que fica fora da pasta de destino e é carregado manualmente no [!DNL Dynamic Media].

   **Endereço de email:** O endereço de email usado para fazer logon [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Senha:** A senha usada para fazer logon em [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Clique em **[!UICONTROL Enviar]**.
