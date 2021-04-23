---
keywords: oferta remota, matriz de seleção de oferta remota, conteúdo armazenado em cache, conteúdo dinâmico, tipo de url
description: Saiba como usar ofertas remotas no Adobe [!DNL Target] para hospedar conteúdo externo (conteúdo em um CMS ou outro sistema). Descubra por que você pode querer usar ofertas remotas.
title: Como Criar Ofertas Remotas?
feature: Experiências e ofertas
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 49%

---

# Criar ofertas remotas

Para hospedar conteúdo fora do [!DNL Adobe Target], use ofertas remotas, que o [!DNL Target] faz referência e entrega aos sites do usuários. Esse conteúdo pode estar em um gerenciamento de conteúdo (CMS) ou outro sistema, seja para facilidade de uso ou por motivos de segurança.

>[!NOTE]
>
>As ofertas remotas podem ser criadas na página [!UICONTROL Offers] > [!UICONTROL Code Offers] ou no [Forms-Based Experience Composer](/help/c-experiences/form-experience-composer.md). Não é possível criar ou aplicar ofertas remotas no Visual Experience Composer (VEC). O conteúdo será injetado nos locais da solicitação [!DNL Target], portanto, provavelmente não são apropriados para uma solicitação global [!DNL Target].
>
>[!DNL Target Classic] inclui recursos semelhantes: [!UICONTROL Oferta em seu site] e [!UICONTROL Oferta fora do Test&amp;Target].

Alguns exemplos de ofertas remotas incluem:

* Diferentes versões de vendas casadas
* Mensagens do carrinho de compras dinâmico
* Formulários
* Calculadoras
* Atualizações de taxa de juros
* E-mails
* Quiosque
* Assistentes de voz

## Práticas recomendadas para usar ofertas remotas {#section_7718512D08E14121B6F6B8C38134F4BC}

Práticas recomendadas para usar ofertas remotas em suas atividades:

* Se sua oferta reside no mesmo domínio que as solicitações [!DNL Target], usar a opção [!UICONTROL Armazenada em Cache] permite usar URLs relativos ao descrever a localização da oferta.

   Isso significa que ao mover sua atividade dos servidores de armazenamento temporário para produção, o conteúdo se tornará automaticamente acessível, sem necessidade de alterar o URL manualmente.

