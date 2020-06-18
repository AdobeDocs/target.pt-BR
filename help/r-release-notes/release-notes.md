---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Adobe Target Standard e do Target Premium.
title: 'Notas de versão do Target (atual) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: b25108284abbc44320fdceddd8ca155e2b800b3c
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 29%

---


# Notas de versão do Target (atual){#target-release-notes-current}

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium. Além disso, as notas de versão para APIs de Públicos alvos, SDKs, biblioteca JavaScript (at.js) e outras alterações de plataforma também são incluídas, quando aplicável.

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


Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## Target Standard/Premium 20.5.1 (17 de junho de 2020)

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| Analytics for Target (A4T) suporte para [!UICONTROL autoalocação] de atividades | [!UICONTROL A Autoalocação] de atividades agora é compatível com [Analytics para Público alvo](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Essa integração permite que você use a capacidade de alocação [!UICONTROL automática de bandido com vários braços para direcionar o tráfego para experiências vencedoras, ao mesmo tempo em que usa uma métrica de objetivo do] Adobe Analytics [!UICONTROL e/ou recursos de relatórios e análise] Adobe Analytics  .<br>Se você já tiver [implementado a A4T](/help/c-integrating-target-with-mac/a4t/a4timplementation.md) para uso com atividades de teste A/B e direcionamento de experiência, todos estarão configurados!<br>Para obter mais informações, consulte Suporte da [Analytics para Públicos alvos (A4T) para Autoalocar atividades](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) na criação *de* Atividades. |
| Tokens de resposta para o Método de alocação de tráfego para atividades de Público alvo automático e personalização automatizada | Dois tokens [de](/help/administrating-target/response-tokens.md) resposta foram adicionados às atividades [!UICONTROL Público alvo] automático e Personalização  automatizada para permitir determinar se um visitante recebeu uma experiência específica como resultado de ser atribuído ao tráfego &quot;controlado&quot; ou &quot;direcionado&quot;.<ul><li>`experience.trafficAllocationId` retornará 0 se um visitante tiver recebido uma experiência de estar no tráfego de &quot;controle&quot; e 1 se um visitante tiver recebido uma experiência da distribuição de tráfego &quot;direcionada&quot;.</li><li>`experience.trafficAllocationType` retornará &quot;controle&quot; e &quot;direcionado&quot;, respectivamente.</li></ul>Para obter mais informações sobre controle vs. tráfego direcionado, consulte [Selecionar o controle para a personalização automatizada ou atividade](/help/c-activities/t-automated-personalization/experience-as-control.md)de Público alvo automático. |
| [!UICONTROL Papel do editor] | Essa nova função é semelhante à função atual do [!UICONTROL Observador] (pode visualização atividades, mas não pode criá-las ou editá-las). No entanto, a função [!UICONTROL Editor] tem permissão adicional para ativar o atividade.<br>Para obter mais informações, consulte: <ul><li>**Usuários** do Target Standard: [Especifique funções e permissões](/help/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) em *Usuários*.</li><li>**Usuários** do Target Premium: [Etapa 6: Especifique funções e permissões](/help/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) em *Configurar permissões* corporativas.</li></ul> |
| Suporte a A4T em 25 [!DNL Analysis Workspace]<br>de junho de 2020 | [!UICONTROL O Analytics for Target] (A4T) agora é compatível com [!DNL Analysis Workspace]. O painel [!UICONTROL Analytics for Target (A4T) permite que você analise suas] atividades e experiências no [!DNL Adobe Target] [!DNL Analysis Workspace].<br>Para obter mais informações, consulte [Relatórios na Analytics](/help/c-integrating-target-with-mac/a4t/reporting.md) no relatórios ** A4T e no painel [A4T (Público alvo A4T) no Guia](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/a4t-panel.html) de ferramentas da ** Analytics. |

### Melhorias, correções e alterações

* Correção de um problema que fazia com que a métrica &quot;visitantes&quot; fosse armazenada na definição de atividade em vez de &quot;Visitantes únicos&quot;. (TGT-37098)
* Corrigido um problema na interface do usuário que fazia com que a barra de rolagem vertical não funcionasse corretamente na página do [!DNL Target] Audiência  . (TGT-36968)

## Versões at.js 1.8.2 e at.js 2.3.1 (15 de junho de 2020)

As seguintes melhorias e correções foram feitas nas bibliotecas do [!DNL Target] at.js:

| Recurso  / Aprimoramento | Descrição |
| --- | --- |
| at.js 1.8.2 | Esta versão do at.js é uma versão de manutenção e inclui a seguinte correção:<ul><li>Correção de um problema ao usar o CNAME e a substituição de borda, at.js 1.*O x* pode criar incorretamente o domínio do servidor, o que resultou na falha da [!DNL Target] solicitação. (TNT-35064)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
| at.js 2.3.1 | Essa versão do at.js é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:<ul><li>A `deviceIdLifetime` configuração foi substituída por [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). (TNT-36349)</li><li>Correção de um problema ao usar o CNAME e a substituição de borda, at.js 2.*O x* pode criar incorretamente o domínio do servidor, o que resultou na falha da [!DNL Target] solicitação. (TNT-35065)</li><li>Correção de um problema ao usar a [!DNL Target] extensão v2 e a [!DNL Launch][!DNL Adobe Analytics] extensão, [!DNL Launch] atrasou a [!DNL Target] [!DNL Analytics] `sendBeacon` chamada. (TNT-36407, TNT-35990, TNT-36000)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão - APIs do lado do servidor do Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notas de versão relacionadas às APIs do Adobe Target Server |
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
