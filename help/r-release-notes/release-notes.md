---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Adobe Target Standard e do Target Premium.
title: 'Notas de versão do Target (atual) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 51abcafed1641d073b38800d0fea756df92b3685

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium. Além disso, as notas de versão para APIs do Target, SDKs, biblioteca JavaScript (at.js) e outras alterações da plataforma também são incluídas, quando aplicável.

>[!NOTE]
>
>* **Alterações** de suporte a TLS: A partir de 1º de março de 2020, o Target desativará o suporte para criptografia TLS 1.1 e TLS 1.0. A Segurança da camada de transporte (TLS) é o protocolo de segurança mais amplamente implantado usado atualmente em navegadores Web e outros aplicativos que exigem dados trocados de maneira segura por meio de uma rede. Essa alteração é necessária para atender ao padrão de conformidade de segurança geralmente aceito do TLS 1.2 ou superior. Verifique qual versão do TLS você está usando no momento. Se sua versão for inferior a 1.2, implemente as alterações necessárias antes de 1º de março de 2020 para continuar a usar o Target conforme esperado.
   >
   >   
   Para obter informações detalhadas sobre o possível impacto e as etapas que podem ser necessárias para atualizar sua implementação, consulte Alterações [de criptografia de](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)TLS (Transport Layer Security).
   >
   >
* **desaprovação** da mbox.js: Em 30 de agosto de 2020, o Adobe Target não oferecerá mais suporte à biblioteca mbox.js. Após 30 de agosto de 2020, todas as chamadas feitas do mbox.js falharão e afetarão suas páginas que têm atividades do Target em execução. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
   >
   >   
   Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferecer o suporte que você espera da Adobe.
   >
   >
* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].


## Summit Live: A Conferência sobre Experiência Digital {#summit}

O Adobe Summit se tornou um evento virtual! A Adobe está removendo todas as paradas com uma experiência digital ao vivo a partir de 31 de março de 2020. Essa experiência ao vivo incluirá nosso endereço Keynote de estágio principal, minikeynotes com as últimas tendências e avanços, insights sobre o sucesso dos líderes do setor e sessões de grupo.

* **Assista ao teclado ao vivo**: Saiba mais sobre tendências e novos produtos que estão transformando as indústrias do conforto de seu lugar.
* **Explore mais de 100 sessões de grupo por demanda:** Obtenha acesso gratuito a mais de cem sessões de grupo por demanda da Adobe, clientes e parceiros.
* **Atacar um pico no futuro**: Junte-se à convidada especial Chelsea Handler para ver a mais recente tecnologia experimental dos nossos laboratórios. no Adobe Sneaks.

Para se registrar para obter acesso gratuito a todo o evento digital, acesse [a Conferência da Experiência Digital: Cúpula](https://www.adobe.com/summit.html) .

## Target Standard/Premium 20.2.1 (17 de março de 2020) 

>[!IMPORTANT]
>
>Consulte as informações acima sobre a desaprovação do mbox.js.

Esta versão contém os seguintes aprimoramentos, correções e alterações:

* Correção de um problema que impedia os clientes de selecionar uma coleção ao executar uma pesquisa de catálogo. (TGT-36230)
* Correção de um problema em que um critério criado por meio da API, mas não referenciado por uma atividade criada na interface do usuário do Target, podia ser excluído erroneamente da interface do usuário. (TGT-35917)
* Aprimoramentos de segurança implementados na Política de segurança de conteúdo (CSP). (TGT-36190)
* Correção de um problema que fazia com que &quot;NaN%&quot; fosse exibido ao deslizar a barra de porcentagem de Ponderação do atributo para a extremidade esquerda. (TGT-36211)
* Solução de problemas de localização para que o texto da interface em vários idiomas seja exibido corretamente.
* As seguintes métricas do Adobe Analytics não são mais suportadas pelo Analytics para Target (A4T) em vigor na versão de março de 2020 do Target:
   * averagvisitdepth
   * bots
* As métricas a seguir não são mais suportadas e são convertidas automaticamente em novas versões da métrica na primeira vez que um usuário modifica uma atividade que contém a métrica:

   | Métrica obsoleta | Nova métrica |
   |--- |--- |
   | `averagetimespentonpage` | `averagetimespentonsite` (nota: medido em minutos em vez de segundos) |
   | `instances` | `occurrences` |
   | `singleaccess` | `singlepagevisits` |
   | `uniquevisitors` | `visitors` |
   | `visitorsdaily`, `visitorshourly`, `visitorsmonthly`, `visitorsquarterly`, `visitorsweekly`, `visitorsyearly` | `visitors` |

## Navegação na Adobe Experience Cloud (22 de fevereiro de 2019)

* Ao efetuar logon no [!DNL Adobe Experience Cloud], você será direcionado para a nova navegação do cabeçalho. É muito semelhante à navegação anterior com a barra preta na parte superior, mas oferece as seguintes melhorias:

   * Comutação mais fácil entre organizações [!DNL Identity Management System] (IMS) ou para uma solução diferente.
   * Ajuda do usuário aprimorada: Os resultados da pesquisa incluem os resultados da documentação do [!DNL Target] produto, bem como fóruns da comunidade e mais conteúdo de vídeo, facilitando o acesso a mais conteúdo para ajudá-lo a obter o máximo proveito [!DNL Target]. Também adicionamos um mecanismo de feedback diretamente no menu [!UICONTROL Ajuda] , facilitando o relatório de problemas ou o compartilhamento de ideias.

   * Melhoria na funcionalidade de feedback do Net Promoter Score (NPS) para que o modal da pesquisa não atrapalhe seu fluxo de trabalho.
   * Fluxo de logon aprimorado. Anteriormente, todos os [!DNL Target] clientes chegavam na página inicial do Target depois de clicar no [!DNL Target] ícone no cabeçalho. Essa página permitiu que os clientes continuassem com [!DNL Target Standard/Premium], [!DNL Search&Promote]ou [!DNL Recommendations Classic], como mostrado abaixo:

      ![Página de aterrissagem](/help/r-release-notes/assets/landing.png)

      Eliminamos esta página de aterrissagem para todos os nossos clientes. Agora, você sempre é direcionado diretamente para a página Lista [!UICONTROL de] atividades clicando no [!DNL Target] ícone na nova barra de navegação do cabeçalho.

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
| [Notas de versão - APIs do lado do servidor do Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notas de versão relacionadas às APIs do servidor do Adobe Target. |
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
