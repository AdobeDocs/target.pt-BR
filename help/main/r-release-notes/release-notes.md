---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 1a5c47277bfd5eb1c90887728540bbc3b0433d77
workflow-type: tm+mt
source-wordcount: '3800'
ht-degree: 9%

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

## [!DNL Target Standard/Premium] 25.8.2 (14 de agosto de 2025)

Esta versão do inclui as seguintes correções e atualizações:

**[!UICONTROL Activities]**

+++Ver detalhes
* **Correção de um problema de carregamento de atividade na [!DNL Target] interface atualizada**: correção de um problema na [!DNL Target] interface atualizada em que determinadas atividades não eram carregadas ao tentar editar. Esse problema fazia com que os clientes deixassem os usuários em uma tela de carregamento indefinida. Esse problema afetou várias atividades e foi relatado para ocorrer de forma inconsistente entre os clientes. Com essa correção, as atividades afetadas agora são carregadas corretamente, permitindo uma edição perfeita e reduzindo a interrupção dos workflows de atividades. (TGT-53209)
* **Correção de um erro de salvamento no processo de criação de atividade devido à `optionLocalId` validação**: correção de um problema no processo de criação de atividade que impedia os clientes de salvar alterações devido a um erro de validação de back-end: `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:` Esse problema ocorria ao modificar elementos específicos em uma atividade, resultando em uma falha na operação de salvamento. A correção garante que as referências do `optionLocalId` agora sejam validadas corretamente, permitindo que os clientes salvem as atividades sem encontrar esse erro. (TGT-53293)
* **Correção de uma falha no processo de criação de atividade causada por referências de opção inválidas ao alternar páginas**: correção de um problema no processo de criação de atividade que causava uma falha na interface do usuário após alternar páginas três vezes durante a edição. A falha foi acionada por referências de opção inválidas, resultando em erros de console, como &quot;Opção com localId &#39;7&#39; não encontrada&quot;. Com essa atualização, os clientes agora podem alternar entre páginas e aplicar modificações sem encontrar falhas ou interrupções do sistema. (TGT-53295)
* **Correção de um erro de salvamento no processo de criação de atividade causado por entradas de usuário inválidas ao editar experiências**: correção de um problema no processo de criação de atividade em que os clientes não conseguiam salvar as alterações em uma atividade devido a um erro de entrada de usuário inválido. O erro ocorria ao modificar experiências na interface atualizada, impedindo que as atualizações fossem confirmadas. A atividade agora pode ser salva com sucesso, permitindo que os clientes editem e publiquem sem interrupção. (TGT-53267)
* **Correção de um problema de carregamento no processo de criação de atividade que bloqueava a edição na interface atualizada**: correção de um problema no processo de criação de atividade em que os clientes não conseguiam editar atividades na interface atualizada devido a uma tela de carregamento contínuo. Agora, os clientes podem abrir e modificar atividades sem encontrar falhas de carregamento. (TGT-53415)
* **Correção de um problema de requisito de experiência no processo de criação de atividades para atividades AP na interface atualizada**: correção de um problema no processo de criação de atividades, no qual [!UICONTROL Automated Personalization] atividades (AP) exigiam dois locais em vez de duas experiências na interface atualizada. Esse comportamento bloqueou casos de uso em que os clientes configuravam um único local com várias ofertas, que eram compatíveis anteriormente. O requisito foi corrigido para corresponder à funcionalidade original, permitindo que os clientes continuem com atividades AP usando duas experiências, independentemente da contagem de localização. (TGT-53429)
* **Corrigido o comportamento do campo de elementos rastreados no modo de rastreamento de cliques para evitar entradas não salvas e melhorar a clareza**: corrigido um problema no processo de criação de atividades, em que o campo [!UICONTROL Tracked Element] no modo [!DNL Click Track] era editável, mas não mantinha o nome inserido, causando confusão para os clientes. O campo agora está desativado para impedir entradas não salvas e a nomeação de elementos selecionados foi esclarecida para melhorar a configuração da meta e a precisão do rastreamento.** (TGT-53458)
* **Correção de um problema no processo de criação de atividade que bloqueava a nomeação de componentes rastreados no modo [!UICONTROL Click Track]**: correção de um problema no processo de criação de atividade em que os clientes não conseguiam nomear componentes rastreados no modo [!UICONTROL Click Track]. Depois de inserir um nome, o campo parecia editável, mas não retinha a entrada, padronizando para rótulos genéricos como &quot;MY PRIMARY GOAL 0&quot; no modo de edição. O campo de elemento rastreado agora está desativado e o comportamento de nomenclatura foi esclarecido para melhorar a configuração da meta e a precisão do rastreamento. (TGT-51396)

