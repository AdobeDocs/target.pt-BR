---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 6ecc59588b51da505b8f567a7e87ccef0f375477
workflow-type: tm+mt
source-wordcount: '1959'
ht-degree: 15%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão e documentação detalhadas por meio do [!UICONTROL Experience League]. Estes são alguns destaques importantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

+++Ver detalhes
A equipe do [!DNL Target] está oferecendo um recurso temporário que permite alternar entre a interface atualizada do usuário do [!DNL Target] e a versão herdada usando um botão de alternância. Essa opção está disponível somente durante a fase final de implantação da interface.

![Alternância da versão da interface do usuário de destino](/help/main/r-release-notes/assets/toggle.png)

Quando a implantação for concluída, o botão de alternância será removido e todos os usuários farão a transição permanentemente para a interface atualizada. A [!DNL Adobe] recomenda um planejamento antecipado, pois esse recurso será eliminado em breve.

#### Linha do tempo de descontinuação

Devido aos problemas recentes identificados, relacionados principalmente a personalizações complexas de clientes, a equipe do [!DNL Target] ajustou a linha do tempo de desativação:

* **17 de junho de 2025**: todas as Organizações IMS foram habilitadas para a interface do usuário [!DNL Target] atualizada, para usuários específicos ou em toda a organização, para começar a testar a nova experiência.

