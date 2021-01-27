---
keywords: remote offer;remote offer selection matrix;cached content;dynamic content;url type
description: É possível usar ofertas remotas para hospedar conteúdo externo?
title: Criar ofertas remotas
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: 4109b0580ddb2809d29e75d0e5ec7ed4b5b126cf
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 54%

---


# Criar ofertas remotas

Para hospedar conteúdo fora do [!DNL Adobe Target], use ofertas remotas, que o [!DNL Target] faz referência e entrega aos sites do usuários. Esse conteúdo pode estar em uma gestão de conteúdo (CMS) ou em outro sistema, por motivos de facilidade de uso ou de segurança.

>[!NOTE]
>
>Ofertas remotas podem ser criadas na página [!UICONTROL Oferta] > [!UICONTROL Ofertas de código] ou na página [Compositor de experiências baseado em Forms](/help/c-experiences/form-experience-composer.md). Não é possível criar ou aplicar ofertas remotas no Visual Experience Composer (VEC). O conteúdo será inserido nos locais de solicitação [!DNL Target], portanto, é provável que eles não sejam apropriados para uma solicitação global [!DNL Target].
>
>[!DNL Target Classic] inclui recursos semelhantes: [!UICONTROL Oferta em seu site] e [!UICONTROL Oferta fora do Test&amp;Target].

Alguns exemplos de ofertas remotas incluem:

* Diferentes versões de vendas casadas
* Mensagens do carrinho de compras dinâmico
* Formulários
* Calculadoras
* Atualizações de taxa de juros

## Criar uma oferta remota na página Ofertas de código

1. Clique em **[!UICONTROL Ofertas]** e selecione a guia **[!UICONTROL Ofertas de código]**.

   ![Ofertas > Ofertas de código](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. Clique em **[!UICONTROL Criar]** > **[!UICONTROL Oferta remota]**.

   ![Caixa de diálogo Criar Oferta remota](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca [!UICONTROL Ativos].

1. Especifique o tipo de URL de redirecionamento.

   Consulte [Redirecionar tipo de URL: Em cache ou Dinâmico](#url-type) abaixo para obter mais informações.

1. Especifique o URL remoto para a oferta remota.

1. Clique em **[!UICONTROL Salvar]**.

## Crie uma oferta remota usando o Criador de experiências baseado em forma

1. Ao criar uma atividade usando o [Criador de experiências baseado em forma](/help/c-experiences/form-experience-composer.md), selecione o local para exibir a seção **[!UICONTROL Conteúdo]**.

   ![Seção de conteúdo no Criador de experiências baseado em forma](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. Clique na lista suspensa **[!UICONTROL Conteúdo padrão]** e, em seguida, clique em **[!UICONTROL Alterar Oferta remota]**.

   ![Opção Alterar Oferta remota](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Clique em **[!UICONTROL Criar]** > **[!UICONTROL Oferta remota]**.

   ![Caixa de diálogo Criar Oferta remota](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca [!UICONTROL Ativos].

1. Especifique o tipo de URL de redirecionamento.

   Consulte [Redirecionar tipo de URL: Em cache ou Dinâmico](#url-type) abaixo para obter mais informações.

1. Especifique o URL remoto para a oferta remota.

1. Clique em **[!UICONTROL Salvar]**.

## Tipo de URL de redirecionamento: Em cache ou dinâmico {#url-type}

As seguintes informações ajudam você a entender as diferenças entre as duas opções:

### URL em cache

O conteúdo de uma oferta remota em cache é exibido no [!DNL Target].

A cada duas horas, o [!DNL Target] busca o conteúdo no URL remoto e, em seguida, armazena o conteúdo dentro do [!DNL Target]. Quando os visitantes carregam um site com uma experiência que inclui uma oferta remota, a oferta é entregue pelo [!DNL Target].

As ofertas remotas em cache fornecem segurança aprimorada porque alguém conectado a [!DNL Target] não pode alterar o conteúdo. Para alterar o conteúdo, alguém precisaria fazer login no gerenciamento de conteúdo ou outro sistema e alterar o conteúdo lá.

Você pode especificar um URL absoluto ou relativo para uma oferta remota em cache.

### URL dinâmico

Uma oferta remota dinâmica é servida a partir do gerenciamento de conteúdo ou outro sistema, em vez do [!DNL Target].

Talvez você não queira que o conteúdo seja armazenado em cache periodicamente e entregue pelo [!DNL Target] sempre que os visitantes carregarem um site com uma experiência que inclua uma oferta remota. Em vez disso, você deseja chamar o sistema que está hospedando o conteúdo, possivelmente transmita informações específicas para que a oferta retornada possa ser dinâmica (ou diferente) para cada usuário. Por exemplo, se um usuário fizer login em um site para um cartão de crédito que inclua uma experiência com uma oferta remota dinâmica, você poderá passar parâmetros para o URL das informações da conta do usuário. Em seguida, o site pode fornecer informações específicas do usuário, como o saldo da conta.

Você pode clicar em **[!UICONTROL Adicionar Parâmetro]** para adicionar uma ou mais solicitações [!DNL Target] ou parâmetros de solicitação.

## Usar ofertas remotas no atividade

Você deve aplicar ofertas remotas usando o [!UICONTROL Criador de experiências baseado em forma]. No momento, não é possível aplicar ofertas remotas usando o VEC.

1. Crie ou edite uma atividade no [!UICONTROL Criador de experiências baseado em forma].

   Consulte [Criador de experiências baseado em forma](/help/c-experiences/form-experience-composer.md) para obter instruções detalhadas passo a passo.

1. Especifique o local desejado e adicione quaisquer refinamentos de audiência, conforme necessário.

1. Clique na lista suspensa na seção **[!UICONTROL Conteúdo]** e clique em **[!UICONTROL Alterar Oferta Remota]**.

   ![Opção Alterar Oferta remota](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. Selecione a oferta remota desejada na caixa de diálogo [!UICONTROL Selecionar Oferta remota] e clique em **[!UICONTROL Concluído]**.

1. Termine configurando a atividade.

## Práticas recomendadas para o uso do oferta remoto {#section_7718512D08E14121B6F6B8C38134F4BC}

Práticas recomendadas para usar ofertas remotas em suas atividades:

* Se sua oferta reside no mesmo domínio das solicitações [!DNL Target], usar a opção [!UICONTROL Cache] permite usar URLs relativos ao descrever a localização da oferta.

   Isso significa que ao mover sua atividade dos servidores de armazenamento temporário para produção, o conteúdo se tornará automaticamente acessível, sem necessidade de alterar o URL manualmente.

* Se o seu teste envolve dados gerados dinamicamente pelo seu servidor, a opção [!UICONTROL Dinâmica] pode ser a opção correta.
* Se você pretende testar apenas a aparência do seu conteúdo de oferta remota existente, use o [!UICONTROL Visual Experience Composer] para alterar a aparência do conteúdo retornado do sistema de gerenciamento de conteúdo.
* Use a Matriz de seleção de Oferta remota (abaixo) para ajudá-lo a escolher a oferta mais adequada para seu caso específico. Entre em contato com seu representante de conta caso tenha dúvidas.

## Como as ofertas remotas dinâmicas funcionam {#concept_CC2A969420B34364A9FA78C1CE251818}

Ofertas dinâmicas remotas utilizam tecnologia de página dinâmica para enviar os valores para a oferta.

A oferta é executada após a página ser renderizada. Um iframe invisível coleta os dados, os copia para fora do quadro e os insere na página, carregando os valores transmitidos.

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