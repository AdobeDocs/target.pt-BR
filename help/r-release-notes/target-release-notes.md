---
keywords: notas de versão, versões, atualizações, versão futura, melhorias, novos recursos, correções, atualizações, pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na próxima versão do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos serão incluídos na próxima versão?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 93bcfdf291892f5e0c3c16dbe553c2a33d74248c
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 43%

---

# Notas de versão do Target (pré-lançamento)

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização em: 6 outubro de 2021**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!IMPORTANT]
>
>**Fim da vida útil da mbox.js**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão.
>
>Para evitar possíveis problemas com seus sites, migre para a versão mais recente do novo [!DNL Adobe Experience Platform Web SDK] ou para a biblioteca at.js de JavaScript. Para obter mais informações, consulte [Visão geral: implementar o Target para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.10.1 (6 de outubro de 2021)

Este lançamento inclui os seguintes novos recursos:

| Recurso | Detalhes |
| --- | --- |
|  Atualização da interface do usuário do Audiences | Como parte do esforço contínuo da equipe [!DNL Adobe Target] para melhorar a experiência do usuário para usuários [!DNL Target], esta versão atualiza as páginas [!UICONTROL Públicos-alvo] e [!UICONTROL Scripts de perfil] na interface do usuário [!DNL Target]. Essa atualização unifica e padroniza padrões de design que eram inconsistentes anteriormente, além de adicionar novas melhorias, como:<ul><li>A capacidade de selecionar e excluir vários públicos simultaneamente</li><li>Um [design do construtor de público-alvo atualizado](/help/c-target/c-audiences/create-audience.md)</li><li>Suporte a regras de exclusão no construtor de regras da biblioteca [!UICONTROL Audience]</li><li>Um novo filtro &quot;Fonte de público-alvo&quot;, para permitir uma descoberta de público-alvo mais rápida</li><li>Opções de filtro e pesquisa persistente da sessão</li></ul>Para obter mais informações, consulte [Públicos](/help/c-target/target.md).<br>**Observação**: Os novos   Públicos-alvo e  [!UICONTROL Interface ] de perfil serão lançados para todas as regiões na próxima semana. |
| [!UICONTROL Atualização ] da interface do usuário de scripts de perfil | A biblioteca [!UICONTROL Scripts de perfil] também foi atualizada e inclui uma interface atualizada junto com várias atualizações de produtividade:<ul><li>A capacidade de selecionar e excluir vários scripts de perfil simultaneamente</li><li>Um novo editor de código para scripts de perfil</li><li>Realce da sintaxe e verificação de erros no editor de código</li><li>Parâmetros de tokens de preenchimento automático (mbox ou perfil) por meio de atalhos do teclado</li></ul>Para obter mais informações, consulte [Perfis de visitante](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**Observação**: Os novos   Públicos-alvo e  [!UICONTROL Interface ] de perfil serão lançados para todas as regiões na próxima semana. |
| ![Selo Premium ](/help/assets/premium.png) Critérios do Recommendations criar e editar | O fluxo de trabalho de criação e edição de [!UICONTROL Recommendations Criteria] foi simplificado para simplificar a escolha do algoritmo e das configurações de recomendações certas para atingir suas metas.<br>Para obter mais informações, consulte  [Criar critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md). |
| ![Selo Premium ](/help/assets/premium.png) Janela de retrospectiva do Recommendations e melhorias na taxa de atualização do algoritmo | Agora é possível executar os algoritmos &quot;Mais visualizados&quot; e &quot;Mais vendidos&quot; com uma janela de retrospectiva de seis horas para capturar o conteúdo das tendências mais recentes. Quando a janela de retrospectiva de seis horas é selecionada, os resultados das recomendações são atualizados a cada 3 a 6 horas ao longo do dia.<br>Para obter mais informações, consulte  [Fonte ](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) de dados em  *Criar critérios*. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
