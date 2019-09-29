---
description: O URL da atividade determina a página que é usada no teste e que é aberta quando o teste é criado.
keywords: Visão geral e referência
seo-description: O URL da atividade determina a página que é usada no teste e que é aberta quando o teste é criado.
seo-title: URL da atividade
solution: Target
title: URL da atividade
topic: Padrão
uuid: 65489969-d548-4286-858f-8420120317c0
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# URL da atividade{#activity-url}

O URL da atividade determina a página que é usada no teste e que é aberta quando o teste é criado.

Quando solicitado durante a criação da atividade, especifique o URL da atividade. Digite o URL completo (incluindo `https://`) e clique em **[!UICONTROL Criar]**.

>[!NOTE]
>
>[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://www.adobe.com`] têm correspondência.

## Especificar um URL diferente

Por padrão, o [!UICONTROL Visual Experience Composer] abre a página especificada nas suas [Preferências da conta do Target](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). Você pode especificar uma página diferente durante a criação da atividade.

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

Clique em **[!UICONTROL Salvar]quando tiver concluído.**

>[!NOTE]
>
>Se você tiver inserido um URL para um site que não inclui o código JavaScript do [!DNL Target] Standard, não será possível selecionar elementos de página.

Por padrão, o [!UICONTROL Visual Experience Composer] não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar a opção **[!UICONTROL Renderizar usando JavaScript]** se quiser alterar esses elementos usando o [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.
