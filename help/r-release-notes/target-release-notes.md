---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras da DNL Adobe Target.
title: Notas de pré-lançamento do Adobe Target
feature: null
translation-type: tm+mt
source-git-commit: 531e147d99bbc73414f790d66a3633bd1de8f50f
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 11%

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 6 de janeiro de 2021**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do tempo das versões. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>**Fim da vida útil** do mbox.js: Em 31 de março de 2021, não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem [!DNL Target] atividades sendo executadas com o conteúdo padrão. Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca JavaScript at.js antes dessa data para evitar possíveis problemas com seus sites.
>
>* **Adobe Experience Platform Web SDK**: O  [!UICONTROL Adobe Experience Platform Web ] SDK permite que você interaja com os vários serviços no  [!DNL Experience Cloud] (incluindo  [!DNL Target]) por meio da Adobe Experience Edge Network. Se você optar por migrar para [!DNL Adobe Experience Platform Web SDK], consulte [O que é Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html), no *Guia do SDK da Web*. Consulte [Visão geral do Público alvo](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html) para obter [!DNL Target] informações específicas.
   >
   >
* **at.js**: A biblioteca JavaScript do at.js oferece muitas vantagens em relação ao mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única. Se você optar por migrar para at.js, consulte [Como o At.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e [Adobe Target Skill Builder: Bate-papo no desenvolvedor, migre o mbox.js do Adobe Target para o at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Embora a mbox.js seja atualmente suportada (até 31 de março de 2021), não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. Ao mover todos os clientes para o [!UICONTROL Adobe Experience Platform Web SDK] ou o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferta o suporte que você espera do Adobe.

## Target Standard/Premium 20.10.1 (27 de outubro de 2020)

Esta versão contém os seguintes novos recursos:

| Recurso | Detalhes |
| --- | --- |
| [Decisão no dispositivo](https://adobetarget-sdks.gitbook.io/docs/on-device-decisioning/introduction-to-on-device-decisioning) | A decisão no dispositivo permite que tanto os profissionais de marketing quanto os desenvolvedores de produtos forneçam experimentação e personalização orientada pelo Machine Learning a partir de um dispositivo do usuário, em canais, a uma latência quase zero.<br>Questões de velocidade e desempenho — em insights do cliente e satisfação do usuário.<br>A decisão no dispositivo permite compilar instruções importantes de personalização e experimentação em tipos de atividade de teste A/B e direcionamento de experiência (XT) em &quot;artefatos de otimização&quot;: objetos JSON carregados em dispositivos do cliente por meio do CDN. E como a decisão no dispositivo se conecta nativamente com [!DNL Adobe Experience Cloud] produtos, os usuários [!DNL Target] obtêm análise rápida e iterações de experiência mais rápidas.<br>Para obter mais informações, consulte *Decisão [no dispositivo](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md). |

Esta versão contém os seguintes aprimoramentos, correções e alterações:

* Correção de um problema que impedia que [!UICONTROL Intervalo médio de confiança de incentivo] e [!UICONTROL Confiança] fossem exibidos no relatórios [!DNL Auto-Target] para a linha [!UICONTROL Total]. Medições exibidas corretamente para todas as experiências individuais. (TGT-37301)
* Correção de um problema que afetava o relatórios [!DNL Adobe Target Premium] [!UICONTROL Público alvo automático] dos usuários a partir de 15 de setembro, 14:30. (PDT) para 6 de outubro, 9:25 (TFD). Ao exibir relatórios para as métricas de conversão afetadas (configuradas usando a opção &quot;[!UICONTROL Exibida uma página]&quot; ou &quot;[!UICONTROL Clicadas em mbox]&quot;), as taxas de conversão são reportadas incorretamente. Não há nenhum problema de delivery conhecido no momento. Para obter informações sobre como ressincronizar e corrigir seu relatórios, consulte [relatórios de Público alvo automático](/help/r-release-notes/known-issues-resolved-issues.md#at-metrics) em *Problemas resolvidos* em *Problemas conhecidos e problemas resolvidos*.
* Adicionada uma coluna [!UICONTROL Última atualização em] selecionável na tabela [!UICONTROL Pesquisa de catálogo] e um filtro [!UICONTROL Última atualização em]. Esse aprimoramento economiza tempo e esforço, pois você não precisa abrir cada item individual para ver quando ele foi atualizado pela última vez e pode filtrar por data em que os itens foram atualizados pela última vez.

   ![Última atualização na ilustração da coluna e do filtro](/help/r-release-notes/assets/column-and-filter.png)

* Foram feitas atualizações para ajudar a tornar a interface do Público alvo compatível com [Diretrizes de acessibilidade de conteúdo da Web](https://www.w3.org/WAI/standards-guidelines/wcag/) 2.0 Nível A e Critérios de sucesso AA (WCAG 2.0 AA). (TGT-34384 e TGT-24679)
* Foram feitos aprimoramentos na Política de segurança de conteúdo (CSP). (TGT-37035)
* Introduziu uma forma de especificar o código do cliente como parâmetro para clientes que usam CNAME. (TNT-38571)
* [!DNL Adobe Experience Cloud] a documentação está sendo transferida para  [!DNL Experience League]. Durante o mês de outubro, todas as notas de versão, artigos, vídeos e tutoriais serão movidos de seu local atual em `docs.adobe.com` para [!DNL Experience League]. Essa mudança garante que todo o aprendizado, a autoajuda, a ativação e o conteúdo da comunidade sejam fornecidos de um único local. Quando essa alteração ocorrer, não há nada que você precise fazer, pois todos os links serão redirecionados para [!DNL Experience League]. Atualizaremos as notas de versão quando o cutover começar.

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
