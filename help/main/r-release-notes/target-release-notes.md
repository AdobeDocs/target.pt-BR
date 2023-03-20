---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 7b8390042a0e15df6c05d176b2f525ddd83c9608
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 49%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 20 de março de 2023**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.3.1 (30 de março de 2023)

Esta versão estará disponível de acordo com o seguinte agendamento:

* **28 de março**: regiões da Europa, Oriente Médio e África (EMEA)
* **29 de março**: região da Ásia-Pacífico (APAC)
* **30 de março**: região das Américas

Essa versão contém os seguintes novos recursos, aprimoramentos e correções:

| Recurso | Detalhes |
|--- |--- |
| AEM fragmentos de conteúdo para personalização e experimentação sem periféricos | Use [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragmentos de conteúdo] em [!DNL Target] atividades. Combine a facilidade de uso e o poder do AEM com os poderosos recursos de Inteligência Artificial (AI) e Aprendizagem de Máquina (ML) em [!DNL Target] para testar e personalizar experiências em escala. |
| Métricas otimizadas do A4T para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] | O [!DNL Target] permite escolher métricas baseadas em eventos binomiais ou em eventos contínuos ao usar o [!UICONTROL A4T] para as atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático].<P>Esteja ciente da seguinte alteração nas métricas compatíveis:<ul><li>O [!DNL Target] preservará o comportamento anterior para as atividades já existentes até 9 de setembro de 2023. Após essa data, as atividades usando métricas incompatíveis serão descontinuadas para forçar a migração de atividades existentes para o novo comportamento.</li></ul> |
| [!UICONTROL Alocação automática] usando o [!UICONTROL Analytics for Target] (A4T) | Tutorial atualizado:<ul><li>[Configuração de relatórios do A4T no [!DNL Analysis Workspace] para as atividades de [!UICONTROL Alocação automática]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=pt-BR){target=_blank}</li></ul> |
| [!UICONTROL Direcionamento automático] usando o [!UICONTROL Analytics for Target] (A4T) | Tutorial atualizado:<ul><li>[Configuração de relatórios do A4T no [!DNL Analysis Workspace] para as atividades de [!UICONTROL Direcionamento automático]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=pt-BR){target=_blank}</li></ul> |

* Sincronização aprimorada de público-alvo e atividade para que os itens criados em [!DNL Adobe Experience Platform] e [!DNL Adobe Audience Manager] estão disponíveis no [!DNL Target] Interface do usuário mais rápida. (TGT-44568)
* Alterações feitas para permitir que os usuários removam a variável [!UICONTROL URL padrão] under [!UICONTROL Administração] > [!UICONTROL Visual Experience Composer] > [!UICONTROL URL padrão]. Essa alteração permite que os clientes alterem o URL padrão de volta para uma string vazia, o que anteriormente não era possível após a configuração inicial. (TGT-44577)
* Remoção de restrições que impedia clientes de editar ou excluir públicos-alvo prontos para uso (públicos-alvo com nomes reservados). (TGT-44655)
* Desativado o &quot;[!UICONTROL Concluído]&quot; ao carregar os giradores, a opção estava visível no [!DNL Target] IU ao criar [públicos-alvo combinados](/help/main/c-target/combining-multiple-audiences.md). (TGT-44079)
* Correção do [!UICONTROL Idioma] na parte inferior do [!UICONTROL Públicos-alvo] para que ele vincule corretamente ao &quot;[!UICONTROL Preferências de comunicação da conta]&quot;. (TGT-43562)
* Solução de um problema que, ocasionalmente, impedia que os clientes criassem [!UICONTROL Teste A/B] depois de selecionar a variável [!UICONTROL Adobe Analytics] opção em [!UICONTROL Administração] > [!UICONTROL Relatório] > [!UICONTROL Solução de relatório do Experience Cloud]. (TGT-44844)
* Correção de um problema que impedia que os clientes visualizassem a última experiência em um [!UICONTROL Teste multivariado] com muitas experiências dentro da variável [!UICONTROL Visual Experience Composer] (VEC). O [Caminho DOM](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) na parte inferior do VEC, às vezes, impedia que os clientes visualizassem a última experiência. (TGT-44578)
* Correção de um problema que fazia com que o URL de navegação no VEC não refletisse a página atual que está visível em uma sessão normal do navegador se a página requer autorização ou chama redirecionamentos. (TGT-44350)
* Correção de um problema que impedia que os clientes alterassem a configuração [!UICONTROL Filtrar critérios incompatíveis] definição em [!UICONTROL Recommendations] > [!UICONTROL Configurações]. (TGT-44398)
* Correção de um problema que fazia com que solicitações POST criassem um novo [!DNL Recommendations] os feeds falham ao usar [!UICONTROL Classificações do Analytics] com conjuntos de relatórios com pontos em seus nomes. (TGT-44598)
* Links atualizados na [!DNL Target] IU para apontar para a nova [Extensão do Visual Editing Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md). (TGT-44459)
* Segurança aprimorada para impedir tentativas de falsificação de solicitação do lado do servidor (SSRF) em [!DNL Recommendations] feeds. (TGT-43769)
* Correção de um problema que impedia que os clientes visualizassem imagens em [!DNL Recommendations] designs se o nome da imagem contiver [GB18030 caracteres](https://en.wikipedia.org/wiki/GB_18030){target=_blank}. (TGT-44614)
* Correção de um problema que causava alguns [GB18030 caracteres](https://en.wikipedia.org/wiki/GB_18030){target=_blank} a ser evitada no [!UICONTROL Modificações] painel ao editar [!UICONTROL Texto/HTML] em uma atividade do [!UICONTROL Experiências] página. (TGT-44600)
* Várias correções de localização foram feitas na interface do [!DNL Target].


## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |


## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
