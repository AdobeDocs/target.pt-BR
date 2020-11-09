---
keywords: Targeting
description: O URL da atividade determina a página que é usada no teste multivariado (MVT) e que é aberta quando o teste é criado no Target.
title: URL da atividade
feature: mvt
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 93%

---


# URL da atividade{#activity-url}

O URL da atividade determina a página que é usada no [!UICONTROL teste multivariado] (MVT) e que é aberta quando o teste é criado no [!DNL Adobe Target].

Quando solicitado durante a [criação da atividade](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md), especifique o URL da atividade. Digite o URL completo (incluindo `https://`) e clique em **[!UICONTROL Avançar]**.

>[!NOTE]
>
>[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `https://www.adobe.com`] e [!DNL `http://www.adobe.com`] têm correspondência.

By default, the [!UICONTROL Visual Experience Composer] (VEC) opens the page that is specified in your [Visual Experience Composer settings](/help/administrating-target/visual-experience-composer-set-up.md). Você pode especificar uma página diferente durante a criação da atividade.

Para exibir uma página diferente depois da abertura do VEC, clique no ícone **[!UICONTROL Configurar]** e selecione **[!UICONTROL Entrega de página]**, depois especifique o URL.

![Caixa de diálogo Entrega de página](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/url-config.png)

Clique em **[!UICONTROL Adicionar regra ao modelo]** para adicionar mais páginas ou seções à atividade.

Regras adicionais podem ser baseadas em qualquer um dos seguintes:

* URL
* Domínio
* Caminho
* Fragmento em hash (#)
* Consulta
* Parâmetro

Regras adicionais podem ser unidas no URL da atividade com AND ou OR. Todas regras que você adicionar são avaliadas contra si próprias com AND.

Clique em **[!UICONTROL Salvar]** quando tiver concluído.

>[!NOTE]
>
>Caso tenha inserido um URL para um site que não inclui o código JavaScript do Target Standard, você não pode selecionar elementos da página.

Por padrão, o VEC não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar a opção **[!UICONTROL Renderizar usando JavaScript]** se quiser alterar esses elementos usando o [!UICONTROL Visual Experience Composer].

>[!NOTE]
>
>Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.