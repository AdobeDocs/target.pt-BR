---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Essas notas de versão oferecem informações sobre recursos, aprimoramentos, correções e problemas conhecidos para cada lançamento do Adobe Target Standard e do Target Premium.
title: 'Notas de versão do Target (atual) '
feature: Release Notes
translation-type: tm+mt
source-git-commit: 2dce7bbe94f20ad6f6732dfc3abceb69058a1f75
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 36%

---


# Notas de versão do Target (atual)

Essas notas de versão oferecem informações sobre recursos, aprimoramentos e correções para cada lançamento do Target Standard e do Target Premium. Além disso, as notas de versão para APIs de Públicos alvos, SDKs, biblioteca JavaScript (at.js) e outras alterações de plataforma também são incluídas, quando aplicável.

>[!IMPORTANT]
>
>**Fim da vida útil** do mbox.js: Em 31 de março de 2021, não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem [!DNL Target] atividades sendo executadas com o conteúdo padrão. Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca JavaScript at.js antes dessa data para evitar possíveis problemas com seus sites.
>
>* **Adobe Experience Platform Web SDK**: O  [!UICONTROL Adobe Experience Platform Web ] SDK permite que você interaja com os vários serviços no  [!DNL Experience Cloud] (incluindo  [!DNL Target]) por meio da Adobe Experience Edge Network. Se você optar por migrar para [!DNL Adobe Experience Platform Web SDK], consulte [O que é Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) no *Guia do SDK da Web*.
   >
   >
* **at.js**: A biblioteca JavaScript do at.js oferece muitas vantagens em relação ao mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única. Se você optar por migrar para at.js, consulte [Como o At.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e [Adobe Target Skill Builder: Bate-papo no desenvolvedor, migre o mbox.js do Adobe Target para o at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Embora a mbox.js seja atualmente suportada (até 31 de março de 2021), não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. Ao mover todos os clientes para o [!UICONTROL Adobe Experience Platform Web SDK] ou o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferta o suporte que você espera do Adobe.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

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

## at.js 2.4.0 (14 de janeiro de 2021)

Esta versão do at.js é uma versão de manutenção e inclui as seguintes correções:

* Adiciona suporte para ID de perfil/plataforma unificada às IDs de clientes da API do delivery.
* Correção de uma injeção de tag de estilo inválida.

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
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte Notas [ de versão do ](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Lista de atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |
