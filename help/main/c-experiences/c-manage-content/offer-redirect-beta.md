---
keywords: oferta de redirecionamento, criar oferta de redirecionamento, adicionar oferta html, passar todos parâmetros de URL no redirecionamento, passar mboxSessionId no redirecionamento (necessário somente quando o redirecionamento passar por um domínio diferente)
description: Saiba como criar ofertas de redirecionamento no [!DNL Target] para fazer com que um navegador redirecione para uma nova página.
title: Como Criar Ofertas De Redirecionamento?
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#beta newtab=true" tooltip="O que são recursos beta no  [!DNL Adobe Target]."
hide: true
hidefromtoc: true
source-git-commit: 3fe1094ff5a2610207034c38d749ae031e7b8caf
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 31%

---

# Criar Ofertas de redirecionamento

Criar ofertas de redirecionamento em [!DNL Adobe Target] para fazer com que um navegador redirecione para uma nova página.

>[!NOTE]
>
>Este artigo contém informações sobre atualizações no [!DNL Target] que atualmente faz parte de um programa Beta. A variável [!DNL Adobe Target] A equipe do geralmente ativa novos recursos para clientes selecionados para fins de teste e feedback. Após a conclusão do período de teste, esses recursos serão habilitados para todos os clientes no futuro [!DNL Target Standard/Premium] versões e anunciadas nas notas de versão.

Você pode ter duas páginas completamente diferentes para testar, em vez de mudar apenas partes do conteúdo dentro de uma página. Nesse caso, o teste A/B compara a página A versus a página B. Configure uma [!UICONTROL A/B Test] Atividade com duas experiências: uma apontando para a página A padrão e a outra redirecionando para a página B. A oferta é configurada para redirecionar o visitante para uma página diferente.

