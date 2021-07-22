---
keywords: scene7;dynamic media classic;gerenciamento de ativos digitais;ativos;dam;biblioteca de conteúdo;trocar imagem
description: Saiba como integrar o Adobe  [!DNL Target]  ao Adobe Dynamic Media Classic (antigo Scene7) para oferecer Gerenciamento de ativos digitais (DAM) na biblioteca de conteúdo.
title: Como configurar a integração do Dynamic Media Classic (Scene7)?
feature: Administração & configuração
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: ht
source-wordcount: '404'
ht-degree: 100%

---

# Configuração do Dynamic Media Classic (antigo Scene7)

O [!DNL Adobe Target] pode ser integrado ao [!DNL Adobe Dynamic Media Classic] (antigo [!DNL Scene7]) para oferecer o Gerenciamento de ativos digitais ( DAM) na [!UICONTROL Biblioteca de conteúdo].

>[!NOTE]
>
>A integração do [!DNL Target] ao [!DNL Dynamic Media Classic] permite a entrega de ativos (como parte das atividades) carregados na pasta de ativos da [!DNL Adobe Experience Cloud]. Essa integração não permite o acesso a todos ativos carregados no [!DNL Dynamic Media Classic] para entrega em atividades do [!DNL Target].

Se você já tiver uma conta do [!DNL Dynamic Media], forneça suas credenciais existentes. Se não tiver, você poderá solicitar uma conta de uso restrito do [!DNL Dynamic Media Classic] sem custo adicional ao representante da [!DNL Adobe]. Essa conta pode ser usada para propósitos restritos apenas no [!DNL Target]. Este serviço está disponível para cliente com fluxos de trabalho que precisam de funcionalidade de troca de imagem.

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

Se esta configuração não estiver definida, a opção [!UICONTROL Trocar imagem de oferta] no fluxo de trabalho da criação da atividade não estará disponível. Após está configuração estar definida, a opção de trocar imagens de oferta ficará disponível no  [Visual Experience Composer (VEC) e no Experience Composer baseado em formulários](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D). Você pode aproveitar ofertas de imagens com imagens que foram carregadas da [!DNL Adobe Experience Cloud] para uso em atividades do [!DNL Target].

Se você quer referenciar um URL de imagem pública diretamente em uma oferta ou código personalizado durante a criação da atividade, você deve implantar a imagem em seu próprio servidor web e usar seu próprio URL no código. Não há como obter o URL publicado de uma imagem carregada na [!DNL Experience Cloud] para consumir diretamente ou fora de workflows para construção do target usando o [!DNL Target]. Esta funcionalidade não é permitida, de acordo com o contrato.

Observe que o URL de armazenamento e os URLs finais de imagens publicadas do [!DNL Dynamic Media] são diferentes e você *NÃO* deve criar ofertas usando o link de imagens armazenadas, pois a entrega não funcionará nesses casos. Você precisa usar a capacidade de ofertas de imagem conforme explicado em nossa documentação de ajuda.

Para integrar ao [!DNL Dynamic Media Classic] ([!DNL Scene7]), é preciso especificar as informações a seguir.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Configuração do Scene7]**.

   ![Página do Scene7](/help/administrating-target/assets/scene7.png)

1. Especifique as seguintes informações da conta do [!DNL Dynamic Media Classic]:

   **Região:** A região de sua conta do [!DNL Dynamic Media]: América do Norte, Europa ou Ásia.

   **Pasta adhoc:** O local do conteúdo que fica fora da pasta de destino e é carregado manualmente no [!DNL Dynamic Media].

   **Endereço de email:** o endereço de email usado para fazer logon no [!DNL Dynamic Media Classic] ([!DNL Scene7]).

   **Senha:** a senha usada para fazer logon no [!DNL Dynamic Media Classic] ([!DNL Scene7]).

1. Clique em **[!UICONTROL Enviar]**.
