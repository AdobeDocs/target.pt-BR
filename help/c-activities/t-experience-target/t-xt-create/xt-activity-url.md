---
description: O URL da atividade determina a página usada na atividade de direcionamento de experiência e que é aberta no Visual Experience Composer (VEC) ou no Criador de experiências baseado em forma quando a atividade é projetada.
keywords: Direcionamento
seo-description: O URL da atividade determina a página usada na atividade de direcionamento de experiência e que é aberta no Adobe Target Visual Experience Composer (VEC) ou no Criador de experiências baseado em forma quando a atividade é projetada.
seo-title: URL da atividade
solution: Target
title: URL da atividade
uuid: 970de8ba-ab60-4339-866b-27889bec67f9
translation-type: tm+mt
source-git-commit: ca9639ccca286dac182728f7bbd43fac78217209

---


# URL da atividade{#activity-url}

O URL da atividade determina a página usada na atividade de direcionamento de experiência (XT) e que abre no Visual Experience Composer (VEC) ou no Criador de experiências baseado em forma quando a atividade é projetada.

1. Quando solicitado ao [criar uma atividade XT](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), especifique o URL da atividade. Digite o URL completo (incluindo `https://`) e clique em **[!UICONTROL Criar atividade]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] e [!DNL `http://www.adobe.com`] têm correspondência.
   >
   >Por padrão, o VEC ou Criador de experiências baseado em forma abre a página especificada nas suas Preferências [de conta](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). Você pode especificar uma página diferente durante a criação da atividade.
   >
   >Se você especificar um URL para um site que não inclui o código javascript do Target Standard, não será possível selecionar elementos de página.

1. (Condicional) Para exibir uma página diferente após a abertura da VEC, clique **[!UICONTROL em Configurar]**, selecione **[!UICONTROL Entrega]** de página e especifique o URL no campo [!UICONTROL URL] .

   ![Caixa de diálogo Entrega de página](/help/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

   >[!NOTE]
   >
   >Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.

1. (Condicional) Clique **[!UICONTROL em Adicionar regra de modelo]** para adicionar mais páginas ou seções à atividade.

   Regras adicionais podem ser baseadas em qualquer um dos seguintes:

   * URL
   * Domínio
   * Caminho
   * Fragmento em hash (#)
   * Consulta
   * Parâmetro da mbox
   Regras adicionais podem ser unidas no URL da atividade com AND ou OR. Todas regras que você adicionar são avaliadas contra si próprias com AND.

1. Clique em **[!UICONTROL Salvar]quando tiver concluído.**