+++

**Fragmentos de experiência (XFs)**

+++Ver detalhes
* **Correção de um problema no processo de criação de atividades que permitia a edição não intencional de fragmentos exportados pelo AEM pelo HTML**: correção de um problema no processo de criação de atividades que permitia aos clientes editar o HTML de [!DNL Experience Fragments] (XFs) exportado do [!DNL Adobe Experience Manager] (AEM) no [!DNL Target]. Esse comportamento não foi intencional, pois os XFs devem permanecer bloqueados para edição depois de publicados no AEM. A correção garante que a opção &quot;Editar HTML&quot; não esteja mais disponível para fragmentos exportados pelo AEM, preservando a integridade do conteúdo e o controle esperado. (TGT-53286)
* **Correção de um problema de visualização intermitente para conteúdo XF no processo de criação de atividade na interface do usuário atualizada**: correção de um problema no processo de criação de atividade em que o conteúdo XF falhava intermitentemente na renderização no modo de visualização na interface do usuário atualizada. Embora o conteúdo tenha sido entregue corretamente, a pré-visualização não era exibida de forma consistente, dificultando a validação da configuração da oferta para os clientes. As visualizações XF agora são carregadas de forma confiável, melhorando a confiança e a eficiência durante a configuração da atividade. (TGT-53318)

+++

**Modo de controle de qualidade**

+++Ver detalhes
* **Correção de um problema no processo de criação de atividade em que os espaços à esquerda nas URLs causavam links de controle de qualidade com falha**: correção de um problema no processo de criação de atividade em que os espaços à esquerda na URL da atividade não eram cortados corretamente ao salvar. Isso causava links de controle de qualidade inválidos e formatação incorreta no back-end. Após a atualização, os URLs agora são salvos corretamente, evitando links quebrados e melhorando a confiabilidade dos fluxos de trabalho de controle de qualidade para os clientes. (TGT-53427)

+++

**[!UICONTROL Recommendations]**

