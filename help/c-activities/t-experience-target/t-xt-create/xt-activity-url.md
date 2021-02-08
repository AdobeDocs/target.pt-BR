---
keywords: Direcionamento de experiência;xt;url de atividade;url
description: Saiba como especificar o URL de Atividade que determina a página que é usada no teste e que é aberta quando a atividade de direcionamento de experiência é projetada com o Adobe Target.
title: O que é o URL da Atividade em uma Atividade de direcionamento de experiência (XT)?
feature: Experience Targeting
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 63%

---


# URL de atividade nas atividades de direcionamento de experiência (XT)

O [!UICONTROL URL de Atividade] determina a página que é usada na atividade [!DNL Adobe Target] [!UICONTROL Experience Targeting] (XT) e que é aberta no [!UICONTROL Visual Experience Composer] (VEC) ou [!UICONTROL Compositor de Experiência Baseado em Formulário] quando a atividade é projetada.

1. Quando solicitado ao [criar uma atividade de XT](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), especifique o URL da atividade. Digite o URL completo (incluindo `https://`) e clique em **[!UICONTROL Criar atividade]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] e [!DNL `http://www.adobe.com`] têm correspondência.
   >
   >Por padrão, o VEC ou o Criador de experiências baseado em forma abre a página especificada nas [configurações do Visual Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.
   >
   >Caso tenha especificado um URL para um site que não inclui o código JavaScript do Target Standard, não será possível selecionar elementos da página.

1. (Condicional) Para exibir uma página diferente após a abertura do VEC, clique em **[!UICONTROL Configurar]**, selecione **[!UICONTROL Entrega de página]** e especifique o URL no campo [!UICONTROL URL].

   ![Caixa de diálogo Entrega de página](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.

1. (Condicional) Clique em **[!UICONTROL Adicionar regra ao modelo]** para adicionar mais páginas ou seções à atividade.

   Regras adicionais podem ser baseadas em qualquer um dos seguintes:

   * URL
   * Domínio
   * Caminho
   * Fragmento em hash (#)
   * Consulta
   * Parâmetro da mbox

   Regras adicionais podem ser unidas no URL da atividade com AND ou OR. Todas regras que você adicionar são avaliadas contra si próprias com AND.

1. Clique em **[!UICONTROL Salvar]** quando tiver concluído.