---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras do Adobe Target DNL.
title: Notas de pré-lançamento de Adobe Target
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: a55aeb18e86a4428187faa5ecba6c66d11feda6d
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 14%

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 17 de junho de 2020**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do tempo das versões. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!NOTE]
>
>* **desaprovação** da mbox.js: Em 30 de agosto de 2020, o Adobe Target não oferecerá mais suporte à biblioteca mbox.js. Após 30 de agosto de 2020, todas as chamadas feitas do mbox.js falharão e afetarão suas páginas com atividades do Target em execução. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Como o At.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e o Construtor de habilidades [Adobe Target: Bate-papo do desenvolvedor, migre o Adobe Target mbox.js para o at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
   >
   >   
   Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferta do suporte que você espera da Adobe.
   >
   >
* **Anúncios** do Público alvo: Consulte a página de anúncios do Público alvo para obter informações sobre eventos futuros, incluindo sessões do Target Skill Builder, bate-papos para desenvolvedores, webinars e sessões do Target Coffee Break. Para obter mais informações, consulte Anúncios de [Públicos alvos](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.5.1 (17 de junho de 2020)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| Analytics for Target (A4T) suporte para [!UICONTROL autoalocação] de atividades | [!UICONTROL A Autoalocação] de atividades agora é compatível com [Analytics para Público alvo](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Essa integração permite que você use a capacidade de alocação [!UICONTROL automática de bandido com vários braços para direcionar o tráfego para experiências vencedoras, ao mesmo tempo em que usa uma métrica de objetivo do] Adobe Analytics [!UICONTROL e/ou recursos de relatórios e análise] Adobe Analytics  .<br>Se você já tiver [implementado a A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) para uso com atividades de teste A/B e direcionamento de experiência, todos estarão configurados!<br>Para obter mais informações, consulte Suporte da [Analytics para Públicos alvos (A4T) para Autoalocar atividades](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) na criação *de* Atividades. |
| Tokens de resposta para o Método de alocação de tráfego para atividades de Público alvo automático e personalização automatizada | Dois tokens [de](/help/administrating-target/response-tokens.md) resposta foram adicionados às atividades [!UICONTROL Público alvo] automático e Personalização  automatizada para permitir determinar se um visitante recebeu uma experiência específica como resultado de ser atribuído ao tráfego &quot;controlado&quot; ou &quot;direcionado&quot;.<ul><li>`experience.trafficAllocationId` retornará 0 se um visitante tiver recebido uma experiência de estar no tráfego de &quot;controle&quot; e 1 se um visitante tiver recebido uma experiência da distribuição de tráfego &quot;direcionada&quot;.</li><li>`experience.trafficAllocationType` retornará &quot;controle&quot; ou &quot;direcionado&quot;.</li></ul>Para obter mais informações sobre controle vs. tráfego direcionado, consulte [Selecionar o controle para a personalização automatizada ou atividade](/help/c-activities/t-automated-personalization/experience-as-control.md)de Público alvo automático. |
| [!UICONTROL Papel do editor] | Essa nova função é semelhante à função atual do [!UICONTROL Observador] (pode visualização atividades, mas não pode criá-las ou editá-las). No entanto, a função [!UICONTROL Editor] tem permissão adicional para ativar o atividade.<br>Para obter mais informações, consulte: <ul><li>**Usuários** do Target Standard: [Especifique funções e permissões](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) em *Usuários*.</li><li>**Usuários** do Target Premium: [Etapa 6: Especifique funções e permissões](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) em *Configurar permissões* corporativas.</li></ul> |
| Suporte a A4T em 25 [!DNL Analysis Workspace]<br>de junho de 2020 | [!UICONTROL O Analytics for Target] (A4T) agora é compatível com [!DNL Analysis Workspace]. O painel [!UICONTROL Analytics for Target (A4T) permite que você analise suas] atividades e experiências no [!DNL Adobe Target] [!DNL Analysis Workspace].<br>Para obter mais informações, consulte [Relatórios na Analytics](/help/c-integrating-target-with-mac/a4t/reporting.md) no relatórios ** A4T e no painel [A4T (Público alvo A4T) no Guia](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) de ferramentas da ** Analytics. |

### Melhorias, correções e alterações

* Correção de um problema que fazia com que a métrica &quot;visitantes&quot; fosse armazenada na definição de atividade em vez de &quot;Visitantes únicos&quot;. (TGT-37098)
* Corrigido um problema na interface do usuário que fazia com que a barra de rolagem vertical não funcionasse corretamente na página do [!DNL Target] Audiência  . (TGT-36968)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
