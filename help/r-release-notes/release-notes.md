---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes
description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Adobe Target Standard e do Target Premium.
title: 'Notas de versão do Target (atual) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 6b49e4fb6c92da023678c1f27823458229d21711

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium. Além disso, as notas de versão para APIs do Target, SDKs, biblioteca JavaScript (at.js) e outras alterações da plataforma também são incluídas, quando aplicável.

Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Target Java SDK versão 1.1.0 (16 de dezembro de 2019)

* Suporte para configuração de proxy adicionado devido a uma contribuição de código aberto feita por @hisham-hassan.

Para obter mais informações, consulte Notas de [versão - SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)Java do Target.

## Target Java SDK versão 1.0.1 (11 de novembro de 2019)

O seguinte problema foi corrigido na versão 1.0.1:

* Envie uma ID de dados adicional em uma solicitação do Target mesmo quando não houver cookie da API do visitante presente.

Para obter mais informações, consulte Notas de [versão - SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)Java do Target.

## Plataforma Target (31 de outubro de 2019)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| Java SDK | O [!DNL Target] Java SDK permite implantar o lado do [!DNL Target] servidor. Esse Java SDK ajuda você a se integrar facilmente [!DNL Target] com outras [!DNL Adobe Experience Cloud] soluções, como [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]e [!DNL Adobe Audience Manager].<br>O Java SDK apresenta práticas recomendadas e remove complexidades ao integrar-se [!DNL Target] por meio de nossa API de entrega, para que suas equipes de engenharia possam se concentrar na lógica comercial. A seguir estão recursos notáveis que estamos introduzindo na versão mais recente:<ul><li>Suporte para busca prévia e notificações que permitem otimizar o desempenho por meio do cache.</li><li>Suporte para otimizar o desempenho quando você tem uma integração híbrida do [!DNL Target] em suas páginas da Web e do lado do servidor. Estamos introduzindo uma configuração chamada `serverState` que é preenchida por experiências recuperadas pelo lado do servidor para que o at.js 2.2 não faça mais uma chamada de servidor adicional para recuperar as experiências. Essa abordagem otimiza o desempenho de carregamento da página.</li><li>Suporte para recuperar atividades criadas pelo VEC por meio do Java SDK, possibilitado pela nova API de entrega.</li><li>Criado de forma aberta para que seus desenvolvedores possam contribuir com o [Target Java SDK](https://github.com/adobe/target-java-sdk).</li></ul>Para obter mais informações, consulte Notas de [versão - SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)Java do Target.<br>Saiba mais sobre o Target Java SDK no Adobe Tech Blog - Otimização do lado do [servidor com o novo Target Java SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2). |

## Target Standard/Premium 19.10.2 (31 de outubro de 2019)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| ![Atributos de múltiplos valores do selo](/help/assets/premium.png) Premium | Às vezes, você deseja trabalhar com um campo de vários valores. Considere os exemplos a seguir:<ul><li>Você oferece filmes aos usuários. Um determinado filme tem vários atores.</li><li>Você vende ingressos para concertos. Um determinado usuário tem várias bandas favoritas.</li><li>Você vende roupas. Uma camisa está disponível em vários tamanhos.</li></ul>Para lidar com recomendações nesses cenários, você pode passar dados de vários valores para o Target Recommendations e usar operadores especiais de vários valores.<br>Para obter mais informações, consulte [Trabalhar com atributos](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md)de vários valores. |

## Target Standard/Premium 19.10.1 (22 de outubro de 2019)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| ![Recomendações](/help/assets/premium.png) baseadas<br>no usuário do crachá Premium (24 de outubro de 2019) | Recomenda itens com base no histórico de navegação, visualização e compra de cada visitante. Esses itens são geralmente chamados de "Recomendado para você".<br>Esse critério permite que você forneça conteúdo e experiências personalizadas para visitantes novos e recorrentes. A lista de recomendações é ponderada em relação à atividade mais recente do visitante, é atualizada na sessão e se torna mais personalizada à medida que o visitante navega em seu site.<br>Para obter mais informações, consulte "Recomendações baseadas no usuário" em [Critérios/Algoritmos](/help/c-recommendations/c-algorithms/algorithms.md#criteria-algorithms). |

### Navegação na Adobe Experience Cloud

