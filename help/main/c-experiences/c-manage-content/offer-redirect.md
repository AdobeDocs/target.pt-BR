---
keywords: oferta de redirecionamento;criar oferta de redirecionamento;adicionar oferta html;Passar todos os parâmetros de URL no redirecionamento
description: Saiba como criar ofertas de redirecionamento para orientar os navegadores para novas páginas com facilidade.
title: Como Criar Ofertas De Redirecionamento?
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 25%

---

# Criar Ofertas de redirecionamento

Saiba como criar ofertas de redirecionamento para orientar os navegadores para novas páginas com facilidade.

Você pode ter duas páginas completamente diferentes para testar, em vez de mudar apenas partes do conteúdo dentro de uma página. Nesse caso, o teste A/B compara a página A versus a página B. Configure uma atividade [!UICONTROL A/B Test] com duas experiências: uma apontando para a página A padrão e a outra redirecionando para a página B. A oferta é configurada para redirecionar o visitante para uma página diferente.

>[!NOTE]
>
> * As ofertas de redirecionamento podem ser criadas na página [!UICONTROL Offers] > [!UICONTROL Code Offers] ou no [Experience Composer baseado no Forms](/help/main/c-experiences/form-experience-composer.md). Não é possível criar ou aplicar ofertas de redirecionamento no [!UICONTROL Visual Experience Composer] (VEC). O conteúdo é inserido nos locais de solicitação [!DNL Target], portanto, esses locais provavelmente não são apropriados para uma solicitação global [!DNL Target].
>
>* Não é possível usar ofertas de redirecionamento em mboxes AJAX (`mboxUpdate`).
>
>* Para ofertas de redirecionamento em atividades que usam o [[!UICONTROL Analytics as the reporting source]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), sua implementação deve atender a certos requisitos mínimos. Além disso, há informações importantes que você precisa saber. Consulte [Ofertas de redirecionamento - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Para obter informações sobre como configurar uma experiência com redirecionamento, consulte [Redirecionar para um URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

A oferta de redirecionamento executa um código JavaScript para redirecionar o navegador. Ela usa o método `window.location.replace();`, para que a página que o visitante é redirecionado não fique armazenada no histórico do navegador. Esse processo permite que os visitantes usem o botão Voltar em seus navegadores.

>[!NOTE]
>
>Se quiser passar o valor referenciador da landing page, use uma oferta do HTML em vez de uma oferta de redirecionamento.

## Criar uma oferta de redirecionamento a partir da página [!UICONTROL Code Offers]

1. Clique em **[!UICONTROL Offers]** e selecione a guia **[!UICONTROL Code Offers]**.
1. Clique em **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.
1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca [!UICONTROL Assets].

1. (Condicional) Se você tiver uma [conta do Target Premium](/help/main/c-intro/intro.md#premium), selecione o [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) desejado.

1. Especifique o URL do conteúdo ou destino exclusivo para o qual você deseja redirecionar. Este URL deve ser um URL absoluto.

   >[!NOTE]
   >
   >O redirecionamento de ofertas resulta em um loop infinito se o URL de redirecionamento também qualifica o usuário para a mesma atividade. Certifique-se de que o usuário não se requalifica para a atividade após ser redirecionado.

1. Selecione as opções desejadas para personalizar sua oferta de redirecionamento:

   * **[!UICONTROL Include all URL parameters]:** Habilite esta opção se desejar que todos os parâmetros de URL presentes na página anterior sejam propagados para uma página redirecionada.

     Por exemplo, você quer redirecionar visitantes diretamente de uma página de produtos masculinos para uma página de categoria de camisas masculinas. Você também quer que os parâmetros dinâmicos no URL sejam passados, pois esse método é usado para rastrear se as pessoas acessaram o site por email, banner publicitário, pesquisa de anúncio ou organicamente. Ao habilitar esta opção, sua oferta de redirecionamento na página `https://www.mycompany.com/mens.html?emailId=123` automaticamente se tornará `https://www.mycompany.com/mensShirts.html?emailId=123` quando o valor inserido na caixa de URL foi `https://www.mycompany.com/mensShirts.html`.

   * **[!UICONTROL Pass mbox session ID]:** Necessário para redirecionar para um domínio diferente. Deslize o botão de alternância para habilitar esta opção se desejar que o `sessionId` seja incluído automaticamente no redirecionamento. Essa opção é necessária somente quando você está testando cliques de um email ou cliques de um domínio para outro. A `sessionId` corresponde ao cookie do visitante, para que o visitante continue sendo monitorado e o conteúdo correto seja exibido.

     Se você usar a configuração de cookies próprios e de terceiros, não será necessário transmitir a ID de sessão da mbox ao atravessar domínios. Isso é persistente no cookie de terceiros, por isso não é necessário no URL.

1. Clique em **[!UICONTROL Create]**.

>[!IMPORTANT]
>
>Entre em contato com seu consultor de implementação antes de iniciar esses testes.

## Criar uma oferta de redirecionamento usando o [!UICONTROL Form-Based Experience Composer]

1. Ao criar uma atividade usando o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md), selecione o local para exibir a seção **[!UICONTROL Content]**.
1. Clique na lista suspensa **[!UICONTROL Content]**, clique no ícone **[!UICONTROL List]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) e clique em **[!UICONTROL Change Redirect Offer]**.
1. Clique em **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.
1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca [!UICONTROL Assets].

1. Especifique o URL do conteúdo ou destino exclusivo para o qual você deseja redirecionar. Este URL deve ser um URL absoluto.

   >[!NOTE]
   >
   >O redirecionamento de ofertas resulta em um loop infinito se o URL de redirecionamento também qualifica o usuário para a mesma atividade. Certifique-se de que o usuário não se requalifica para a atividade após ser redirecionado.

1. Selecione as opções desejadas para personalizar sua oferta de redirecionamento:

   * **[!UICONTROL Include all URL parameters]:** Deslize o botão de alternância para habilitar esta opção se desejar que todos os parâmetros de URL presentes na página anterior sejam propagados para a página redirecionada.

     Por exemplo, você quer redirecionar visitantes diretamente de uma página de produtos masculinos para uma página de categoria de camisas masculinas. Você também quer que os parâmetros dinâmicos no URL sejam passados, pois esse método é usado para rastrear se as pessoas acessaram o site por email, banner publicitário, pesquisa de anúncio ou organicamente. Ao habilitar esta opção, sua oferta de redirecionamento na página `https://www.mycompany.com/mens.html?emailId=123` automaticamente se tornará `https://www.mycompany.com/mensShirts.html?emailId=123` quando o valor inserido na caixa de URL foi `https://www.mycompany.com/mensShirts.html`.

   * **[!UICONTROL Pass mbox session ID]:** Necessário para redirecionar para um domínio diferente. Deslize o botão de alternância para habilitar esta opção se desejar que o `sessionId` seja incluído automaticamente no redirecionamento. Essa opção é necessária somente quando você está testando cliques de um email ou cliques de um domínio para outro. A `sessionId` corresponde ao cookie do visitante, para que o visitante continue sendo monitorado e o conteúdo correto seja exibido.

     Se você usar a configuração de cookies próprios e de terceiros, não será necessário transmitir a ID de sessão da mbox ao atravessar domínios. Isso é persistente no cookie de terceiros, por isso não é necessário no URL.

1. Clique em **[!UICONTROL Create]**.

>[!IMPORTANT]
>
>Entre em contato com seu consultor de implementação antes de iniciar esses testes.

## Usar ofertas de redirecionamento em atividades

Aplicar ofertas de redirecionamento usando o [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md). No momento, não é possível aplicar ofertas de redirecionamento usando o [!UICONTROL Visual Experience Composer] (VEC).

O [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] é uma experiência não visual e uma interface de criação de ofertas útil para criar experiências para uso nas atividades do [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Recommendations] quando o [!UICONTROL Visual Experience Composer] não está disponível ou é prático para uso. Por exemplo, você pode usar o [!UICONTROL Form-Based Experience Composer] para criar experiências que usam ofertas de redirecionamento.

1. Crie ou edite uma atividade no [!UICONTROL Form-Based Experience Composer].

   Consulte o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter instruções detalhadas passo a passo.

1. Especifique o local desejado e adicione os refinamentos de público-alvo, conforme necessário.

1. Clique na lista suspensa **[!UICONTROL Content]**, clique no ícone **[!UICONTROL List]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) e clique em **[!UICONTROL Change Redirect Offer]**.
1. Selecione a oferta de redirecionamento desejada na caixa de diálogo [!UICONTROL Select Redirect Offer] e clique em **[!UICONTROL Add]**.
1. Termine configurando a atividade.
