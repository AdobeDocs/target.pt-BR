---
keywords: oferta de redirecionamento, criar oferta de redirecionamento, adicionar oferta html, passar todos parâmetros de URL no redirecionamento, passar mboxSessionId no redirecionamento (necessário somente quando o redirecionamento passar por um domínio diferente)
description: 'Saiba como criar ofertas de redirecionamento no Adobe Target para fazer com que um navegador seja redirecionado para uma nova página. '
title: Como crio Ofertas de redirecionamento?
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 48%

---


# Criar Ofertas de redirecionamento

Redirecionar ofertas em [!DNL Adobe Target] faz com que um navegador redirecione para uma nova página.

Você pode ter duas páginas completamente diferentes para testar, em vez de mudar apenas partes do conteúdo dentro de uma página. Nesse caso, o teste A/B compara a página A e a página B. Configure uma atividade de teste A/B com duas experiências: um apontando para a página A padrão e o outro redirecionando para a página B. A oferta é configurada para redirecionar o visitante para uma página diferente.

>[!NOTE]
>
> * Ofertas de redirecionamento podem ser criadas na página [!UICONTROL Oferta] > [!UICONTROL Ofertas de código] ou no [Criador de experiências baseado em Forms](/help/c-experiences/form-experience-composer.md). Não é possível criar ou aplicar ofertas de redirecionamento no Visual Experience Composer (VEC). O conteúdo será inserido nos locais de solicitação [!DNL Target], portanto, é provável que eles não sejam apropriados para uma solicitação global [!DNL Target].
   >
   >
* Não é possível usar ofertas de redirecionamento em mboxes ajax (`mboxUpdate`).
   >
   >