* Se o seu teste envolve dados gerados dinamicamente pelo seu servidor, a opção [!UICONTROL Dinâmica] pode ser a opção correta.
* Se você pretende testar apenas a aparência do seu conteúdo de oferta remota existente, use o [!UICONTROL Visual Experience Composer] para alterar a aparência do conteúdo retornado do sistema de gerenciamento de conteúdo.
* Use a [Matriz de seleção de oferta remota](#reference_B23BEDD29DDD47709A7651AFD27E776B) (abaixo) para ajudá-lo a escolher a oferta mais adequada para o seu caso específico. Entre em contato com seu representante de conta caso tenha dúvidas.

## Crie uma oferta remota da página Ofertas de código

1. Clique em **[!UICONTROL Ofertas]** e selecione a guia **[!UICONTROL Ofertas de código]**.

   ![Ofertas > Ofertas de código](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Clique em **[!UICONTROL Criar]** > **[!UICONTROL Oferta remota]**.

   ![Caixa de diálogo Criar oferta remota](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca [!UICONTROL Ativos].

1. Especifique o tipo de URL de redirecionamento.

   Consulte [Tipo de URL de redirecionamento: Armazenado em cache ou Dinâmico](#url-type) abaixo para obter mais informações.

1. Especifique o URL remoto para a oferta remota.

1. Clique em **[!UICONTROL Salvar]**.

## Crie uma oferta remota usando o Experience Composer baseado em formulário

1. Ao criar uma atividade usando o [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md), selecione o local para exibir a seção **[!UICONTROL Conteúdo]**.

   ![Seção de conteúdo no Experience Composer baseado em formulário](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. Clique na lista suspensa **[!UICONTROL Conteúdo padrão]** e, em seguida, clique em **[!UICONTROL Alterar oferta remota]**.

   ![Opção Alterar oferta remota](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Clique em **[!UICONTROL Criar]** > **[!UICONTROL Oferta remota]**.

   ![Caixa de diálogo Criar oferta remota](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca [!UICONTROL Ativos].

1. Especifique o tipo de URL de redirecionamento.

   Consulte [Tipo de URL de redirecionamento: Armazenado em cache ou Dinâmico](#url-type) abaixo para obter mais informações.

1. Especifique o URL remoto para a oferta remota.

1. Clique em **[!UICONTROL Salvar]**.

## Tipo de URL de redirecionamento: Armazenado em cache ou dinâmico {#url-type}

As informações a seguir ajudam você a entender as diferenças entre as duas opções:

### URL em cache

O conteúdo de uma oferta remota em cache é exibido no [!DNL Target].

A cada duas horas, o [!DNL Target] busca o conteúdo no URL remoto e, em seguida, armazena o conteúdo dentro do [!DNL Target]. Quando os visitantes carregam um site com uma experiência que inclui uma oferta remota, a oferta é entregue pelo [!DNL Target].

As ofertas remotas em cache fornecem segurança aprimorada porque alguém conectado em [!DNL Target] não pode alterar o conteúdo. Para alterar o conteúdo, alguém precisaria fazer login no gerenciamento de conteúdo ou outro sistema e alterar o conteúdo lá.

Você pode especificar um URL absoluto ou relativo para uma oferta remota em cache.

### URL dinâmico

Uma oferta remota dinâmica é servida a partir do gerenciamento de conteúdo ou outro sistema, em vez do [!DNL Target].

Talvez você não queira que o conteúdo seja armazenado em cache periodicamente e entregue pelo [!DNL Target] sempre que os visitantes carregarem um site com uma experiência que inclua uma oferta remota. Em vez disso, você deseja chamar o sistema que hospeda o conteúdo, possivelmente transmitir informações específicas para que a oferta retornada possa ser dinâmica (ou diferente) para cada usuário. Por exemplo, se um usuário fizer login em um site para um cartão de crédito que inclua uma experiência com uma oferta remota dinâmica, você poderá passar parâmetros para o URL das informações da conta do usuário. Em seguida, o site pode fornecer informações específicas do usuário, como o saldo da conta.

Você pode clicar em **[!UICONTROL Adicionar Parâmetro]** para adicionar uma ou mais solicitações [!DNL Target] ou solicitar parâmetros.

## Usar ofertas remotas em atividades

Você deve aplicar ofertas remotas usando o [!UICONTROL Experience Composer baseado em formulário]. No momento, não é possível aplicar ofertas remotas usando o VEC.

O [!DNL Adobe Target] [!UICONTROL Experience Composer baseado em formulário] é uma experiência não visual e uma interface de criação de ofertas úteis na criação de experiências para uso em [!UICONTROL Testes A/B], [!UICONTROL Direcionamento de experiência] (XT), [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Recommendations a 10/> atividades quando o visual experience composer não estiver disponível ou for prático para uso. ] Por exemplo, você pode usar o [!UICONTROL Experience Composer baseado em formulário] para criar experiências que usam ofertas remotas.

1. Crie ou edite uma atividade no [!UICONTROL Experience Composer baseado em formulário].

   Consulte [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md) para obter instruções detalhadas passo a passo.

1. Especifique o local desejado e adicione os refinamentos do público-alvo, conforme necessário.

1. Clique na lista suspensa na seção **[!UICONTROL Content]** e, em seguida, clique em **[!UICONTROL Change Remote Offer]**.

   ![Opção Alterar oferta remota](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Selecione a oferta remota desejada na caixa de diálogo [!UICONTROL Selecionar Oferta Remota] e clique em **[!UICONTROL Concluído]**.

1. Termine configurando a atividade.

## Como as ofertas remotas dinâmicas funcionam {#concept_CC2A969420B34364A9FA78C1CE251818}

Ofertas dinâmicas remotas utilizam tecnologia de página dinâmica para enviar os valores para a oferta.

A oferta é executada após a página ser renderizada. Um iframe invisível coleta os dados, os copia para fora do quadro e insere na página, carregando os valores passados.

![](assets/remote_offer_howitworks_2.jpeg)

## Matriz de seleção de oferta remota {#reference_B23BEDD29DDD47709A7651AFD27E776B}

A Matriz de seleção de oferta dinâmica ajuda a decidir qual tipo de oferta dinâmica você deve selecionar: [!UICONTROL Armazenada em cache] ou [!UICONTROL Dinâmica].

| Recurso | Armazenado em cache | Dinâmico |
|--- |--- |--- |
| Atualizado sempre que o usuário faz uma solicitação. | Não | Sim |
| Atualizações de conteúdo | Em cache a cada 2 horas | Atualizado imediatamente após cada solicitação |
| Tempo de carregamento | Mais rápido | Mais lento devido ao processamento do pedido |
| JavaScript pode ser visto na página | Sim | Não, mas pode enviar via URL |
| As ofertas podem incluir JavaScript | Sim | Sim |
| URL de oferta | Absoluto   ou relativo | Relativo |
| Computador solicitante | Servidores da Adobe | O computador do visitante, que armazena os cookies do visitante |

## Vídeo de treinamento: Composer baseado em formulário ![Selo tutorial](/help/assets/tutorial.png)

Este vídeo fornece uma demonstração do compositor baseado em formulário, que pode ser usada para criar ofertas remotas.

* Criar uma atividade usando o Experience Composer baseado em formulário
* Entenda quando usar o Experience Composer baseado em formulário ou o Visual Experience Composer
* Use refinamentos para direcionar um local

>[!VIDEO](https://video.tv.adobe.com/v/17390)
