---
keywords: Notas de versão;novos recursos;versões;atualizações;atualização;versão;aprimoramento;aprimoramentos;correções;correções de bugs;atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: Quais são os novos recursos incluídos na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 93bcfdf291892f5e0c3c16dbe553c2a33d74248c
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 59%

---

# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium] Além disso, as notas de versão para APIs do Target, SDKs, [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Migre para a versão mais recente do novo [!DNL Adobe Experience Platform Web SDK] ou para a biblioteca at.js JavaScript para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

## [!DNL Target Standard/Premium] 21.10.1 (6 de outubro de 2021)

Este lançamento inclui os seguintes novos recursos:

| Recurso | Detalhes |
| --- | --- |
|  Atualização da interface do usuário do Audiences | Como parte do esforço contínuo da equipe [!DNL Adobe Target] para melhorar a experiência do usuário para usuários [!DNL Target], esta versão atualiza as páginas [!UICONTROL Públicos-alvo] e [!UICONTROL Scripts de perfil] na interface do usuário [!DNL Target]. Essa atualização unifica e padroniza padrões de design que eram inconsistentes anteriormente, além de adicionar novas melhorias, como:<ul><li>A capacidade de selecionar e excluir vários públicos simultaneamente</li><li>Um [design do construtor de público-alvo atualizado](/help/c-target/c-audiences/create-audience.md)</li><li>Suporte a regras de exclusão no construtor de regras da biblioteca [!UICONTROL Audience]</li><li>Um novo filtro &quot;Fonte de público-alvo&quot;, para permitir uma descoberta de público-alvo mais rápida</li><li>Opções de filtro e pesquisa persistente da sessão</li></ul>Para obter mais informações, consulte [Públicos](/help/c-target/target.md).<br>**Observação**: Os novos   Públicos-alvo e  [!UICONTROL Interface ] de perfil serão lançados para todas as regiões na próxima semana. |
| [!UICONTROL Atualização ] da interface do usuário de scripts de perfil | A biblioteca [!UICONTROL Scripts de perfil] também foi atualizada e inclui uma interface atualizada junto com várias atualizações de produtividade:<ul><li>A capacidade de selecionar e excluir vários scripts de perfil simultaneamente</li><li>Um novo editor de código para scripts de perfil</li><li>Realce da sintaxe e verificação de erros no editor de código</li><li>Parâmetros de tokens de preenchimento automático (mbox ou perfil) por meio de atalhos do teclado</li></ul>Para obter mais informações, consulte [Perfis de visitante](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**Observação**: Os novos   Públicos-alvo e  [!UICONTROL Interface ] de perfil serão lançados para todas as regiões na próxima semana. |
| ![Selo Premium ](/help/assets/premium.png) Critérios do Recommendations criar e editar | O fluxo de trabalho de criação e edição de [!UICONTROL Recommendations Criteria] foi simplificado para simplificar a escolha do algoritmo e das configurações de recomendações certas para atingir suas metas.<br>Para obter mais informações, consulte  [Criar critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md). |
| ![Selo Premium ](/help/assets/premium.png) Janela de retrospectiva do Recommendations e melhorias na taxa de atualização do algoritmo | Agora é possível executar os algoritmos &quot;Mais visualizados&quot; e &quot;Mais vendidos&quot; com uma janela de retrospectiva de seis horas para capturar o conteúdo das tendências mais recentes. Quando a janela de retrospectiva de seis horas é selecionada, os resultados das recomendações são atualizados a cada 3 a 6 horas ao longo do dia.<br>Para obter mais informações, consulte  [Fonte ](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) de dados em  *Criar critérios*. |

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte as [Notas de versão da Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR). |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Atualização de produtos prioritários da Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |
