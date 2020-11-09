---
keywords: Targeting
description: O URL da atividade determina a página usada na atividade de Direcionamento de experiência, que é aberta no Visual Experience Composer (VEC) ou no Experience Composer baseado em formulário do Adobe Target quando a atividade é criada.
title: URL da atividade
feature: xt
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 92%

---


# URL da atividade{#activity-url}

O URL da atividade determina a página usada na atividade de Direcionamento de experiência (XT), que é aberta no Visual Experience Composer (VEC) ou no Experience Composer baseado em formulário quando a atividade é criada.

1. Quando solicitado ao [criar uma atividade de XT](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), especifique o URL da atividade. Digite o URL completo (incluindo `https://`) e clique em **[!UICONTROL Criar atividade]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] e [!DNL `http://www.adobe.com`] têm correspondência.
   >
   >By default, the VEC or Form-Based Experience Composer opens the page that is specified in your [Visual Experience Composer settings](/help/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.
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