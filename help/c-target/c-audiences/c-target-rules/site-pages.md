---
keywords: páginas do site, páginas do site do target, direcionamento, página atual, página atual do target, página anterior, página anterior do target, páginas de aterrissagem, páginas de aterrissagem do target, mbox, mbox do target
description: Você pode direcionar os visitantes que estão em uma página específica ou têm um parâmetro de mbox específico usando o Adobe Target.
title: Páginas do site no Adobe Target
topic: Padrão
uuid: 1cf9fa94-dbec-4719-9a0a-79c1eb91a233
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Páginas do site{#site-pages}

Você pode direcionar os visitantes que estão em uma página específica ou têm um parâmetro de mbox específico.

>[!NOTE]
>
>Os tipos de página de site de público-alvo e os operadores de comparação agora correspondem aos tipos e operadores de comparação do Target Classic. É possível criar públicos-alvo de página do site usando seu próprio "parâmetro de consulta definido pelo usuário" ou "cabeçalho definido pelo usuário".

1. Na interface do [!DNL Target], clique em **[!UICONTROL Públicos-alvo]** &gt; **[!UICONTROL Criar público-alvo]**.
1. Dê um nome ao público-alvo.
1. Clique em **[!UICONTROL Adicionar regra]** &gt; **[!UICONTROL Páginas do site]**.

   ![Público-alvo de Páginas do site](assets/target_site_pages.png)

1. Clique em **[!UICONTROL Selecionar]** e selecione uma destas opções:

   * **Página atual:** a página que o usuário está atualmente, que é a página que contém uma mbox na atividade. Se você direcionar no nível da atividade, essa pode ser uma página com uma mbox que você está usando para definir condições de entrada ou uma página que exibe conteúdo. Se você está direcionando por experiência, então a página atual é a página em que a mbox é exibida. Para o direcionamento da Métrica de sucesso ou da conversão, então é a página em que essas mboxes estão.
   * **Página anterior:** é a página onde o usuário estava antes de clicar na página atual. (Para que a página seja acompanhada, o usuário deve clicar da página anterior para a página atual. A página anterior não é acompanhada se o usuário digitar um novo URL no navegador.) O conteúdo atual dessa página depende do design do seu site. Por exemplo, se a página atual exibir informações sobre um produto específico, a página anterior pode ser uma página de categoria onde o visitante seleciona o item específico (por exemplo, uma página que exibe diversas câmeras de um tipo específico) ou pode ser a página de aterrissagem que leva à página final.
   * **Página inicial:** a página inicial é a primeira página que o visitante vê ao acessar seu site. Por exemplo, se o visitante clica em um link no Google, que leva a uma página da categoria, a página da categoria é a página de aterrissagem. Se o link leva para sua home page, a home page é a página de aterrissagem. A página de aterrissagem é lembrada para a sessão do visitante. É possível direcionar mais profundo no site baseado em que a página de aterrissagem do visitante estava nessa sessão.

      >[!NOTE]
      >
      >O objeto `landing.url` é redefinido em uma alteração de subdomínio ou em uma substituição do URL direto.

   * **Mbox:** a mbox para a qual você está definindo metas. Por exemplo, se você quiser contar pedidos com um Pedido total de US$ 100 ou mais, você passaria `orderTotal` como um parâmetro de mbox com esse direcionamento especificado aqui.
   * **Domínio:** o domínio completo da página. Ao especificar um domínio, a prática recomendada é usar "contém". Por exemplo, "Domínio igual a facebook.com" não aceitará `m.facebook.com` ou `www.facebook.com`. "Domínio conterá facebook.com" aceitará qualquer variante de facebook.com.
   * **Consulta:** o conteúdo do URL após o primeiro ponto de interrogação (?).

      `foo.html?e0a72cb2a2c7`

1. (Opcional) Clique em **[!UICONTROL Adicionar regra]** e configure regras adicionais para o público-alvo.
1. Clique em **[!UICONTROL Salvar]**.

É possível criar públicos-alvo de páginas do site usando seu próprio "parâmetro de consulta definido pelo usuário" ou "cabeçalho definido pelo usuário".

Use um:

* parâmetro de consulta se a regra selecionada pelo usuário é Página atual, Página de aterrissagem ou Página anterior.
* Cabeçalho se a regra selecionada pelo usuário for um cabeçalho HTTP.

conforme ilustrado abaixo:

![](assets/site_pages.png)

## Solução de problemas {#ts}

* Para que os públicos-alvo da página inicial funcionem corretamente, as solicitações devem ter o `mboxReferrer` parâmetro definido (para a API de entrega, o `context.address.referringUrl` parâmetro) que a biblioteca JavaScript do at.js obtém da página usando o `document.referrer` atributo. Este `HTMLDocument` atributo retorna o URI da página da qual o usuário navegou. O valor desse atributo é uma string vazia quando o usuário navega para a página diretamente (não por meio de um link, mas, por exemplo, por meio de um marcador).

   Se esse comportamento não corresponder aos seus requisitos, considere executar uma das seguintes ações:

   * Enviar parâmetros [de](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) mbox para [!DNL Target] serem usados para fins de direcionamento.
   * Use uma atividade [de teste](/help/c-activities/t-test-ab/test-ab.md) A/B em vez de uma atividade de página inicial. As atividades de teste A/B não alternam as experiências do mesmo visitante.
   * Em vez disso, use um perfil [de](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) visitante.

## Vídeo de treinamento: Criação de públicos-alvo

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392?captions=por_br)
