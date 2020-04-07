---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras do Público alvo DNL da Adobe.
title: Notas de pré-lançamento do Adobe Público alvo
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 1d34000b446c0fd37c6894bf5066f3cd16fc92a7

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 25 de março de 2020**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do tempo das versões. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!NOTE]
>
>* **desaprovação** da mbox.js: Em 30 de agosto de 2020, o Público alvo da Adobe não oferecerá mais suporte à biblioteca mbox.js. Após 30 de agosto de 2020, todas as chamadas feitas do mbox.js falharão e afetarão suas páginas com atividades do Público alvo em execução. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. For more information, see [How At.js Works](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md).
   >
   >   
   Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
   >
   >   
   Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferta do suporte que você espera da Adobe.


## Público alvo at.js (25 de março de 2020)

As novas versões do Público alvo at.js das bibliotecas JavaScript estão disponíveis:

* at.js versão 2.3.0
* at.js versão 1.8.1

For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## Target Standard/Premium 20.2.1 (23 de março de 2020) 

>[!IMPORTANT]
>
>Consulte as informações acima sobre a desaprovação do mbox.js.

Esta versão contém os seguintes aprimoramentos, correções e alterações:

* Correção de um problema que impedia os clientes de selecionar uma coleção ao executar uma pesquisa de catálogo. (TGT-36230)
* Correção de um problema em que um critério criado por meio de uma API, mas não referenciado por uma atividade criada na interface do usuário do Público alvo, podia ser excluído erroneamente da interface do usuário. (TGT-35917)
* Aprimoramentos de segurança implementados na Política de segurança de conteúdo (CSP). (TGT-36190)
* Correção de um problema que fazia com que &quot;NaN%&quot; fosse exibido ao deslizar a barra de porcentagem de Ponderação do atributo para a extremidade esquerda. (TGT-36211)
* Correção de problemas de localização para que o texto da interface do usuário em vários idiomas seja exibido corretamente.
* Nós padronizamos a lista de métricas disponíveis do Adobe Analytics para atividades do Público alvo (A4T), substituindo as métricas do Adobe Analytics não suportadas na versão atual das APIs do Adobe Analytics. Isso nos permitirá estender nosso suporte A4T em versões futuras do Público alvo da Adobe.

   Foram feitas as seguintes alterações:

   * &quot;Tempo médio gasto na página&quot; foi substituído por &quot;Tempo médio gasto no site&quot;. Qualquer atividade que usa essa métrica como métrica a Métrica de meta principal terá &quot;Tempo médio gasto no site&quot; (observação: medida em minutos em vez de segundos) selecionada como a Métrica de objetivo principal na próxima vez que a atividade for editada.
   * &quot;Visitantes&quot; foi substituído por &quot;Visitantes únicos&quot;. Todas as atividades que usarem essa métrica como a Métrica de meta principal terão &quot;Visitantes únicos&quot; selecionados como a Métrica de meta principal na próxima vez que a atividade for editada.

* As métricas a seguir foram substituídas e não podem mais ser selecionadas como a Métrica de meta principal ao criar uma nova atividade A4T.

   | Métricas obsoletas | Métricas de substituição sugeridas |
   |--- |--- |
   | Visitantes diários, Visitantes por hora, Visitantes mensais, Visitantes trimestrais, Visitantes semanais, Visitantes anuais | Visitantes únicos |
   | Profundidade média da visita | n/d. Não sugerido como uma métrica de objetivo principal |
   | Bots | n/d. Não sugerido como uma métrica de objetivo principal |
   | Taxa De Falha Móvel, Duração Média Da Sessão Anterior Móvel, Classificação Média Da Loja De Aplicativos Móveis, Taxa De Falha De Desempenho Do Aplicativo Móvel, Classificação Média Da Loja De Aplicativos Móveis | n/d. Não sugerido como uma métrica de objetivo principal |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