+++Ver detalhes
* **Correção de um problema na interface de pesquisa de catálogo em que a pesquisa avançada não fornecia sugestões**: correção de um problema na nova interface de usuário [!UICONTROL Catalog Search] em que o recurso [!UICONTROL Advanced Search] não fornecia sugestões. Os usuários precisavam inserir valores exatos com ortografia precisa, tornando a experiência de pesquisa complicada e sujeita a erros. Com essa correção, o [!UICONTROL Advanced Search] agora oferece sugestões relevantes à medida que os usuários digitam, melhorando a usabilidade e reduzindo o atrito na localização de produtos. (TGT-52008)
* **Solução de vários problemas de filtragem e interface de usuário para melhorar a capacidade de resposta e a interação com a entidade**: solução de vários problemas, incluindo capacidade insuficiente de resposta dos detalhes dos critérios em dispositivos de tela pequena, falta de resultados ao selecionar &quot;Todos os grupos de hosts&quot; no filtro Ambiente e incapacidade de interagir com entidades sem nome. Essas correções melhoram a usabilidade em tamanhos de tela, garantem uma filtragem precisa e permitem a interação total com todas as entidades do produto, melhorando a experiência geral para os usuários. (TGT-52992)
* **Correção de IDs de produtos ausentes na exibição detalhada do Recommendations durante a criação da atividade**: correção de um problema no processo de criação de atividades do [!DNL Recommendations], em que as IDs de produtos estavam ausentes na tela de detalhes do produto, dificultando aos clientes a cópia ou a referência às IDs de produtos durante fluxos de trabalho. As IDs de produto agora aparecem claramente na visualização de detalhes, melhorando a visibilidade e oferecendo suporte a um gerenciamento de produtos mais eficiente para os clientes. (TGT-51964)
* **Correção de um problema no processo de criação de atividade em que as mensagens do produto não eram exibidas na exibição de recomendações**: correção de um problema no processo de criação de atividade em que a coluna [!UICONTROL Message] na exibição [!DNL Recommendations] não exibia os dados do produto, mesmo que as mensagens estivessem presentes. Os clientes tinham que remover e adicionar novamente a coluna manualmente para revelar temporariamente o conteúdo, que muitas vezes desaparecia novamente ao rolar ou pesquisar. Essa atualização restaura a visibilidade consistente das mensagens do produto, melhorando a navegação no catálogo e os workflows de revisão. (TGT-52777)
* **Correção de um problema no processo de criação de atividade em que a seleção de &#39;Todos os grupos de hosts&#39; não retornava resultados na exibição de recomendações**: correção de um problema no processo de criação de atividade em que a seleção do ambiente &quot;Todos os grupos de hosts&quot; na exibição [!DNL Recommendations] não retornava resultados. Os clientes agora podem visualizar os dados do produto em todos os grupos de hosts conforme esperado, melhorando a visibilidade e a precisão do filtro durante a configuração da atividade. (TGT-53006)
* **Correção de um problema no processo de criação de atividade em que a alternância de promoção frontal não persistia após salvar**: correção de um problema no processo de criação de atividade em que a desabilitação da alternância de promoção frontal nas configurações de atividade não persistia após salvar. Os clientes que tentaram remover a promoção principal descobriram que o botão de alternância era reativado ao revisitar a atividade, impedindo a personalização adequada. Essa atualização permite que as alterações sejam salvas de forma confiável, dando aos clientes controle total sobre as configurações de promoção. (TGT-53215)
* **Correção de uma classificação inconsistente por [!UICONTROL Last Updated] coluna:** correção de um problema no processo de criação de atividade, em que a classificação do catálogo pela coluna [!UICONTROL Last updated] gerava resultados inconsistentes. Os clientes não conseguiam organizar de forma confiável os dados do produto com base nos carimbos de data e hora de atualização, dificultando a análise e o gerenciamento do catálogo. A classificação agora funciona conforme esperado, melhorando a precisão e a usabilidade na interface atualizada. (TGT-53116)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes
* **Correção do carregamento de atividades e de [!UICONTROL Cancel] problemas de botões no processo de criação de atividades**: correção de um problema no processo de criação de atividades em que determinadas atividades não eram carregadas, impossibilitando o acesso de clientes a modificações. Além disso, o botão [!UICONTROL Cancel] não respondia, impedindo os clientes de interromper o processo de carregamento ou sair do modo de edição. Essa correção garante que as atividades agora sejam carregadas de forma confiável, e que o botão [!UICONTROL Cancel] funcione conforme esperado, melhorando a estabilidade geral e a experiência do usuário no Visual Experience Composer. (VEC)(TGT-53218)
* **Correção de um problema de alternância de experiência na interface do VEC atualizada que bloqueava a edição e desabilitava o botão [!UICONTROL Cancel]**: correção de um problema na interface do VEC atualizada em que as modificações falhavam ao carregar ao alternar entre experiências em uma atividade de Direcionamento de Experiência (XT). Os clientes não puderam editar experiências além da que inseriram inicialmente, e o botão [!UICONTROL Cancel] estava ausente ou sem resposta. Essa correção garante que as modificações agora sejam carregadas corretamente em todas as experiências e que o botão [!UICONTROL Cancel] funcione de maneira confiável, mesmo sem a extensão Auxiliar, melhorando a edição de fluxos de trabalho e reduzindo a frustração. (TGT-53256)
* **Correção de um problema de tela branca ao alternar entre várias experiências no processo de criação de atividade**: correção de um problema em que a alternância entre várias experiências causava uma tela branca. Também foi corrigido um problema no processo de criação de atividade em que os clientes encontravam uma tela branca ao tentar modificar várias experiências em uma atividade. Esse problema ocorria após aplicar alterações em duas experiências e selecionar uma terceira experiência, impedindo mais edições. A atualização garante transições tranquilas entre experiências, permitindo que os clientes façam modificações sem interrupção. (TGT-53266)
* **Correção de um problema no VEC em que as alterações de código personalizado não eram salvas de forma confiável nas sessões de edição**: correção de um problema em que as modificações de código personalizado feitas no Visual Experience Composer (VEC) não eram salvas de forma confiável em uma única tentativa. Os clientes relataram que alterações, como atualizações de estilo ou edição do HTML, estavam ausentes intermitentemente do site e das URLs de controle de qualidade, mesmo após o uso dos botões [!UICONTROL Edit Content] e [!UICONTROL Save] final. Essa regressão foi resolvida, garantindo que todas as alterações no código personalizado persistam conforme esperado em todas as sessões de edição.** (TGT-53418)
* **Correção de `triggerViews` ausente na interface atualizada durante a criação da atividade**: correção de um problema no processo de criação da atividade em que `triggerViews` não aparecia na interface atualizada, mesmo que ela estivesse implementada corretamente na página. Isso afetou vários clientes e dificultou a validação de acionadores baseados em visualização durante a configuração da atividade. O `TriggerViews` agora é exibido conforme esperado, permitindo que os clientes concluam e testem suas configurações de forma confiável. (TGT-53239)
* **Correção de um problema de carregamento de exibição no processo de criação de atividade para páginas da Web específicas na interface do usuário atualizada**: correção de um problema no processo de criação de atividade em que as exibições não eram carregadas na interface do usuário atualizada para páginas da Web específicas, apesar de estarem corretamente implementadas e visíveis nas chamadas de entrega ou de interação. Isso afetou vários clientes e dificultou a validação do direcionamento baseado em visualização. As exibições agora são preenchidas de forma consistente em todas as páginas compatíveis, melhorando a confiabilidade durante a configuração da atividade. (TGT-53246)
* **Correção de um problema intermitente de carregamento de exibição no processo de criação de atividade na interface do usuário atualizada**: correção de um problema no processo de criação de atividade, em que as exibições falhavam intermitentemente ao aparecer na interface do usuário atualizada durante a edição da atividade. Embora o nome de exibição correto estivesse presente na carga da rede, ele não era reconhecido consistentemente na interface, afetando a capacidade dos clientes de configurar a personalização baseada na visualização. As exibições agora são exibidas de forma confiável, oferecendo suporte a fluxos de trabalho de configuração e validação mais suaves. (TGT-53223)
* **Correção de um problema no processo de criação de atividades em que os nomes das ações rastreadas não eram salvos na interface atualizada**: correção de um problema no processo de criação de atividades em que as métricas das ações rastreadas não podiam ser salvas na interface atualizada. Depois de nomear um elemento rastreado e salvar a atividade, o nome era redefinido para um rótulo padrão quando reaberto, causando confusão e interrompendo a configuração da meta. As ações rastreadas agora mantêm seus nomes atribuídos, permitindo que os clientes definam e gerenciem métricas de conversão com precisão. (TGT-53453)

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
