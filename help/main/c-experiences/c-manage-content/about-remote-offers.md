---
keywords: oferta remota;conteúdo em cache;conteúdo dinâmico;tipo de url
description: Descubra como aproveitar as ofertas remotas no  [!DNL Target]  para hospedar conteúdo externo de um CMS ou outros sistemas.
title: Como criar ofertas remotas?
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: 856396264c4a7b7e3370cd268e7f010092e2eae2
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 19%

---

# Criar ofertas remotas

Use ofertas remotas para hospedar conteúdo fora do [!DNL Adobe Target], permitindo que [!DNL Target] faça referência a esse conteúdo e o entregue aos sites do usuário. Esse conteúdo pode residir em um sistema de gerenciamento de conteúdo (CMS) ou em outro sistema por motivos de facilidade de uso ou segurança.

As ofertas remotas podem ser criadas na página [!UICONTROL Offers] > [!UICONTROL Code Offers] ou no [Experience Composer baseado no Forms](/help/main/c-experiences/form-experience-composer.md). Não é possível criar ou aplicar ofertas remotas no [!UICONTROL Visual Experience Composer] (VEC). O conteúdo é inserido nos locais de solicitação [!DNL Target], portanto, esses locais provavelmente não são apropriados para uma solicitação global [!DNL Target].

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

* As ofertas remotas são compatíveis com o:

   * Atividades A/B
   * Atividades do Direcionamento de experiência (XT)
   * Fluxos de trabalho baseados em formulário

