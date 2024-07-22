---
keywords: oferta de redirecionamento, criar oferta de redirecionamento, adicionar oferta html, passar todos parâmetros de URL no redirecionamento, passar mboxSessionId no redirecionamento (necessário somente quando o redirecionamento passar por um domínio diferente)
description: Saiba como criar ofertas de redirecionamento no Adobe [!DNL Target] para fazer com que um navegador redirecione para uma nova página.
title: Como Criar Ofertas De Redirecionamento?
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 45%

---

# Criar Ofertas de redirecionamento

Ofertas de redirecionamento em [!DNL Adobe Target] fazem com que um navegador redirecione para uma nova página.

Você pode ter duas páginas completamente diferentes para testar, em vez de mudar apenas partes do conteúdo dentro de uma página. Nesse caso, o teste A/B compara a página A versus a página B. Configure uma atividade de Teste A/B com duas experiências: uma apontando para a página A padrão e a outra redirecionando para a página B. A oferta é configurada para redirecionar o visitante para uma página diferente.

>[!NOTE]
>
> * As ofertas de redirecionamento podem ser criadas na página [!UICONTROL Offers] > [!UICONTROL Code Offers] ou no [Experience Composer baseado no Forms](/help/main/c-experiences/form-experience-composer.md). Não é possível criar ou aplicar ofertas de redirecionamento no Visual Experience Composer (VEC). O conteúdo será injetado nos locais de solicitação [!DNL Target], portanto, provavelmente não são apropriados para uma solicitação global [!DNL Target].
>
>* Não é possível usar ofertas de redirecionamento em mboxes ajax (`mboxUpdate`).
>
>* Para ofertas de redirecionamento em atividades usando A4T, sua implementação deve atender certos requisitos mínimos. Além disso, há informações importantes que você precisa saber. Para obter mais informações, consulte [Perguntas frequentes das Ofertas de redirecionamento - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Para obter informações sobre como configurar uma experiência com redirecionamento, consulte [Redirecionar para um URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

A oferta de redirecionamento executa um código JavaScript para redirecionar o navegador. Ela usa o método `window.location.replace();`, para que a página que o visitante é redirecionado não fique armazenada no histórico do navegador. Isso permite que o visitante consiga utilizar o botão Voltar de seu navegador.

>[!NOTE]
>
>Se desejar passar o valor referenciador da página de aterrissagem, é recomendado usar uma oferta HTML em vez de uma oferta de redirecionamento.

## Criar uma oferta de redirecionamento na página Ofertas de código

1. Clique em **[!UICONTROL Offers]** e selecione a guia **[!UICONTROL Code Offers]**.

   ![guia Ofertas de código](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Clique em **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Caixa de diálogo Criar Oferta de Redirecionamento](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca do Assets.

1. Insira o URL do conteúdo ou destino único para onde você quer redirecionar. O URL deve ser absoluto.

   >[!NOTE]
   >
   >O redirecionamento de ofertas resulta em um loop infinito se o URL de redirecionamento também qualifica o usuário para a mesma atividade. Você deve se certificar de que o usuário não se requalifica para a atividade após ser redirecionado.

1. Selecione as opções desejadas para personalizar sua oferta de redirecionamento:

   * **Incluir todos os parâmetros de URL:** Deslize o botão de alternância para habilitar esta opção se desejar que todos os parâmetros de URL presentes na página anterior sejam propagados para a página redirecionada.

     Por exemplo, você quer redirecionar visitantes diretamente de uma página de produtos masculinos para uma página de categoria de camisas masculinas. Você também pode desejar que os parâmetros dinâmicos presentes no URL sejam enviados, porque dessa forma você pode identificar se o visitante acessou o seu site a partir de um email, banners publicitários, publicidade de pesquisa ou organicamente. Ao habilitar esta opção, sua oferta de redirecionamento na página `https://www.mycompany.com/mens.html?emailId=123` automaticamente se tornará `https://www.mycompany.com/mensShirts.html?emailId=123` quando o valor inserido na caixa de URL foi `https://www.mycompany.com/mensShirts.html`.

   * **ID de sessão da mbox de passagem:** Necessário para redirecionar para um domínio diferente. Deslize o botão de alternância para habilitar esta opção se desejar que `sessionId` seja incluído automaticamente no redirecionamento. Isso é necessário somente quando você está testando cliques de um email ou cliques de um domínio para outro. A `sessionId` corresponde ao cookie do visitante, para que o visitante continue sendo monitorado e o conteúdo correto seja exibido.

     Se você usar a configuração de cookies próprios e de terceiros, não será necessário transmitir a ID de sessão da mbox ao atravessar domínios. Isso é persistente no cookie de terceiros, por isso não é necessário no URL.

1. Clique em **[!UICONTROL Save]**.

>[!NOTE]
>
>Entre em contato com seu Consultor de implementações antes de iniciar esses testes.

## Criar uma oferta de redirecionamento usando o Experience Composer baseado em formulário

1. Ao criar uma atividade usando o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md), selecione o local para exibir a seção **[!UICONTROL Content]**.

   ![Seção de conteúdo no Experience Composer baseado em formulário](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Clique na lista suspensa **[!UICONTROL Default Content]** e em **[!UICONTROL Change Redirect Offer]**.

   ![Alterar opção de Oferta de Redirecionamento](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Clique em **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Caixa de diálogo Criar Oferta de Redirecionamento](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca do Assets.

1. Insira o URL do conteúdo ou destino único para onde você quer redirecionar. O URL deve ser absoluto.

   >[!NOTE]
   >
   >O redirecionamento de ofertas resulta em um loop infinito se o URL de redirecionamento também qualifica o usuário para a mesma atividade. Você deve se certificar de que o usuário não se requalifica para a atividade após ser redirecionado.

1. Selecione as opções desejadas para personalizar sua oferta de redirecionamento:

   * **Incluir todos os parâmetros de URL:** Deslize o botão de alternância para habilitar esta opção se desejar que todos os parâmetros de URL presentes na página anterior sejam propagados para a página redirecionada.

     Por exemplo, você quer redirecionar visitantes diretamente de uma página de produtos masculinos para uma página de categoria de camisas masculinas. Você também pode desejar que os parâmetros dinâmicos presentes no URL sejam enviados, porque dessa forma você pode identificar se o visitante acessou o seu site a partir de um email, banners publicitários, publicidade de pesquisa ou organicamente. Ao habilitar esta opção, sua oferta de redirecionamento na página `https://www.mycompany.com/mens.html?emailId=123` automaticamente se tornará `https://www.mycompany.com/mensShirts.html?emailId=123` quando o valor inserido na caixa de URL foi `https://www.mycompany.com/mensShirts.html`.

   * **ID de sessão da mbox de passagem:** Necessário para redirecionar para um domínio diferente. Deslize o botão de alternância para habilitar esta opção se desejar que `sessionId` seja incluído automaticamente no redirecionamento. Isso é necessário somente quando você está testando cliques de um email ou cliques de um domínio para outro. A `sessionId` corresponde ao cookie do visitante, para que o visitante continue sendo monitorado e o conteúdo correto seja exibido.

     Se você usar a configuração de cookies próprios e de terceiros, não será necessário transmitir a ID de sessão da mbox ao atravessar domínios. Isso é persistente no cookie de terceiros, por isso não é necessário no URL.

1. Clique em **[!UICONTROL Save]**.

>[!NOTE]
>
>Entre em contato com seu Consultor de implementações antes de iniciar esses testes.

## Usar ofertas de redirecionamento em atividades

Você deve aplicar ofertas de redirecionamento usando o [!UICONTROL Form-Based Experience Composer]. No momento, não é possível aplicar ofertas de redirecionamento usando o VEC.

O [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] é uma experiência não visual e uma interface de criação de ofertas útil para criar experiências para uso nas atividades do [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Recommendations] quando o Visual Experience Composer não estiver disponível ou não for prático. Por exemplo, você pode usar o [!UICONTROL Form-Based Experience Composer] para criar experiências que usam ofertas de redirecionamento.

1. Crie ou edite uma atividade no [!UICONTROL Form-Based Experience Composer].

   Consulte o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter instruções detalhadas passo a passo.

1. Especifique o local desejado e adicione os refinamentos de público-alvo, conforme necessário.

1. Clique na lista suspensa na seção **[!UICONTROL Content]** e depois clique em **[!UICONTROL Change Redirect Offer]**.

   ![Alterar opção de Oferta de Redirecionamento](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Selecione a oferta de redirecionamento desejada na caixa de diálogo [!UICONTROL Select Remote Offer] e clique em **[!UICONTROL Done]**.

1. Termine configurando a atividade.

## Vídeo de treinamento: criador baseado em formulário ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo fornece uma demonstração do compositor baseado em formulário, que você pode usar para criar ofertas de redirecionamento.

* Criar uma atividade usando o Experience Composer baseado em formulário
* Entenda quando usar o Experience Composer baseado em formulário ou o Visual Experience Composer
* Use refinamentos para direcionar um local

>[!VIDEO](https://video.tv.adobe.com/v/17390)
