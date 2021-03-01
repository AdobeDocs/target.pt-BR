---
keywords: Notas de versão, novos recursos, versões, atualizações, atualização, versão, aprimoramento, aprimoramentos, correções, correções de erros, atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos estão incluídos na versão atual?
feature: ' Notas de versão '
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 42%

---


# Notas de versão do Target (atual)

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium. Além disso, as notas de versão para APIs do Target, SDKs, biblioteca de JavaScript (at.js) e outras alterações na plataforma também são incluídas, quando aplicável.

>[!IMPORTANT]
>
>**Fim da vida útil** da mbox.js: Em 31 de março de 2021, o não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js normalmente falharão e afetarão suas páginas que têm [!DNL Target] atividades em execução ao veicular conteúdo padrão.
>
>Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

## Target Standard/Premium 21.1.1 (19 de janeiro de 2021)

Esta versão de manutenção contém os seguintes aprimoramentos, correções e alterações.

Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

* Adição de um aviso ao selecionar uma métrica [!DNL Adobe Analytics] ao usar [!UICONTROL o Analytics como fonte de relatórios] (A4T) em uma atividade [!UICONTROL Direcionamento automático]. [!UICONTROL Os modelos de ] Direcionamento automático são otimizados para funcionar com métricas binárias (baseadas em conversão). Selecionar uma métrica contínua, como receita, pode ter resultados aquém do ideal e os relatórios [!UICONTROL Insights de personalização] podem não ser precisos. (TGT-38926)
* Adição de um ícone de status no relatório [!UICONTROL Resumo do direcionamento automático] para atividades de [!UICONTROL Direcionamento automático] que usam o A4T. O ícone de verificação verde ao lado de cada experiência no relatório indica que um modelo personalizado de aprendizagem de máquina foi gerado para essa experiência. O ícone do relógio indica que não foi fornecido tráfego suficiente para construir o modelo. (TGT-38925)
* Os relatórios de [!UICONTROL Segmentos automatizados] e [!UICONTROL Atributos importantes] para atividades de [!UICONTROL Direcionamento automático] que usam as métricas de conversão A4T e [!DNL Analytics] são gerados e parecem iguais ao usar [!DNL Target] como fonte de relatórios. (TGT-38931)
* Adição de uma opção de filtragem de ambiente à lista [!UICONTROL Recommendations] [!UICONTROL Coleções]. (TGT-38353)
* Correção de um problema que fazia com que a contagem de produtos incorreta fosse exibida em [!UICONTROL Recommendations] coleções. (TGT-39162)
* Adição de um filtro [!UICONTROL Última atualização] ao [!UICONTROL Recommendations] [!UICONTROL Pesquisa no catálogo]. (TGT-38340)
* Correção de um problema no [!UICONTROL Recommendations] que fazia com que a página [!UICONTROL Criar sequência] travasse após alterar o vertical do setor. (TGT-38160)
* Correção de um problema que impedia o salvamento da atividade se o Device Co-op fosse ativado e o usuário alterasse de [!DNL Target] como fonte de relatórios para [!DNL Analytics] (A4T). (TGT-38163)
* Correção de um problema que impedia os usuários de removerem um público-alvo de uma oferta em uma atividade de [!UICONTROL Personalização automatizada] (AP). (TGT-39058)
* Correção de um problema que fazia com que o período incorreto (datas de início e término) fosse exibido em cartões [!UICONTROL Informações do público-alvo] para alguns clientes. (TGT-39150)
* Correção de um problema que impedia que alguns clientes visualizassem a lista de atividades no [!UICONTROL Espaço de trabalho padrão]. (TGT-38526)

## at.js 2.4.0 (14 de janeiro de 2021)

Esta versão da at.js é uma versão de manutenção e inclui as seguintes correções:

* Adiciona suporte para unfied profile/platform id para delivery de API customerIds.
* Corrige a injeção de tag de estilo inválida.

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não ser incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte Notas de versão da  [Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html). |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Lista de atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |
