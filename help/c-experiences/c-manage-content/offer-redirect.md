---
keywords: redirect offer;create redirect offer;add html offer;Pass all URL parameters in redirect;Pass mboxSessionId in redirect (only needed when the redirect is going to a different domain)
description: Informações sobre ofertas de redirecionamento no Adobe Target que fazem com que um navegador redirecione para uma nova página.
title: Criar Ofertas de redirecionamento
feature: null
topic: Standard
uuid: 54336965-a26e-47c3-b3bc-079d3573502a
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 98%

---


# Criar Ofertas de redirecionamento{#create-redirect-offers}

A Oferta de redirecionamento faz com que o navegador seja redirecionado para uma nova página.

Você pode ter duas páginas completamente diferentes para testar, em vez de mudar apenas partes do conteúdo dentro de uma página. Neste caso, o teste A/B compara a página A com a página B. Configure uma campanha de testes A/B, com duas experiências: uma apontando para a página A padrão e a outra redirecionando para a página B. A oferta é configurada para redirecionar o visitante para uma página diferente.

>[!NOTE]
>
>Não é possível usar ofertas de redirecionamento em mboxes ajax (`mboxUpdate`).
>
>Para ofertas de redirecionamento em atividades usando A4T, sua implementação deve atender certos requisitos mínimos. Além disso, há informações importantes que você precisa saber. Para obter mais informações, consulte [Ofertas de redirecionamento - Perguntas frequentes do A4T](../../c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).

Para obter informações sobre como configurar uma experiência com redirecionamento, consulte [Redirecionar para um URL](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

A oferta de redirecionamento executa um código JavaScript para redirecionar o navegador. Ela usa o método `window.location.replace();`, para que a página que o visitante é redirecionado não fique armazenada no histórico do navegador. Isso permite que o visitante consiga utilizar o botão Voltar de seu navegador.

>[!NOTE]
>
>Se desejar passar o valor referenciador da página de aterrissagem, é recomendado usar uma oferta HTML em vez de uma oferta de redirecionamento.

**Para criar uma oferta de redirecionamento:**

1. Clique em **[!UICONTROL Ofertas]** e selecione a guia **[!UICONTROL Ofertas de código]**.
1. Clique em **[!UICONTROL Criar]** > **[!UICONTROL Oferta de redirecionamento]**.
1. Insira um nome de oferta.
1. Insira o URL do conteúdo ou destino único para onde você quer redirecionar. O URL deve ser absoluto.

   >[!NOTE]
   >
   >O redirecionamento de ofertas resulta em um loop infinito se o URL de redirecionamento também qualifica o usuário para a mesma atividade. Você deve se certificar de que o usuário não se requalifica para a atividade após ser redirecionado.

1. Selecione as opções desejadas para personalizar sua oferta de redirecionamento:

* **Inclua todos parâmetros de URL:** selecione essa caixa se desejar que todos os parâmetros de URL presentes na página anterior sejam propagados para uma página redirecionada.

   Por exemplo, você quer redirecionar visitantes diretamente de uma página de produtos masculinos para uma página de categoria de camisas masculinas. Você também pode desejar que os parâmetros dinâmicos presentes no URL sejam enviados, porque dessa forma você pode identificar se o visitante acessou o seu site a partir de um email, banners publicitários, publicidade de pesquisa ou organicamente. Ao marcar essa caixa de seleção, sua oferta de redirecionamento na página [!DNL `https://www.mycompany.com/mens.html?emailId=123`] automaticamente se tornará [!DNL `https://www.mycompany.com/mensShirts.html?emailId=123`] quando o endereço digitado na barra de endereços foi somente [!DNL `https://www.mycompany.com/mensShirts.html`].

* **Envie a ID de sessão da mbox (necessária para redirecionar para um domínio diferente):** selecione essa caixa se desejar que a `sessionId` seja incluída automaticamente no redirecionamento. Isso somente é necessário quando você está testando a navegação a partir de um email ou de um domínio para outro. A `sessionId` corresponde ao cookie do visitante, para que o visitante continue sendo monitorado e o conteúdo correto seja exibido.

   Se você usar a configuração de cookies próprios e de terceiros, você não precisa enviar a ID de sessão da mbox ao mudar de domínios. Isso é persistente no cookie de terceiros, por isso não é necessário no URL.

>[!NOTE]
>
>Entre em contato com seu Consultor de implementações antes de iniciar esses testes.

## Vídeo de treinamento: o repositório de conteúdo (4:56) ![Etiqueta de visão geral](/help/assets/overview.png)

Este vídeo inclui informações sobre o gerenciamento de conteúdo.

* Conexão entre a [biblioteca de ativos da Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/assets/creative-cloud.html) e a biblioteca de conteúdo do Target
* Ofertas HTML personalizadas
* Ofertas HTML personalizadas no Visual Experience Composer

>[!VIDEO](https://video.tv.adobe.com/v/17387)
