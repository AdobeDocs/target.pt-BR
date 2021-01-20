---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras da DNL Adobe Target.
title: Notas de pré-lançamento do Adobe Target
feature: Release Notes
translation-type: tm+mt
source-git-commit: ae44c57c7b8767915fbbce4271a4b1858dd07efd
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 27%

---


# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 14 de janeiro de 2021**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do tempo das versões. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>**Fim da vida útil** do mbox.js: Em 31 de março de 2021, não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem [!DNL Target] atividades sendo executadas com o conteúdo padrão.
>
>Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca JavaScript at.js antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implemente o Público alvo para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Target Standard/Premium 21.1.1 (19 de janeiro de 2021)

Esta versão de manutenção contém os seguintes aprimoramentos, correções e alterações.

Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

* Adicionado um aviso ao selecionar uma métrica [!DNL Adobe Analytics] ao usar [!UICONTROL Analytics como a fonte do relatórios] (A4T) em uma atividade [!UICONTROL Público alvo automático]. [!UICONTROL Os modelos de ] direcionamento automático são otimizados para funcionar com métricas binárias (baseadas em conversão). Selecionar uma métrica contínua, como receita, pode ter resultados abaixo do ideal e os relatórios [!UICONTROL Insights de personalização] podem não ser precisos. (TGT-38926)
* Adição de um ícone de status no relatório [!UICONTROL Resumo do Público alvo automático] para [!UICONTROL Público alvo automático] atividades que usam A4T. O ícone de verificação verde ao lado de cada experiência no relatório indica que um modelo personalizado de aprendizagem de máquina foi gerado para essa experiência. O ícone do relógio indica que não foi fornecido tráfego suficiente para construir o modelo. (TGT-38925)
* Os relatórios [!UICONTROL Segmentos automatizados] e [!UICONTROL Atributos importantes] para [!UICONTROL Público alvo automático] atividades que usam as métricas de conversão A4T e [!DNL Analytics] são gerados e têm a mesma aparência que ao usar [!DNL Target] como fonte de relatórios. (TGT-38931)
* Adicionada uma opção de filtragem de ambiente à lista [!UICONTROL Recommendations] [!UICONTROL Collections]. (TGT-38353)
* Correção de um problema que fazia com que a contagem de produtos incorreta fosse exibida em [!UICONTROL coleções do Recommendations]. (TGT-39162)
* Adicionado um filtro [!UICONTROL Última atualização] ao [!UICONTROL Recommendations] [!UICONTROL Pesquisa de catálogo]. (TGT-38340)
* Correção de um problema em [!UICONTROL Recommendations] que causava o travamento da página [!UICONTROL Criar sequência] após alterar a vertical do setor. (TGT-38160)
* Correção de um problema que impedia que a atividade fosse salva se o Device Co-op estivesse ativado e o usuário fosse alterado de [!DNL Target] como a fonte do relatórios para [!DNL Analytics] (A4T). (TGT-38163)
* Correção de um problema que impedia os usuários de removerem uma audiência de uma oferta em uma atividade [!UICONTROL Automated Personalization] (AP). (TGT-39058)
* Correção de um problema que fazia com que o período incorreto (datas de start e término) fosse exibido nos cartões [!UICONTROL Informações da Audiência] para alguns clientes. (TGT-39150)
* Correção de um problema que impedia alguns clientes de visualizarem a lista de atividades no [!UICONTROL Espaço de trabalho padrão]. (TGT-38526)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
