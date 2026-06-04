---
keywords: oferta remota;conteúdo em cache;conteúdo dinâmico;tipo de url
description: Descubra como aproveitar as ofertas remotas no  [!DNL Target]  para hospedar conteúdo externo de um CMS ou outros sistemas.
title: Como criar ofertas remotas?
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
TQID: https://experienceleague.adobe.com/maKcis5ROOKMcc3-axxGv1qJIQzC6o-Qc-Cjl8clQ1I
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1145
ht-degree: 24%

---

# Criar ofertas remotas

Use ofertas remotas para hospedar conteúdo fora do [!DNL Adobe Target], permitindo que [!DNL Target] faça referência a esse conteúdo e o entregue aos sites do usuário. Esse conteúdo pode residir em um sistema de gerenciamento de conteúdo (CMS) ou em outro sistema por motivos de facilidade de uso ou segurança.

As ofertas remotas podem ser criadas na página [!UICONTROL Ofertas] > [!UICONTROL Ofertas de código] ou no [Experience Composer baseado no Forms](/help/main/c-experiences/form-experience-composer.md). Não é possível criar ou aplicar ofertas remotas no [!UICONTROL Visual Experience Composer] (VEC). O conteúdo é inserido nos locais de solicitação [!DNL Target], portanto, esses locais provavelmente não são apropriados para uma solicitação global [!DNL Target].

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

* Se sua oferta estiver no mesmo domínio que as solicitações [!DNL Target], o uso da opção [!UICONTROL Em cache] permitirá que você use URLs relativas na descrição do local da oferta.

  Isso significa que quando você move sua atividade dos servidores de preparo para a produção, o conteúdo é acessível automaticamente sem precisar alterar o URL manualmente.

