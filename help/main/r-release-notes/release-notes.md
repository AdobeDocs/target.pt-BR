---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 550fa1e8d4127babe02403708b73862505bf8c99
workflow-type: tm+mt
source-wordcount: '1772'
ht-degree: 15%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão detalhadas e documentação até [!UICONTROL Experience League]. Estes são alguns destaques importantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

Para obter mais informações, consulte [[!DNL Target] Perguntas frequentes sobre atualização da interface](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 26.1.1 (segunda-feira, 18 de janeiro de 2026)

**Atividades**

+++Ver detalhes

* **Não é possível copiar a atividade - entrada de usuário inválida.** O problema que fazia com que os usuários vissem um erro &quot;entrada de usuário inválida&quot; inútil ao copiar uma atividade foi corrigido. Anteriormente, quando uma atividade era duplicada, suas atribuições de propriedade específicas do espaço de trabalho não eram preservadas, fazendo com que o back-end rejeitasse a solicitação de salvamento porque ABActivity requer pelo menos uma propriedade pertencente a um espaço de trabalho não padrão. Essa incompatibilidade acionou um erro genérico na interface do usuário, deixando os usuários sem orientação. A correção garante que as atribuições de espaço de trabalho sejam retidas corretamente durante as operações de cópia, permitindo que os usuários salvem a atividade copiada sem modificação e evitando erros de validação enganosos. (TGT-54282)
* **Habilitar a coluna de espaço de trabalho na oferta do editor da Web.** Essa atualização soluciona a confusão do cliente causada por ofertas do [!UICONTROL Default Workspace] que aparecem em outros espaços de trabalho dentro do Editor da Web. Embora esse comportamento esteja funcionando como projetado, as ofertas do [!UICONTROL Default Workspace] estão intencionalmente visíveis em todos os espaços de trabalho, os clientes relataram que a interface do usuário não deixou a origem do espaço de trabalho clara, especialmente ao criar atividades em um espaço de trabalho não padrão, como &quot;Aprovadores&quot;. Para melhorar a clareza, a coluna [!UICONTROL Workspace] foi habilitada na lista de ofertas do Editor da Web, permitindo que os usuários distingam facilmente a qual espaço de trabalho cada oferta pertence e evitando interpretações incorretas das ofertas adicionais exibidas. (TGT-54138)
* **Links com target=&quot;_blank&quot; são abertos em uma nova guia.** Essa correção soluciona um problema em que sites criados contendo links com ~target=&quot;_blank&quot;~ abririam em uma nova guia do navegador quando clicados no modo [!UICONTROL Browse], interrompendo a experiência de visualização no editor. O comportamento ocorreu porque os atributos de link nativo da página criada não estavam sendo interceptados pelo JavaScript inserido na extensão, ao contrário da interface herdada, em que os elementos de ancoragem foram transformados e seus destinos foram substituídos para manter a navegação dentro do editor. A atualização garante que os links que usam ~target=&quot;_blank&quot;~ agora sejam manipulados corretamente no Editor da Web, para que não abram mais guias externas durante a criação. (TGT-54134)
* **Aviso de desseleção de propriedade.** Esta atualização apresenta um aviso visual para informar claramente aos usuários quando eles desmarcam uma propriedade detectada automaticamente no Editor de atividades. Anteriormente, a remoção de uma propriedade detectada automaticamente não fornecia nenhuma indicação de que a propriedade seria excluída permanentemente, o que poderia levar à perda acidental da configuração de direcionamento. A correção adiciona um ícone de aviso, consistente com o comportamento na interface herdada, para notificar os usuários que desmarcar a propriedade a remove da atividade. (TGT-54121)
* A lista suspensa **[!UICONTROL Workspaces]está limitada a 20 na seção [!UICONTROL Users].** Essa correção resolve um problema em que a lista suspensa [!UICONTROL Workspaces] na seção [!UICONTROL Administration] > [!UICONTROL Users] exibia apenas 20 espaços de trabalho, mesmo quando um usuário tinha acesso a muitos outros. A chamada subjacente do GraphQL para `licenseGroups` também foi limitada a 20 resultados, fazendo com que a interface do usuário mostrasse uma lista incompleta apesar de o usuário ter acesso a mais espaços de trabalho na organização. A atualização remove esse limite rígido para que o conjunto completo de espaços de trabalho disponíveis agora seja retornado e exibido corretamente. (TGT-53820)
* **Correção de um problema em que o modal de ofertas não mostrava a coluna do espaço de trabalho.** Correção de um problema em que o modal de ofertas não exibia a coluna do espaço de trabalho na interface atualizada. Isso causou confusão para os clientes porque as ofertas do [!UICONTROL Default Workspace] apareciam junto com as ofertas do espaço de trabalho selecionado, sem nenhuma indicação de sua origem. A coluna espaço de trabalho agora está ativada para que os clientes possam identificar claramente a qual espaço de trabalho cada oferta pertence. (TGT-52320)

+++

**Propriedades**

+++Ver detalhes
* **A edição da atividade não deve adicionar uma propriedade detectada automaticamente se já tiver sido removida.** Essa correção soluciona um problema em que a edição de uma atividade reintroduziria automaticamente uma propriedade detectada automaticamente que o usuário havia removido. Ao reabrir uma atividade para edição, o sistema restaurou incorretamente a propriedade removida, gerando comportamento inconsistente e confusão no [!UICONTROL Properties List]. A atualização garante que, uma vez removida, a propriedade detectada automaticamente permanecerá removida durante todas as edições subsequentes e não reaparecerá, a menos que o usuário a adicione explicitamente de volta. (TGT-54182)
* **Não adicionar propriedades detectadas automaticamente se já tiverem sido removidas.** Essa correção garante que, uma vez que um usuário remova manualmente uma propriedade detectada automaticamente de uma atividade, o sistema não a reintroduza mais durante a navegação subsequente no editor de atividades. Anteriormente, se um usuário desmarcasse uma propriedade detectada automaticamente, movesse para a etapa [!UICONTROL Targeting] e retornasse a [!UICONTROL Experiences], o editor preencheria novamente a propriedade removida com base na lista detectada automaticamente armazenada na fatia de estado do Editor de atividades. A lógica atualizada agora compara as propriedades detectadas automaticamente com as propriedades atuais na fatia ~ActivityState~ e impede a readição de qualquer propriedade detectada automaticamente que o usuário já tenha removido. Isso resulta em um comportamento consistente nas etapas e respeita a intenção do usuário. (TGT-54181)
* **Adicionar texto detectado automaticamente à lista de propriedades.** Esse aprimoramento atualiza o [!UICONTROL Properties List] para rotular claramente qualquer propriedade que tenha sido detectada automaticamente pelo sistema. Quando uma propriedade detectada automaticamente também está presente no [!UICONTROL Properties List] visível para o usuário, ela agora exibe o texto &quot;(Detectado Automaticamente)&quot; ao lado de seu nome, usando o valor armazenado no estado ~ActivityEditorSlice~. Isso espelha o comportamento da interface herdada e ajuda os usuários a distinguir facilmente entre as propriedades selecionadas manualmente e as propriedades identificadas automaticamente. (TGT-54120)
* **Adicionar [!UICONTROL Properties] detectado automaticamente ao estado.** Essa atualização garante que o estado ~ActivityEditorSlice.ExperienceEditor~ mantenha, de maneira consistente, uma lista atualizada de todas as IDs de propriedade detectadas automaticamente transmitidas do Editor da Web para a guia Atividade [!UICONTROL Experiences]. Cada vez que o usuário navega para a guia [!UICONTROL Experiences], o estado é atualizado com qualquer propriedade recém-detectada, evitando duplicatas, garantindo um rastreamento preciso e um comportamento downstream confiável. (TGT-54119)

+++

**Recomendações**

+++Ver detalhes
* O menu suspenso **[!UICONTROL Environment]mostra apenas 100 resultados.** Essa correção resolve uma limitação em que os clientes com mais de 100 ambientes só podiam ver as primeiras 100 entradas no menu suspenso [!UICONTROL Environment] em [!UICONTROL Recommendations]. A consulta subjacente do GraphQL (~getEnvironmentsV2~) foi paginada com um tamanho de página codificado de 100, fazendo com que a interface exiba apenas uma lista parcial, mesmo quando houver páginas adicionais disponíveis. Para clientes que têm mais de 100 ambientes, esse problema resultou na ausência de opções e em uma experiência de seleção incompleta. A atualização aumenta o limite para que todos os ambientes sejam retornados e exibidos, garantindo visibilidade total independentemente da contagem do ambiente. (TGT-53903)

+++

**Relatórios**

+++Ver detalhes

* **Correção de um problema em que a seta [!UICONTROL Reports] não indicava claramente colunas expansíveis.** Correção de um problema em que a tabela de relatórios não mostrava claramente que colunas adicionais poderiam ser expandidas na interface atualizada. Uma dica de ferramenta que desaparece foi adicionada à seta [!UICONTROL Reports] próxima aos cabeçalhos da coluna para ajudar os clientes a entenderem que mais colunas estão disponíveis.

+++

**Exibições**

+++Ver detalhes

* **Não é possível excluir as modificações aplicadas aos modos de exibição.** Essa correção resolve um problema em que os usuários não conseguiam excluir modificações em uma atividade, a menos que a modificação tivesse sido reaplicada primeiro a exibições adicionais. Ao editar uma atividade (por exemplo, ID de atividade 302467), as tentativas de excluir qualquer modificação não tinham efeito, impedindo que os usuários removessem alterações indesejadas. No entanto, uma vez que uma modificação foi reaplicada usando &quot;Aplicar a mais exibições&quot; e atribuída a um evento `Page Load`, a exclusão funcionou repentinamente como esperado. (TGT-54088)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Ver detalhes
* O nome **[!UICONTROL Experience Fragment]foi truncado na nova interface do VEC** (TGT-54312)
* **Não é possível usar [!UICONTROL Advanced Settings] para a métrica [!UICONTROL Revenue].** Essa correção soluciona um problema em que os usuários encontravam um erro 403 de &quot;Acesso negado&quot; ao configurar o [!UICONTROL Advanced Settings] para a métrica [!UICONTROL Revenue] no [!UICONTROL Goals & Settings]. O problema ocorria ao adicionar uma condição de dependência vinculada à meta principal; o back-end exigia incorretamente o privilégio do editor mesmo para usuários que já tinham permissões suficientes para criar e editar atividades. Como resultado, ocorreu uma falha ao salvar a atividade apesar da configuração válida. A atualização corrige a verificação de permissão para que os usuários com acesso apropriado possam adicionar com êxito as dependências da métrica Receita sem acionar um erro de recurso proibido. (TGT-54092)
* **Correção de um problema em que o botão Adicionar não se aplicava às imagens selecionadas.** Correção de um problema que impedia os clientes de adicionar determinadas imagens ao selecionar ou atualizar uma imagem no processo de criação da atividade. Quando os clientes pesquisavam ativos específicos, por exemplo, as imagens retornadas ao pesquisar por &quot;ipp&quot;, clicando no botão [!UICONTROL Add], não aplicavam a imagem selecionada e nenhuma modificação era criada. A seleção de outras imagens, como `Homepage-banner-1-moz.jpg`, continuou a funcionar conforme esperado. Essa atualização garante que todas as imagens válidas possam ser aplicadas de forma consistente na interface atualizada. (TGT-53610)
* **Correção de um problema em que a exclusão de uma condição de URL redefinia a configuração da métrica de meta.** Correção de um problema em que a remoção de uma única condição de URL na métrica [!UICONTROL Goal] fazia com que toda a configuração fosse redefinida na interface atualizada. Quando os clientes tentaram excluir uma condição de URL salva em [!UICONTROL Conversion] > [!UICONTROL Viewed a Page], o tipo de meta alternou inesperadamente para [!UICONTROL Viewed an Mbox] e todas as configurações definidas anteriormente foram removidas. Essa atualização garante que somente a condição de URL selecionada seja excluída e que todas as configurações de meta restantes permaneçam intactas. (TGT-53271)
* **Correção de um problema em que a pesquisa não pesquisava subpastas.** Correção de um problema em que a pesquisa por ofertas não retornava resultados de subpastas na interface atualizada. Os clientes só poderiam encontrar uma oferta se navegassem manualmente para a pasta em que ela estava armazenada, tornando o comportamento da pesquisa inconsistente com os recursos da API. A pesquisa agora é compatível com a pesquisa recursiva de pastas para que os clientes possam localizar ofertas sem precisar abrir cada pasta individualmente. (TGT-51954)

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
