---
keywords: páginas do site, páginas do site do target, direcionamento, página atual, página atual do target, página anterior, página anterior do target, página de aterrissagem, página de aterrissagem do target, cabeçalho http
description: Saiba como direcionar visitantes usando [!DNL Adobe Target] que estão em uma página específica do seu site.
title: Posso definir metas para visitantes com base nas páginas do site?
feature: Audiences
exl-id: 4c770b7b-775f-4483-aced-43f18a9a68c1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 26%

---

# Páginas do site

Você pode direcionar visitantes usando [!DNL Adobe Target] que acessam uma página específica do seu site.

1. Na interface do [!DNL Target], clique em **[!UICONTROL Públicos-alvo]** > **[!UICONTROL Criar público-alvo]**.
1. Nomeie o público-alvo e adicione uma descrição opcional.
1. Arrastar e soltar **[!UICONTROL Páginas do site]** no painel do construtor de público-alvo.

   ![Público-alvo de Páginas do site](assets/target_site_pages.png)

1. Clique no botão **[!UICONTROL Selecionar]** na lista suspensa, selecione uma das opções a seguir e configure a regra conforme desejado.

   As opções e avaliadores disponíveis nas listas suspensas subsequentes na regra variam de acordo com qual opção você escolher. A ilustração a seguir mostra as opções disponíveis se você escolher [!UICONTROL Página atual]:

   ![Página atual](assets/current-page.png)

   As seguintes opções estão disponíveis na lista suspensa inicial ao escolher [!UICONTROL Selecionar].

   * **[!UICONTROL Página atual]:** A página que o usuário está visualizando.

      As seguintes opções estão disponíveis na segunda lista suspensa se você escolher essa opção:

      * [!UICONTROL URL] (Para obter mais informações sobre como [!DNL Target] avalia URLs, consulte [Perguntas frequentes sobre direcionamentos e públicos](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domínio]
      * [!UICONTROL Consulta]
      * [!UICONTROL Subdomínio]
      * [!UICONTROL Domínio de nível superior]
      * [!UICONTROL Caminho]
      * [!UICONTROL Fragmento em hash (#)]
   * **[!UICONTROL Página anterior]:** A página que o usuário foi visualizado antes de clicar na página atual. O usuário deve clicar da página anterior para a página atual para que a página seja rastreada. A página anterior não é acompanhada se o usuário digitar um novo URL no navegador. O conteúdo atual dessa página depende do design do seu site. Por exemplo, se a página atual exibe informações sobre um produto específico, a página anterior pode ser uma página de categoria, onde o visitante seleciona o item específico. Por exemplo, uma página exibindo várias câmeras de um determinado tipo ou pode ser a página inicial que leva à página final.

      As seguintes opções estão disponíveis na segunda lista suspensa se você escolher essa opção:

      * [!UICONTROL URL] (Para obter mais informações sobre como o Target avalia URLs, consulte [Perguntas frequentes sobre direcionamentos e públicos](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domínio]
      * [!UICONTROL Consulta]
      * [!UICONTROL Subdomínio]
      * [!UICONTROL Domínio de nível superior]
      * [!UICONTROL Caminho]
   * **Página inicial:** a página inicial é a primeira página que o visitante vê ao acessar seu site. Por exemplo, se o visitante clica em um link no Google, que leva a uma página da categoria, a página da categoria é a página de aterrissagem. Se o link leva para sua home page, a home page é a página de aterrissagem. A página de aterrissagem é lembrada para a sessão do visitante. É possível direcionar mais profundo no site baseado em que a página de aterrissagem do visitante estava nessa sessão.

      As seguintes opções estão disponíveis na segunda lista suspensa se você escolher essa opção:

      * [!UICONTROL URL] (Para obter mais informações sobre como o Target avalia URLs, consulte [Perguntas frequentes sobre direcionamentos e públicos](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
      * [!UICONTROL Domínio]
      * [!UICONTROL Consulta]
      * [!UICONTROL Subdomínio]
      * [!UICONTROL Domínio de nível superior]
      * [!UICONTROL Caminho]
      * [!UICONTROL Fragmento em hash (#)]

      >[!NOTE]
      >
      >O objeto `landing.url` é redefinido em uma alteração de subdomínio ou em uma substituição do URL direto.

   * **[!UICONTROL Cabeçalho HTTP]:** Essa opção avalia as informações no cabeçalho HTTP da variável [!DNL Target] solicitação. Por exemplo, se o cabeçalho HTTP contiver informações de idioma, você poderá criar uma regra que contenha a variável `Accept-Language: es` para direcionar os visitantes que acessam a página em espanhol.

      As seguintes opções estão disponíveis na segunda lista suspensa se você escolher essa opção:

      * [!UICONTROL Accept]
      * [!UICONTROL Accept-Charset]
      * [!UICONTROL Accept-Encoding]
      * [!UICONTROL Accept-Language]
      * [!UICONTROL Autorização]
      * [!UICONTROL Controle de cache]
      * [!UICONTROL Conexão]
      * [!UICONTROL Tamanho do conteúdo]
      * [!UICONTROL Content-MDS]
      * [!UICONTROL Tipo de conteúdo]
      * [!UICONTROL Data]
      * [!UICONTROL Esperança]
      * [!UICONTROL De]
      * [!UICONTROL Host]
      * [!UICONTROL If-Match]
      * [!UICONTROL If-Modified-Since]
      * [!UICONTROL Se-Nenhum-Corresponder]
      * [!UICONTROL If-Range]
      * [!UICONTROL If-Unmodified-Since]
      * [!UICONTROL Max-Forwards]
      * [!UICONTROL Pragma]
      * [!UICONTROL Autorização de proxy]
      * [!UICONTROL Intervalo]
      * [!UICONTROL Referenciador]
      * [!UICONTROL TE]
      * [!UICONTROL Atualização]
      * [!UICONTROL User-Agent]
      * [!UICONTROL Via]
      * [!UICONTROL Aviso]

   Se você escolher [!UICONTROL Página atual], [!UICONTROL Página anterior]ou [!UICONTROL Página de aterrissagem], o [!UICONTROL Domínio] e [!UICONTROL Query] estão disponíveis. Considere o seguinte ao escolher essas opções:

   * **Domínio:** o domínio completo da página. Ao especificar um domínio, a prática recomendada é usar &quot;contém&quot;. Por exemplo, &quot;Domínio igual a facebook.com&quot; não aceita `m.facebook.com` ou `www.facebook.com`. &quot;Domínio contém facebook.com&quot; aceita qualquer variante de facebook.com.
   * **Consulta:** o conteúdo do URL após o primeiro ponto de interrogação (?).

      `foo.html?e0a72cb2a2c7`





1. (Opcional) Configure regras adicionais para o público-alvo.
1. Clique em **[!UICONTROL Concluído]**.

É possível criar públicos-alvo de páginas do site usando seu próprio &quot;parâmetro de consulta definido pelo usuário&quot; ou &quot;cabeçalho definido pelo usuário&quot;.

Use um:

* Parâmetro de consulta se a regra selecionada pelo usuário for [!UICONTROL Página atual], [!UICONTROL Página de aterrissagem]ou [!UICONTROL Página anterior]
* Cabeçalho se a regra selecionada pelo usuário for um cabeçalho HTTP

## Solução de problemas {#ts}

* Para que os públicos-alvo da página de aterrissagem funcionem corretamente, as solicitações devem ter a variável `mboxReferrer` conjunto de parâmetros (para a API de entrega, o `context.address.referringUrl` ) que a biblioteca at.js de JavaScript obtém da página usando o `document.referrer` atributo. Essa `HTMLDocument` retorna o URI da página que o usuário navegou. O valor desse atributo é uma string vazia quando o usuário navega diretamente para a página (não por meio de um link, mas, por exemplo, por meio de um marcador).

   Se esse comportamento não corresponder aos seus requisitos, considere executar uma das seguintes ações:

   * Passar [parâmetros de mbox](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) para [!DNL Target] para serem usados para fins de direcionamento.
   * Use um [Atividade de teste A/B](/help/main/c-activities/t-test-ab/test-ab.md) em vez de uma atividade de landing page. As atividades de Teste A/B não alternam as experiências do mesmo visitante.
   * Use um [perfil do visitante](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) em vez disso.

* Ao usar avaliadores &quot;inicia/termina com&quot; em strings contendo vírgulas, essas strings são avaliadas como uma matriz de valores, em que cada valor separado por vírgula é avaliado. Por exemplo, se você tiver o valor de um cabeçalho: `Accept-Language: en,zh;q=0.9,en-IN;q=0.8,zh-CN;q=0.7` ele se qualifica para condições como:
   * começa com zh,
   * começa com en,
   * termina com 0,7,
   * termina com 0,8.

## Vídeo de treinamento: Criação de públicos-alvo

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)