* Se o seu teste envolve dados gerados dinamicamente pelo seu servidor, a opção [!UICONTROL Dinâmica] pode ser a opção correta.
* Se você pretende testar apenas a aparência do seu conteúdo de oferta remota existente, use o [!UICONTROL Visual Experience Composer] para alterar a aparência do conteúdo retornado do sistema de gerenciamento de conteúdo.
* Use a [Matriz de seleção de oferta remota](#reference_B23BEDD29DDD47709A7651AFD27E776B) (abaixo) para ajudá-lo a escolher a oferta mais adequada ao seu caso específico. Entre em contato com seu representante de conta caso tenha dúvidas.

## Criar uma oferta remota a partir da página [!UICONTROL Ofertas de código]

1. Clique em **[!UICONTROL Ofertas]** e selecione a guia **[!UICONTROL Ofertas de código]**.

1. Clique em **[!UICONTROL Criar oferta]** > **[!UICONTROL Oferta remota]**.

1. Na caixa de diálogo [!UICONTROL Criar oferta remota], forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca [!UICONTROL Ofertas].

1. (Condicional) Se você tiver uma [conta do Target Premium](/help/main/c-intro/intro.md#premium), selecione o [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) desejado.

1. Especifique o tipo de URL de redirecionamento.

   Consulte [Tipo de URL de redirecionamento: [!UICONTROL No site em cache] ou [!UICONTROL No site dinâmico]](#url-type) abaixo para obter mais informações.

1. Especifique o URL remoto absoluto para a oferta remota.

1. Clique em **[!UICONTROL Criar]**.

## Crie uma oferta remota usando o [!UICONTROL Experience Composer baseado em formulário]

1. Ao criar uma atividade usando o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md), selecione o local para exibir a seção **[!UICONTROL Conteúdo]**.
1. Clique na lista suspensa **[!UICONTROL Conteúdo]**, clique no ícone **[!UICONTROL Lista]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) e clique em **[!UICONTROL Alterar oferta remota]**.

1. Clique em **[!UICONTROL Criar oferta]** > **[!UICONTROL Oferta remota]**.

1. Forneça um nome descritivo para a oferta.

   Um nome descritivo ajuda você e outras pessoas a encontrar rapidamente a oferta na biblioteca [!UICONTROL Ativos].

1. (Condicional) Se você tiver uma [conta do Target Premium](/help/main/c-intro/intro.md#premium), selecione o [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) desejado.

1. Especifique o tipo de URL de redirecionamento.

   Consulte [Tipo de URL de redirecionamento: [!UICONTROL No site em cache] ou [!UICONTROL No site dinâmico]](#url-type) abaixo para obter mais informações.

1. Especifique o URL remoto para a oferta remota.

1. Clique em **[!UICONTROL Criar]**.

## Tipo de URL de redirecionamento: [!UICONTROL No site Armazenado em Cache] ou [!UICONTROL No site Dinâmico] {#url-type}

As informações a seguir ajudam a entender as diferenças entre as duas opções:

### URL [!UICONTROL Em Cache] No Site

O conteúdo de uma oferta remota em cache é distribuído de [!DNL Target].

A cada duas horas, [!DNL Target] busca o conteúdo na URL remota e, em seguida, armazena o conteúdo dentro de [!DNL Target]. Quando os visitantes carregam um site com uma experiência que inclui uma oferta remota, o [!DNL Target] entrega a oferta.

As ofertas remotas em cache fornecem segurança aprimorada porque alguém conectado no [!DNL Target] não pode alterar o conteúdo. Para alterar o conteúdo, alguém precisaria fazer logon no gerenciamento de conteúdo ou outro sistema e alterar o conteúdo lá.

Você pode especificar um URL absoluto ou relativo para uma oferta remota em cache.

### URL [!UICONTROL Dinâmica] no Site

Uma oferta remota dinâmica é servida a partir do gerenciamento de conteúdo ou outro sistema, em vez de [!DNL Target].

Talvez você não queira que o conteúdo seja armazenado em cache periodicamente e entregue por [!DNL Target] sempre que os visitantes carregarem um site com uma experiência que inclua uma oferta remota. Em vez disso, você deseja chamar o sistema que hospeda o conteúdo, possivelmente transmitir informações específicas para que a oferta retornada possa ser dinâmica (ou diferente) para cada usuário. Por exemplo, se um usuário fizer login em um site para um cartão de crédito que inclua uma experiência com uma oferta remota dinâmica, você poderá passar parâmetros para o URL das informações da conta do usuário. Em seguida, o site pode fornecer informações específicas do usuário, como o saldo da conta.

Você pode clicar em **[!UICONTROL Adicionar Parâmetro]** para adicionar uma ou mais solicitações [!DNL Target] ou solicitar parâmetros.

## Usar ofertas remotas em atividades

Aplicar ofertas remotas usando o [!UICONTROL Experience Composer baseado em formulário]. No momento, não é possível aplicar ofertas remotas usando o [!UICONTROL Visual Experience Composer] (VEC).

O [!DNL Adobe Target] [!UICONTROL Experience Composer baseado em formulário] é uma interface de criação de ofertas e experiências não visuais que é útil na criação de experiências para uso em [!UICONTROL Testes A/B], [!UICONTROL Direcionamento de experiência] (XT), [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Atividades do Recommendations] quando o [!UICONTROL Visual Experience Composer] não estiver disponível ou não for prático. Por exemplo, você pode usar o [!UICONTROL Experience Composer baseado em formulário] para criar experiências que usam ofertas remotas.

1. Crie ou edite uma atividade no [!UICONTROL Experience Composer baseado em formulário].

   Consulte o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter instruções detalhadas passo a passo.

1. Especifique o local desejado e adicione os refinamentos de público-alvo, conforme necessário.

1. Clique na lista suspensa **[!UICONTROL Conteúdo]**, clique no ícone **[!UICONTROL Lista]** ( ![Lista](/help/main/assets/icons/MoreSmallList.svg) ) e clique em **[!UICONTROL Alterar oferta remota]**.

1. Selecione a oferta remota desejada na caixa de diálogo [!UICONTROL Alterar Oferta Remota] e clique em **[!UICONTROL Criar Oferta]** > **[!UICONTROL Oferta Remota]**.

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

A matriz de seleção de oferta remota ajuda você a decidir qual tipo de oferta remota escolher: [!UICONTROL No Site em Cache] ou [!UICONTROL No Site Dinâmico].

| Recurso | Em cache no local | Dinâmica no local |
|--- |--- |--- |
| Atualizado sempre que o usuário faz uma solicitação. | Não | Sim |
| Atualizações de conteúdo | Armazenado em cache a cada duas horas | Atualizado imediatamente após cada solicitação |
| Tempo de carregamento | Mais rápido | Mais lento devido ao processamento do pedido |
| JavaScript pode ser visto na página | Sim | Não, mas pode enviar via URL |
| As ofertas podem incluir JavaScript | Sim | Sim |
| URL de oferta | Absoluto ou Relativo | Relativo |
| Computador solicitante | Servidores da Adobe | O computador do visitante, que armazena os cookies do visitante |