* As ofertas remotas não são compatíveis com o:

   * [Recursos premium](/help/main/c-intro/intro.md#premium) (Automated Personalization (AP), Direcionamento automático e Recommendations)
   * Multivariate Testing (MVT), devido à dependência no VEC, que não oferece suporte a ofertas remotas.

* Se a sua oferta estiver no mesmo domínio que as solicitações [!DNL Target], o uso da opção [!UICONTROL Cached] permitirá que você use URLs relativas na descrição da sua localização de oferta.

  Isso significa que quando você move sua atividade dos servidores de preparo para a produção, o conteúdo é acessível automaticamente sem precisar alterar o URL manualmente.

* Se o teste envolve dados gerados dinamicamente pelo servidor, a opção [!UICONTROL Dynamic] pode ser a escolha certa.
* Se você planeja testar somente a aparência do conteúdo de oferta remota existente, use o [!UICONTROL Visual Experience Composer] para alterar a aparência do conteúdo retornado do sistema de gerenciamento de conteúdo.
* Use a [Matriz de seleção de oferta remota](#reference_B23BEDD29DDD47709A7651AFD27E776B) (abaixo) para ajudá-lo a escolher a oferta mais adequada ao seu caso específico. Entre em contato com seu representante de conta caso tenha dúvidas.

## Criar uma oferta remota da página [!UICONTROL Code Offers]

1. Clique em **[!UICONTROL Offers]** e selecione a guia **[!UICONTROL Code Offers]**.

1. Clique em **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

1. Na caixa de diálogo [!UICONTROL Create Remote Offer], forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca [!UICONTROL Offers].

1. (Condicional) Se você tiver uma [conta do Target Premium](/help/main/c-intro/intro.md#premium), selecione o [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) desejado.

1. Especifique o tipo de URL de redirecionamento.

   Consulte [Tipo de URL de redirecionamento: [!UICONTROL Onsite Cached] ou [!UICONTROL Onsite Dynamic]](#url-type) abaixo para obter mais informações.

1. Especifique o URL remoto absoluto para a oferta remota.

1. Clique em **[!UICONTROL Create]**.

## Criar uma oferta remota usando o [!UICONTROL Form-Based Experience Composer]

1. Ao criar uma atividade usando o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md), selecione o local para exibir a seção **[!UICONTROL Content]**.
1. Clique na lista suspensa **[!UICONTROL Content]**, clique no ícone **[!UICONTROL List]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) e clique em **[!UICONTROL Change Remote Offer]**.

1. Clique em **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca [!UICONTROL Assets].

1. (Condicional) Se você tiver uma [conta do Target Premium](/help/main/c-intro/intro.md#premium), selecione o [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) desejado.

1. Especifique o tipo de URL de redirecionamento.

   Consulte [Tipo de URL de redirecionamento: [!UICONTROL Onsite Cached] ou [!UICONTROL Onsite Dynamic]](#url-type) abaixo para obter mais informações.

1. Especifique o URL remoto para a oferta remota.

1. Clique em **[!UICONTROL Create]**.

## Tipo de URL de redirecionamento: [!UICONTROL Onsite Cached] ou [!UICONTROL Onsite Dynamic] {#url-type}

As informações a seguir ajudam a entender as diferenças entre as duas opções:

### URL [!UICONTROL Onsite Cached]

O conteúdo de uma oferta remota em cache é distribuído de [!DNL Target].

A cada duas horas, [!DNL Target] busca o conteúdo na URL remota e, em seguida, armazena o conteúdo dentro de [!DNL Target]. Quando os visitantes carregam um site com uma experiência que inclui uma oferta remota, o [!DNL Target] entrega a oferta.

As ofertas remotas em cache fornecem segurança aprimorada porque alguém conectado no [!DNL Target] não pode alterar o conteúdo. Para alterar o conteúdo, alguém precisaria fazer logon no gerenciamento de conteúdo ou outro sistema e alterar o conteúdo lá.

Você pode especificar um URL absoluto ou relativo para uma oferta remota em cache.

### URL [!UICONTROL Onsite Dynamic]

Uma oferta remota dinâmica é servida a partir do gerenciamento de conteúdo ou outro sistema, em vez de [!DNL Target].

Talvez você não queira que o conteúdo seja armazenado em cache periodicamente e entregue por [!DNL Target] sempre que os visitantes carregarem um site com uma experiência que inclua uma oferta remota. Em vez disso, você deseja chamar o sistema que hospeda o conteúdo, possivelmente transmitir informações específicas para que a oferta retornada possa ser dinâmica (ou diferente) para cada usuário. Por exemplo, se um usuário fizer login em um site para um cartão de crédito que inclua uma experiência com uma oferta remota dinâmica, você poderá passar parâmetros para o URL das informações da conta do usuário. Em seguida, o site pode fornecer informações específicas do usuário, como o saldo da conta.

Você pode clicar em **[!UICONTROL Add Parameter]** para adicionar uma ou mais [!DNL Target] solicitações ou parâmetros de solicitação.

## Usar ofertas remotas em atividades

Aplicar ofertas remotas usando o [!UICONTROL Form-Based Experience Composer]. No momento, não é possível aplicar ofertas remotas usando o [!UICONTROL Visual Experience Composer] (VEC).

O [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] é uma experiência não visual e uma interface de criação de ofertas útil para criar experiências para uso nas atividades do [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] (XT), [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Recommendations] quando o [!UICONTROL Visual Experience Composer] não está disponível ou é prático para uso. Por exemplo, você pode usar o [!UICONTROL Form-Based Experience Composer] para criar experiências que usam ofertas remotas.

1. Crie ou edite uma atividade no [!UICONTROL Form-Based Experience Composer].

   Consulte o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter instruções detalhadas passo a passo.

1. Especifique o local desejado e adicione os refinamentos de público-alvo, conforme necessário.

1. Clique na lista suspensa **[!UICONTROL Content]**, clique no ícone **[!UICONTROL List]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) e clique em **[!UICONTROL Change Remote Offer]**.

1. Selecione a oferta remota desejada na caixa de diálogo [!UICONTROL Change Remote Offer] e clique em **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

1. Termine configurando a atividade.

## Como funcionam as ofertas dinâmicas remotas {#concept_CC2A969420B34364A9FA78C1CE251818}

Ofertas dinâmicas remotas utilizam tecnologia de página dinâmica para enviar os valores para a oferta.

A oferta é executada após a página ser renderizada. Um iFrame invisível reúne os dados, copia os dados do quadro e insere na página, carregando os valores passados.

![imagem de remote_offer_howitworks_2](assets/remote_offer_howitworks_2.jpeg)

1. O navegador do visitante solicita uma página do seu servidor.

2. O navegador renderiza a página, incluindo mboxes.

3. A chamada `mboxCreate` inclui parâmetros necessários para renderizar conteúdo dinâmico.

4. [!DNL Target] retorna uma URL com o local do conteúdo dinâmico e seus parâmetros. Define um iFrame na área da mbox.

5. O navegador solicita o URL e é renderizado na página.

## Matriz de seleção de oferta remota {#reference_B23BEDD29DDD47709A7651AFD27E776B}

A matriz de seleção de oferta remota ajuda você a decidir qual tipo de oferta remota escolher: [!UICONTROL Onsite Cached] ou [!UICONTROL Onsite Dynamic].

| Recurso | Em cache no local | Dinâmica no local |
|--- |--- |--- |
| Atualizado sempre que o usuário faz uma solicitação. | Não | Sim |
| Atualizações de conteúdo | Armazenado em cache a cada duas horas | Atualizado imediatamente após cada solicitação |
| Tempo de carregamento | Mais rápido | Mais lento devido ao processamento do pedido |
| JavaScript pode ser visto na página | Sim | Não, mas pode enviar via URL |
| As ofertas podem incluir JavaScript | Sim | Sim |
| URL de oferta | Absoluto ou Relativo | Relativo |
| Computador solicitante | Servidores da Adobe | O computador do visitante, que armazena os cookies do visitante |
