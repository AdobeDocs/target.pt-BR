---
keywords: oferta remota;matriz de seleção de oferta remota;conteúdo armazenado em cache;conteúdo dinâmico;tipo de url
description: Saiba como usar ofertas remotas no Adobe [!DNL Target]  para hospedar conteúdo externo (conteúdo em um CMS ou outro sistema). Descubra por que você pode querer usar ofertas remotas.
title: Como criar ofertas remotas?
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 29%

---

# Criar ofertas remotas

Para hospedar conteúdo fora do [!DNL Adobe Target], use ofertas remotas, que o [!DNL Target] faz referência e entrega aos sites do usuários. Esse conteúdo pode estar em um gerenciamento de conteúdo (CMS) ou outro sistema, seja para facilidade de uso ou por motivos de segurança.

>[!NOTE]
>
>As ofertas remotas podem ser criadas na página [!UICONTROL Offers] > [!UICONTROL Code Offers] ou no [Experience Composer baseado no Forms](/help/main/c-experiences/form-experience-composer.md). Não é possível criar ou aplicar ofertas remotas no Visual Experience Composer (VEC). O conteúdo será injetado nos locais de solicitação [!DNL Target], portanto, provavelmente não são apropriados para uma solicitação global [!DNL Target].
>
>[!DNL Target Classic] incluiu recursos semelhantes: [!UICONTROL Offer on Your Site] e [!UICONTROL Offer Outside Test&Target].

Alguns exemplos de ofertas remotas incluem:

* Diferentes versões de vendas casadas
* Mensagens do carrinho de compras dinâmico
* Formulários
* Calculadoras
* Atualizações de taxa de juros
* E-mails
* Quiosques
* Assistentes de voz

## Práticas recomendadas para usar ofertas remotas {#section_7718512D08E14121B6F6B8C38134F4BC}

Práticas recomendadas para usar ofertas remotas em suas atividades:

* Se a sua oferta estiver no mesmo domínio que as solicitações [!DNL Target], o uso da opção [!UICONTROL Cached] permitirá que você use URLs relativas na descrição da sua localização de oferta.

  Isso significa que ao mover sua atividade dos servidores de armazenamento temporário para produção, o conteúdo se tornará automaticamente acessível, sem necessidade de alterar o URL manualmente.

