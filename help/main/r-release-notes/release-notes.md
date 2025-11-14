---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: e5bc137ed1f32b07569a4f1a31746da19fb164d3
workflow-type: tm+mt
source-wordcount: '1736'
ht-degree: 17%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão detalhadas e documentação até [!UICONTROL Experience League]. Estes são alguns destaques importantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

Para obter mais informações, consulte [[!DNL Target] Perguntas frequentes sobre atualização da interface](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 25.11.2 (14 de novembro de 2025)

**Ofertas de decisão**

+++Ver detalhes
* **Decisões de oferta com seletores ocultos ou inválidos não editáveis na interface atualizada.** Correção de um problema na interface do usuário atualizada em que as decisões de oferta vinculadas a seletores ocultos ou inválidos não podiam ser editadas, a menos que o elemento estivesse visível no Visual Experience Composer (VEC). A edição agora é suportada diretamente no painel, restaurando a funcionalidade disponível na interface herdada e garantindo que as decisões de oferta possam ser modificadas, independentemente da visibilidade do seletor. (TGT-53899)

+++

**Recommendations**

+++Ver detalhes
* **A edição de critérios em uma atividade causou uma falha na página.** Correção de um problema na interface do usuário atualizada em que os critérios da atividade de edição faziam com que a página falhasse com erros de console relacionados a `useCrudActionsCtx`. O editor de critérios agora é carregado e funciona corretamente, garantindo que as atividades possam ser editadas sem interrupção. (TGT-53971)
* A coluna **[!UICONTROL Message]falhou intermitentemente ao exibir os dados do produto na interface atualizada.** Correção de um problema na interface do usuário [!UICONTROL Recommendations] atualizada em que a coluna [!UICONTROL Message] em [!UICONTROL Catalog Search] falhava intermitentemente em exibir dados do produto, mesmo que os valores estivessem presentes no feed. A coluna agora mostra consistentemente os valores de mensagem corretos em todos os produtos, garantindo visibilidade confiável sem a necessidade de reconfiguração manual da coluna. (TGT-52777)
* O botão **[!UICONTROL Download Recommendations Data]não fica visível após salvar a atividade na interface atualizada.** Correção de um problema na interface do usuário atualizada em que o botão [!UICONTROL Download Recommendations Data] não era exibido para determinadas atividades salvas, mesmo depois de salvar novamente. O botão agora é exibido de forma consistente em todas as atividades, garantindo que os usuários possam exportar dados de recomendação com confiança sem precisar de soluções alternativas. (TGT-53802)
* **A abertura de determinados produtos de uma coleção retornou &quot;O recurso solicitado não foi encontrado&quot; e o modal não tinha uma opção de fechamento.** Correção de um problema na interface atualizada do Recommendations, em que a abertura de determinados produtos a partir de uma coleção disparava um erro &quot;O recurso solicitado não foi encontrado&quot; e exibia uma modal em branco sem uma opção de fechamento. O modal agora carrega os detalhes do produto corretamente e uma opção de fechamento está sempre disponível para sair normalmente. (TGT-53986)

+++

## [!DNL Target Standard/Premium] 25.11.1 (10 de novembro de 2025)


**Analytics for Target (A4T)**

+++Ver detalhes
* **[!UICONTROL Goals & Settings]mensagem de erro ao usar [!DNL Adobe Analytics] como fonte de relatórios na interface atualizada.** Correção de um problema na interface atualizada do usuário [!UICONTROL Overview], na qual a seção Metas exibia o erro &quot;Algo deu errado. Não podemos completar o seu pedido. Entre em contato com [!DNL Adobe Client Care] se o problema persistir&quot; quando [!DNL Adobe Analytics] (A4T) for selecionado como a fonte de relatórios. As metas agora são exibidas corretamente com as métricas [!UICONTROL Adobe Analytics], garantindo uma visibilidade consistente em todas as fontes de relatórios. (TGT-54021)

+++

**Públicos-alvo**

+++Ver detalhes
* **Não é possível selecionar vários públicos-alvo de relatório na interface atualizada.** Correção de um problema na interface do usuário atualizada em que os usuários não podiam selecionar vários públicos de relatórios recém-criados simultaneamente ao editar uma atividade. Agora, vários públicos-alvo podem ser atribuídos de uma só vez, melhorando a flexibilidade e a eficiência na configuração de relatórios. (TGT-53253)

+++

**Ofertas de decisão**

+++Ver detalhes
* **Não é possível editar ou substituir ofertas de decisão na interface atualizada.** Correção de um problema na interface atualizada em que as ofertas de decisão não podiam ser editadas ou substituídas por meio do painel [!UICONTROL Modifications] e os nomes das ofertas apareciam em branco. As ofertas de decisão agora são totalmente acessíveis e editáveis, restaurando a paridade com a interface herdada e garantindo que os clientes possam gerenciar ofertas diretamente nas atividades do. (TGT-53884)

+++

**Localização**

+++Ver detalhes
* **Correção de vários erros de localização na interface do usuário coreana e japonesa.** (TGT-54003, TGT-54004, TGT-54006, TGT-54007, &amp; TGT-54018)

+++

**[!UICONTROL Recommendations]**

+++Ver detalhes
* **A Promoção por Atributo com Correspondência de Atributo de Entidade falhou ao carregar a chave de recomendação após salvar a atividade.** Corrigido um problema onde promoções do tipo [!UICONTROL Promotion by Attribute] com o tipo de regra [!UICONTROL Entity Attribute Matching] não carregavam a chave de recomendação quando editadas após salvar uma atividade. O problema foi causado pelo `customKeyId` não ter sido solicitado por meio do GraphQL. As chaves de recomendação agora são carregadas corretamente durante as edições de promoção. (TGT-53117)
* **A recomendação persiste visualmente ao alternar de ExpB para ExpA.** Correção de um problema em que inserir uma recomendação na Experiência B e, em seguida, alternar para a Experiência A deixava a caixa de oferta de recomendação visível. Isso era apenas uma inconsistência visual; as modificações agora são renderizadas corretamente ao alternar entre experiências, garantindo um comportamento preciso da interface. (TGT-53911)
* **A chave de recomendação não está carregando para [!UICONTROL Promotion by Attribute] com [!UICONTROL Entity Attribute] Correspondência.** Correção de um problema em que promoções do tipo [!UICONTROL Promotion by Attribute] com o tipo de regra [!UICONTROL Entity Attribute Matching] não carregavam a chave de recomendação quando editadas após salvar uma atividade. A chave de recomendação agora é recuperada corretamente por meio do GraphQL, garantindo que as promoções sejam exibidas e funcionem conforme esperado. (TGT-53917)
* **Recomendações de edição sobre elementos ocultos do HTML que não funcionam na interface atualizada.** Correção de um problema na [!UICONTROL New Create] e na interface do VEC em que as atividades de recomendação aplicadas a elementos ocultos do HTML não podiam ser editadas. Essa funcionalidade agora funciona conforme esperado, restaurando a paridade com a interface herdada e garantindo que as recomendações possam ser modificadas independentemente da visibilidade do elemento. (TGT-53953)
* **Não é possível editar atividades de recomendação em elementos ocultos do HTML na interface atualizada.** Correção de um problema na interface atualizada em que as atividades de recomendação aplicadas a elementos ocultos do HTML não podiam ser editadas. Essa funcionalidade agora funciona conforme esperado, restaurando a paridade com a interface herdada e garantindo que as recomendações possam ser modificadas independentemente da visibilidade do elemento. (TGT-53951)
* **O catálogo de recomendações não tem valores de atributo na interface atualizada.** Correção de um problema na interface atualizada do usuário do [!UICONTROL Recommendations], em que as listagens de pesquisa de catálogo falhavam intermitentemente em exibir determinados valores de atributo (por exemplo, mensagem), mesmo quando presentes no feed do produto. Os valores de atributo agora são carregados de forma consistente nos resultados da pesquisa sem exigir reconfiguração da coluna, melhorando a confiabilidade e a eficiência do gerenciamento de catálogos. (TGT-52769)
* O botão **[!UICONTROL Download Recommendations]está ausente para atividades [!DNL Recommendations] na interface atualizada.** Correção de um problema na interface atualizada do usuário [!DNL Recommendations] em que o botão [!UICONTROL Download Recommendations] não estava visível para atividades A/B que usam recomendações. O botão agora é exibido corretamente, permitindo que os usuários exportem os dados de recomendação conforme esperado, de forma consistente com a funcionalidade na interface herdada. (TGT-53768)
* O botão **[!UICONTROL Download Recommendation Data]está ausente na interface de Visão Geral atualizada.** Correção de um problema na interface do usuário atualizada [!UICONTROL Overview] em que o botão [!UICONTROL Download Recommendation Data] não estava visível para atividades que continham recomendações. O botão agora é exibido corretamente, garantindo que os usuários possam exportar os dados de recomendações diretamente, sem precisar alternar de volta para a interface herdada. (TGT-53772)
* **A edição dos critérios de atividade às vezes resultava em tela em branco na interface do usuário atualizada.** Correção de um problema na interface do usuário atualizada em que clicar em [!UICONTROL Edit Criteria in Experiences] ocasionalmente resultava em uma tela em branco para determinadas atividades. O editor de critérios agora é carregado de forma confiável em todas as atividades, garantindo que os usuários possam editar sem interrupção. (TGT-53961)
* **Não é possível editar critérios de sequência na interface atualizada.** Correção de um problema na interface do usuário atualizada em que a tentativa de editar [!UICONTROL Sequence Criteria] fazia com que o pop-up de critérios permanecesse preso ao carregar e, em seguida, exibisse uma tela em branco. O editor de critérios agora é carregado corretamente, permitindo que os usuários editem e atualizem os critérios de sequência sem interrupção. (TGT-53985)

+++

**[!UICONTROL Reports]**

+++Ver detalhes
* **[!UICONTROL Multivariate Test]locais (MVT) e problema de relatório de gráfico impediram a geração de relatório.** Correção de um problema em que as atividades do MVT falhavam ao gerar relatórios do [!UICONTROL Location Contribution] e do Graph na interface do usuário do Target, exibindo o erro &quot;Algo deu errado. Não podemos completar o seu pedido.&quot; Agora os relatórios são carregados corretamente na interface do usuário, garantindo visibilidade total. (TGT-53654)
* **Relatórios de MVT não carregam devido a [!UICONTROL Element] erro no relatório de contribuição.** Correção de um problema em que os relatórios de atividades do MVT falhavam ao serem carregados na interface do usuário do Target, mostrando o erro &quot;Não foi possível buscar o relatório de contribuição do elemento.&quot; Os relatórios agora são exibidos corretamente, garantindo total visibilidade das contribuições de elementos. (TGT-53691)
* **Exportar detalhes do pedido para um problema de CSV para [!UICONTROL Experience Targeting] (XT) atividades.** Correção de um problema em que a opção [!UICONTROL Export Order Details to CSV] aparecia incorretamente para atividades XT e retornava um arquivo vazio. A opção agora só é exibida para atividades de AP, garantindo uma funcionalidade de exportação precisa e evitando confusão. (TGT-53798)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes
* O problema do botão **[!UICONTROL Delete Modification]impediu a remoção das modificações da atividade.** Correção de um problema em que o botão [!UICONTROL Delete Modification] da interface do usuário [!DNL Target] não funcionava, impedindo usuários de removerem modificações nas atividades. O botão agora funciona conforme esperado, permitindo que as modificações sejam excluídas de forma confiável sem demora. (TGT-53728)
* **Os seletores preferenciais não são reconhecidos na interface atualizada.** Correção de um problema na interface do usuário atualizada em que os seletores preferenciais, como `data-target-component-id`, não apareciam na lista do seletor de CSS no VEC. Os usuários agora podem selecionar atributos preferenciais de maneira confiável em vez de nomes de classe gerados dinamicamente, garantindo um direcionamento estável em atualizações de página de SPA. (TGT-53908)
* **Incompatibilidade de alinhamento de local de atividade entre [!UICONTROL Edit] e [!UICONTROL Overview] páginas.** Correção de um problema em que a numeração do local da atividade na página [!UICONTROL Overview] não estava alinhada com as atualizações feitas na página [!UICONTROL &#x200B; Edit Experience]. Agora, os locais permanecem consistentes em ambas as exibições, garantindo um alinhamento preciso e evitando posições ausentes ou com numeração incorreta. (TGT-53960 e TGT-53954)
* **Não é possível voltar para o modo [!UICONTROL Design] no VEC atualizado.** Correção de um problema na interface atualizada do VEC em que os usuários não podiam voltar para o modo [!UICONTROL Design] depois de navegarem para uma nova página no modo [!UICONTROL Browse]. A opção [!UICONTROL Design] agora funciona corretamente, permitindo que as modificações sejam aplicadas facilmente nas páginas. (TGT-53988 e TGT-53993)
* **Parâmetro de consulta não exibido na visão geral da atividade.** Correção de um problema na interface atualizada em que os parâmetros de consulta não eram exibidos na página [!UICONTROL Overview] para atividades, causando discrepâncias entre o [!UICONTROL Overview] e as URLs de entrega da página. Agora os parâmetros de consulta são exibidos corretamente, garantindo que os locais de atividade sejam totalmente representados e consistentes em todas as exibições. (TGT-53701)

+++

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| [Alterações de documentação](/help/main/r-release-notes/doc-change.md) | Veja informações detalhadas sobre atualizações neste manual que podem não estar incluídas nas notas de versão. |
| [Notas de versões anteriores](/help/main/r-release-notes/release-notes-for-previous-releases.md). | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium. |
| [Notas de versão do Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=pt-BR){target=_blank} | Veja as notas de versão mais recentes das soluções da Adobe Experience Cloud. |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| [Atualização de produtos prioritários da Adobe](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | Receba notificações antecipadas sobre futuros aprimoramentos de produtos para o [!DNL Target] e outras soluções da [!DNL Adobe Experience Cloud]. |
| [Notas de versão do Target - Pré-lançamento](/help/main/r-release-notes/target-release-notes.md){target=_blank} | Informações sobre os lançamentos do Target no mês atual, incluindo informações de pré-lançamento. |
