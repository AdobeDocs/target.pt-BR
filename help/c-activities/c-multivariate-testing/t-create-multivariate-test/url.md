---
description: O URL da atividade determina a página usada no Teste multivariado (MVT) e que é aberta quando o teste é projetado no Target.
keywords: Direcionamento
seo-description: O URL da atividade determina a página usada no Teste multivariado (MVT) e que é aberta quando o teste é projetado no Adobe Target.
seo-title: URL da atividade
solution: Target
title: URL da atividade
uuid: ddc7330c-199a-4e38-b3d4-6786e3997783
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# URL da atividade{#activity-url}

The activity URL determines the page that is used in the [!UICONTROL Multivariate Test] (MVT), and that opens when the test is designed in [!DNL Adobe Target].

When prompted during [activity creation](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), specify the activity URL. Type the complete URL (including `https://`), then click **[!UICONTROL Next]**.

>[!NOTE]
>
>[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] e [!DNL `http://www.adobe.com`] têm correspondência.

By default, the [!UICONTROL Visual Experience Composer] (VEC) opens the page that is specified in your [Account Preferences](/help/administrating-target/r-target-account-preferences/target-account-preferences.md). Você pode especificar uma página diferente durante a criação da atividade.

To display a different page after the VEC opens, click the **[!UICONTROL Configure]** icon, then select **[!UICONTROL Page Delivery]**, then specify the URL.

![Caixa de diálogo Entrega de página](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Clique em **[!UICONTROL Adicionar regra ao modelo]para adicionar mais páginas ou seções à atividade.**

Regras adicionais podem ser baseadas em qualquer um dos seguintes:

* URL
* Domínio
* Caminho
* Fragmento em hash (#)
* Consulta
* Parâmetro

Regras adicionais podem ser unidas no URL da atividade com AND ou OR. Todas regras que você adicionar são avaliadas contra si próprias com AND.

Clique em **[!UICONTROL Salvar]quando tiver concluído.**

>[!NOTE]
>
>Caso tenha inserido um URL para um site que não inclui o código JavaScript do Target Standard, você não pode selecionar elementos da página.

Por padrão, o VEC não permite alterações a elementos que contenham javascript, como banners giratórios. Você pode desativar a opção **[!UICONTROL Renderizar usando JavaScript]** se quiser alterar esses elementos usando o [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.