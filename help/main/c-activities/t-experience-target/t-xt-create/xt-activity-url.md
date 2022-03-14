---
keywords: Direcionamento de experiência; xt; url da atividade; url
description: Saiba como especificar o URL da atividade que determina a página usada no teste e que é aberta quando a atividade de Direcionamento de experiência é criada usando o Adobe Target.
title: O que é o URL da atividade em uma atividade de direcionamento de experiência (XT)?
feature: Experience Targeting
exl-id: 8e3be814-6ad6-4ffa-be8d-68f0cb7857b5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 63%

---

# URL da atividade nas atividades de Direcionamento de experiência (XT)

O [!UICONTROL URL da atividade] determina a página que é usada no [!DNL Adobe Target] [!UICONTROL Direcionamento de experiência] (XT), e isso é aberto no [!UICONTROL Visual Experience Composer] (VEC) ou [!UICONTROL Experience Composer baseado em formulário] quando a atividade for projetada.

1. Quando solicitado ao [criar uma atividade de XT](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md), especifique o URL da atividade. Digite o URL completo (incluindo `https://`) e clique em **[!UICONTROL Criar atividade]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] e [!DNL `http://www.adobe.com`] têm correspondência.
   >
   >Por padrão, o VEC ou o Experience Composer baseado em formulário abre a página especificada no [Configurações do Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.
   >
   >Caso tenha especificado um URL para um site que não inclui o código JavaScript do Target Standard, não será possível selecionar elementos da página.

1. (Condicional) Para exibir uma página diferente após a abertura do VEC, clique em **[!UICONTROL Configurar]**, selecione **[!UICONTROL Entrega de página]** e especifique o URL no campo [!UICONTROL URL].

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