>[!NOTE]
>
> * As ofertas de redirecionamento podem ser criadas no [!UICONTROL Offers] > [!UICONTROL Code Offers] ou na página [Experience Composer baseado no Forms](/help/main/c-experiences/form-experience-composer.md). Não é possível criar ou aplicar ofertas de redirecionamento no [!UICONTROL Visual Experience Composer] (VEC). O conteúdo é inserido no [!DNL Target] locais de solicitação, portanto, esses locais provavelmente não são apropriados para um [!DNL Target] solicitação.
>
>* Não é possível usar ofertas de redirecionamento em mboxes AJAX (`mboxUpdate`).
>
>* Para ofertas de redirecionamento em atividades que usam o Analytics como fonte de relatórios (A4T), sua implementação deve atender a certos requisitos mínimos. Além disso, há informações importantes que você precisa saber. Para obter mais informações, consulte [Perguntas frequentes das Ofertas de redirecionamento - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
>
>* Para obter informações sobre como configurar uma experiência com redirecionamento, consulte [Redirecionar para um URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA).

A oferta de redirecionamento executa um código JavaScript para redirecionar o navegador. Ela usa o método `window.location.replace();`, para que a página que o visitante é redirecionado não fique armazenada no histórico do navegador. Esse processo permite que os visitantes usem o botão Voltar em seus navegadores.

>[!NOTE]
>
>Se quiser passar o valor referenciador da landing page, use uma oferta HTML em vez de uma oferta de redirecionamento.

## Crie uma oferta de redirecionamento do [!UICONTROL Code Offers] página

1. Clique em **[!UICONTROL Offers]**, em seguida, selecione a **[!UICONTROL Code Offers]** guia.

   ![Guia Ofertas de código](/help/main/c-experiences/c-manage-content/assets/offers-code-offers-new.png)

1. Clique em **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.

   ![Caixa de diálogo Criar oferta de redirecionamento](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer-new.png)

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na [!UICONTROL Assets] biblioteca.

1. (Condicional) Se você tiver uma [Conta do Target Premium](/help/main/c-intro/intro.md#premium), selecione o desejado [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. Especifique o URL do conteúdo ou destino exclusivo para o qual você deseja redirecionar. Este URL deve ser um URL absoluto.

   >[!NOTE]
   >
   >O redirecionamento de ofertas resulta em um loop infinito se o URL de redirecionamento também qualifica o usuário para a mesma atividade. Certifique-se de que o usuário não se requalifica para a atividade após ser redirecionado.

1. Selecione as opções desejadas para personalizar sua oferta de redirecionamento:

   * **Incluir todos os parâmetros de URL:** Deslize o botão para ativar essa opção se desejar que todos os parâmetros de URL presentes na página anterior sejam propagados para a página redirecionada.

     Por exemplo, você quer redirecionar visitantes diretamente de uma página de produtos masculinos para uma página de categoria de camisas masculinas. Você também pode desejar que os parâmetros dinâmicos presentes no URL sejam enviados, porque dessa forma você pode identificar se o visitante acessou o seu site a partir de um email, banners publicitários, publicidade de pesquisa ou organicamente. Ao ativar essa opção, sua oferta de redirecionamento na página `https://www.mycompany.com/mens.html?emailId=123` torna-se automaticamente `https://www.mycompany.com/mensShirts.html?emailId=123` quando tudo o que você digitou na caixa de URL foi `https://www.mycompany.com/mensShirts.html`.

   * **Envio da ID de sessão da mbox:** Necessário para redirecionar para um domínio diferente. Deslize o botão para ativar essa opção se desejar que o `sessionId` para ser incluído automaticamente no redirecionamento. Essa opção é necessária somente quando você está testando cliques de um email ou cliques de um domínio para outro. A `sessionId` corresponde ao cookie do visitante, para que o visitante continue sendo monitorado e o conteúdo correto seja exibido.

     Se você usar a configuração de cookies próprios e de terceiros, não será necessário transmitir a ID de sessão da mbox ao atravessar domínios. Isso é persistente no cookie de terceiros, por isso não é necessário no URL.

1. Clique em **[!UICONTROL Create]**.

>[!NOTE]
>
>Entre em contato com seu consultor de implementação antes de iniciar esses testes.

## Crie uma oferta de redirecionamento usando o [!UICONTROL Form-Based Experience Composer]

1. Ao criar uma atividade usando o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md), selecione o local para exibir a **[!UICONTROL Content]** seção.

   ![Seção de conteúdo no Experience Composer baseado em formulário](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Clique em **[!UICONTROL Default Content]** e clique em **[!UICONTROL Change Redirect Offer]**.

   ![Opção Alterar oferta de redirecionamento](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. Clique em **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![Caixa de diálogo Criar oferta de redirecionamento](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na [!UICONTROL Assets] biblioteca.

1. Especifique o URL do conteúdo ou destino exclusivo para o qual você deseja redirecionar. Este URL deve ser um URL absoluto.

   >[!NOTE]
   >
   >O redirecionamento de ofertas resulta em um loop infinito se o URL de redirecionamento também qualifica o usuário para a mesma atividade. Certifique-se de que o usuário não se requalifica para a atividade após ser redirecionado.

1. Selecione as opções desejadas para personalizar sua oferta de redirecionamento:

   * **Incluir todos os parâmetros de URL:** Deslize o botão para ativar essa opção se desejar que todos os parâmetros de URL presentes na página anterior sejam propagados para a página redirecionada.

     Por exemplo, você quer redirecionar visitantes diretamente de uma página de produtos masculinos para uma página de categoria de camisas masculinas. Você também pode desejar que os parâmetros dinâmicos presentes no URL sejam enviados, porque dessa forma você pode identificar se o visitante acessou o seu site a partir de um email, banners publicitários, publicidade de pesquisa ou organicamente. Ao ativar essa opção, sua oferta de redirecionamento na página `https://www.mycompany.com/mens.html?emailId=123` torna-se automaticamente `https://www.mycompany.com/mensShirts.html?emailId=123` quando tudo o que você digitou na caixa de URL foi `https://www.mycompany.com/mensShirts.html`.

   * **Envio da ID de sessão da mbox:** Necessário para redirecionar para um domínio diferente. Deslize o botão para ativar essa opção se desejar que o `sessionId` para ser incluído automaticamente no redirecionamento. Essa opção é necessária somente quando você está testando cliques de um email ou cliques de um domínio para outro. A `sessionId` corresponde ao cookie do visitante, para que o visitante continue sendo monitorado e o conteúdo correto seja exibido.

     Se você usar a configuração de cookies próprios e de terceiros, não será necessário transmitir a ID de sessão da mbox ao atravessar domínios. Isso é persistente no cookie de terceiros, por isso não é necessário no URL.

1. Clique em **[!UICONTROL Save]**.

>[!NOTE]
>
>Entre em contato com seu consultor de implementação antes de iniciar esses testes.

## Usar ofertas de redirecionamento em atividades

Você deve aplicar ofertas de redirecionamento usando o [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md). No momento, não é possível aplicar ofertas de redirecionamento usando o [!UICONTROL Visual Experience Composer] (VEC).

A variável [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] O é uma experiência não visual e uma interface de criação de ofertas útil na criação de experiências para uso no [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] XT), [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Recommendations] atividades quando o visual experience composer não estiver disponível ou não for prático para uso. Por exemplo, você pode usar a variável [!UICONTROL Form-Based Experience Composer] para criar experiências que usam ofertas de redirecionamento.

1. Crie ou edite uma atividade no [!UICONTROL Form-Based Experience Composer].

   Consulte [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter instruções detalhadas passo a passo.

1. Especifique o local desejado e adicione os refinamentos de público-alvo, conforme necessário.

1. Clique na lista suspensa no **[!UICONTROL Content]** e clique em **[!UICONTROL Change Redirect Offer]**.

   ![Opção Alterar oferta de redirecionamento](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. Selecione a oferta de redirecionamento desejada na [!UICONTROL Select Remote Offer] e clique em **[!UICONTROL Done]**.

1. Termine configurando a atividade.

## Vídeo de treinamento: criador baseado em forma ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo fornece uma demonstração do [!UICONTROL Form-Based Experience Composer], que você pode usar para criar ofertas de redirecionamento.

* Crie uma atividade usando o [!UICONTROL Form-Based Experience Composer]
* Entenda quando usar o [!UICONTROL Form-Based Experience Composer] vs. o [!UICONTROL Visual Experience Composer]
* Use refinamentos para direcionar um local

>[!VIDEO](https://video.tv.adobe.com/v/17390)