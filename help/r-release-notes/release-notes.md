---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Adobe Target Standard e do Target Premium.
title: 'Notas de versão do Target (atual) '
feature: release notes
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 1397891d4451d9e66a25e018e6bd7078e70cfd3f
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 24%

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium. Além disso, as notas de versão para APIs de Públicos alvos, SDKs, biblioteca JavaScript (at.js) e outras alterações de plataforma também são incluídas, quando aplicável.

>[!IMPORTANT]
>
>* **Adobe Novamente nomeado líder no Quadrante Mágico Gartner para mecanismos** de personalização: Adobe foi mais uma vez nomeado Líder no Quadrante Magic da Gartner para Mecanismos de Personalização, relatório de 2020. O Gartner Magic Quadrant for Personalization Engines avaliou os fornecedores em 15 critérios que se dividem em duas categorias: integridade da visão e capacidade de execução. [Leia sobre isso no The Adobe Blog](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/).
   >
   >
* **Remoção** do mbox.js: Em 18 de janeiro de 2021, a Adobe Target não oferecerá mais suporte à biblioteca mbox.js. Após 18 de janeiro de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem atividades Públicos alvos em execução, atendendo ao conteúdo padrão. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Como o At.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e o [Adobe Target Skill Builder: Bate-papo no desenvolvedor, migre o mbox.js do Adobe Target para o at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
   >
   >   
   Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão oferecer novas funcionalidades e oferta do suporte que você espera da Adobe.
   >
   >
* **Anúncios** do público alvo: Consulte a página de anúncios do Público alvo para obter informações sobre eventos futuros, incluindo sessões do Público alvo Skill Builder, bate-papos para desenvolvedores, webinars e sessões do Público alvo Coffee Break. Para obter mais informações, consulte Anúncios de [Públicos alvos](/help/r-release-notes/target-announcements.md).


Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Target Standard/Premium 20.9.1 (30 de setembro de 2020)

Esta versão de manutenção contém os seguintes aprimoramentos, correções e alterações:

* Navegação e funcionalidade aprimoradas para usuários somente de teclado. (TGT-34487, TGT-34516, TGT-34517, TGT-34514)
* Adicionadas etiquetas na interface do usuário para ajudar os usuários a usar tecnologias de assistência. (TGT-34500, TGT-34501, TGT-34502, TGT-24504)
* Texto e contraste de cor aprimorados para imagens e texto na interface do usuário. (TGT-34513)

## Target Standard/Premium 20.8.3 (15 de setembro de 2020)

| Recurso | Detalhes |
| --- | --- |
| ![Suporte Premium badge](/help/assets/premium.png) do Analytics para Públicos alvos (A4T) para atividades de Público alvo automático | [!UICONTROL As atividades de Público alvo] automático agora são compatíveis com o [Analytics para Públicos alvos](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Essa integração permite que você use o algoritmo de aprendizado de máquina do conjunto [!UICONTROL Automático] para escolher a melhor experiência para cada visitante com base no perfil, comportamento e contexto.<br>Se você já tiver [implementado a A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) para uso com atividades de teste A/B e direcionamento de experiência, todos estarão configurados!<br>Para obter mais informações, consulte Suporte [do Analytics para Públicos alvos (A4T) para Autoalocação e atividades](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) de Público alvo automático na criação *de* Atividades. |

## Target Standard/Premium 20.8.2 (10 de setembro de 2020)

| Recurso | Detalhes |
| --- | --- |
| ![Slots de recomendações de controle de emblema](/help/assets/premium.png) Premium em sequências de critérios | As Sequências de critérios agora permitem controlar o número de slots absorvidos por cada critério de recomendação, permitindo que você combine e corresponda tipos diferentes de itens ou diferentes lógicas de algoritmo.<br>Consulte [Criar sequências](/help/c-recommendations/c-algorithms/create-criteria-sequence.md#sequence) de critérios para saber mais. |

## Target Standard/Premium 20.8.1 (2 de setembro de 2020)

Esta versão contém os seguintes aprimoramentos, correções e alterações:

* Correção de um problema que causava a exibição de erros ao carregar as novas páginas [!UICONTROL de Administração] após a alternância de organizações. (TGT-37730)
* Corrigido um problema de exibição que fazia com que o código do cliente incorreto fosse exibido na página [!UICONTROL Administração > Implementação] . (TGT-37849)
* Correção de um problema que às vezes impedia os usuários de usar os recursos de edição no [!UICONTROL Visual Experience Composer] (VEC) após carregar o VEC com êxito. (TGT-37162)
* Correção de um problema que impedia o carregamento de páginas no VEC e no Enhanced Experience Composer (EEC) mesmo se a extensão do VEC Helper estivesse instalada. Isso se deve a mudanças no Google Chrome 80+. Baixe a extensão [do VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)atualizada. (TGT-37893)
* Correção de um problema que às vezes impedia os usuários de baixar o at.js na página [!UICONTROL Administração > Implementação] após alternar entre as organizações. (TGT-37668)
* O botão de download do at.js agora está desativado durante o carregamento para impedir o envio [!DNL Target] de várias solicitações se os usuários clicarem no botão de download várias vezes. (TGT-37633)
* Correção de um problema nas atividades [!UICONTROL Experience Targeting] (XT) que fazia com que as experiências exibissem &quot;resultados de busca&quot; por um longo período de tempo. (TGT-37684)
* Navegação e funcionalidade aprimoradas para usuários somente de teclado. (TGT-34479 e TGT-34473)
* Adicionadas etiquetas na interface do usuário para ajudar os usuários a usar tecnologias de assistência. (TGT-34480)
* Mensagem de erro aprimorada ao excluir um visor móvel que está sendo usado em uma atividade. A mensagem de erro agora diz: &quot;Atualmente, esse visor está associado a uma ou várias atividades. Você precisa remover o visor dessas atividades antes de poder excluí-lo.&quot; (TGT-37030)
* Adição de suporte no VEC para permitir o rastreamento de cliques em um seletor css que corresponde a mais de um elemento na página. (TGT-37323)
* Correção de um problema que impedia certos usuários de exibirem a lista da [!UICONTROL Atividade] . A seguinte mensagem de erro foi exibida: &quot;Não é possível buscar URLsugestões.&quot; O erro ocorria para os usuários que usavam retornos de carro em FirstName (FirstName/r/n) no sistema de backend de Adobe. (TGT-37330)
* Correção de um problema que impedia que os usuários exibissem a página de [!UICONTROL Atividade] se o nome do espaço de trabalho (especificado no [!UICONTROL Adobe Admin Console for Enterprise]) contivesse um apóstrofo. (TGT-37709)
* Correção de um problema em [!UICONTROL Autoalocar] atividades ao selecionar métricas de otimização e conversão em que uma mensagem de erro informava incorretamente os usuários a selecionar um conjunto de relatórios, mesmo que um conjunto de relatórios já tivesse sido especificado. (TGT-37689)
* Correção de um problema que às vezes fazia com que as métricas na página [!UICONTROL Metas e Configurações] ficassem em branco depois de navegar para a página [!UICONTROL Definição de metas] e, em seguida, voltar. (TGT-37691)
* Correção de um problema que causava um valor modificado por último incorreto para [!DNL Recommendations] critérios. (TGT-37666)
* Correção de um problema que fazia com que IDs de mbox fossem exibidas na lista suspensa Mboxes em vez de nomes de mbox. (TGT-37739)

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão - APIs do lado do servidor do Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notas de versão relacionadas às APIs do lado do servidor da Adobe Target. |
| [Notas de versão - SDK Node.js do Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notas de versão relacionadas ao Adobe Target Node.js SDK. |
| [Notas de versão - SDK Java do Público alvo](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notas de versão relacionadas ao Adobe Target Java SDK. |
| [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre as alterações em cada versão da biblioteca JavaScript do Adobe Target at.js. |
| [Detalhes da versão da mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Esta página mostra as alterações em cada versão da mbox.js.<br>Observe que a biblioteca mbox.js não está mais sendo desenvolvida. Todos os clientes devem migrar da mbox.js para a at.js. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não ser incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](../r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte Notas [de versão do](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Lista de atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |
