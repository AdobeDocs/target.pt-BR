---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras da DNL Adobe Target.
title: Notas de pré-lançamento do Adobe Target
feature: null
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: b6d3a241362592d5034f9db6141b459db7c6739b
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 10%

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização em: 23 outubro de 2020**

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
| Decisão no dispositivo | A decisão no dispositivo permite que tanto os profissionais de marketing quanto os desenvolvedores de produtos forneçam experimentação e personalização orientada pelo Machine Learning a partir de um dispositivo do usuário, em canais, a uma latência quase zero.<br>Questões de velocidade e desempenho — em insights do cliente e satisfação do usuário.<br>A decisão no dispositivo permite compilar instruções importantes de personalização e experimentação em tipos de atividade de teste A/B e direcionamento de experiência (XT) em &quot;artefatos de otimização&quot;: objetos JSON carregados em dispositivos do cliente por meio do CDN. E como a decisão no dispositivo se conecta nativamente com [!DNL Adobe Experience Cloud] produtos, [!DNL Target] os usuários obtêm uma análise rápida e iterações de experiência mais rápidas.<br>**Registre-se agora para um webinar ao vivo.** Junte-se aos especialistas em produtos da Adobe Target quando eles discutirem como mover as decisões de otimização de experiência crítica no dispositivo para execução local com latência zero pode abrir portas para novos casos de uso interessantes e, ao mesmo tempo, melhorar o desempenho do site para seus clientes.<ul><li>10 de novembro de 2020</li><li>10 h PT / 12 h CT / 13 h ET</li><li>[Registre-se aqui](https://www.adobeeventsonline.com/Target/2020/OnDeviceDecisions/invite.html)</li></ul> |

Esta versão contém os seguintes aprimoramentos, correções e alterações:

* Correção de um problema que impedia a exibição do Intervalo [!UICONTROL de confiança de incentivo] médio e da [!UICONTROL confiança] no [!DNL Auto-Target] relatórios da linha [!UICONTROL Total] . Medições exibidas corretamente para todas as experiências individuais. (TGT-37301)
* Correção de um problema que afetava o relatórios de Público alvo [!DNL Adobe Target Premium] automático [!UICONTROL de] usuários a partir de 15 de setembro, 14:30. (PDT) para 6 de outubro, 9:25 (TFD). Ao exibir relatórios para as métricas de conversão afetadas (configuradas usando a opção &quot;[!UICONTROL Visualizou uma página]&quot; ou &quot;[!UICONTROL Clicou em mbox]&quot;), as taxas de conversão são reportadas incorretamente. Não há nenhum problema de delivery conhecido no momento. Para obter informações sobre como ressincronizar e corrigir seu relatórios, consulte relatórios [de Público alvo](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) automático em *Solução de problemas* em problemas *conhecidos e problemas* resolvidos.
* Adicionada uma coluna [!UICONTROL Última atualização em] na tabela Pesquisa [!UICONTROL de] catálogo e um filtro [!UICONTROL Última atualização em] . Esse aprimoramento economiza tempo e esforço, pois você não precisa abrir cada item individual para ver quando ele foi atualizado pela última vez e pode filtrar por data em que os itens foram atualizados pela última vez.

   ![Última atualização na ilustração da coluna e do filtro](/help/r-release-notes/assets/column-and-filter.png)

* Foram feitas atualizações para ajudar a tornar a interface do Público alvo compatível com as Diretrizes [de acessibilidade do conteúdo da](https://www.w3.org/WAI/standards-guidelines/wcag/) Web 2.0 Nível A e Critérios de sucesso AA (WCAG 2.0 AA). (TGT-34384 e TGT-24679)
* Foram feitos aprimoramentos na Política de segurança de conteúdo (CSP). (TGT-37035)
* Introduziu uma forma de especificar o código do cliente como parâmetro para clientes que usam CNAME. (TNT-38571)
* [!DNL Adobe Experience Cloud] a documentação está sendo transferida para [!DNL Experience League]. Durante o mês de outubro, todas as notas de versão, artigos, vídeos e tutoriais serão movidos do local atual para `docs.adobe.com` o [!DNL Experience League]. Essa mudança garante que todo o aprendizado, a autoajuda, a ativação e o conteúdo da comunidade sejam fornecidos de um único local. Quando essa alteração ocorrer, não há nada que você precise fazer, pois todos os links serão redirecionados para [!DNL Experience League]. Atualizaremos as notas de versão quando o cutover começar.

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
