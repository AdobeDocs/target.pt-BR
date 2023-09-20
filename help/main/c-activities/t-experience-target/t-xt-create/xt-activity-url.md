---
keywords: Direcionamento de experiência;xt;url de atividade;url
description: Saiba como especificar o [!UICONTROL URL da atividade] que determina a página que é usada no teste e que é aberta quando a variável [!UICONTROL Direcionamento de experiência] A atividade do foi projetada usando [!DNL Adobe Target].
title: O que é o [!UICONTROL URL da atividade] Em um [!UICONTROL Direcionamento de experiência] (XT) Atividade?
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 24513d8cb39d38dcfbc74bf40961d5517cc90a4b
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 48%

---

# URL da atividade em [!UICONTROL Direcionamento de experiência] Atividades do (XT)

A variável [!UICONTROL URL da atividade] determina a página que é usada em um [!DNL Adobe Target] [!UICONTROL Direcionamento de experiência] (XT). Esta é a página que abre no [!UICONTROL Visual Experience Composer] (VEC) [!UICONTROL Experience Composer baseado em formulário] quando a atividade é criada.

1. Quando solicitado ao [criar uma atividade de XT](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), especifique o URL da atividade. Digite o URL completo (incluindo `https://`) e clique em **[!UICONTROL Criar atividade]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] e [!DNL `http://www.adobe.com`] têm correspondência.
   >
   >Por padrão, o VEC ou [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) abre a página especificada no [Configurações do Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.
   >
   >Se você especificar um URL para um site que não inclua um [[!DNL Target] Biblioteca JavaScript at.js ou [!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/overview.html?lang=pt-BR){target=_blank}, não é possível selecionar elementos de página.

1. (Condicional) Para exibir uma página diferente após a abertura do VEC, clique em **[!UICONTROL Configurar]**, selecione **[!UICONTROL Entrega da página]** e, em seguida, especifique o URL no [!UICONTROL URL] campo.

   ![Caixa de diálogo Entrega de página](/help/main/c-activities/t-experience-target/t-xt-create/assets/url-config-new.png)

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
