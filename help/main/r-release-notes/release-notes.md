---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f0536e466d59fc4e3cccd61c25b7fe7f48f03954
workflow-type: tm+mt
source-wordcount: '4858'
ht-degree: 7%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão detalhadas e documentação até [!UICONTROL Experience League]. Estes são alguns destaques importantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

Para obter mais informações, consulte [[!DNL Target] Perguntas frequentes sobre atualização da interface](/help/main/c-intro/updated-ui-faq.md).

## [!DNL Target Standard/Premium] 25.9.3 (30 de setembro de 2025)

Esta versão inclui os seguintes aprimoramentos e correções.

+++[!UICONTROL Audiences]

* **As regras de exclusão de público-alvo foram exibidas incorretamente como inclusão na interface do usuário [!DNL Target].** públicos-alvo configurados com regras de exclusão apareciam como incluídos ao editar o direcionamento em uma atividade. Embora a lógica de exclusão tenha sido aplicada corretamente durante a execução, a interface do usuário não refletia a regra com precisão, omitindo o rótulo &quot;excluindo&quot;. A interface do usuário do [!DNL Target] agora exibe corretamente as regras de exclusão nos fluxos de trabalho de configuração de público-alvo e direcionamento, garantindo clareza e consistência para a configuração da campanha. (TGT-53808)
* **A seção [!UICONTROL Targeting] não indicou que uma regra de público-alvo foi definida para exclusão.** públicos-alvo configurados com lógica de exclusão foram exibidos incorretamente como inclusão na seção [!UICONTROL Targeting] da interface de criação da atividade. Embora o back-end tenha aplicado corretamente a regra de exclusão, a interface do usuário não conseguiu representá-la visualmente, omitindo o rótulo &quot;Excluir&quot; e causando confusão durante a configuração da campanha. A seção [!UICONTROL Targeting] agora exibe claramente as regras de exclusão, garantindo a consistência entre a configuração de público e a visualização de direcionamento. (TGT-53809)

+++

+++Localização

* **Correção de uma inconsistência de terminologia na tradução do chinês simplificado de &quot;Exibição completa de detalhes&quot;.**
Anteriormente, o termo &quot;Detalhes&quot; era traduzido incorretamente como &quot;详情&quot; na localidade do chinês simplificado (zh_CN), violando as diretrizes de terminologia estabelecidas. Esse valor foi corrigido para &quot;详细信息&quot; para garantir a consistência com o termo base. (TGT-53741)

+++

+++[!UICONTROL Recommendations]

* **As caixas de recomendação foram difíceis de localizar e selecionar no VEC.** Depois de adicionar uma oferta do recommendations no (VEC), clicar na modificação no painel esquerdo não realçou nem rolou até a caixa de recomendação correspondente na página. Isso dificultava localizar e editar a oferta, especialmente quando oculta em seletores ou estilizada minimamente. Ao clicar em uma modificação de recomendação, agora o realça e rola corretamente para o elemento associado, melhorando a usabilidade e a eficiência de edição no processo de criação de atividade atualizado. (TGT-52571)
* **Os seletores de recomendação foram regravados incorretamente após salvar uma atividade.** Ao adicionar uma recomendação a um elemento no VEC, o seletor estava inicialmente correto, mas após salvar e reabrir a atividade, ele foi alterado para um seletor genérico. As tentativas de restaurar manualmente o seletor original resultaram em erros de validação. Os seletores de recomendação agora persistem com precisão após salvar, garantindo um direcionamento confiável e capacidade de edição no processo de criação de atividade atualizado. (TGT-53709)
* **Não foi possível editar o conteúdo dos critérios ao modificar uma atividade existente.** Ao editar uma atividade, a seção de conteúdo [!UICONTROL Criteria] aparecia desabilitada, com botões esmaecidos e sem resposta. Esse problema foi resolvido verificando se as configurações do [!UICONTROL Criteria] são totalmente editáveis durante as atualizações da atividade. Os clientes agora podem modificar o conteúdo do [!UICONTROL Criteria] sem precisar alternar seleções ou usar soluções alternativas, melhorando a flexibilidade e a usabilidade no processo de criação de atividades atualizado. (TGT-53812)
* **Não foi possível editar o critério em uma atividade.** As opções [!UICONTROL Edit Criteria] e [!UICONTROL Remove Criteria] foram desabilitadas ao acessar critérios de dentro de uma atividade. No entanto, os mesmos critérios podem ser editados com êxito por meio da guia [!UICONTROL Recommendations]. Os critérios agora podem ser totalmente editados tanto no fluxo de trabalho de edição da atividade quanto na guia [!UICONTROL Recommendations], garantindo uma experiência de edição consistente e eficiente. (TGT-53814)

+++

+++[!UICONTROL Reports]

