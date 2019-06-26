---
description: O URL da atividade determina a página usada na atividade de direcionamento de experiência e que é aberta no Visual Experience Composer (VEC) ou no Criador de experiências baseado em forma quando a atividade é projetada.
keywords: Direcionamento
seo-description: O URL da atividade determina a página usada na atividade de direcionamento de experiência e que é aberta no Adobe Target Visual Experience Composer (VEC) ou no Criador de experiências baseado em forma quando a atividade é projetada.
seo-title: URL da atividade
solution: Target
title: URL da atividade
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# URL da atividade{#activity-url}

O URL da atividade determina a página usada na atividade de direcionamento de experiência (XT) e que abre no Visual Experience Composer (VEC) ou no Criador de experiências baseado em forma quando a atividade é projetada.

1. When prompted while [creating an XT activity](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), specify the activity URL. Digite o URL completo (incluindo `https://`) e clique em **[!UICONTROL Criar atividade]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] e [!DNL `http://www.adobe.com`] têm correspondência.
   >
   >By default, the VEC or Form-Based Experience Composer opens the page that is specified in your [Account Preferences](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). Você pode especificar uma página diferente durante a criação da atividade.
   >
   >Se você especificar um URL para um site que não inclui o código javascript do Target Standard, não será possível selecionar elementos de página.

1. (Conditional) To display a different page after the VEC opens, click **[!UICONTROL Configure]**, select **[!UICONTROL Page Delivery]**, and specify the URL in the [!UICONTROL URL] field.

   ![Caixa de diálogo Entrega de página](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.

1. (Conditional) Click **[!UICONTROL Add Template Rule]** to add more pages or sections to the activity.

   Regras adicionais podem ser baseadas em qualquer um dos seguintes:

   * URL
   * Domínio
   * Caminho
   * Fragmento em hash (#)
   * Consulta
   * Parâmetro da mbox
   Regras adicionais podem ser unidas no URL da atividade com AND ou OR. Todas regras que você adicionar são avaliadas contra si próprias com AND.

1. Clique em **[!UICONTROL Salvar]quando tiver concluído.**