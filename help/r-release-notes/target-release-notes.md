---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras da DNL Adobe Target.
title: Notas de pré-lançamento do Adobe Target
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 8b1f98e6c05844308e63e2c32255c32d0c126cba
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 10%

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização em: 14 outubro de 2020**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do tempo das versões. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>* **Adobe Novamente nomeado líder no Quadrante Mágico Gartner para mecanismos** de personalização: Adobe foi mais uma vez nomeado Líder no Quadrante Magic da Gartner para Mecanismos de Personalização, relatório de 2020. O Gartner Magic Quadrant for Personalization Engines avaliou os fornecedores em 15 critérios que se dividem em duas categorias: integridade da visão e capacidade de execução. [Leia sobre isso no The Adobe Blog](https://theblog.adobe.com/adobe-again-named-leader-in-gartner-magic-quadrant-for-personalization-engines/).
   >
   >
* **Fim da vida útil** do mbox.js: Em 18 de janeiro de 2021, a Adobe Target não oferecerá mais suporte à biblioteca mbox.js. Após 18 de janeiro de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem atividades Públicos alvos em execução, atendendo ao conteúdo padrão. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Como o At.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e o [Adobe Target Skill Builder: Bate-papo no desenvolvedor, migre o mbox.js do Adobe Target para o at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
   >
   >   
   Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão oferecer novas funcionalidades e oferta do suporte que você espera da Adobe.
   >
   >
* **Anúncios** do público alvo: Consulte a página de anúncios do Público alvo para obter informações sobre eventos futuros, incluindo sessões do Público alvo Skill Builder, bate-papos para desenvolvedores, webinars e sessões do Público alvo Coffee Break. Para obter mais informações, consulte Anúncios de [Públicos alvos](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.10.1 (27 de outubro de 2020)

Esta versão contém os seguintes novos recursos:

| Recurso | Detalhes |
| --- | --- |
| Decisões no dispositivo | As decisões no dispositivo permitem que tanto os profissionais de marketing quanto os desenvolvedores de produtos forneçam experimentação e personalização orientada pelo Machine Learning a partir de um dispositivo do usuário, em canais, a uma latência quase zero.<br>Questões de velocidade e desempenho — em insights do cliente e satisfação do usuário. As decisões no dispositivo permitem que os profissionais de marketing, e agora desenvolvedores de produtos, testem e otimizem experiências diretamente de um dispositivo de usuário, diminuindo os tempos de decisão e carga para quase zero para experiências contextuais em tempo real.<br>As decisões no dispositivo permitem compilar todas as instruções de personalização e experimentação em &quot;artefatos de otimização&quot;, que são carregados em dispositivos do cliente. Esses artefatos de latência zero proporcionam aos comerciantes personalização individual, redefinição de metas comportamentais e recomendações de conteúdo e produtos em tempo real, ao mesmo tempo em que proporcionam aos desenvolvedores e proprietários de produtos acesso direto ao código para testar experiências do usuário e lançamentos de produtos em público alvo e fase, aprimorando em tempo real. E como as decisões no dispositivo se conectam nativamente com [!DNL Adobe Experience Cloud] produtos, [!DNL Target] os usuários obtêm uma análise rápida e iterações de experiência mais rápidas.<br>**Registre-se agora para um webinar ao vivo.** Junte-se aos especialistas em produtos da Adobe Target quando eles discutirem como mover as decisões de otimização de experiência crítica no dispositivo para execução local com latência zero pode abrir portas para novos casos de uso interessantes e, ao mesmo tempo, melhorar o desempenho do site para seus clientes.<ul><li>10 de novembro de 2020</li><li>10 h PT / 12 h CT / 13 h ET</li><li>[Registre-se aqui](https://www.adobeeventsonline.com/Target/2020/OnDeviceDecisions/invite.html)</li></ul> |

Esta versão contém os seguintes aprimoramentos, correções e alterações:

* Correção de um problema que impedia a exibição do Intervalo [!UICONTROL de confiança de incentivo] médio e da [!UICONTROL confiança] no [!DNL Auto-Target] relatórios da linha [!UICONTROL Total] . Medições exibidas corretamente para todas as experiências individuais. (TGT-37301)
* Correção de um problema que afetava o relatórios de Público alvo [!DNL Adobe Target Premium] automático [!UICONTROL de] usuários a partir de 15 de setembro, 14:30. (PDT) para 6 de outubro, 9:25 (TFD). Ao exibir relatórios para as métricas de conversão afetadas (configuradas usando a opção &quot;[!UICONTROL Visualizou uma página]&quot; ou &quot;[!UICONTROL Clicou em mbox]&quot;), as taxas de conversão são reportadas incorretamente. Não há nenhum problema de delivery conhecido no momento. Para obter informações sobre como ressincronizar e corrigir seu relatórios, consulte relatórios [de Público alvo](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) automático em *Solução de problemas* em problemas *conhecidos e problemas* resolvidos.
* Adicionada uma coluna [!UICONTROL Última atualização em] na tabela Pesquisa [!UICONTROL de] catálogo e um filtro [!UICONTROL Última atualização em] . Esse aprimoramento economiza tempo e esforço, pois você não precisa abrir cada item individual para ver quando ele foi atualizado pela última vez e pode filtrar por data em que os itens foram atualizados pela última vez.

   ![Última atualização na ilustração da coluna e do filtro](/help/r-release-notes/assets/column-and-filter.png)

* Navegação e funcionalidade aprimoradas para usuários somente de teclado.
* Adicionadas etiquetas na interface do usuário para ajudar os usuários a usar tecnologias de assistência.
* Texto e contraste de cor aprimorados para imagens e texto na interface do usuário.

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
