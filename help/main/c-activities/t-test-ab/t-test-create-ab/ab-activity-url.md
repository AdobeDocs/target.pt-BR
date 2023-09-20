---
keywords: url da atividade;url;url diferente
description: Saiba como especificar o URL da atividade que determina a página que é usada no teste e que é aberta quando o teste é criado usando [!DNL Adobe Target].
title: Qual é o URL da atividade em uma atividade A/B?
feature: A/B Tests
exl-id: 7482ae10-fb7e-42ba-9ea0-97b82ed85bff
source-git-commit: 6bca763d24649349dbc7cdf6e5f2dbc4ac0a480d
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 64%

---

# URL da atividade

O URL da atividade determina a página que é usada no teste e que é aberta quando o teste é criado usando o Adobe Target.

Quando solicitado durante a criação da atividade, especifique o URL da atividade. Digite o URL completo (incluindo `https://`) e clique em **[!UICONTROL Criar]**.

>[!NOTE]
>
>[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://www.adobe.com`] têm correspondência.

## Especificar um URL diferente

Por padrão, a variável [!UICONTROL Visual Experience Composer] abre a página especificada no [Configurações do Visual Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.

1. Para exibir uma página diferente após a variável [!UICONTROL Visual Experience Composer] abre, no **[!UICONTROL Experiências]** clique no link **[!UICONTROL Configurar]** ícone de engrenagem e selecione **[!UICONTROL Entrega da página]**.

1. Especifique o URL no **[!UICONTROL URL]** campo.

   ![Caixa de diálogo Entrega de página](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

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

Se você tiver inserido um URL para um site que não inclui o código JavaScript do [!DNL Target] Standard, não será possível selecionar elementos de página.

Por padrão, o [!UICONTROL Visual Experience Composer] não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar a opção **[!UICONTROL Renderizar usando JavaScript]** se quiser alterar esses elementos usando o [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.
