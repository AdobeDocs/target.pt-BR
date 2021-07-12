---
keywords: scene7, dynamic media classic, gerenciamento de ativos digitais, ativos, dam, biblioteca de conteúdo, trocar imagem
description: Saiba como integrar o Adobe [!DNL Target] com o Adobe Dynamic Media Classic (antigo Scene7) para fornecer gerenciamento de ativos digitais (DAM) na Biblioteca de conteúdo.
title: Como configurar a integração do Dynamic Media Classic (Scene7)?
feature: Administração e configuração
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 28%

---

# Configuração do Dynamic Media Classic (antigo Scene7)

[!DNL Adobe Target] pode ser integrado ao  [!DNL Adobe Dynamic Media Classic] (antigo  [!DNL Scene7]) para fornecer gerenciamento de ativos digitais (DAM) na Biblioteca  [!UICONTROL de conteúdo].

>[!NOTE]
>
>Integrar [!DNL Target] com [!DNL Dynamic Media Classic] permite a entrega de ativos (como parte das atividades) carregados na pasta [!DNL Adobe Experience Cloud] de ativos. Essa integração não habilita o acesso a todos os ativos carregados em [!DNL Dynamic Media Classic] para entrega em [!DNL Target] atividades.

Se você já tiver uma conta [!DNL Dynamic Media], poderá fornecer suas credenciais existentes. Se você não tiver uma conta, poderá solicitar uma conta de uso restrito [!DNL Dynamic Media Classic] sem custo adicional do representante [!DNL Adobe]. Esta conta pode ser usada para finalidades restritas para uso somente em [!DNL Target]. Este serviço está disponível para cliente com fluxos de trabalho que precisam de funcionalidade de troca de imagem.

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

Se essa configuração não estiver definida, a opção [!UICONTROL Trocar oferta de imagem] no fluxo de trabalho de criação da atividade não estará disponível. Após está configuração estar definida, a opção de trocar imagens de oferta ficará disponível no  [Visual Experience Composer (VEC) e no Experience Composer baseado em formulários](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Em seguida, você pode aproveitar as ofertas de imagem com imagens que foram carregadas do [!DNL Adobe Experience Cloud] para uso nas atividades [!DNL Target] .

Se você quer referenciar um URL de imagem pública diretamente em uma oferta ou código personalizado durante a criação da atividade, você deve implantar a imagem em seu próprio servidor web e usar seu próprio URL no código. Não há como obter o URL publicado de uma imagem carregada no [!DNL Experience Cloud] para consumir diretamente ou fora dos workflows para construção do target usando [!DNL Target]. Esta funcionalidade não é permitida, de acordo com o contrato.

Observe que o URL de armazenamento e os URLs finais de imagens publicadas de [!DNL Dynamic Media] são diferentes e você deve *NOT* criar ofertas usando o link de armazenamento de imagens, pois a entrega não funcionará nesses casos. Você deve usar a capacidade de ofertas de imagem conforme explicado em nossa documentação de ajuda.

Para integrar com [!DNL Dynamic Media Classic] ([!DNL Scene7]), é necessário especificar as seguintes informações.

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Scene7 Configuration]**.

   ![página do Scene7](/help/administrating-target/assets/scene7.png)

1. Especifique as seguintes informações da conta [!DNL Dynamic Media Classic]:

   **Região:**[!DNL Dynamic Media] A região de sua conta do : América do Norte, Europa ou Ásia.

   **Pasta adhoc:** O local do conteúdo que fica fora da pasta de destino e é carregado manualmente no [!DNL Dynamic Media].

   **Endereço de email:** O endereço de email usado para fazer logon no  [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Senha:** A senha usada para fazer logon em  [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Clique em **[!UICONTROL Enviar]**.