* **Gerar ofertas ad-hoc em atividades A[!UICONTROL utomated Personalization] causou inconsistências de relatório.** O uso do recurso Gerar ofertas ad-hoc em [!UICONTROL Automated Personalization] atividades (AP) levou a relatórios imprecisos. Especificamente, as IDs de oferta foram reutilizadas em vários locais, fazendo com que os dados de relatório fossem atribuídos incorretamente ou substituídos. As ofertas ad-hoc agora são geradas com identificadores distintos por local, garantindo um rastreamento e relatórios precisos em todas as experiências configuradas. (TGT-53757)
* **Falha ao carregar os relatórios de atividade devido a um erro no JavaScript.** Os clientes encontraram uma mensagem de &quot;Algo deu errado&quot; ao acessar a guia [!UICONTROL Reports] para determinadas atividades. O erro foi causado por uma exceção do JavaScript: não é possível ler propriedades de indefinido (lendo &#39;indexOf&#39;), acionado durante a chamada do GraphQL `getAnalyticsReportSummary`. Agora os relatórios são carregados corretamente, e o tratamento de erros foi aprimorado para evitar falhas semelhantes no fluxo de trabalho atualizado de criação de atividades. (TGT-53797)
* **Os relatórios falharam após interagirem com a barra de rolagem.** Clicar na barra de rolagem na guia [!UICONTROL Reports] causou uma falha na página, acompanhada por um erro de JavaScript:
  `SyntaxError: Failed to execute 'querySelector' on 'Element': '[data-key="a-currentcopy"hiretalent""]' is not a valid selector.` Agora os relatórios são carregados e rolados corretamente sem erros ou falhas. (TGT-53828)
* **Os relatórios não exibiram a métrica primária.** A métrica primária, configurada como uma métrica de conversão usando uma mbox, estava ausente nos relatórios de atividades. A pesquisa por nome de métrica ou nome de mbox não produziu resultados, impedindo a visibilidade dos principais dados de desempenho. As métricas primárias agora aparecem corretamente na guia [!UICONTROL Reports], garantindo um rastreamento e análise precisos do desempenho da campanha. (TGT-53773)
* **A guia [!UICONTROL Reports] na interface atualizada falhou ao interagir com a barra de rolagem horizontal.** A exibição [!UICONTROL Reports] falhou intermitentemente com um erro &quot;Algo deu errado&quot; ao usar a barra de rolagem horizontal para acessar métricas fora da exibição. A barra de rolagem agora funciona de forma confiável, permitindo que os clientes visualizem e analisem todas as métricas sem precisar de soluções alternativas, como reduzir ou usar a rolagem shift. (TGT-53824)

+++

+++[!UICONTROL Visual Experience Composer] (VEC)

* **Clicar em navegações estruturais no VEC não exibia de maneira consistente o menu de edição.**
Ao selecionar elementos do HTML por meio da navegação estrutural no (VEC), o menu de edição não era exibido ou desaparecia rapidamente, o que tornava a seleção de elementos não confiável. O menu de edição agora é exibido de forma consistente ao navegar por navegações estruturais, melhorando o fluxo de trabalho de seleção de elemento no processo de criação de atividade atualizado. (TGT-52873)
* **O menu de contexto falhou intermitentemente ao aparecer no VEC.** O menu de contexto na interface do VEC atualizada não era exibido de forma consistente ao clicar em elementos, dificultando o acesso às opções de edição. O menu de contexto agora é exibido de forma confiável a partir da seleção de elementos, melhorando o fluxo de trabalho de edição e a usabilidade geral no processo de criação de atividades atualizado. (TGT-53015)
* **Falha ao exibir o menu de contexto para determinados elementos no VEC.** O menu de contexto não foi exibido ao selecionar elementos específicos no VEC atualizado, dificultando a aplicação de modificações. O menu de contexto agora é exibido de forma consistente para todos os elementos compatíveis, melhorando a confiabilidade e a usabilidade da experiência de edição no fluxo de trabalho de criação de atividade atualizado. (TGT-53248)
* **O menu de contexto desapareceu no primeiro clique ao usar navegações estruturais no VEC.** Selecionar um elemento pai por meio da navegação estrutural no VEC fez com que o menu de contexto aparecesse brevemente e depois desaparecesse, dificultando o acesso às opções de edição. O menu de contexto agora permanece visível e funcional ao navegar pelos elementos por navegações estruturais, melhorando a confiabilidade do fluxo de trabalho de seleção de elementos no processo de criação de atividades atualizado. (TGT-53424)
* **O menu de contexto não foi exibido para elementos de nível superior no VEC.** A seleção de elementos de nível superior, como `<div>` ou `<main>` marcas, por meio da navegação estrutural no VEC não acionou o menu de contexto, impedindo mais ações de edição. O menu de contexto agora é exibido de forma consistente para todos os elementos compatíveis, incluindo contêineres de nível superior, melhorando a flexibilidade e a usabilidade do fluxo de trabalho de criação da atividade. (TGT-53770)
* **Os elementos em uma página específica não eram editáveis no VEC.** Determinados elementos na página não puderam ser selecionados ou editados no VEC atualizado. Esse problema foi isolado àquela página e não afetou outras páginas dentro da mesma conta. Todos os elementos na página agora podem ser selecionados e editados conforme esperado, restaurando a funcionalidade completa no fluxo de trabalho de criação da atividade. (TGT-53353)
* **Fluxo de trabalho melhorado ao exibir elementos secundários durante a seleção de elementos no VEC.** Para melhorar a usabilidade e a precisão durante a criação da atividade, o VEC agora exibe elementos filho ao passar o mouse sobre ou selecionar um elemento HTML pai. Esse aprimoramento permite que os clientes entendam melhor a estrutura da página e façam modificações mais precisas, simplificando o fluxo de trabalho de edição na interface atualizada. (TGT-53416)
* **Não foi possível editar elementos em atividades existentes usando a barra de modificação.** Ao editar atividades criadas anteriormente, a barra de modificação não era ativada para determinados elementos na página, impedindo atualizações. Esse problema foi observado principalmente em atividades modificadas e foi difícil de reproduzir nas recém-criadas. A barra de modificação agora é exibida de forma consistente e permite a edição de todos os elementos compatíveis, melhorando a confiabilidade e a usabilidade no fluxo de trabalho de criação de atividade atualizado. (TGT-53013)

+++

+++[!UICONTROL Workspaces]

* **A clonagem de uma atividade para um espaço de trabalho diferente disparou um erro de &quot;Entrada de Usuário Inválida&quot;.** A tentativa de clonar uma atividade de um espaço de trabalho para outro resultou em um erro: &quot;InvalidProperty.Json - Nome de propriedade &#39;content&#39; não reconhecido.&quot; Esse problema era causado pelo manuseio inadequado de metadados de atividade durante o processo de clonagem. Agora, as atividades podem ser clonadas com êxito entre espaços de trabalho sem acionar erros de validação, garantindo workflows de implantação de atividades mais suaves. (TGT-53731 e TGT-53736)

+++

## [!DNL Target Standard/Premium] 25.9.2 (22 de setembro de 2025)

Essa versão inclui as seguintes correções e aprimoramentos:

**[!UICONTROL Audiences]**

+++Ver detalhes
* **Correção de um problema em que as atividades não podiam ser copiadas devido a IDs de público-alvo inválidas.** Os clientes que tentam copiar atividades no processo de criação de atividade atualizado encontraram um erro causado por IDs de público-alvo inválidas (por exemplo, -1752722444307). Esse problema de validação de backend impedia a duplicação de atividades no mesmo espaço de trabalho. Esse problema foi resolvido e agora as atividades podem ser copiadas com êxito sem erros relacionados ao público-alvo. (TGT-53717)
* **Correção de um problema em que erros de entrada de usuário inválidos apareciam em públicos somente atividade nas atividades [!UICONTROL Automated Personalization] do modal [!UICONTROL Manage Content].** Clientes encontraram erros de entrada de usuário inválidos ao configurar públicos somente atividade no modal [!UICONTROL &#x200B; Manage Content] para atividades de AP. Esse problema ocorreu apesar de os públicos-alvo serem usados anteriormente com sucesso. As configurações de público-alvo combinadas agora são salvas corretamente sem acionar erros de validação. (TGT-53749)

+++

**Documentação**

+++Ver detalhes
* **As páginas de documentação do Web SDK específicas do Target foram movidas para o repositório do Adobe Target.** Como parte da reestruturação da documentação do Web SDK, o conteúdo específico de [!DNL Target] foi migrado dos documentos gerais do Web SDK para o [!DNL Adobe Target] [Guia do desenvolvedor](https://experienceleague.adobe.com/en/docs/target-dev/developer/a4t/overview-a4t?lang=en){target=_blank}. Essa alteração melhora a descoberta de conteúdo e garante que a orientação específica da solução seja mantida pela equipe apropriada do produto. (TGT-53374)

+++

**[!UICONTROL Offer Decisions]**

+++Ver detalhes
* **A opção Offer Decision agora está consistentemente visível durante a criação da atividade inicial.** Correção de um problema na interface do usuário atualizada em que a opção [!UICONTROL Offer Decision] não era exibida durante o primeiro fluxo de criação das atividades A/B, principalmente quando acessada no modo incógnito em locatários com as Decisões de oferta habilitadas. A opção só apareceu depois de navegar até a etapa [!UICONTROL Targeting] e voltar para [!UICONTROL Experiences]. Essa correção garante que a opção [!UICONTROL Offer Decision] esteja imediatamente disponível durante a configuração inicial, melhorando a usabilidade e reduzindo a confusão. (TGT-51888)

+++

**[!UICONTROL Offers]**

+++Ver detalhes
* **Correção de um problema em que as ofertas de redirecionamento não incluíam `redirectOptions` na carga quando `includeContent=true`.** Clientes recuperando ofertas de redirecionamento com `includeContent=true ` não tinham o campo `redirectOptions` na carga da resposta. Essa inconsistência afetou os workflows, como cópia de oferta e criação de atividade. As ofertas de redirecionamento agora incluem `redirectOptions` corretamente quando o conteúdo é solicitado. (TGT-53737)

+++

**[!DNL Recommendations]**

+++Ver detalhes
* **Rastreamento de cliques restaurado para [!UICONTROL Recommendations] atividades criadas na interface atualizada.** Solução de um problema em que as atividades [!UICONTROL Recommendations] criadas na interface atualizada não registravam o rastreamento de cliques, resultando em zero conversões relatadas. As atividades criadas na interface herdada rastrearam os cliques corretamente e relataram conversões conforme esperado. Essa correção garante que as atividades do Recommendations criadas na interface atualizada agora incluam os atributos de rastreamento corretos, restaurando o relatório de conversão e o alinhamento com as métricas do A4T. (TGT-53287)
* **Rastreamento de cliques restaurado para atividades de Recomendação.** Solução de um problema em que as atividades [!UICONTROL Recommendations] criadas na interface atualizada não registravam o rastreamento de cliques, resultando em zero conversões relatadas. A interface herdada aplicou corretamente uma ID de rastreamento (`at-track-click`) ao conteúdo [!UICONTROL Recommendations], enquanto a interface atualizada inseriu por engano um espaço reservado (`__recsClickTrackIdPlaceholder__`), impedindo o rastreamento de back-end. Essa correção garante que o conteúdo do [!DNL Recommendations] agora inclua a ID de rastreamento correta, restaurando o relatório de conversão e o alinhamento com as métricas do A4T. (TGT-53496)
* **Falha resolvida no editor de coleção na interface atualizada.** Correção de um problema na interface do VEC ([!UICONTROL Visual Experience Composer]) atualizada, em que abrir uma coleção no painel Editor causava uma falha da página com um TypeError: não é possível ler propriedades de indefinido (lendo &#39;customLocale&#39;). Este erro ocorreu em vários tipos de atividades, incluindo [!UICONTROL Recommendations] e testes A/B. (TGT-53703)
* **Opção para remover a coleção selecionada restaurada no VEC.** Correção de um problema no VEC em que os usuários só podiam substituir uma coleção selecionada em uma atividade [!UICONTROL Recommendations], mas não podiam removê-la totalmente. Essa limitação bloqueou casos de uso que exigem uma remoção limpa da coleção sem substituição. Essa correção apresenta uma opção clara para remover a coleção selecionada, permitindo maior flexibilidade na configuração da atividade e alinhamento com o comportamento da interface herdada. (TGT-53652)
* **As coleções de critérios personalizados agora são exibidas corretamente na interface do usuário do [!UICONTROL Recommendations].** Correção de um problema na interface do Recommendations em que as coleções criadas com o uso de critérios personalizados não exibiam os resultados do produto. Embora as coleções padrão baseadas em atributos funcionassem como esperado, as que usam filtros personalizados retornavam &quot;Nenhum resultado encontrado&quot; apesar das correspondências de catálogo válidas. Essa correção garante que as coleções que usam atributos personalizados agora sejam preenchidas corretamente na guia [!UICONTROL Product], restaurando a funcionalidade completa para fluxos de trabalho de recomendações personalizadas. (TGT-53653)
* **Correção de um problema em que as coleções não exibiam produtos ao abrir a página [!UICONTROL Products] pela primeira vez.** clientes que acessam coleções na seção [!UICONTROL Recommendations] obtiveram resultados vazios do produto ao abrir a página [!UICONTROL Products] pela primeira vez. Esse problema era causado por um erro de backend na consulta do GraphQL, que não carregava dados do produto para coleções com critérios personalizados. O problema foi resolvido e os produtos agora são exibidos corretamente sem a necessidade de alternância de ambiente. (TGT-53694)
* **Correção de um problema em que as coleções não podiam ser removidas em atividades [!UICONTROL Recommendations] baseadas em formulário.** Clientes criando [!UICONTROL Recommendations] atividades usando [!UICONTROL Form-Based Experience Composer] não puderam desmarcar uma coleção selecionada anteriormente. A interface exigia que uma coleção fosse selecionada antes de salvar, impedindo que os usuários revertessem para &quot;Todas as coleções&quot;. Esse comportamento foi atualizado para corresponder à funcionalidade do VEC, permitindo que os clientes salvem sem uma coleção selecionada e padronizando para &quot;Todas as coleções&quot;, conforme esperado. (TGT-53708)
* **Correção de um problema em que as promoções não podiam ser definidas pelo atributo devido à ausência de valores de regras de filtragem ou coleção.** Clientes configurando promoções por atributo no processo de criação de atividade encontraram um erro informando que uma promoção não tinha uma ID de coleção ou valores de regra de filtragem. Esse problema de validação bloqueava a progressão mesmo quando a configuração parecia concluída. Agora, as promoções podem ser salvas com sucesso quando configuradas por atributo. (TGT-53750)
* **Correção de um problema em que não era possível salvar atividades devido a nomes de experiência duplicados.** Os clientes encontraram um erro de entrada de usuário inválido ao salvar atividades que incluíam combinações específicas de critérios e designs. O erro foi acionado por nomes de experiência duplicados, mesmo quando a configuração parecia válida. Atividades com configurações distintas agora podem ser salvas sem conflitos de nomenclatura. (TGT-53805)
* **Correção de um problema em que a validação permanecia inválida para promoções configuradas por atributo.** Os clientes encontraram erros de validação persistentes ao configurar promoções por atributo no processo de criação de atividade, mesmo quando todos os campos obrigatórios estavam preenchidos corretamente. Esse problema foi causado pela lógica de validação incorreta no fluxo de trabalho [!UICONTROL Recommendations]. As promoções baseadas em atributos agora são validadas e salvas conforme esperado. (TGT-53811)
* **Correção de um problema em que a aplicação de uma promoção a uma atividade [!UICONTROL Recommendations] em tempo real gerava um erro.** Clientes encontraram o erro &quot;Uma promoção não tem uma ID de coleção ou valores de regra de filtragem&quot; ao tentar aplicar uma promoção principal a uma atividade [!UICONTROL Recommendations] ativa, mesmo depois de fornecer detalhes de configuração válidos. As promoções agora podem ser aplicadas com sucesso a atividades ativas sem acionar erros de validação, garantindo uma experiência mais suave na interface atualizada de criação de atividades. (TGT-53738)
* **Correção de um problema em que os produtos não estavam visíveis em coleções na interface do usuário [!UICONTROL Recommendations].** Clientes de um único locatário relataram que as listas de produtos não foram carregadas ao exibir determinadas coleções na seção [!UICONTROL Recommendations] da Nova interface do usuário. O problema foi resolvido temporariamente ao alternar ambientes, mas essa solução alternativa resultou em uma experiência do usuário ruim. As entidades do produto agora são carregadas de forma consistente sem exigir alternância de ambiente. (TGT-53783)
* **Correção de um problema em que os critérios e os designs não eram exibidos em uma linha na interface de criação de atividade.** Anteriormente, os critérios e designs no processo de criação da atividade eram mostrados em um formato compactado, dificultando para os clientes visualizar e gerenciar itens individuais. Cada critério e design agora aparecem em sua própria linha, melhorando a legibilidade e a usabilidade na interface atualizada. (TGT-53818)

+++

**Relatórios**

+++Ver detalhes
* A métrica **[!UICONTROL Total Revenue]agora está incluída nas exportações CSV dos relatórios de atividades.** Correção de um problema na interface atualizada do usuário do [!UICONTROL Overview] em que a receita total era exibida corretamente na exibição do relatório de atividades, mas estava ausente na exportação de CSV, mostrando como $0. Essa discrepância impedia que os usuários dependessem de dados exportados para análises e relatórios offline. (TGT-53325)
* A métrica **[!UICONTROL Total Sales]agora está incluída nas exportações CSV dos relatórios de atividades.** Correção de um problema na interface atualizada em que a métrica [!UICONTROL Total Sales] aparecia corretamente na exibição do relatório de atividades, mas estava ausente na exportação de CSV. Essa discrepância impedia que os usuários acessassem dados completos de desempenho nos relatórios baixados. Essa correção garante que os valores [!UICONTROL Total Sales] sejam incluídos com precisão nas exportações de CSV, restaurando a consistência entre os relatórios no aplicativo e a análise offline. (TGT-53330)
* **Mensagens de erro aprimoradas para [!UICONTROL Graph View] quando as métricas não estão habilitadas.** Correção de um problema no VEC em que [!UICONTROL Graph View] exibia uma mensagem genérica de &quot;Algo deu errado&quot; quando uma métrica solicitada não estava habilitada no conjunto de relatórios [!DNL Analytics] associado. Esse problema foi acionado por um erro `not_enabled_metric` na resposta do GraphQL de back-end. Essa correção substitui o erro vago por uma mensagem mais informativa que ajuda os usuários a identificar problemas de configuração no [!DNL Analytics], reduzindo a confusão e os escalonamentos de suporte desnecessários. (TGT-53577)
* **Correção de um problema em que a duração do relatório excedia o limite suportado de 90 dias.** Clientes usando o filtro &quot;[!UICONTROL Last X Days]&quot; na seção [!UICONTROL Reports] puderam selecionar durações superiores a 90 dias, o que pode levar a problemas de desempenho e dados incompletos. O filtro foi atualizado para aplicar um intervalo máximo de 90 dias, garantindo relatórios consistentes e confiáveis. (TGT-53795)
* **Correção de um problema em que os relatórios CSV de desempenho eram gerados usando o ambiente padrão em vez do ambiente selecionado.** Anteriormente, quando os clientes alteravam o ambiente nas configurações do relatório e geravam um relatório de desempenho, o CSV resultante continha dados do ambiente padrão em vez do ambiente selecionado.  A interface agora passa corretamente o parâmetro `environmentId`, garantindo que o relatório reflita o ambiente escolhido. Além disso, o tratamento de erros foi aprimorado. Se ocorrerem erros de GraphQL durante a geração de CSV, a interface do usuário agora exibirá uma mensagem de erro clara, em vez de produzir um arquivo CSV vazio. (TGT-53064)
* **Correção de um problema em que os relatórios do Analytics for Target (A4T) não exibiam dados em [!UICONTROL Graph View].** clientes que usam o [!DNL Target] com integração A4T encontraram um erro &quot;Algo deu errado&quot; ao alternar para o Modo de Exibição de Gráfico na guia Relatórios das atividades de teste A/B. Embora o [!UICONTROL Table View] tenha sido carregado corretamente, o [!UICONTROL Graph View] não pôde renderizar tendências de métrica no intervalo de tempo selecionado. O [!UICONTROL Graph View] agora exibe dados de desempenho conforme esperado para todas as métricas suportadas, melhorando a visibilidade e a precisão dos relatórios na interface atualizada. (TGT-53573)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes
* **Os metadados do elemento agora estão visíveis ao passar o mouse no menu de navegação estrutural.** Melhoria do menu de navegação estrutural no VEC para mostrar detalhes adicionais do elemento, como ID, classe e nome, ao passar o mouse sobre um item. Esse aprimoramento ajuda os usuários a identificar e diferenciar elementos com mais facilidade durante a configuração da atividade. (TGT-53409)
* **A navegação estrutural focalizada agora destaca o elemento correspondente no VEC.** Melhorou o [!UICONTROL Visual Experience Composer] para realçar o elemento correspondente no editor ao passar o mouse sobre os itens no menu de navegação estrutural. O tipo de elemento também é exibido, como container, texto em negrito ou botão. Esse comportamento se aplica a elementos irmãos e exclui tipos não compatíveis, como o SVG, com base na lista de validação. (TGT-53411)
* **Alerta de alterações não salvas restaurado em fluxos de trabalho de modificação do VEC.** Correção de um problema no VEC em que os usuários não eram mais notificados sobre alterações não salvas em modificações de código personalizado. Diferentemente da interface herdada, a nova experiência não tinha prompts ao sair ou fechar o editor de personalização, o que levou à perda acidental de progresso. Essa correção restaura os alertas para todos os tipos de modificação, incluindo o código personalizado, e garante que os usuários sejam avisados antes de sair sem salvar. (TGT-53435).
* **As alterações no código personalizado agora persistem durante a atualização da página no VEC.** Correção de um problema no VEC em que as modificações de código personalizadas eram perdidas durante as atualizações do site. Esse problema ocorria em páginas com vários recarregamentos, fazendo com que o editor redefinisse e revertesse as alterações não salvas. A correção garante que as edições de código personalizadas permaneçam intactas, mesmo que a página seja recarregada durante a edição, evitando a perda acidental de progresso. (TTGT-53501)
* **Problema de logon resolvido para acesso ao site no VEC.** Correção de um problema em que os usuários não conseguiam fazer logon em seus sites ao acessá-los pelo VEC. O fluxo de logon redirecionava os usuários repetidamente para a página de logon, impedindo a configuração e a pré-visualização da atividade. Essa correção garante que o VEC não interfira mais no comportamento de logon, restaurando o acesso esperado para usuários autenticados. (TGT-53524)
* **Problema de duplicações de cookies resolvido na extensão do VEC Helper.** Correção de um problema em que a extensão [!UICONTROL Adobe Experience Cloud Visual Editing Helper] duplicava o cookie `at_qa_mode` durante o controle de qualidade por meio de links de visualização. Ao alternar manualmente os índices de visualização, vários cookies foram criados com valores conflitantes entre os domínios, impedindo que os testadores alternassem variantes de forma confiável. Esse comportamento foi observado mesmo fora da interface do usuário do Target e afetou as contas internas e das contas do cliente. Essa correção garante a manipulação consistente de cookies, evitando entradas duplicadas e alinhando o escopo do domínio, permitindo a alternância de variante sem interrupção, sem a necessidade de limpeza manual de cookies. (TGT-53579)
* **Correção de um problema em que clicar em elementos em uma determinada página inicial causava vazamentos de memória.** Os clientes que criaram atividades nesta página inicial experimentaram vazamentos de memória ao interagirem com elementos da página. O problema estava vinculado a avisos de console excessivos e aumento do uso de memória em subquadros, particularmente relacionados a atributos srcset malformados. O uso de memória agora permanece estável durante a interação. (TGT-53761)
* **Correção de um problema em que o VEC falhava e exibia uma tela em branco ao carregar determinadas atividades.** Clientes de um locatário específico relataram que o editor falhou ao carregar atividades específicas. O VEC permaneceu preso na &quot;Aplicação de modificações iniciais&quot; antes de travar e mostrar uma tela em branco. O VEC agora carrega atividades afetadas sem erros no processo de criação de atividades atualizado. (TGT-52932)
* **Correção de um problema em que o painel [!UICONTROL Manage Content] nas atividades [!UICONTROL Automated Personalization] exibia rótulos de localização inconsistentes.** Clientes relataram que o painel [!UICONTROL Manage Content] mostrou números de localização incompatíveis nas guias [!UICONTROL Experiences] e [!UICONTROL Offers]. (por exemplo, Local 2 e Local 4 em Experiências, e Local 1 e Local 2 em Oferta) mesmo quando apenas dois locais foram configurados. Os rótulos de localização agora são consistentes e mapeados com precisão para modificações, melhorando a clareza e a usabilidade no processo de criação da atividade. (TGT-52934)
* **Correção de um problema em que as modificações no VEC eram perdidas após salvar.** Clientes relataram que, após salvar uma modificação no VEC, a página atualizaria e reverteria a alteração para sua versão anterior. Esse problema fazia com que as atualizações mais recentes fossem perdidas, a menos que toda a atividade fosse salva imediatamente. As modificações agora persistem corretamente após salvar e o editor não reverte mais as alterações inesperadamente, garantindo uma experiência confiável no fluxo de trabalho de criação da atividade. (TGT-53500)
* **Seleção de elemento aprimorada no VEC exibindo o tipo de elemento ao passar o mouse e a seleção.** Para melhorar a usabilidade durante a criação da atividade, o VEC agora decora os elementos do HTML com seu tipo quando focalizados ou selecionados. Esse aprimoramento ajuda os clientes a identificar e selecionar os elementos corretos com mais facilidade. Os elementos selecionados são realçados com uma cor distinta, e os elementos focalizados são contornados em azul. O tipo de elemento também é exibido, fornecendo um contexto mais claro durante a edição. (TGT-53502)

+++

## Atualizações de sequência de dados (19 de setembro de 2025)

A combinação da ID da sequência de dados e da sandbox deve ser exclusiva para [!DNL Adobe Target] conexões de destino.

Atualização da lógica de validação para conexões de destino [!DNL Target] para impor que a combinação da ID da sequência de dados e do nome da sandbox seja exclusiva em uma Organização IMS. Isso significa:

* O mesmo par de ID de fluxo de dados + nome de sandbox não pode ser reutilizado em várias conexões de destino [!DNL Target].
* A mesma ID de fluxo de dados pode ser usada para conexões diferentes somente se estiverem configuradas em sandboxes diferentes.
* Essa regra se aplica a todas as seleções de sequência de dados, incluindo quando &quot;Nenhum&quot; é selecionado.

Essa atualização garante uma configuração consistente e evita conflitos em ambientes de várias sandboxes. Para obter mais informações, consulte [conexão com o Adobe Target](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank} no guia *Destinos do Experience Platform*.

## [!DNL Target Standard/Premium] 25.9.1 (5 de setembro de 2025)

Esta versão inclui as seguintes atualizações e correções:

**[!UICONTROL Experience Fragments]**

+++Ver detalhes
* **Atribuição de usuário aprimorada para [!UICONTROL AEM Experience Fragment] ofertas.** Solução de um problema no VEC em que o campo &quot;[!UICONTROL Last updated]&quot; de [!UICONTROL AEM Experience Fragment] (XF) oferece uma ID de Código exibida incorretamente em vez do nome de usuário. Essa discrepância ocorreu durante a seleção da oferta na interface atualizada, criando inconsistência com a interface herdada e as ofertas do HTML, que mostravam corretamente o nome do último editor. Essa correção garante uma atribuição consistente do usuário em todos os tipos de oferta, melhorando a transparência e o alinhamento com o comportamento esperado. (TGT-52880 e TGT-52898)

+++

**Offer Decisioning**

+++Ver detalhes
* **Erro do Offer Decision resolvido para ofertas ODE.** Correção de um problema em que as ofertas de Mecanismo do Offer Decision (ODE) inseridas por meio de [!DNL Target] retornavam um erro 400 devido à ausência de metadados de formato. A mensagem de erro indicou que o tipo MIME era nulo, impedindo o processamento bem-sucedido de decisões de oferta. Essa correção garante o manuseio adequado de metadados de oferta, restaurando a funcionalidade para a entrega de conteúdo personalizado e permitindo a execução ininterrupta de campanhas de marketing. (TGT-53635)
* **Problema de renderização de oferta ODS resolvido.** Solução de um problema em que as ofertas do [!DNL Offer Decision Service] (ODS) criadas via [!DNL Adobe Journey Optimizer] (AJO) não eram renderizadas quando as atividades eram compiladas usando o VEC na interface atualizada. A mesma configuração funcionava corretamente na interface herdada, gerando confusão e bloqueando a execução da campanha. Essa correção garante uma entrega de oferta consistente em ambas as versões da interface do usuário, restaurando o comportamento esperado para personalização orientada pela AJO.

+++

**Relatórios**

+++Ver detalhes
* **Opção de download restaurada na seção de relatórios da interface de visão geral de relatórios atualizada.** Correção de um problema na nova interface de visão geral em que o botão [!UICONTROL Download] não estava na seção Relatórios, impedindo que os usuários exportassem pontuações de importância do atributo. Essa atualização restaura a funcionalidade completa de exportação, permitindo o acesso simplificado a dados para download para análise e relatórios. (TGT-53222)
* Botão **[!UICONTROL Download full CSV report]restaurado na exibição [!UICONTROL Important attributes].** Solução de um problema na interface de criação de atividade atualizada em que o botão [!UICONTROL Download full CSV report] estava ausente da seção [!UICONTROL Important Attributes] no modo de exibição de relatórios. Essa correção restaura o acesso a insights baixáveis, garantindo uma funcionalidade consistente nas interfaces atualizadas e herdadas. (TGT-53238)
* **Solução de problemas de interface do usuário que afetam os relatórios do [!UICONTROL Auto Target] na interface do usuário de visão geral atualizada.** Correção de vários problemas de interface do usuário na interface de visão geral atualizada que afetavam o relatório de atividades [!UICONTROL Auto Target]. Essas correções incluem:

   * Métricas de aumento e confiança ausentes nos relatórios de resumo
   * Indicador de cor incorreto para a caixa de seleção &quot;modelos criados&quot;
   * Relatório de gráfico não funcional apesar da variação de dados em [!DNL Analytics]
   * Link de download ausente para os relatórios [!UICONTROL Automated Segments] e [!UICONTROL Important Attributes]
   * Exibição do relatório [!UICONTROL Automated Segments] interrompida

  Essas correções restauram o comportamento esperado dos relatórios e melhoram a visibilidade do desempenho do [!UICONTROL Auto Target] na interface atualizada. (TGT-53484)

+++

**[!UICONTROL Visual Experience Composer]**

+++Ver detalhes
* **Validação de formulário corrigida para condições de presença de parâmetro na interface atualizada.** Correção de um problema na interface do usuário atualizada em que selecionar &quot;[!UICONTROL Custom mbox parameter value is present]&quot; ou &quot;[!UICONTROL Parameter is present]&quot; exigia incorretamente que os clientes inserissem um valor. Esse comportamento entrou em conflito com a lógica pretendida, que simplesmente verifica a existência de um parâmetro independentemente de seu valor. A correção alinha a validação do formulário ao comportamento esperado, permitindo uma configuração de atividade mais suave e a adoção total da interface atualizada. (TGT-53638)
* **Lógica de formulário corrigida para regras de presença de parâmetro na entrega da página.&quot;** Correção de um problema na interface do usuário atualizada em que a seleção de regras de entrega de página, como &quot;[!UICONTROL Parameter is present]&quot;, &quot;[!UICONTROL Parameter is not present],&quot;[!UICONTROL Parameter value is present]&quot; ou &quot;[!UICONTROL Parameter value is not present]&quot;, exigia incorretamente que os usuários inserissem um valor de parâmetro adicional. Esse comportamento era inconsistente com a interface herdada e contradizia a lógica pretendida de detectar a presença de parâmetros sem especificar um valor. Essa correção restaura o comportamento esperado de configuração da regra, simplificando a configuração da atividade e melhorando a usabilidade. (TGT-53640)
* **Lógica de validação aprimorada para o construtor de regras de várias páginas na interface atualizada.** Solução de vários problemas de validação no construtor de regras de várias páginas na interface atualizada. Essas correções incluem:

   * Como impedir a criação de regras quando o parâmetro da mbox está vazio
   * Exibição de mensagens de erro apropriadas para estados de regras inválidas
   * Correção da lógica de validação para operadores unários e baseados em parâmetros que não exigem valores de operando
   * Ativar regras de fragmento de hash com operadores unários restaurando a funcionalidade de salvar

  Essas atualizações garantem uma configuração de regra precisa e melhoram a usabilidade em cenários complexos de entrega de página. (TGT-53722)
* **Problema de renomeação de local resolvido em atividades A/B e MVT.** Correção de um bug na interface do usuário atualizada em que a renomeação de um local em uma atividade [!UICONTROL A/B Test] ou [!UICONTROL Multivariate Test] (MVT) não persistia após a navegação entre a lista de locais, o direcionamento e a versão posterior. Essa atualização garante que as alterações no nome da localização sejam salvas e refletidas de forma consistente em todo o fluxo de trabalho da atividade. (TGT-52367)
* **Persistência do nome do local corrigida para atividades MVT e AP na interface atualizada.** Correção de um problema na interface do usuário atualizada em que os nomes de locais editados nas atividades [!UICONTROL Multivariate Test] (MVT) e [!UICONTROL Automated Personalization] (AP) não eram salvos corretamente. Após renomear um local, a navegação entre guias, como [!UICONTROL Targeting] e [!UICONTROL Experiences], fez com que os nomes fossem revertidos para seu estado anterior. Essa correção garante uma nomenclatura de localização consistente entre guias e melhora a confiabilidade durante a configuração da atividade. (TGT-52927)
* **O rótulo de local foi corrigido no painel Gerenciar experiências para atividades MVT.** Correção de um problema na interface do usuário atualizada em que o painel [!UICONTROL Manage Experiences] nas atividades [!UICONTROL Multivariate Test] (MVT) exibia uma numeração de local inconsistente. Essa correção garante que os rótulos de localização sejam sequenciais e alinhados corretamente com as modificações definidas pelo usuário, melhorando a clareza e a usabilidade durante a configuração da experiência. (TGT-52929)

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