* Ao efetuar logon no [!DNL Adobe Experience Cloud], você será direcionado para a nova navegação do cabeçalho. É muito semelhante à navegação anterior com a barra preta na parte superior, mas oferece as seguintes melhorias:

   * Comutação mais fácil entre organizações [!DNL Identity Management System] (IMS) ou para uma solução diferente.
   * Ajuda do usuário aprimorada: Os resultados da pesquisa incluem os resultados da documentação do [!DNL Target] produto, bem como fóruns da comunidade e mais conteúdo de vídeo, facilitando o acesso a mais conteúdo para ajudá-lo a obter o máximo proveito [!DNL Target]. Também adicionamos um mecanismo de feedback diretamente no menu [!UICONTROL Ajuda] , facilitando o relatório de problemas ou o compartilhamento de ideias.

   * Melhoria na funcionalidade de feedback do Net Promoter Score (NPS) para que o modal da pesquisa não atrapalhe seu fluxo de trabalho.
   * Fluxo de logon aprimorado. Anteriormente, todos os [!DNL Target] clientes chegavam na página inicial do Target depois de clicar no [!DNL Target] ícone no cabeçalho. Essa página permitiu que os clientes continuassem com [!DNL Target Standard/Premium], [!DNL Search&Promote]ou [!DNL Recommendations Classic], conforme mostrado abaixo:

      ![Página de aterrissagem](/help/r-release-notes/assets/landing.png)

      Eliminamos esta página de aterrissagem para todos os nossos clientes. Agora, você sempre é direcionado diretamente para a página Lista [!UICONTROL de] atividades clicando no [!DNL Target] ícone na nova barra de navegação do cabeçalho.

      Se você usar [!DNL Recommendations Classic], poderá ir diretamente para a solução ou ir do link curto criado na guia [!UICONTROL Recomendações] , como mostrado abaixo:

      ![Link profundo Recs Classic](/help/r-release-notes/assets/recs-classic.png)

      Se você usar [!DNL Search&Promote], precisará ir diretamente para o URL [do](https://center.atomz.com/center/?ims=1) Search&amp;Promote (https://center.atomz.com/center/?ims=1). O caminho para alcançar [!DNL Search&Promote] de dentro de [!DNL Adobe Target] foi completamente removido.

   * No momento, as notificações para não [!DNL Target] estão disponíveis no menu suspenso [!UICONTROL Notificações] no cabeçalho.
   >[!NOTE]
   >
   >Esses recursos não serão implementados de uma vez, nem serão lançados para todos os clientes juntos. Estaremos lançando esses recursos ao longo das próximas semanas, a partir da versão [!DNL Target Standard/Premium] 19.10.1 (22 de outubro de 2019).
   >
   >Como parte do lançamento da nova barra de navegação, você também notará algumas alterações no URL. Todos os links marcados anteriores continuam a funcionar, mas recomendamos que você marque novos links para uma abertura mais rápida.

## at.js versões 2.2 e 1.8 (10 de outubro de 2019)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| at.js versão 2.2<br><br>andat.js versão 1.8 | Essas versões do at.js fornecem:<ul><li>Desempenho aprimorado ao usar o Serviço da Experience Cloud ID (ECID) v4.4 e o at.js 2.2 ou o at.js 1.8 em suas páginas da Web.</li><li>Anteriormente, o ECID fazia duas chamadas de bloqueio antes que o at.js pudesse buscar experiências. Isso foi reduzido a uma única chamada, o que melhora significativamente o desempenho.</li></ul> Para aproveitar essas melhorias de desempenho, atualize para at.js 2.2 ou at.js 1.8 junto com a Biblioteca ECID v4.4.<br>at.js 2.2 fornece:<ul><li>**serverState**: Uma configuração disponível em at.js v2.2+ que pode ser usada para otimizar o desempenho da página quando uma integração híbrida do Target é implementada. A integração híbrida significa que você está usando o at.js v2.2+ no lado do cliente e a API de entrega ou um SDK do Target no lado do servidor para fornecer experiências. `serverState` oferece ao at.js v2.2+ a capacidade de aplicar experiências diretamente do conteúdo obtido no lado do servidor e retornado ao cliente como parte da página que está sendo fornecida.<br>Para obter mais informações, consulte "serverState" em [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state).</li></ul> |

## Plataforma Target (9 de outubro de 2019)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| Node.js SDK versão 1.0 | O SDK do Target Node.js permite implantar o servidor do Target.<br>Esse SDK do Node.js ajuda a integrar facilmente o Target a outras soluções da Experience Cloud, como o Adobe Experience Cloud Identity Service, o Adobe Analytics e o Adobe Audience Manager.<br>O SDK do Node.js apresenta práticas recomendadas e remove complexidades ao integrar-se ao Adobe Target por meio de nossa API de entrega, para que suas equipes de engenharia possam se concentrar na lógica comercial. A seguir estão recursos notáveis que estamos introduzindo na versão mais recente:<ul><li>Suporte para busca prévia e notificações que permitem otimizar o desempenho por meio do cache.</li><li>Suporte para otimizar o desempenho quando você tem uma integração híbrida do Target em suas páginas da Web e no servidor. Estamos introduzindo uma configuração chamada `serverState` que será preenchida por experiências recuperadas pelo lado do servidor para que o at.js 2.2 não faça mais uma chamada de servidor adicional para recuperar as experiências. Essa abordagem otimiza o desempenho de carregamento da página.</li><li> Suporte para recuperar atividades criadas pelo VEC por meio do SDK Node.js, que é possibilitado pela nova API de entrega.</li><li>Criado de forma aberta para que seus desenvolvedores possam contribuir com o SDK Node.js.</li></ul><br>Para obter mais informações, consulte Notas de [versão - SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)do Target Node.js.<br>Saiba mais sobre o SDK do Target Node.js no Blog técnico da Adobe - [Abrir Seleção de Fornecedor do Novo SDK](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc)do Adobe Target Node.js. |
| API de entrega | Um terminal de API de entrega totalmente novo (/v1/delivery) está disponível na produção. Os principais recursos são:<ul><li>Um terminal para recuperar experiências para uma ou mais mboxes.</li><li>Recupere atividades criadas pelo VEC por meio da API.</li><li>Suporte para um objeto totalmente novo chamado Exibições, usado para aplicativos de página única (SPAs) e aplicativos móveis.</li></ul><br>Para obter mais informações, consulte Notas de [versão - APIs](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)do servidor do Target. |

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão - APIs do servidor do Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notas de versão relacionadas às APIs do servidor do Adobe Target. |
| [Notas de versão - SDK do Target Node.js](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notas de versão relacionadas ao SDK Node.js do Adobe Target. |
| [Notas de versão - Target Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notas de versão relacionadas ao Java SDK do Adobe Target. |
| [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre as alterações em cada versão da biblioteca JavaScript do Adobe Target at.js. |
| [Detalhes da versão da mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Esta página mostra as alterações em cada versão da mbox.js.<br>Observe que a biblioteca mbox.js não está mais sendo desenvolvida. Todos os clientes devem migrar da mbox.js para a at.js. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não ser incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](../r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte Notas [de versão da](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Lista de atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |
