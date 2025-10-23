---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 7d73870275c266055825c2fce90489ef82825fca
workflow-type: tm+mt
source-wordcount: '1700'
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

## [!DNL Target Standard/Premium] 25.10.1 (22 de outubro de 2025)

Esta versão inclui as seguintes atualizações e correções:

**Atividades**

+++ Ver detalhes
* **Solução de um problema de usabilidade na interface atualizada**. [!UICONTROL Observers] agora pode visualizar atividades usando a opção [!UICONTROL View Activity], exatamente como na interface do usuário herdada. (TGT-51741)
* **[!UICONTROL Observer]usuários agora podem exibir o conteúdo da atividade na interface atualizada.** Visibilidade restaurada para usuários com função de Observador na interface atualizada da Atividade. Anteriormente, os Observadores não conseguiam exibir modificações, ofertas e alterações de conteúdo — funcionalidade que estava disponível na interface herdada. (TGT-53785)
* **[!UICONTROL Approver]usuários agora podem editar metas da atividade sem erro de privilégio do editor.** Correção de um problema de permissão na interface de Criação de atividade que impedia os usuários em nível de Aprovador de salvar alterações nas configurações de meta avançadas. Os usuários afetados receberam um erro `403 Forbidden.Resource` que exigia privilégios de editor, apesar de terem acesso suficiente. (TGT-53819)

+++

**Públicos-alvo**

+++Ver detalhes
* **Seleção de vários públicos-alvo restaurada nos relatórios &quot;Somente esta atividade&quot;.** Correção de um problema na interface de Criação da Atividade que impedia os usuários de selecionar vários públicos na seção [!UICONTROL This activity only] em [!UICONTROL Goals & Settings]. (TGT-53283)
* **Os gráficos de relatórios com base no público-alvo agora exibem os dados de conversão corretamente.** Correção de um problema na guia [!UICONTROL Reports] que causava a falha de gráficos ao selecionar públicos não padrão. Enquanto dados e métricas de confiança estavam disponíveis, o gráfico visual mostrava apenas uma linha sólida, dificultando a análise. (TGT-53769)
* **A interface do usuário [!UICONTROL Targeting] agora indica claramente as regras de público-alvo excluídas.** Solução de um problema na seção [!UICONTROL Targeting] da interface de criação de atividade, na qual as regras de público-alvo definidas como [!UICONTROL Exclude] não eram exibidas claramente. Isso levou a confusão ao revisar a lógica de direcionamento, especialmente para públicos-alvo que excluem URLs específicos. (TGT-53809)
* **Valores de definição de público-alvo agora selecionáveis e copiáveis na guia [!UICONTROL Targeting].** Correção de um problema na interface de Criação de atividade que impedia os usuários de selecionar e copiar valores de regras de audiência na guia [!UICONTROL Targeting]. Essa funcionalidade estava disponível na interface herdada, mas ausente na interface atualizada. (TGT-53856)

+++

**Localização**

+++Ver detalhes
* **Corrigido o erro de tradução de &quot;quote&quot; no contexto do editor de páginas zh_CN.** Corrigido um erro de tradução contextual na localidade zh_CN, onde o termo &quot;quote&quot; foi traduzido incorretamente como &quot;报价&quot;, o que implica uma cotação de preço comercial. Na seção Tipografia > Estilo de cabeçalho > Cotação de bloco, o significado pretendido se refere a um elemento de formatação, o bloco de cotação, e não à precificação. (TGT-53841)
* **Erro de tradução corrigido de &quot;aspas removidas&quot; no contexto do editor de páginas zh_CN.** Correção de um erro de tradução na localidade zh_CN onde &quot;quote removed&quot; era renderizado incorretamente como &quot;移除了报价&quot;, implicando uma cotação de preço comercial. Na seção Tipografia > Estilo de cabeçalho > Cotação de bloco, o termo se refere a um elemento de formatação, o bloco de cotação, e não à precificação. (TGT-53843)
* **Corrigido o erro de tradução de &quot;quote reorganizado&quot; no contexto do editor de páginas zh_CN.** Correção de um erro de tradução contextual na localidade zh_CN, onde &quot;quote reorganize&quot; era traduzido incorretamente como &quot;重新排列了报价&quot;, implicando uma cotação de preço comercial. Na seção Tipografia > Estilo de cabeçalho > Cotação de bloco, o termo se refere a um elemento de formatação, o bloco de cotação, e não à precificação. (TGT-53844)
* **Corrigido o erro de tradução de &quot;aspas alteradas&quot; no contexto do editor de páginas zh_CN.** Corrigido um erro de tradução na localidade zh_CN onde &quot;quote changed&quot; foi renderizado incorretamente como &quot;更改了报价&quot;, sugerindo uma cotação de preço comercial. Na seção Tipografia > Estilo de cabeçalho > Cotação de bloco, o termo se refere a um elemento de formatação, o bloco de cotação, e não à precificação. (TGT-53845)