* Para ofertas de redirecionamento em atividades usando A4T, sua implementação deve atender certos requisitos mínimos. Além disso, há informações importantes que você precisa saber. Para obter mais informações, consulte [Ofertas de redirecionamento - Perguntas frequentes do A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
   >
   >
* Para obter informações sobre como configurar uma experiência com redirecionamento, consulte [Redirecionar para um URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).


A oferta de redirecionamento executa um código JavaScript para redirecionar o navegador. Ela usa o método `window.location.replace();`, para que a página que o visitante é redirecionado não fique armazenada no histórico do navegador. Isso permite que o visitante consiga utilizar o botão Voltar de seu navegador.

>[!NOTE]
>
>Se desejar passar o valor referenciador da página de aterrissagem, é recomendado usar uma oferta HTML em vez de uma oferta de redirecionamento.

## Criar uma oferta de redirecionamento na página Ofertas de código

1. Clique em **[!UICONTROL Ofertas]** e selecione a guia **[!UICONTROL Ofertas de código]**.

   ![Guia Ofertas de código](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Clique em **[!UICONTROL Criar]** > **[!UICONTROL Oferta de redirecionamento]**.

   ![Caixa de diálogo Criar Oferta de redirecionamento](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca Ativos.

1. Insira o URL do conteúdo ou destino único para onde você quer redirecionar. O URL deve ser absoluto.

   >[!NOTE]
   >
   >O redirecionamento de ofertas resulta em um loop infinito se o URL de redirecionamento também qualifica o usuário para a mesma atividade. Você deve se certificar de que o usuário não se requalifica para a atividade após ser redirecionado.

1. Selecione as opções desejadas para personalizar sua oferta de redirecionamento:

   * **Incluir todos os parâmetros de URL:** Deslize a alternância para ativar essa opção se desejar que todos os parâmetros de URL presentes na página anterior sejam propagados para a página redirecionada.

      Por exemplo, você quer redirecionar visitantes diretamente de uma página de produtos masculinos para uma página de categoria de camisas masculinas. Você também pode desejar que os parâmetros dinâmicos presentes no URL sejam enviados, porque dessa forma você pode identificar se o visitante acessou o seu site a partir de um email, banners publicitários, publicidade de pesquisa ou organicamente. Ao ativar essa opção, sua oferta de redirecionamento na página `https://www.mycompany.com/mens.html?emailId=123` se tornará automaticamente `https://www.mycompany.com/mensShirts.html?emailId=123` quando tudo o que você inseriu na caixa de URL for `https://www.mycompany.com/mensShirts.html`.

   * **Enviar ID de sessão da mbox:** obrigatório para redirecionar para um domínio diferente. Deslize a alternância para ativar essa opção se desejar que `sessionId` seja incluído automaticamente no redirecionamento. Isso é necessário somente quando você está testando cliques de um email ou cliques de um domínio para outro. A `sessionId` corresponde ao cookie do visitante, para que o visitante continue sendo monitorado e o conteúdo correto seja exibido.

      Se você usar a configuração de cookies próprios e de terceiros, não precisará passar a ID de sessão da mbox ao atravessar domínios. Isso é persistente no cookie de terceiros, por isso não é necessário no URL.

1. Clique em **[!UICONTROL Salvar]**.

>[!NOTE]
>
>Entre em contato com seu Consultor de implementações antes de iniciar esses testes.

## Criar uma oferta de redirecionamento usando o Criador de experiências baseado em forma

1. Ao criar uma atividade usando o [Criador de experiências baseado em forma](/help/c-experiences/form-experience-composer.md), selecione o local para exibir a seção **[!UICONTROL Conteúdo]**.

   ![Seção de conteúdo no Criador de experiências baseado em forma](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. Clique na lista suspensa **[!UICONTROL Conteúdo padrão]** e clique em **[!UICONTROL Alterar Oferta de redirecionamento]**.

   ![Opção Alterar Oferta de redirecionamento](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Clique em **[!UICONTROL Criar]** > **[!UICONTROL Oferta de redirecionamento]**.

   ![Caixa de diálogo Criar Oferta de redirecionamento](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca Ativos.

1. Insira o URL do conteúdo ou destino único para onde você quer redirecionar. O URL deve ser absoluto.

   >[!NOTE]
   >
   >O redirecionamento de ofertas resulta em um loop infinito se o URL de redirecionamento também qualifica o usuário para a mesma atividade. Você deve se certificar de que o usuário não se requalifica para a atividade após ser redirecionado.

1. Selecione as opções desejadas para personalizar sua oferta de redirecionamento:

   * **Incluir todos os parâmetros de URL:** Deslize a alternância para ativar essa opção se desejar que todos os parâmetros de URL presentes na página anterior sejam propagados para a página redirecionada.

      Por exemplo, você quer redirecionar visitantes diretamente de uma página de produtos masculinos para uma página de categoria de camisas masculinas. Você também pode desejar que os parâmetros dinâmicos presentes no URL sejam enviados, porque dessa forma você pode identificar se o visitante acessou o seu site a partir de um email, banners publicitários, publicidade de pesquisa ou organicamente. Ao ativar essa opção, sua oferta de redirecionamento na página `https://www.mycompany.com/mens.html?emailId=123` se tornará automaticamente `https://www.mycompany.com/mensShirts.html?emailId=123` quando tudo o que você inseriu na caixa de URL for `https://www.mycompany.com/mensShirts.html`.

   * **Enviar ID de sessão da mbox:** obrigatório para redirecionar para um domínio diferente. Deslize a alternância para ativar essa opção se desejar que `sessionId` seja incluído automaticamente no redirecionamento. Isso é necessário somente quando você está testando cliques de um email ou cliques de um domínio para outro. A `sessionId` corresponde ao cookie do visitante, para que o visitante continue sendo monitorado e o conteúdo correto seja exibido.

      Se você usar a configuração de cookies próprios e de terceiros, não precisará passar a ID de sessão da mbox ao atravessar domínios. Isso é persistente no cookie de terceiros, por isso não é necessário no URL.

1. Clique em **[!UICONTROL Salvar]**.

>[!NOTE]
>
>Entre em contato com seu Consultor de implementações antes de iniciar esses testes.

## Usar ofertas de redirecionamento no atividade

Você deve aplicar ofertas de redirecionamento usando o [!UICONTROL Criador de experiências baseado em forma]. No momento, não é possível aplicar ofertas de redirecionamento usando o VEC.

O [!DNL Adobe Target] [!UICONTROL Criador de experiências baseado em forma] é uma interface de experiência não visual e criação de ofertas que é útil na criação de experiências para uso em [!UICONTROL Testes A/B], [!UICONTROL Definição de metas de experiência] (XT), [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Recommendations a10/> atividade quando o Visual Experience Composer não está disponível ou é prático para uso. ] Por exemplo, você pode usar o [!UICONTROL Criador de experiências baseado em forma] para criar experiências que usam ofertas de redirecionamento.

1. Crie ou edite uma atividade no [!UICONTROL Criador de experiências baseado em forma].

   Consulte [Criador de experiências baseado em forma](/help/c-experiences/form-experience-composer.md) para obter instruções detalhadas passo a passo.

1. Especifique o local desejado e adicione quaisquer refinamentos de audiência, conforme necessário.

1. Clique na lista suspensa na seção **[!UICONTROL Conteúdo]** e clique em **[!UICONTROL Alterar Oferta de Redirecionamento]**.

   ![Opção Alterar Oferta de redirecionamento](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Selecione a oferta de redirecionamento desejada na caixa de diálogo [!UICONTROL Selecionar Oferta remota] e clique em **[!UICONTROL Concluído]**.

1. Termine configurando a atividade.

## Vídeo de treinamento: Compositor baseado em forma ![Etiqueta do tutorial](/help/assets/tutorial.png)

Este vídeo fornece uma demonstração do compositor baseado em formulário, que você pode usar para criar ofertas de redirecionamento.

* Criar uma atividade usando o Experience Composer baseado em formulário
* Entenda quando usar o Experience Composer baseado em formulário ou o Visual Experience Composer
* Use refinamentos para direcionar um local

>[!VIDEO](https://video.tv.adobe.com/v/17390)