* Se o teste envolve dados gerados dinamicamente pelo servidor, a opção [!UICONTROL Dynamic] pode ser a escolha certa.
* Se você planeja testar somente a aparência do conteúdo de oferta remota existente, use o [!UICONTROL Visual Experience Composer] para alterar a aparência do conteúdo retornado do sistema de gerenciamento de conteúdo.
* Use a [Matriz de seleção de oferta remota](#reference_B23BEDD29DDD47709A7651AFD27E776B) (abaixo) para ajudá-lo a escolher a oferta mais adequada ao seu caso específico. Entre em contato com seu representante de conta caso tenha dúvidas.

## Criar uma oferta remota na página Ofertas de código

1. Clique em **[!UICONTROL Offers]** e selecione a guia **[!UICONTROL Code Offers]**.

   ![Ofertas > Ofertas de código](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Clique em **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![Caixa de diálogo Criar oferta remota](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca [!UICONTROL Assets].

1. Especifique o tipo de URL de redirecionamento.

   Consulte [Tipo de URL de Redirecionamento: Em Cache ou Dinâmico](#url-type) abaixo para obter mais informações.

1. Especifique o URL remoto para a oferta remota.

1. Clique em **[!UICONTROL Save]**.

## Criar uma oferta remota usando o Experience Composer baseado em formulário

1. Ao criar uma atividade usando o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md), selecione o local para exibir a seção **[!UICONTROL Content]**.

   ![Seção de conteúdo no Experience Composer baseado em formulário](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. Clique na lista suspensa **[!UICONTROL Default Content]** e em **[!UICONTROL Change Remote Offer]**.

   ![Alterar opção de oferta remota](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Clique em **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![Caixa de diálogo Criar oferta remota](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca [!UICONTROL Assets].

1. Especifique o tipo de URL de redirecionamento.

   Consulte [Tipo de URL de Redirecionamento: Em Cache ou Dinâmico](#url-type) abaixo para obter mais informações.

1. Especifique o URL remoto para a oferta remota.

1. Clique em **[!UICONTROL Save]**.

## Tipo de URL de redirecionamento: em cache ou dinâmico {#url-type}

As informações a seguir ajudam a entender as diferenças entre as duas opções:

### URL em cache

O conteúdo de uma oferta remota em cache é distribuído de [!DNL Target].

A cada duas horas, [!DNL Target] busca o conteúdo na URL remota e, em seguida, armazena o conteúdo dentro de [!DNL Target]. Quando os visitantes carregam um site com uma experiência que inclui uma oferta remota, a oferta é entregue por [!DNL Target].

As ofertas remotas em cache fornecem segurança aprimorada porque alguém conectado no [!DNL Target] não pode alterar o conteúdo. Para alterar o conteúdo, alguém precisaria fazer login no gerenciamento de conteúdo ou outro sistema e alterar o conteúdo lá.

Você pode especificar um URL absoluto ou relativo para uma oferta remota em cache.

### URL dinâmico

Uma oferta remota dinâmica é servida a partir do gerenciamento de conteúdo ou outro sistema, em vez de [!DNL Target].

Talvez você não queira que o conteúdo seja armazenado em cache periodicamente e entregue por [!DNL Target] sempre que os visitantes carregarem um site com uma experiência que inclua uma oferta remota. Em vez disso, você deseja chamar o sistema que hospeda o conteúdo, possivelmente transmitir informações específicas para que a oferta retornada possa ser dinâmica (ou diferente) para cada usuário. Por exemplo, se um usuário fizer login em um site para um cartão de crédito que inclua uma experiência com uma oferta remota dinâmica, você poderá passar parâmetros para o URL das informações da conta do usuário. Em seguida, o site pode fornecer informações específicas do usuário, como o saldo da conta.

Você pode clicar em **[!UICONTROL Add Parameter]** para adicionar uma ou mais [!DNL Target] solicitações ou parâmetros de solicitação.

## Usar ofertas remotas em atividades

Você deve aplicar ofertas remotas usando o [!UICONTROL Form-Based Experience Composer]. No momento, não é possível aplicar ofertas remotas usando o VEC.

O [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] é uma experiência não visual e uma interface de criação de ofertas útil para criar experiências para uso nas atividades do [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Recommendations] quando o Visual Experience Composer não estiver disponível ou não for prático. Por exemplo, você pode usar o [!UICONTROL Form-Based Experience Composer] para criar experiências que usam ofertas remotas.

1. Crie ou edite uma atividade no [!UICONTROL Form-Based Experience Composer].

   Consulte o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter instruções detalhadas passo a passo.

1. Especifique o local desejado e adicione os refinamentos de público-alvo, conforme necessário.

1. Clique na lista suspensa na seção **[!UICONTROL Content]** e depois clique em **[!UICONTROL Change Remote Offer]**.

   ![Alterar opção de oferta remota](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Selecione a oferta remota desejada na caixa de diálogo [!UICONTROL Select Remote Offer] e clique em **[!UICONTROL Done]**.

1. Termine configurando a atividade.

## Como funcionam as ofertas dinâmicas remotas {#concept_CC2A969420B34364A9FA78C1CE251818}

Ofertas dinâmicas remotas utilizam tecnologia de página dinâmica para enviar os valores para a oferta.

A oferta é executada após a página ser renderizada. Um iframe invisível reúne os dados, copia-os do quadro e insere na página, carregando os valores passados.

![imagem de remote_offer_howitworks_2](assets/remote_offer_howitworks_2.jpeg)

## Matriz de seleção de oferta remota {#reference_B23BEDD29DDD47709A7651AFD27E776B}

A Matriz de Seleção de Oferta Remota ajuda você a decidir qual tipo de oferta remota escolher: [!UICONTROL Cached] ou [!UICONTROL Dynamic].

| Recurso | Armazenado em cache | Dinâmico |
|--- |--- |--- |
| Atualizado sempre que o usuário faz uma solicitação. | Não | Sim |
| Atualizações de conteúdo | Em cache a cada 2 horas | Atualizado imediatamente após cada solicitação |
| Tempo de carregamento | Mais rápido | Mais lento devido ao processamento do pedido |
| JavaScript pode ser visto na página | Sim | Não, mas pode enviar via URL |
| As ofertas podem incluir JavaScript | Sim | Sim |
| URL de oferta | Absoluto ou Relativo | Relativo |
| Computador solicitante | Servidores da Adobe | O computador do visitante, que armazena os cookies do visitante |

## Vídeo de treinamento: criador baseado em formulário ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo fornece uma demonstração do compositor baseado em formulário, que você pode usar para criar ofertas remotas.

* Criar uma atividade usando o Experience Composer baseado em formulário
* Entenda quando usar o Experience Composer baseado em formulário ou o Visual Experience Composer
* Use refinamentos para direcionar um local

>[!VIDEO](https://video.tv.adobe.com/v/17390)
