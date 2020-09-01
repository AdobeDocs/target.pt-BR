---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras da DNL Adobe Target.
title: Notas de pré-lançamento do Adobe Target
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 4efaf7ce039aabb26fc130e541fb6057115a3c7e
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 11%

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 31 de agosto de 2020**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do tempo das versões. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>* **Adobe Novamente nomeado líder no Quadrante Mágico Gartner para mecanismos** de personalização: Adobe foi mais uma vez nomeado Líder no Quadrante Magic da Gartner para Mecanismos de Personalização, relatório de 2020. O Gartner Magic Quadrant for Personalization Engines avaliou os fornecedores em 15 critérios que se dividem em duas categorias: integridade da visão e capacidade de execução. [Leia sobre isso no The Adobe Blog](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/).
   >
   >
* **desaprovação** da mbox.js: Em 18 de janeiro de 2021, a Adobe Target não oferecerá mais suporte à biblioteca mbox.js. Após 18 de janeiro de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem atividades Públicos alvos em execução, atendendo ao conteúdo padrão. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Como o At.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e o [Adobe Target Skill Builder: Bate-papo no desenvolvedor, migre o mbox.js do Adobe Target para o at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
   >
   >   
   Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão oferecer novas funcionalidades e oferta do suporte que você espera da Adobe.
   >
   >
* **Anúncios** do público alvo: Consulte a página de anúncios do Público alvo para obter informações sobre eventos futuros, incluindo sessões do Público alvo Skill Builder, bate-papos para desenvolvedores, webinars e sessões do Público alvo Coffee Break. Para obter mais informações, consulte Anúncios de [Públicos alvos](/help/r-release-notes/target-announcements.md).


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

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
