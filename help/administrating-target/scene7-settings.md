---
keywords: scene7;dynamic media classic;digital asset management;assets;dam;content library;swap image
description: A Adobe Target pode ser integrada ao Adobe Dynamic Media Classic (antigo Scene7) para fornecer o Gerenciamento de ativos digitais (DAM) na Biblioteca de conteúdo.
title: Integração da configuração de integração do Dynamic Media Classic
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 2e80c972e432ce97596c856dd396b8f1be05a61a
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 29%

---


# Configuração do Dynamic Media Classic (antigo Scene7)

[!DNL Adobe Target] pode ser integrado com  [!DNL Adobe Dynamic Media Classic] (anteriormente  [!DNL Scene7]) para fornecer Gerenciamento de ativos digitais (DAM) na Biblioteca de conteúdo.

>[!NOTE]
>
>Integrar [!DNL Target] com [!DNL Dynamic Media Classic] permite o delivery de ativos (como parte do atividade) carregados na pasta de ativos [!DNL Adobe Experience Cloud]. Essa integração não permite o acesso a todos os ativos carregados em [!DNL Dynamic Media Classic] para delivery no [!DNL Target] atividade.

Se você já tiver uma conta [!DNL Dynamic Media], poderá fornecer suas credenciais existentes. Se você não tiver uma conta, poderá solicitar uma conta [!DNL Dynamic Media Classic] de uso restrito sem custo adicional do representante [!DNL Adobe]. Esta conta pode ser usada para fins restritos para uso somente em [!DNL Target]. Este serviço está disponível para cliente com fluxos de trabalho que precisam de funcionalidade de troca de imagem.

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

Se essa configuração não estiver configurada, a opção [!UICONTROL Trocar oferta de imagem] no fluxo de trabalho de criação da atividade não estará disponível. Após está configuração estar definida, a opção de trocar imagens de oferta ficará disponível no  [Visual Experience Composer (VEC) e no Experience Composer baseado em formulários](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Você pode aproveitar ofertas de imagem com imagens que foram carregadas de [!DNL Adobe Experience Cloud] para uso em [!DNL Target] atividades.

Se você quer referenciar um URL de imagem pública diretamente em uma oferta ou código personalizado durante a criação da atividade, você deve implantar a imagem em seu próprio servidor web e usar seu próprio URL no código. Não há como obter o URL publicado de uma imagem carregada no [!DNL Experience Cloud] para consumir diretamente ou fora dos workflows de definição de metas usando [!DNL Target]. Esta funcionalidade não é permitida, de acordo com o contrato.

Observe que o URL do armazenamento e os URLs de publicação final das imagens de [!DNL Dynamic Media] são diferentes e é necessário *NOT* criar ofertas usando o link de armazenamento das imagens, pois o delivery não funcionará nesses casos. Você deve usar o recurso ofertas de imagem, conforme explicado em nossa documentação de ajuda.

Para integrar com [!DNL Dynamic Media Classic] ([!DNL Scene7]), é necessário especificar as seguintes informações.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Configuração do Scene7]**.

   ![Página do Scene7](/help/administrating-target/assets/scene7.png)

1. Especifique as seguintes informações da conta [!DNL Dynamic Media Classic]:

   **Região:**[!DNL Dynamic Media] A região de sua conta do : América do Norte, Europa ou Ásia.

   **Pasta adhoc:** O local do conteúdo que fica fora da pasta de destino e é carregado manualmente no [!DNL Dynamic Media].

   **Endereço de email:** O endereço de email usado para fazer logon  [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Senha:** a senha usada para fazer logon  [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Clique em **[!UICONTROL Enviar]**.
