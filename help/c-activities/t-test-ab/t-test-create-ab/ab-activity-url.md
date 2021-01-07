---
keywords: activity url;url;different url
description: O URL da Atividade determina a página que é usada no teste e que é aberta quando o teste é projetado usando o Adobe Target.
title: URL da atividade
feature: A/B Tests
translation-type: tm+mt
source-git-commit: 8110807a73e4d6d9848a52224db04faba033c98c
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 78%

---


# URL da atividade

O URL da Atividade determina a página que é usada no teste e que é aberta quando o teste é projetado usando o Adobe Target.

Quando solicitado durante a criação da atividade, especifique o URL da atividade. Digite o URL completo (incluindo `https://`) e clique em **[!UICONTROL Criar]**.

>[!NOTE]
>
>[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://www.adobe.com`] têm correspondência.

## Especificar um URL diferente

Por padrão, o [!UICONTROL Visual Experience Composer] abre a página especificada nas [configurações do Visual Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md)
. Você pode especificar uma página diferente durante a criação da atividade.

Para exibir uma página diferente depois que o [!UICONTROL Visual Experience Composer] é aberto, clique no ícone de engrenagem **[!UICONTROL Configurar]** e selecione **[!UICONTROL Entrega da página]**. Insira o URL no campo URL da atividade.

![Caixa de diálogo Entrega de página](/help/c-activities/t-test-ab/t-test-create-ab/assets/url-config-new.png)

Clique em **[!UICONTROL Adicionar regra ao modelo]** para adicionar mais páginas ou seções à atividade.

Regras adicionais podem ser baseadas em qualquer um dos seguintes:

* URL
* Domínio
* Caminho
* Fragmento em hash (#)
* Consulta
* Parâmetro da mbox

Regras adicionais podem ser unidas no URL da atividade com AND ou OR. Todas regras que você adicionar são avaliadas contra si próprias com AND.

Clique em **[!UICONTROL Salvar]** quando tiver concluído.

>[!NOTE]
>
>Se você tiver inserido um URL para um site que não inclui o código JavaScript do [!DNL Target] Standard, não será possível selecionar elementos de página.

Por padrão, o [!UICONTROL Visual Experience Composer] não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar a opção **[!UICONTROL Renderizar usando JavaScript]** se quiser alterar esses elementos usando o [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.