* **30 de junho de 2025**: a [interface atualizada [!DNL Target] 4&rbrace; se tornou a experiência padrão para todas as organizações IMS que habilitaram a alternância de versão da interface do usuário.](/help/main/c-intro/understand-the-target-ui.md)

   * Os clientes que atualmente veem a interface herdada, por padrão, agora veem a interface atualizada ao fazer logon.
   * O botão de alternância da versão da interface do usuário permanece disponível até o final de julho, permitindo que os usuários alternem de volta, se necessário.

  >[!IMPORTANT]
  >
  > A [!DNL Adobe] recomenda o uso da interface atualizada do usuário do [!DNL Target]. Retorne à interface herdada somente se ocorrer um problema de bloqueador devido a [limitações do comportamento de alternância](#limitations).

* **15 de julho a 30 de julho de 2025**: o botão de alternância da versão da interface do usuário será desabilitado permanentemente em fases. As organizações IMS afetadas não podem mais reverter para a interface do usuário herdada.

   * As exceções são analisadas caso a caso.
   * Atrasos na desativação do botão de alternância são concedidos apenas brevemente (alguns dias), enquanto problemas de bloqueador são resolvidos.

Entre em contato com o [Atendimento ao cliente da Adobe](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md) se tiver dúvidas ou se antecipar problemas durante essa transição.

#### Limitações do comportamento de alternância da interface {#limitations}

As informações a seguir descrevem as limitações que você deve conhecer ao optar por usar a opção de versão:

* **Visibilidade das novas atividades**: as atividades criadas na interface atualizada não estarão visíveis se você voltar para a interface herdada.
* **Editar atividades existentes**: as alterações feitas nas atividades existentes (originalmente criadas na interface herdada) ao usar a interface atualizada são publicadas no seu site. No entanto, essas atualizações não estarão visíveis na interface herdada se você voltar; somente as últimas atualizações feitas na interface herdada aparecerão lá.
* **Consistência dos detalhes da atividade**: as alterações mais recentes, independentemente da interface do usuário usada, são refletidas em seu site ativo. No entanto, a interface herdada mostra apenas as alterações mais recentes feitas nessa versão. Essa situação pode causar confusão se as atividades editadas na interface atualizada forem diferentes do que você vê na interface herdada.

#### Mais recursos para saber mais sobre a interface atualizada

* [[!DNL Target] Perguntas frequentes sobre atualização da interface do usuário](/help/main/c-intro/updated-ui-faq.md): estas perguntas frequentes abordam perguntas comuns sobre a nova interface do usuário do [!DNL Target] e do [!UICONTROL Visual Experience Composer] (VEC), incluindo alterações na navegação, locais de recursos e substituição da versão temporária da interface do usuário. Seja você um profissional de marketing, desenvolvedor ou administrador, essas Perguntas frequentes ajudarão a fazer a transição descomplicada e a aproveitar ao máximo a interface atualizada.
* Notas de versão do [[!DNL Target Standard/Premium] 25.2.1 (17 de fevereiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para [!UICONTROL Activities], [!UICONTROL Recommendations] e o [!UICONTROL Visual Experience Composer] (VEC).
* Notas de versão do [[!DNL Target Standard/Premium] 25.1.1 (9 de janeiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para o [!UICONTROL Offers Library].
* [Compreender a [!DNL Target] Interface](/help/main/c-intro/understand-the-target-ui.md): fornece uma breve visão geral para ajudá-lo a se familiarizar com o [!DNL Target] e fornece links para informações mais detalhadas e instruções passo a passo.
* [[!UICONTROL Visual Experience Composer] alterações](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): a versão [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de fevereiro de 2015) introduz um [!UICONTROL Visual Experience Composer] (VEC) atualizado. Este artigo explica as diferenças entre as versões herdadas e atualizadas do VEC.
* [[!UICONTROL Visual Experience Composer] opções](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): este artigo explica a interface do usuário do VEC atualizada e suas opções.

+++

## [!DNL Target Standard/Premium] 25.8.1 (7 de agosto de 2025)

Essa versão inclui os seguintes aprimoramentos e correções:

**Atividades**

+++Ver detalhes
* Correção de vários problemas com a interface atualizada, incluindo erros ao excluir tipos de página devido ao espaçamento nos valores de entrada, atividade não confiável de cópia entre espaços de trabalho e regras de entrega de página com defeito em ambientes de controle de qualidade. (TGT-52703)
* Correção de um problema na interface atualizada do usuário [!DNL Target], em que os usuários com a função [!UICONTROL Editor] podiam acessar e tentar editar atividades ativas, que deveriam ser restritas. As telas lista de atividades e visão geral exibiam incorretamente as opções de edição para atividades ativas, resultando em possíveis alterações não intencionais. (TGT-53055)
* Correção de um problema na interface do usuário do [!UICONTROL Advanced Search] em que os operadores selecionados como &quot;o valor está presente&quot; ou &quot;o valor não está presente&quot; solicitavam aos usuários a inserção de um operando, que não deveria ser necessário para essas condições. (TGT-51961)
* Correção de um problema na interface atualizada em que as tentativas de copiar atividades do ambiente de preparo para o espaço de trabalho de produção falhavam consistentemente, mesmo em ambientes de sandbox. Os clientes encontraram várias mensagens de erro, incluindo &quot;Público-alvo anônimo já usado pela atividade&quot; e &quot;ID de público-alvo inválida&quot;, apesar de usar configurações válidas e ter permissões apropriadas no espaço de trabalho. (TGT-52394)

+++

**Fragmentos de experiência (XFs)**

+++Ver detalhes
* Correção de um problema em que o conteúdo do Fragmento de experiência (XF) não era renderizado na pré-visualização do [!UICONTROL Visual Experience Composer] (VEC), apesar de funcionar corretamente na entrega de conteúdo. (TGT-53318)

+++

**Localização**

+++Ver detalhes
* Correção de um problema de localização em que o botão &quot;Adicionar promoção&quot; na seção &quot;Promoções&quot; aparecia deslocalizado em vários ambientes de idioma no locatário de controle de qualidade. (TGT-53263)

+++

**Ofertas**

+++Ver detalhes
* Correção de um problema em que a edição de uma oferta existente do HTML por meio do Visual Experience Composer (VEC) fazia com que todas as modificações fossem removidas da entrega de conteúdo. As alterações aparecem esmaecidas na guia de modificação e não são refletidas nas visualizações de QA, apesar de serem aplicadas corretamente na interface herdada. (TGT-52863)
* Correção de um problema na interface do usuário atualizada do [!DNL Target], em que as modificações de oferta do HTML feitas no [!UICONTROL Visual Experience Composer] (VEC) não persistiam após navegar da guia [!UICONTROL Targeting] de volta para [!UICONTROL Experiences]. (TGT-52874)
* Correção de um problema na interface atualizada do usuário [!DNL Target] em que inserir uma oferta do HTML antes e outra depois do mesmo seletor causava a geração de localização incorreta. Quando os clientes retornaram da guia [!UICONTROL Targeting] para a guia [!UICONTROL Experience], apenas um seletor foi retido, resultando em modificações perdidas e na entrega de conteúdo com falha. Esse comportamento diferiu da interface herdada, que preservou corretamente ambas as modificações com identificadores de localização distintos. (TGT-52891)
* Correção de um problema na interface do usuário atualizada do [!DNL Target] em que clicar em uma oferta adicionada no painel [!UICONTROL Modifications] fazia com que o painel direito do [!UICONTROL Configuration] aparecesse e desaparecesse intermitentemente, dificultando a interação com as configurações de oferta. (TGT-53288)
* Correção de um problema em que as ofertas do HTML adicionadas a variações específicas de público-alvo em uma atividade não eram salvas de forma consistente ou exibidas na seção de modificação. Depois de alternar entre públicos durante a edição, as ofertas aplicadas anteriormente às vezes desapareciam ou não eram renderizadas, interrompendo a validação e atrasando a preparação da atividade. (TGT-53440)
* Correção de um problema em que copiar uma atividade que incluía ofertas resultava na criação de ofertas duplicadas na nova atividade. Esse comportamento causava desordem e confusão desnecessárias, principalmente ao mover atividades entre espaços de trabalho. A correção garante que as ofertas do [!DNL Target] sejam copiadas corretamente para o espaço de trabalho de destino sem duplicação, simplificando o gerenciamento de atividades e melhorando a eficiência do fluxo de trabalho. (TGT-53454)

+++

**Aplicativos de Página Única (SPAs)**

+++Ver detalhes
* Correção de um problema no VEC atualizado que impedia os clientes de aplicar modificações nas exibições de [!UICONTROL Single Page Application] (SPA). Embora as atividades criadas na interface antiga fossem compatíveis com o direcionamento específico à visualização, a nova interface não detectava ou permitia edições nessas visualizações, com os controles de troca de visualização aparecendo desativados. (TGT-52556)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes
* Correção de um problema em que as modificações feitas nas experiências no [!UICONTROL Visual Experience Composer] não eram visíveis ou apareciam de forma inconsistente na interface do usuário. (TGT-TGT-53381)
* Correção de um problema no VEC atualizado em que a seção [!UICONTROL Manage Content] não exibia o texto alternativo para miniaturas de experiência. Esse problema dificultava a identificação de documentos pelos usuários, especialmente quando os nomes de arquivo eram longos ou truncados. (TGT-52291)
* Correção de um erro em que os clientes encontravam erros de validação incorretos ao configurar regras do [!UICONTROL page delivery] em atividades do VEC. Especificamente, operadores como &quot;é igual a qualquer um de&quot; e &quot;não é igual a qualquer um de&quot; acionaram &quot;Entrada inválida para o tipo de operador&quot; ao inserir valores de texto, mesmo que o texto deva ser compatível. (TGT-52629)
* Correção de vários problemas que causavam comportamento inconsistente no painel [!UICONTROL Modifications] da interface atualizada ao selecionar ofertas usando o botão &quot;Selecionar uma oferta&quot;. Em vez de substituir a oferta existente, a interface do usuário adicionou uma duplicata e tentou interagir com qualquer oferta, resultando em erros de console, como `selectorNotFound`. Além disso, algumas ofertas não exibem o botão &quot;Selecionar uma oferta&quot;, mostrando apenas propriedades editáveis. (TGT-53321)
* Correção de um problema na interface do usuário atualizada do [!DNL Target], em que as alterações no código HTML feitas durante a configuração da atividade não persistiam em páginas de variação, mesmo que fossem salvas corretamente para grupos de controle. Apesar das várias tentativas e da recriação de testes sem agrupamentos de páginas, as páginas de variação falharam consistentemente ao reter as modificações, afetando a entrega de conteúdo e a validação de controle de qualidade. (TGT-53436)
* Correção de um problema no VEC atualizado em que o operador &quot;igual a qualquer um de&quot; nas regras de entrega da página não aceitava valores de entrada. Ao configurar parâmetros do cliente em todas as mboxes, selecionar esse operador resultava em um erro &quot;Entrada inválida&quot;, impedindo a criação da regra. (TGT-52623)

+++

**Espaços de trabalho**

+++Ver detalhes
* Fluxo de trabalho melhorado ao copiar atividades entre espaços de trabalho. As atividades de cópia entre espaços de trabalho resultavam anteriormente em erros de sincronização devido à falta de públicos-alvo e propriedades não atribuídas. Essa atualização apresenta um fluxo de trabalho mais inteligente e intuitivo que garante que as atividades copiadas sejam configuradas corretamente e estejam prontas para publicação. (TGT-47094)
* Correção de um problema em que os clientes não conseguiam copiar atividades entre espaços de trabalho devido a uma falha na mutação `copyActivityBatchOperations`. As tentativas de duplicar atividades resultaram em um erro de servidor (500) e uma carga de resposta nula. (TGT-52405)
* Correção de um problema em que as atividades não eram sincronizadas quando as ofertas referenciadas na configuração não estavam acessíveis no espaço de trabalho selecionado. Isso causava erros de publicação e deixava as atividades em estado de falha. (TGT-52535)
* Correção de vários problemas ao copiar atividades entre espaços de trabalho na interface atualizada do usuário [!DNL Target]. Os clientes encontraram erros relacionados ao acesso ao público-alvo, especialmente com atividades ativas, e validação de privilégios incorreta, mesmo quando o usuário tinha &quot;[!UICONTROL Approver]&quot; funções nos espaços de trabalho de origem e destino. (TGT-53002)
* Correção de um problema na interface do usuário atualizada em que copiar atividades no mesmo espaço de trabalho duplicava desnecessariamente ofertas e públicos associados. (TGT-53457)
* Correção de um problema para resolver casos em que os públicos-alvo ad-hoc (anônimos) não eram copiados corretamente entre espaços de trabalho não padrão ou entre espaços de trabalho não padrão e padrão. Embora as atualizações anteriores garantissem a duplicação adequada para cenários padrão para não padrão e do mesmo espaço de trabalho, esse aprimoramento se concentrou em preservar configurações de público-alvo combinadas que abrangem vários espaços de trabalho. A correção garante um comportamento consistente do público-alvo e um direcionamento preciso em todas as transições do espaço de trabalho. (TGT-53268)

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