+++

**Recommendations**

+++Ver detalhes
* **As alterações do seletor de CSS das recomendações agora são salvas corretamente.** Correção de um problema na interface de Criação de Atividade que impedia os usuários de atualizar o seletor de CSS para posicionamentos de recomendação. Alterações revertidas após salvar, bloqueando atualizações para contêineres de direcionamento. (TGT-53835)
* **A seleção do evento de carregamento da página agora persiste nas modificações de recomendação.** Correção de um problema na interface de Criação de Atividade que impedia os usuários de salvar alterações ao alternar o tipo de evento de uma recomendação de [!UICONTROL View] para [!UICONTROL Page Load]. Embora a seleção tenha sido bem-sucedida, ela foi revertida depois de sair, bloqueando a publicação da atividade. (TGT-53957)

+++

**Relatórios**

+++Ver detalhes
* **&quot;[!UICONTROL Export order details to CSV]&quot; agora baixa dados completos.** Correção de um problema na interface do usuário [!UICONTROL Overview] atualizada que fazia com que a opção &quot;[!UICONTROL Export Order details to CSV]&quot; baixasse arquivos vazios, mesmo quando dados de relatório válidos estavam presentes. (TGT-53787)

+++

**Segurança**

+++Ver detalhes
* **Pré-filtro IMS adicionado para proteger endpoints GQL de exposição de dados entre organizações.** Correção de uma vulnerabilidade de segurança na guia Admin que afetava os pontos de extremidade GraphQL licenseGroups e targetProperties. O problema resultou do uso da API JIL com um token de cliente administrador que poderia ser explorado para acessar dados de produtos entre organizações. (TGT-53837)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes
* **A estabilidade da criação foi restaurada na interface de Criação de Atividade.** Correção de um problema intermitente na interface do VEC que causava a falha da criação e fazia com que os links se tornassem clicáveis inesperadamente, redirecionando os usuários para fora da página. (TGT-53153)
* **Edição restaurada para atividades salvas na interface de Criação de Atividade.** Correção de um problema que impedia os usuários de editar atividades após salvar modificações. As atividades afetadas permaneceram presas em &quot;[!UICONTROL Applying initial modifications]&quot;, bloqueando mais atualizações e ocultando o botão [!UICONTROL Cancel]. (TGT-53631)
* **O VEC não é mais interrompido em &quot;[!UICONTROL Applying initial modifications]&quot;.** Correção de um problema de desempenho no VEC que causava longos atrasos ao carregar experiências com um alto número de modificações. Os usuários afetados viram a interface travar em &quot;[!UICONTROL Applying initial modifications]&quot; por vários minutos, especialmente em cenários da Experiência B. (TGT-53727)
* **O VEC agora carrega modificações sem elementos raiz.**
Correção de um problema no VEC que causava a paralisação das experiências ao carregar modificações que não tinham um elemento raiz claro. Essas modificações fizeram com que a interface travasse indefinidamente em &quot;A[!UICONTROL pplying initial modifications]&quot;. (TGT-53799)
* **Salvar alterações nas atividades agora funciona conforme esperado.** Correção de um problema relacionado a permissões na Nova interface de Criação que impedia os usuários de salvar alterações ao editar metas e configurações avançadas em atividades. Os usuários afetados viam uma faixa de erros vermelha e uma mensagem &quot;Forbidden.Resource&quot;, apesar de terem acesso apropriado. (TGT-53816)
* A interface do **VEC agora preserva as modificações de experiência nas exibições.** Correção de vários problemas no VEC atualizado que afetavam o desenvolvimento da experiência. As modificações não persistiam corretamente, especialmente ao usar ofertas do HTML ou alternar entre exibições. (TGT-53825)
* **Todas as exibições agora são exibidas corretamente quando uma modificação abrange várias experiências.** Correção de um problema na interface de Criação de Atividade em que apenas um modo de exibição era mostrado quando uma modificação era aplicada em vários modos de exibição. A dica de ferramenta de focalização não listava todas as exibições associadas, mesmo que a modificação tivesse sido aplicada corretamente. (TGT-53827)
* **O VEC não é mais interrompido intermitentemente em &quot;[!UICONTROL Applying initial modifications]&quot;.** Correção de um problema intermitente no VEC em que as experiências falhavam ao carregar e permaneciam presas em &quot;[!UICONTROL Applying initial modifications]&quot;. Esse comportamento era inconsistente e, às vezes, acionava loops de redirecionamento ou exigia limpeza manual do cache. (TGT-53916)
* Não foi possível reproduzir o problema de carregamento do **VEC.** Investigamos um problema relatado em que o VEC permanecia preso em &quot;[!UICONTROL Applying initial modifications]&quot; ao editar atividades existentes. Suspeita-se que o comportamento esteja relacionado ao conteúdo do HTML sem um elemento primário. Continuaremos monitorando a recorrência e recomendaremos o uso de contêineres estruturados para ofertas do HTML para garantir a estabilidade. (TGT-53972)
* O modo **[!UICONTROL Design]no VEC não se comporta mais como o modo [!UICONTROL Browse] intermitentemente.** Correção de um problema na interface do usuário em que o modo [!UICONTROL Design] se comportava intermitentemente como o modo [!UICONTROL Browse], permitindo links `<a>` clicáveis e impedindo a seleção de elementos. Isso fazia com que a caixa de flutuação desaparecesse e bloqueasse os workflows de modificação. (TGT-53136)
* Os cliques no botão **no modo [!UICONTROL Composer] não acionam mais o redirecionamento de página.** Correção de um problema na interface do VEC atualizada em que um clique em um botão no modo [!UICONTROL Composer] causava um redirecionamento inesperado para a URL de destino do botão. Isso impedia que os usuários editassem elementos do call-to-action (CTA) e interrompeu o fluxo de trabalho de criação. (TGT-53137)
* **As atualizações de código de oferta em atividades de personalização automatizada agora são salvas sem erros.** Correção de um problema na Nova Interface de Criação que causava um erro &quot;[!UICONTROL Invalid user input]&quot; ao atualizar o código de oferta em atividades [!UICONTROL Automated Personalization]. O erro impedia que os usuários salvassem as alterações, mesmo quando a entrada era válida. (TGT-53586)
* O modo **[!UICONTROL Design]no VEC agora bloqueia a navegação por links para componentes editáveis.** Correção de um problema no VEC atualizado em que elementos clicáveis, como botões e links, acionavam o redirecionamento de página mesmo no modo [!UICONTROL Design]. Este comportamento imita o modo [!UICONTROL Browse] e impede que os usuários modifiquem os componentes principais. (TGT-53696)
* A métrica **&quot;[!UICONTROL Clicked an element]&quot; agora funciona sem redirecionamento ou erro.** Correção de um problema na Nova interface do usuário Criar que causava redirecionamentos inesperados e telas em branco ao selecionar a métrica de conversão &quot;[!UICONTROL Clicked an element]&quot;. Clicar em um botão durante a instalação acionou a navegação em vez de registrar o elemento, resultando em um erro &quot;[!UICONTROL element not found]&quot;. (TGT-53817)
* **As atividades existentes não ficam mais presas no loop de carregamento infinito durante a edição.** Correção de um problema na Nova interface do usuário para Criar, em que a edição de uma atividade existente no VEC fazia com que a página permanecesse presa em um loop de carregamento infinito. Esse problema não afetava as atividades recém-criadas e era acionado por modificações pré-existentes na página. (TGT-53913)
* **As páginas de atividade existentes com modificações agora são carregadas corretamente no VEC.** Correção de um problema no VEC atualizado que fazia com que as páginas permanecessem presas na fase de carregamento ao editar uma atividade existente com modificações salvas. Novas atividades carregadas sem problema, mas as atividades configuradas anteriormente não foram renderizadas. (TGT-53967)

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
