---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Adobe Target Standard e do Target Premium.
title: 'Notas de versão do Target (atual) '
feature: release notes
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 31%

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium. Além disso, as notas de versão para APIs de Públicos alvos, SDKs, biblioteca JavaScript (at.js) e outras alterações de plataforma também são incluídas, quando aplicável.

>[!IMPORTANT]
>
>* **Adobe Novamente nomeado líder no Quadrante Mágico Gartner para mecanismos** de personalização: Adobe foi mais uma vez nomeado Líder no Quadrante Magic da Gartner para Mecanismos de Personalização, relatório de 2020. O Gartner Magic Quadrant for Personalization Engines avaliou os fornecedores em 15 critérios que se dividem em duas categorias: integridade da visão e capacidade de execução. [Leia sobre isso no The Adobe Blog](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/).
   >
   >
* **desaprovação** da mbox.js: Em 30 de agosto de 2020, a Adobe Target não oferecerá mais suporte à biblioteca mbox.js. Após 30 de agosto de 2020, todas as chamadas feitas do mbox.js falharão e afetarão suas páginas que possuem atividades do Público alvo em execução, atendendo ao conteúdo padrão. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Como o At.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e o [Adobe Target Skill Builder: Bate-papo no desenvolvedor, migre o mbox.js do Adobe Target para o at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
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

## at.js 2.3.2 (24 de julho de 2020)

Esta versão do at.js é uma versão de manutenção e inclui a seguinte correção:

* Correção de um bug quando um script ou código adiciona uma propriedade padrão à janela ou ao documento.

## Target Standard/Premium 20.7.1 (27 de julho de 2020)

Essa versão inclui as seguintes alterações:

### [!UICONTROL Atualização da interface da seção de administração]

Estamos gradualmente reescrevendo a interface inteira usando uma nova pilha técnica para oferta de melhor desempenho, reduzir o tempo de manutenção necessário ao lançar novos recursos e melhorar a experiência do usuário em todo o produto. [!DNL Target] A primeira seção atualizada é a seção [!UICONTROL Configuração] , que foi renomeada para [!UICONTROL Administração].

Como parte dessa atualização, você poderá executar facilmente muitas ações usando as páginas na seção [!UICONTROL Administração] , como:

* Baixe o arquivo at.js mais recente na guia [!UICONTROL Implementação] (**[!UICONTROL Administração]** > **[!UICONTROL Implementação]**).
* Personalize suas configurações do at.js e possa revisar facilmente suas alterações (**[!UICONTROL Administração]** > **[!UICONTROL Implementação]**).
* Modifique as configurações de relatórios aprimoradas, como moeda e fuso horário padrão, IPs a serem excluídos do relatórios etc. (**[!UICONTROL Administração]** > **[!UICONTROL Relatórios]**)
* Ofuscar endereços IP de visitante por motivos de privacidade (**[!UICONTROL Administração]** > **[!UICONTROL Implementação]**)
* Visualização a lista existente de usuários por espaço de trabalho e suas funções, antes de gerenciá-los no Adobe Admin Console (**[!UICONTROL Administração]** > **[!UICONTROL Usuários]**).
* Pesquise e filtre todas as tabelas na seção [!UICONTROL Administração] .

Para obter mais informações, consulte Visão geral [do Público alvo](/help/administrating-target/administrating-target.md)de administração.

### Melhorias, correções e alterações

Esta versão contém os seguintes aprimoramentos, correções e alterações:

* Correção de um problema que impedia a retenção das preferências do site após a atualização. (TGT-37239)
* Correção de um problema que impedia o funcionamento correto de [!UICONTROL Inserir após] > [!UICONTROL Imagem] com imagens SVG (Scalable Vetor Graphics). (TGT-37242)
* Correção de um problema para usuários com a função [!UICONTROL Publisher] que impedia a exclusão de atividades de rascunho. (TGT-37358)
* Correção de um problema que impedia os usuários de editar uma atividade quando [!UICONTROL Todos os Meus Espaços de Trabalho] estava selecionado. (TGT-37276)

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
