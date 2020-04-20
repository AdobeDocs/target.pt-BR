---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Adobe Target Standard e do Target Premium.
title: 'Notas de versão do Target (atual) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 1befd131034805ba81e4d68e7e976fd290041d52

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium. Além disso, as notas de versão para APIs de Públicos alvos, SDKs, biblioteca JavaScript (at.js) e outras alterações de plataforma também são incluídas, quando aplicável.

>[!NOTE]
>
>* **desaprovação** da mbox.js: Em 30 de agosto de 2020, o Público alvo da Adobe não oferecerá mais suporte à biblioteca mbox.js. Após 30 de agosto de 2020, todas as chamadas feitas do mbox.js falharão e afetarão suas páginas com atividades do Público alvo em execução. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). Consulte Construtor de habilidades *do Público alvo da Adobe: Bate-papo no desenvolvedor, migre o mbox.js do Público alvo da Adobe para o at.js* abaixo para obter informações sobre como se registrar em um próximo bate-papo no desenvolvedor sobre esse assunto.
   >
   >   
   Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
   >
   >   
   Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferta do suporte que você espera da Adobe.


Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Construtor de habilidades do Público alvo da Adobe: Bate-papo no desenvolvedor, migre o mbox.js do Público alvo da Adobe para o at.js {#skill-builder}

Junte-se a David Son, gerente de produtos de Públicos alvos da Adobe, já que ele apresenta os benefícios da migração do mbox.js para o at.js. Saiba mais sobre as últimas atualizações do at.js, saiba mais sobre seus recursos avançados e como eles se alinham com as maiores tendências no cenário tecnológico, bem como algumas dicas práticas para garantir que você extraia o valor do Público alvo ao migrar do mbox.js para o at.js. Os desenvolvedores de Públicos alvos da Adobe não vão querer perder isso!

Terça-feira, 5 de maio, 8:00 - 9:00 (PDT)

[Inscreva-se agora!](https://atskillbuilder-devchat.experienceleague.adobeevents.com/)

## Público alvo at.js (25 de março de 2020)

As novas versões do Público alvo at.js das bibliotecas JavaScript estão disponíveis:

* at.js versão 2.3.0
* at.js versão 1.8.1

For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## Target Standard/Premium 20.2.1 (23 de março de 2020) 

>[!IMPORTANT]
>
>Consulte as informações acima sobre a desaprovação do mbox.js.

Esta versão contém os seguintes aprimoramentos, correções e alterações:

* Correção de um problema que impedia os clientes de selecionar uma coleção ao executar uma pesquisa de catálogo. (TGT-36230)
* Correção de um problema em que um critério criado por meio de uma API, mas não referenciado por uma atividade criada na interface do usuário do Público alvo, podia ser excluído erroneamente da interface do usuário. (TGT-35917)
* Aprimoramentos de segurança implementados na Política de segurança de conteúdo (CSP). (TGT-36190)
* Correção de um problema que fazia com que &quot;NaN%&quot; fosse exibido ao deslizar a barra de porcentagem de Ponderação do atributo para a extremidade esquerda. (TGT-36211)
* Correção de problemas de localização para que o texto da interface do usuário em vários idiomas seja exibido corretamente.
* Nós padronizamos a lista de métricas disponíveis do Adobe Analytics para atividades do Público alvo (A4T), substituindo as métricas do Adobe Analytics não suportadas na versão atual das APIs do Adobe Analytics. Isso nos permitirá estender nosso suporte A4T em versões futuras do Público alvo da Adobe.

   Foram feitas as seguintes alterações:

   * &quot;Tempo médio gasto na página&quot; foi substituído por &quot;Tempo médio gasto no site&quot;. Qualquer atividade que usa essa métrica como métrica a Métrica de meta principal terá &quot;Tempo médio gasto no site&quot; (observação: medida em minutos em vez de segundos) selecionada como a Métrica de objetivo principal na próxima vez que a atividade for editada.
   * &quot;Visitantes&quot; foi substituído por &quot;Visitantes únicos&quot;. Todas as atividades que usarem essa métrica como a Métrica de meta principal terão &quot;Visitantes únicos&quot; selecionados como a Métrica de meta principal na próxima vez que a atividade for editada.

* As métricas a seguir foram substituídas e não podem mais ser selecionadas como a Métrica de meta principal ao criar uma nova atividade A4T.

   | Métricas obsoletas | Métricas de substituição sugeridas |
   |--- |--- |
   | Visitantes diários, Visitantes por hora, Visitantes mensais, Visitantes trimestrais, Visitantes semanais, Visitantes anuais | Visitantes únicos |
   | Profundidade média da visita | n/d. Não sugerido como uma métrica de objetivo principal |
   | Bots | n/d. Não sugerido como uma métrica de objetivo principal |
   | Taxa De Falha Móvel, Duração Média Da Sessão Anterior Móvel, Classificação Média Da Loja De Aplicativos Móveis, Taxa De Falha De Desempenho Do Aplicativo Móvel, Classificação Média Da Loja De Aplicativos Móveis | n/d. Não sugerido como uma métrica de objetivo principal |

## Navegação na Adobe Experience Cloud (22 de fevereiro de 2019)

* Ao efetuar logon no [!DNL Adobe Experience Cloud], você será direcionado para a nova navegação do cabeçalho. É muito semelhante à navegação anterior com a barra preta na parte superior, mas oferece as seguintes melhorias:

   * Comutação mais fácil entre organizações [!DNL Identity Management System] (IMS) ou para uma solução diferente.
   * Ajuda do usuário aprimorada: Os resultados da pesquisa incluem os resultados da documentação do [!DNL Target] produto, bem como fóruns da comunidade e mais conteúdo de vídeo, facilitando o acesso a mais conteúdo para ajudá-lo a obter o máximo proveito [!DNL Target]. Também adicionamos um mecanismo de feedback diretamente no menu [!UICONTROL Ajuda] , facilitando o relatório de problemas ou o compartilhamento de ideias.

   * Funcionalidade de feedback NPS (Net Promoter Score) aprimorada, de modo que o modal da pesquisa não atrapalha seu fluxo de trabalho.
   * Fluxo de logon aprimorado. Anteriormente, todos os [!DNL Target] clientes chegavam na landing page do Público alvo depois de clicar no [!DNL Target] ícone no cabeçalho. Essa página permitiu que os clientes continuassem com [!DNL Target Standard/Premium], [!DNL Search&Promote]ou [!DNL Recommendations Classic], conforme mostrado abaixo:

      ![Página de aterrissagem](/help/r-release-notes/assets/landing.png)

      Eliminamos esta landing page para todos os nossos clientes. Agora, você sempre é direcionado diretamente para a página de Lista [!UICONTROL do] Atividade clicando no [!DNL Target] ícone na nova barra de navegação do cabeçalho.

      Se você usar [!DNL Recommendations Classic], poderá ir diretamente para a solução ou ir do link curto criado na guia [!UICONTROL Recomendações] , como mostrado abaixo:

      ![Link profundo Recs Classic](/help/r-release-notes/assets/recs-classic.png)

      Se você usar [!DNL Search&Promote], precisará ir diretamente para o URL [do](https://center.atomz.com/center/?ims=1) Search&amp;Promote (https://center.atomz.com/center/?ims=1). O caminho para alcançar [!DNL Search&Promote] de dentro de [!DNL Adobe Target] foi completamente removido.

   * No momento, as notificações para não [!DNL Target] estão disponíveis no menu suspenso [!UICONTROL Notificações] no cabeçalho.
   >[!NOTE]
   >
   >Como parte do lançamento da nova barra de navegação, você também notará algumas alterações no URL. Todos os links marcados anteriores continuam a funcionar, mas recomendamos que você marque novos links para uma abertura mais rápida.

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão - APIs do lado do servidor do Público alvo](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notas de versão relacionadas às APIs do lado do servidor do Público alvo da Adobe. |
| [Notas de versão - SDK do Node.js do Público alvo](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notas de versão relacionadas ao SDK do Nó.js do Público alvo da Adobe. |
| [Notas de versão - SDK Java do Público alvo](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notas de versão relacionadas ao SDK Java do Público alvo da Adobe. |
| [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre as alterações em cada versão do Público alvo da Adobe na biblioteca JavaScript at.js. |
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
