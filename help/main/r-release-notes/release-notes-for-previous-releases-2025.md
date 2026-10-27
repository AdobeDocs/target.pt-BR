---
keywords: Notas de versão;notas de pré-lançamento;aprimoramentos futuros;correções futuras;recursos futuros;versão futura
description: Veja uma lista de recursos, aprimoramentos e correções incluídos em versões anteriores do Adobe Target.
title: Quais recursos estão incluídos nas versões anteriores de 2025?
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/cjheajZKokzwCNspfQckh6PHh5ecetdj7vZrrq9IqXw'
source-git-commit: 7f111df77c4b368dbe000a699ee19f5ff1ea266f
workflow-type: tm+mt
source-wordcount: '25402'
ht-degree: 5%
---
# Notas de versão para versões anteriores

Notas de versão referentes a versões anteriores do [!DNL Adobe Target], incluindo notas de versão para o [!DNL Target Standard/Premium], a plataforma do [!DNL Target] e a biblioteca JavaScript do [!DNL Target] (at.js).

As notas de versão estão listadas em ordem decrescente por mês e ano da versão.

>[!NOTE]
>
>Consulte [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A) para obter informações sobre as versões do Target para o mês vigente (plataforma e Target Standard/Premium).

## Notas de versão - 2025

### [!DNL Target Standard/Premium] 25.11.2 (14 de novembro de 2025)

**Ofertas de decisão**

+++Ver detalhes

* **Decisões de oferta com seletores ocultos ou inválidos não editáveis na interface atualizada.** Correção de um problema na interface do usuário atualizada em que as decisões de oferta vinculadas a seletores ocultos ou inválidos não podiam ser editadas, a menos que o elemento estivesse visível no Visual Experience Composer (VEC). A edição agora é suportada diretamente no painel, restaurando a funcionalidade disponível na interface herdada e garantindo que as decisões de oferta possam ser modificadas, independentemente da visibilidade do seletor. (TGT-53899)

+++

**Recomendações**

+++Ver detalhes

* **A edição de critérios em uma atividade causou uma falha na página.** Solução de um problema na interface do usuário atualizada em que os critérios da atividade de edição faziam com que a página falhasse com erros de console relacionados a `useCrudActionsCtx`. O editor de critérios agora é carregado e funciona corretamente, garantindo que as atividades possam ser editadas sem interrupção. (TGT-53971)
* A coluna **[!UICONTROL Mensagem] falhou intermitentemente ao exibir os dados do produto na interface atualizada.** Solução de um problema na interface atualizada do usuário do [!UICONTROL Recommendations], em que a coluna [!UICONTROL Mensagem] da [!UICONTROL Pesquisa de Catálogo] falhava intermitentemente ao exibir dados do produto, mesmo que os valores estivessem presentes no feed. A coluna agora mostra consistentemente os valores de mensagem corretos em todos os produtos, garantindo visibilidade confiável sem a necessidade de reconfiguração manual da coluna. (TGT-52777)
* O botão **[!UICONTROL Baixar Dados do Recommendations] não fica visível após salvar a atividade na interface atualizada.** Solução de um problema na interface do usuário atualizada em que o botão [!UICONTROL Baixar dados de recomendações] não era exibido para determinadas atividades salvas, mesmo depois de salvar novamente. O botão agora é exibido de forma consistente em todas as atividades, garantindo que os usuários possam exportar dados de recomendação com confiança sem precisar de soluções alternativas. (TGT-53802)
* **A abertura de determinados produtos de uma coleção retornou &quot;O recurso solicitado não foi encontrado&quot; e o modal não tinha uma opção de fechamento.** Correção de um problema na interface atualizada do Recommendations, em que a abertura de determinados produtos a partir de uma coleção acionava o erro &quot;O recurso solicitado não foi encontrado&quot; e exibia uma modal em branco sem uma opção de fechamento. O modal agora carrega os detalhes do produto corretamente e uma opção de fechamento está sempre disponível para sair normalmente. (TGT-53986)

+++

## [!DNL Target Standard/Premium] 25.11.1 (10 de novembro de 2025)


**Analytics for Target (A4T)**

+++Ver detalhes

* Mensagem de erro de **[!UICONTROL Metas e Configurações] ao usar [!DNL Adobe Analytics] como fonte de relatórios na interface atualizada.** Solução de um problema na interface do usuário atualizada [!UICONTROL Visão geral], na qual a seção Metas exibia o erro &quot;Algo deu errado. Não podemos completar o seu pedido. Entre em contato com [!DNL Adobe Client Care] se o problema persistir&quot; quando [!DNL Adobe Analytics] (A4T) for selecionado como a fonte de relatórios. As metas agora são exibidas corretamente com métricas do [!UICONTROL Adobe Analytics], garantindo uma visibilidade consistente em todas as fontes de relatórios. (TGT-54021)

+++

**Públicos-alvo**

+++Ver detalhes

* **Não é possível selecionar vários públicos-alvo de relatório na interface atualizada.** Solução de um problema na interface do usuário atualizada em que os usuários não podiam selecionar vários públicos de relatórios recém-criados simultaneamente ao editar uma atividade. Agora, vários públicos-alvo podem ser atribuídos de uma só vez, melhorando a flexibilidade e a eficiência na configuração de relatórios. (TGT-53253)

+++

**Ofertas de decisão**

+++Ver detalhes

* **Não é possível editar ou substituir ofertas de decisão na interface atualizada.** Solução de um problema na interface atualizada em que as ofertas de decisão não podiam ser editadas ou substituídas por meio do painel [!UICONTROL Modificações] e os nomes das ofertas apareciam em branco. As ofertas de decisão agora são totalmente acessíveis e editáveis, restaurando a paridade com a interface herdada e garantindo que os clientes possam gerenciar ofertas diretamente nas atividades do. (TGT-53884)

+++

**Localização**

+++Ver detalhes

* **Correção de vários erros de localização na interface do usuário coreana e japonesa.** (TGT-54003, TGT-54004, TGT-54006, TGT-54007 e TGT-54018)

+++

**[!UICONTROL Recomendações]**

+++Ver detalhes

* **A Promoção por Atributo com Correspondência de Atributo de Entidade falhou ao carregar a chave de recomendação após salvar a atividade.** Correção de um problema em que promoções do tipo [!UICONTROL Promoção por atributo] com o tipo de regra [!UICONTROL Correspondência de atributo de entidade] não carregavam a chave de recomendação quando editadas após salvar uma atividade. O problema foi causado pelo `customKeyId` não ter sido solicitado por meio do GraphQL. As chaves de recomendação agora são carregadas corretamente durante as edições de promoção. (TGT-53117)
* **A recomendação persiste visualmente ao alternar de ExpB para ExpA.** Correção de um problema em que inserir uma recomendação na Experiência B e, em seguida, alternar para a Experiência A, deixava a caixa de oferta de recomendação visível. Isso era apenas uma inconsistência visual; as modificações agora são renderizadas corretamente ao alternar entre experiências, garantindo um comportamento preciso da interface. (TGT-53911)
* **A chave de recomendação não está carregando para [!UICONTROL Promoção por Atributo] com [!UICONTROL Correspondência de Atributo de Entidade].** Solução de um problema em que promoções do tipo [!UICONTROL Promoção por atributo] com o tipo de regra [!UICONTROL Correspondência de atributo de entidade] não carregavam a chave de recomendação quando editadas após salvar uma atividade. A chave de recomendação agora é recuperada corretamente por meio do GraphQL, garantindo que as promoções sejam exibidas e funcionem conforme esperado. (TGT-53917)
* **Recomendações de edição sobre elementos ocultos do HTML que não funcionam na interface atualizada.** Solução de um problema na [!UICONTROL Nova Criação] e na interface do VEC em que as atividades de recomendação aplicadas a elementos ocultos do HTML não podiam ser editadas. Essa funcionalidade agora funciona conforme esperado, restaurando a paridade com a interface herdada e garantindo que as recomendações possam ser modificadas independentemente da visibilidade do elemento. (TGT-53953)
* **Não é possível editar atividades de recomendação em elementos ocultos do HTML na interface atualizada.** Correção de um problema na interface do usuário atualizada em que as atividades de recomendação aplicadas a elementos ocultos do HTML não podiam ser editadas. Essa funcionalidade agora funciona conforme esperado, restaurando a paridade com a interface herdada e garantindo que as recomendações possam ser modificadas independentemente da visibilidade do elemento. (TGT-53951)
* **O catálogo de recomendações não tem valores de atributo na interface atualizada.** Solução de um problema na interface atualizada do usuário do [!UICONTROL Recommendations], em que as listagens de pesquisa de catálogo falhavam intermitentemente ao exibir determinados valores de atributo (por exemplo, mensagem), mesmo quando presentes no feed do produto. Os valores de atributo agora são carregados de forma consistente nos resultados da pesquisa sem exigir reconfiguração da coluna, melhorando a confiabilidade e a eficiência do gerenciamento de catálogos. (TGT-52769)
* O botão **[!UICONTROL Baixar Recomendações] não aparece para [!DNL Recommendations] atividades na interface atualizada.** Solução de um problema na interface atualizada do usuário [!DNL Recommendations] em que o botão [!UICONTROL Baixar recomendações] não estava visível para atividades A/B que usam recomendações. O botão agora é exibido corretamente, permitindo que os usuários exportem os dados de recomendação conforme esperado, de forma consistente com a funcionalidade na interface herdada. (TGT-53768)
* O botão **[!UICONTROL Baixar Dados de Recomendação] não aparece na interface de Visão Geral atualizada.** Solução de um problema na interface atualizada do usuário [!UICONTROL Visão geral] em que o botão [!UICONTROL Baixar Dados de Recomendação] não estava visível para atividades que continham recomendações. O botão agora é exibido corretamente, garantindo que os usuários possam exportar os dados de recomendações diretamente, sem precisar alternar de volta para a interface herdada. (TGT-53772)
* **A edição dos critérios de atividade às vezes resultava em tela em branco na interface do usuário atualizada.** Solução de um problema na interface do usuário atualizada, em que clicar em [!UICONTROL Editar critérios em experiências] ocasionalmente resultava em uma tela em branco para determinadas atividades. O editor de critérios agora é carregado de forma confiável em todas as atividades, garantindo que os usuários possam editar sem interrupção. (TGT-53961)
* **Não é possível editar critérios de sequência na interface atualizada.** Correção de um problema na interface do usuário atualizada em que a tentativa de editar o [!UICONTROL Critério de sequência] fazia com que o pop-up de critérios permanecesse preso ao carregar e exibisse uma tela em branco. O editor de critérios agora é carregado corretamente, permitindo que os usuários editem e atualizem os critérios de sequência sem interrupção. (TGT-53985)

+++

**[!UICONTROL Relatórios]**

+++Ver detalhes

* **[!UICONTROL Locais de teste multivariado] (MVT) e problema de relatório de gráfico impediram a geração de relatórios.** Solução de um problema em que as atividades do MVT falhavam ao gerar relatórios de [!UICONTROL Contribuição de localização] e Gráfico na interface do usuário do Target, exibindo o erro &quot;Algo deu errado. Não podemos completar o seu pedido.&quot; Agora os relatórios são carregados corretamente na interface do usuário, garantindo visibilidade total. (TGT-53654)
* **Os relatórios do MVT não estão carregando devido a um erro no relatório de contribuição do [!UICONTROL Elemento].** Correção de um problema em que os relatórios de atividade do MVT não eram carregados na interface do usuário do Target, mostrando o erro &quot;Não foi possível buscar o relatório de contribuição do elemento.&quot; Os relatórios agora são exibidos corretamente, garantindo total visibilidade das contribuições de elementos. (TGT-53691)
* **Exportar detalhes do pedido para um problema de CSV para [!UICONTROL Direcionamento de experiência] (XT) atividades.** Correção de um problema em que a opção [!UICONTROL Exportar detalhes do pedido para CSV] aparecia incorretamente para atividades XT e retornava um arquivo vazio. A opção agora só é exibida para atividades de AP, garantindo uma funcionalidade de exportação precisa e evitando confusão. (TGT-53798)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* **[!UICONTROL O problema do botão Excluir Modificação] impediu a remoção das modificações da atividade.** Solução de um problema em que o botão [!UICONTROL Excluir Modificação] da interface do usuário [!DNL Target] não funcionava, impedindo que os usuários removessem modificações nas atividades. O botão agora funciona conforme esperado, permitindo que as modificações sejam excluídas de forma confiável sem demora. (TGT-53728)
* **Os seletores preferenciais não são reconhecidos na interface atualizada.** Correção de um problema na interface do usuário atualizada em que os seletores preferenciais, como `data-target-component-id`, não apareciam na lista do seletor de CSS no VEC. Os usuários agora podem selecionar atributos preferenciais de maneira confiável em vez de nomes de classe gerados dinamicamente, garantindo um direcionamento estável em atualizações de página de SPA. (TGT-53908)
* **Incompatibilidade de alinhamento de local de atividade entre as páginas [!UICONTROL Editar] e [!UICONTROL Visão geral].** Solução de um problema em que a numeração do local da atividade na página [!UICONTROL Visão geral] não estava alinhada com as atualizações feitas na página [!UICONTROL &#x200B; Editar experiência]. Agora, os locais permanecem consistentes em ambas as exibições, garantindo um alinhamento preciso e evitando posições ausentes ou com numeração incorreta. (TGT-53960 e TGT-53954)
* **Não é possível voltar para o modo [!UICONTROL Design] no VEC atualizado.** Solução de um problema na interface atualizada do VEC em que os usuários não podiam alternar de volta para o modo [!UICONTROL Design] depois de navegarem para uma nova página no modo [!UICONTROL Procurar]. A opção [!UICONTROL Design] agora funciona corretamente, permitindo que as modificações sejam aplicadas facilmente em todas as páginas. (TGT-53988 e TGT-53993)
* **Parâmetro de consulta não exibido na visão geral da atividade.** Solução de um problema na interface atualizada em que os parâmetros de consulta não eram exibidos na página [!UICONTROL Visão geral] para atividades, causando discrepâncias entre a [!UICONTROL Visão geral] e as URLs de entrega da página. Agora os parâmetros de consulta são exibidos corretamente, garantindo que os locais de atividade sejam totalmente representados e consistentes em todas as exibições. (TGT-53701)

+++

### [!DNL Target Standard/Premium] 25.10.1 (22 de outubro de 2025)

Esta versão inclui as seguintes atualizações e correções:

**Atividades**

+++ Ver detalhes
* **Solução de um problema de usabilidade na interface atualizada**. [!UICONTROL Observadores] agora pode visualizar atividades usando a opção [!UICONTROL Exibir Atividade], exatamente como na interface do usuário herdada. (TGT-51741)
* **[!UICONTROL Observador] usuários agora podem exibir o conteúdo da atividade na interface atualizada.** Visibilidade restaurada para usuários com função de Observador na interface atualizada da atividade. Anteriormente, os Observadores não conseguiam exibir modificações, ofertas e alterações de conteúdo — funcionalidade que estava disponível na interface herdada. (TGT-53785)
* **[!UICONTROL Usuários aprovadores] agora podem editar metas de atividade sem erro de privilégio de editor.** Correção de um problema de permissão na interface de Criação de atividade que impedia os usuários em nível de Aprovador de salvar alterações nas configurações avançadas da meta. Os usuários afetados receberam um erro `403 Forbidden.Resource` que exigia privilégios de editor, apesar de terem acesso suficiente. (TGT-53819)

+++

**Públicos-alvo**

+++Ver detalhes

* **Seleção de Vários Públicos Restaurada nos Relatórios &quot;Somente Esta Atividade&quot;.** Solução de um problema na interface de Criação de Atividade que impedia os usuários de selecionar vários públicos na seção [!UICONTROL Somente esta atividade] em [!UICONTROL Metas e configurações]. (TGT-53283)
* **Os gráficos de relatórios baseados no público-alvo agora exibem os dados de conversão corretamente.** Solução de um problema na guia [!UICONTROL Relatórios] que causava a falha de gráficos ao selecionar públicos não padrão. Enquanto dados e métricas de confiança estavam disponíveis, o gráfico visual mostrava apenas uma linha sólida, dificultando a análise. (TGT-53769)
* **A interface de [!UICONTROL Direcionamento] agora indica claramente as regras de público-alvo excluídas.** Solução de um problema na seção [!UICONTROL Direcionamento] da interface de Criação de Atividade, na qual as regras de público-alvo definidas como [!UICONTROL Excluir] não eram exibidas claramente. Isso levou a confusão ao revisar a lógica de direcionamento, especialmente para públicos-alvo que excluem URLs específicos. (TGT-53809)
* **Os valores de definição de público-alvo agora podem ser selecionados e copiados na guia [!UICONTROL Direcionamento].** Solução de um problema na interface de Criação de atividade que impedia os usuários de selecionar e copiar valores de regra de público na guia [!UICONTROL Direcionamento]. Essa funcionalidade estava disponível na interface herdada, mas ausente na interface atualizada. (TGT-53856)

+++

**Localização**

+++Ver detalhes

* **Corrigido o erro de tradução de &quot;quote&quot; no contexto do editor de páginas zh_CN.** Correção de um erro de tradução contextual no local zh_CN, onde o termo &quot;quote&quot; era traduzido incorretamente como &quot;报价&quot;, o que implica uma cotação de preço comercial. Na seção Tipografia > Estilo de cabeçalho > Cotação de bloco, o significado pretendido se refere a um elemento de formatação, o bloco de cotação, e não à precificação. (TGT-53841)
* **Erro de tradução corrigido de &quot;aspas removidas&quot; no contexto do editor de páginas zh_CN.** Correção de um erro de tradução no local zh_CN em que &quot;quote removed&quot; era renderizado incorretamente como &quot;移除了报价&quot;, implicando uma cotação de preço comercial. Na seção Tipografia > Estilo de cabeçalho > Cotação de bloco, o termo se refere a um elemento de formatação, o bloco de cotação, e não à precificação. (TGT-53843)
* **Corrigido o erro de tradução de &quot;aspas reorganizadas&quot; no contexto do editor de páginas zh_CN.** Correção de um erro de tradução contextual no local zh_CN, em que &quot;quote reorganize&quot; era traduzido incorretamente como &quot;重新排列了报价&quot;, o que implica uma cotação de preço comercial. Na seção Tipografia > Estilo de cabeçalho > Cotação de bloco, o termo se refere a um elemento de formatação, o bloco de cotação, e não à precificação. (TGT-53844)
* **Erro de tradução de &quot;aspas alteradas&quot; no contexto do editor de páginas zh_CN.** Correção de um erro de tradução no local zh_CN, em que &quot;quote changed&quot; era renderizado incorretamente como &quot;更改了报价&quot;, sugerindo uma cotação de preço comercial. Na seção Tipografia > Estilo de cabeçalho > Cotação de bloco, o termo se refere a um elemento de formatação, o bloco de cotação, e não à precificação. (TGT-53845)

+++

**Recomendações**

+++Ver detalhes

* **As alterações do seletor de CSS das recomendações agora são salvas corretamente.** Solução de um problema na interface de criação de atividade que impedia os usuários de atualizar o seletor de CSS para inserções de recomendação. Alterações revertidas após salvar, bloqueando atualizações para contêineres de direcionamento. (TGT-53835)
* **A seleção do evento de carregamento da página agora persiste em modificações de recomendação.** Solução de um problema na interface de Criação de Atividade que impedia os usuários de salvar alterações ao alternar o tipo de evento de uma recomendação de [!UICONTROL Exibição] para [!UICONTROL Carregamento de Página]. Embora a seleção tenha sido bem-sucedida, ela foi revertida depois de sair, bloqueando a publicação da atividade. (TGT-53957)

+++

**Relatórios**

+++Ver detalhes

* **&quot;[!UICONTROL Exportar detalhes do pedido para CSV]&quot; agora baixa dados completos.** Solução de um problema na interface do usuário [!UICONTROL Visão geral] atualizada que fazia com que a opção &quot;[!UICONTROL Exportar detalhes do pedido para CSV]&quot; baixasse arquivos vazios, mesmo quando havia dados de relatório válidos. (TGT-53787)

+++

**Segurança**

+++Ver detalhes

* **Pré-filtro IMS adicionado para proteger os pontos de extremidade GQL da exposição de dados entre organizações.** Solução de uma vulnerabilidade de segurança na guia Admin que afetava os endpoints do GraphQL licenseGroups e targetProperties. O problema resultou do uso da API JIL com um token de cliente administrador que poderia ser explorado para acessar dados de produtos entre organizações. (TGT-53837)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes

* **Estabilidade de criação restaurada na interface de Criação de Atividade.** Solução de um problema intermitente na interface do VEC que causava a falha da criação e fazia com que os links se tornassem clicáveis inesperadamente, redirecionando os usuários para fora da página. (TGT-53153)
* **Edição restaurada para atividades salvas na interface de Criação de Atividade.** Correção de um problema que impedia os usuários de editar atividades após salvar modificações. As atividades afetadas permaneceram presas em &quot;[!UICONTROL Aplicando modificações iniciais]&quot;, bloqueando mais atualizações e ocultando o botão [!UICONTROL Cancelar]. (TGT-53631)
* **O VEC não é mais interrompido em &quot;[!UICONTROL Aplicando modificações iniciais].&quot;** Solução de um problema de desempenho no VEC que causava longos atrasos ao carregar experiências com um alto número de modificações. Os usuários afetados viram a interface travar em &quot;[!UICONTROL Aplicando modificações iniciais]&quot; por vários minutos, especialmente em cenários da Experiência B. (TGT-53727)
* **O VEC agora carrega modificações sem elementos raiz.**
Correção de um problema no VEC que causava a paralisação das experiências ao carregar modificações que não tinham um elemento raiz claro. Essas modificações fizeram com que a interface travasse indefinidamente em &quot;A[!UICONTROL aplicando modificações iniciais]&quot;. (TGT-53799)
* **Salvar alterações nas atividades agora funciona conforme esperado.** Solução de um problema relacionado a permissões na Nova interface de criação que impedia os usuários de salvar alterações ao editar metas e configurações avançadas em atividades do. Os usuários afetados viam uma faixa de erros vermelha e uma mensagem &quot;Forbidden.Resource&quot;, apesar de terem acesso apropriado. (TGT-53816)
* A **Interface do VEC agora preserva as modificações de experiência nas exibições.** Solução de vários problemas no VEC atualizado que afetavam o desenvolvimento da experiência. As modificações não persistiam corretamente, especialmente ao usar ofertas do HTML ou alternar entre exibições. (TGT-53825)
* **Todas as exibições agora são exibidas corretamente quando uma modificação abrange várias experiências.** Solução de um problema na interface de criação de atividade em que apenas uma exibição era mostrada quando uma modificação era aplicada em várias exibições. A dica de ferramenta de focalização não listava todas as exibições associadas, mesmo que a modificação tivesse sido aplicada corretamente. (TGT-53827)
* **O VEC não é mais interrompido intermitentemente em &quot;[!UICONTROL Aplicando modificações iniciais].&quot;** Correção de um problema intermitente no VEC em que as experiências falhavam ao carregar e permaneciam presas em &quot;[!UICONTROL Aplicando modificações iniciais].&quot; Esse comportamento era inconsistente e, às vezes, acionava loops de redirecionamento ou exigia limpeza manual do cache. (TGT-53916)
* Não foi possível reproduzir o problema de carregamento do **VEC.** Investigamos um problema relatado em que o VEC permanecia preso em &quot;[!UICONTROL Aplicando modificações iniciais]&quot; ao editar atividades existentes. Suspeita-se que o comportamento esteja relacionado ao conteúdo do HTML sem um elemento primário. Continuaremos monitorando a recorrência e recomendaremos o uso de contêineres estruturados para ofertas do HTML para garantir a estabilidade. (TGT-53972)
* O modo **[!UICONTROL Design] no VEC não se comporta mais como o modo [!UICONTROL Procurar] intermitentemente.** Solução de um problema na interface do usuário em que o modo [!UICONTROL Design] se comportava intermitentemente como o modo [!UICONTROL Procurar], permitindo links `<a>` clicáveis e impedindo a seleção de elementos. Isso fazia com que a caixa de flutuação desaparecesse e bloqueasse os workflows de modificação. (TGT-53136)
* Os cliques no botão **no modo [!UICONTROL Composer] não acionam mais o redirecionamento de página.** Foi resolvido um problema na interface do VEC atualizada em que um clique em um botão no modo [!UICONTROL Composer] causava um redirecionamento inesperado para a URL de destino do botão. Isso impedia que os usuários editassem elementos do call-to-action (CTA) e interrompeu o fluxo de trabalho de criação. (TGT-53137)
* **As atualizações de código de oferta em atividades de personalização automatizada agora são salvas sem erros.** Solução de um problema na Nova Interface de Criação que causava um erro &quot;[!UICONTROL Entrada de usuário inválida]&quot; ao atualizar o código de oferta em atividades de [!UICONTROL Automated Personalization]. O erro impedia que os usuários salvassem as alterações, mesmo quando a entrada era válida. (TGT-53586)
* O modo **[!UICONTROL Design] no VEC agora bloqueia a navegação por links para componentes editáveis.** Foi resolvido um problema no VEC atualizado em que elementos clicáveis, como botões e links, acionavam o redirecionamento de página mesmo no modo [!UICONTROL Design]. Este comportamento imita o modo [!UICONTROL Procurar] e impede que os usuários modifiquem os componentes principais. (TGT-53696)
* A métrica **&quot;[!UICONTROL Clicou em um elemento]&quot; agora funciona sem redirecionamento ou erro.** Solução de um problema na Nova interface do usuário para Criação que causava redirecionamentos inesperados e telas em branco ao selecionar a métrica de conversão &quot;[!UICONTROL Clicou em um elemento]&quot;. Clicar em um botão durante a configuração acionou a navegação em vez de registrar o elemento, resultando em um erro &quot;[!UICONTROL elemento não encontrado]&quot;. (TGT-53817)
* **As atividades existentes não ficam mais presas no loop de carregamento infinito durante a edição.** Solução de um problema na Nova interface de criação, em que a edição de uma atividade existente no VEC fazia com que a página permanecesse presa em um loop de carregamento infinito. Esse problema não afetava as atividades recém-criadas e era acionado por modificações pré-existentes na página. (TGT-53913)
* **As páginas de atividade existentes com modificações agora são carregadas corretamente no VEC.** Solução de um problema no VEC atualizado que fazia com que as páginas permanecessem presas na fase de carregamento ao editar uma atividade existente com modificações salvas. Novas atividades carregadas sem problema, mas as atividades configuradas anteriormente não foram renderizadas. (TGT-53967)

+++

### [!DNL Target Standard/Premium] 25.9.3 (30 de setembro de 2025)

Esta versão inclui os seguintes aprimoramentos e correções.

+++[!UICONTROL Públicos-alvo]

* **As regras de exclusão de público-alvo foram exibidas incorretamente como inclusão na interface do usuário [!DNL Target].** Os públicos configurados com regras de exclusão apareciam como incluídos ao editar o direcionamento em uma atividade. Embora a lógica de exclusão tenha sido aplicada corretamente durante a execução, a interface do usuário não refletia a regra com precisão, omitindo o rótulo &quot;excluindo&quot;. A interface do usuário do [!DNL Target] agora exibe corretamente as regras de exclusão nos fluxos de trabalho de configuração de público-alvo e direcionamento, garantindo clareza e consistência para a configuração da campanha. (TGT-53808)
* **A seção [!UICONTROL Direcionamento] não indicou que uma regra de público-alvo foi definida para exclusão.** Os públicos configurados com lógica de exclusão foram exibidos incorretamente como inclusão na seção [!UICONTROL Direcionamento] da interface de criação de atividade. Embora o back-end tenha aplicado corretamente a regra de exclusão, a interface do usuário não conseguiu representá-la visualmente, omitindo o rótulo &quot;Excluir&quot; e causando confusão durante a configuração da campanha. A seção [!UICONTROL Direcionamento] agora exibe claramente as regras de exclusão, garantindo a consistência entre a configuração do público-alvo e a visualização de direcionamento. (TGT-53809)

+++

+++Localização

* **Correção de uma inconsistência de terminologia na tradução do chinês simplificado de &quot;Exibição completa de detalhes&quot;.**
Anteriormente, o termo &quot;Detalhes&quot; era traduzido incorretamente como &quot;详情&quot; na localidade do chinês simplificado (zh_CN), violando as diretrizes de terminologia estabelecidas. Esse valor foi corrigido para &quot;详细信息&quot; para garantir a consistência com o termo base. (TGT-53741)

+++

+++[!UICONTROL Recomendações]

* **As caixas de recomendação foram difíceis de localizar e selecionar no VEC.** Depois de adicionar uma oferta do recommendations no (VEC), clicar na modificação no painel esquerdo não realçou nem rolou até a caixa de recomendação correspondente na página. Isso dificultava localizar e editar a oferta, especialmente quando oculta em seletores ou estilizada minimamente. Ao clicar em uma modificação de recomendação, agora o realça e rola corretamente para o elemento associado, melhorando a usabilidade e a eficiência de edição no processo de criação de atividade atualizado. (TGT-52571)
* **Os seletores de recomendação foram regravados incorretamente após salvar uma atividade.** Ao adicionar uma recomendação a um elemento no VEC, o seletor estava inicialmente correto, mas depois de salvar e reabrir a atividade, ele foi alterado para um seletor genérico. As tentativas de restaurar manualmente o seletor original resultaram em erros de validação. Os seletores de recomendação agora persistem com precisão após salvar, garantindo um direcionamento confiável e capacidade de edição no processo de criação de atividade atualizado. (TGT-53709)
* **Não foi possível editar o conteúdo dos critérios ao modificar uma atividade existente.** Ao editar uma atividade, a seção de conteúdo [!UICONTROL Critérios] aparecia desabilitada, com botões esmaecidos e sem resposta. Esse problema foi resolvido verificando se as configurações de [!UICONTROL Critério] são totalmente editáveis durante as atualizações da atividade. Os clientes agora podem modificar o conteúdo dos [!UICONTROL Critérios] sem precisar alternar seleções ou usar soluções alternativas, melhorando a flexibilidade e a usabilidade no processo de criação de atividades atualizado. (TGT-53812)
* **Não foi possível editar o critério em uma atividade.** As opções [!UICONTROL Editar critérios]e [!UICONTROL Remover critérios] foram desabilitadas ao acessar critérios de dentro de uma atividade. No entanto, os mesmos critérios podem ser editados com êxito através da guia [!UICONTROL Recommendations]. Os critérios agora podem ser totalmente editados tanto no fluxo de trabalho de edição da atividade quanto na guia [!UICONTROL Recommendations], garantindo uma experiência de edição consistente e eficiente. (TGT-53814)

+++

+++[!UICONTROL Relatórios]

* **Gerar ofertas ad-hoc em atividades A[!UICONTROL Personalization automatizadas] causou inconsistências de relatório.** O uso do recurso Gerar ofertas ad-hoc em atividades do [!UICONTROL Automated Personalization] (AP) resultou em relatórios imprecisos. Especificamente, as IDs de oferta foram reutilizadas em vários locais, fazendo com que os dados de relatório fossem atribuídos incorretamente ou substituídos. As ofertas ad-hoc agora são geradas com identificadores distintos por local, garantindo um rastreamento e relatórios precisos em todas as experiências configuradas. (TGT-53757)
* **Falha ao carregar os relatórios de atividade devido a um erro no JavaScript.** Os clientes encontraram uma mensagem &quot;Ocorreu um erro&quot; ao acessar a guia [!UICONTROL Relatórios] para determinadas atividades. O erro foi causado por uma exceção do JavaScript: não é possível ler propriedades de indefinido (lendo &#39;indexOf&#39;), acionado durante a chamada do GraphQL `getAnalyticsReportSummary`. Agora os relatórios são carregados corretamente, e o tratamento de erros foi aprimorado para evitar falhas semelhantes no fluxo de trabalho atualizado de criação de atividades. (TGT-53797)
* **Os relatórios falharam após interagirem com a barra de rolagem.** Clicar na barra de rolagem na guia [!UICONTROL Relatórios] causou uma falha na página, acompanhada de um erro de JavaScript:
  `SyntaxError: Failed to execute 'querySelector' on 'Element': '[data-key="a-currentcopy"hiretalent""]' is not a valid selector.` Agora os relatórios são carregados e rolados corretamente sem erros ou falhas. (TGT-53828)
* **Os relatórios não exibiram a métrica primária.** A métrica primária, configurada como uma métrica de conversão usando uma mbox, estava ausente nos relatórios de atividades. A pesquisa por nome de métrica ou nome de mbox não produziu resultados, impedindo a visibilidade dos principais dados de desempenho. As métricas primárias agora aparecem corretamente na guia [!UICONTROL Relatórios], garantindo um rastreamento e análise precisos do desempenho da campanha. (TGT-53773)
* **A guia [!UICONTROL Relatórios] da interface atualizada falhou ao interagir com a barra de rolagem horizontal.** A exibição [!UICONTROL Relatórios] falhou intermitentemente com um erro &quot;Algo deu errado&quot; ao usar a barra de rolagem horizontal para acessar métricas fora da exibição. A barra de rolagem agora funciona de forma confiável, permitindo que os clientes visualizem e analisem todas as métricas sem precisar de soluções alternativas, como reduzir ou usar a rolagem shift. (TGT-53824)

+++

+++[!UICONTROL Visual Experience Composer] (VEC)

* **Clicar em navegações estruturais no VEC não exibia de maneira consistente o menu de edição.**
Ao selecionar elementos do HTML por meio da navegação estrutural no (VEC), o menu de edição não era exibido ou desaparecia rapidamente, o que tornava a seleção de elementos não confiável. O menu de edição agora é exibido de forma consistente ao navegar por navegações estruturais, melhorando o fluxo de trabalho de seleção de elemento no processo de criação de atividade atualizado. (TGT-52873)
* **O menu de contexto falhou intermitentemente ao aparecer no VEC.** O menu de contexto na interface do VEC atualizada não era exibido de forma consistente ao clicar em elementos, dificultando o acesso às opções de edição. O menu de contexto agora é exibido de forma confiável a partir da seleção de elementos, melhorando o fluxo de trabalho de edição e a usabilidade geral no processo de criação de atividades atualizado. (TGT-53015)
* **Falha ao exibir o menu de contexto para determinados elementos no VEC.** O menu de contexto não era exibido ao selecionar elementos específicos no VEC atualizado, dificultando a aplicação de modificações. O menu de contexto agora é exibido de forma consistente para todos os elementos compatíveis, melhorando a confiabilidade e a usabilidade da experiência de edição no fluxo de trabalho de criação de atividade atualizado. (TGT-53248)
* **O menu de contexto desapareceu no primeiro clique ao usar navegações estruturais no VEC.** Selecionar um elemento principal por meio da navegação estrutural no VEC fazia com que o menu de contexto aparecesse brevemente e desaparecesse, dificultando o acesso às opções de edição. O menu de contexto agora permanece visível e funcional ao navegar pelos elementos por navegações estruturais, melhorando a confiabilidade do fluxo de trabalho de seleção de elementos no processo de criação de atividades atualizado. (TGT-53424)
* **O menu de contexto não foi exibido para elementos de nível superior no VEC.** A seleção de elementos de nível superior, como `<div>` ou `<main>` tags, por meio da navegação estrutural no VEC não acionou o menu de contexto, impedindo mais ações de edição. O menu de contexto agora é exibido de forma consistente para todos os elementos compatíveis, incluindo contêineres de nível superior, melhorando a flexibilidade e a usabilidade do fluxo de trabalho de criação da atividade. (TGT-53770)
* **Os elementos em uma página específica não eram editáveis no VEC.** Determinados elementos na página não puderam ser selecionados ou editados no VEC atualizado. Esse problema foi isolado àquela página e não afetou outras páginas dentro da mesma conta. Todos os elementos na página agora podem ser selecionados e editados conforme esperado, restaurando a funcionalidade completa no fluxo de trabalho de criação da atividade. (TGT-53353)
* **Fluxo de trabalho melhorado ao exibir elementos secundários durante a seleção de elementos no VEC.** Para melhorar a usabilidade e a precisão durante a criação da atividade, o VEC agora exibe elementos secundários ao passar o mouse sobre ou selecionar um elemento principal do HTML. Esse aprimoramento permite que os clientes entendam melhor a estrutura da página e façam modificações mais precisas, simplificando o fluxo de trabalho de edição na interface atualizada. (TGT-53416)
* **Não foi possível editar elementos em atividades existentes usando a barra de modificação.** Ao editar atividades criadas anteriormente, a barra de modificação não era ativada para determinados elementos na página, impedindo atualizações. Esse problema foi observado principalmente em atividades modificadas e foi difícil de reproduzir nas recém-criadas. A barra de modificação agora é exibida de forma consistente e permite a edição de todos os elementos compatíveis, melhorando a confiabilidade e a usabilidade no fluxo de trabalho de criação de atividade atualizado. (TGT-53013)

+++

+++[!UICONTROL Espaços de trabalho]

* **A clonagem de uma atividade para um espaço de trabalho diferente disparou um erro de &quot;Entrada de Usuário Inválida&quot;.** A tentativa de clonar uma atividade de um espaço de trabalho para outro resultou em um erro: &quot;InvalidProperty.Json - nome de propriedade não reconhecido &#39;content&#39;.&quot; Esse problema era causado pelo manuseio inadequado de metadados de atividade durante o processo de clonagem. Agora, as atividades podem ser clonadas com êxito entre espaços de trabalho sem acionar erros de validação, garantindo workflows de implantação de atividades mais suaves. (TGT-53731 e TGT-53736)

+++

### [!DNL Target Standard/Premium] 25.9.2 (22 de setembro de 2025)

Essa versão inclui as seguintes correções e aprimoramentos:

**[!UICONTROL Públicos-alvo]**

+++Ver detalhes

* **Correção de um problema em que as atividades não podiam ser copiadas devido a IDs de público-alvo inválidas.** Os clientes que tentavam copiar atividades no processo de criação de atividade atualizado encontraram um erro causado por IDs de público-alvo inválidas (por exemplo, -1752722444307). Esse problema de validação de backend impedia a duplicação de atividades no mesmo espaço de trabalho. Esse problema foi resolvido e agora as atividades podem ser copiadas com êxito sem erros relacionados ao público-alvo. (TGT-53717)
* **Correção de um problema em que erros de entrada de usuário inválidos apareciam para públicos somente atividade nas atividades [!UICONTROL Automated Personalization] do modal [!UICONTROL Gerenciar conteúdo].** Os clientes encontraram erros de entrada de usuário inválidos ao configurar públicos somente atividade no modal [!UICONTROL &#x200B; Gerenciar conteúdo] para atividades AP. Esse problema ocorreu apesar de os públicos-alvo serem usados anteriormente com sucesso. As configurações de público-alvo combinadas agora são salvas corretamente sem acionar erros de validação. (TGT-53749)

+++

**Documentação**

+++Ver detalhes

* **As páginas de documentação específicas do Target para o Web SDK foram movidas para o repositório do Adobe Target.** Como parte da reestruturação da documentação do Web SDK, o conteúdo específico do [!DNL Target] foi migrado dos documentos gerais do Web SDK para o [!DNL Adobe Target] [Guia do desenvolvedor](https://experienceleague.adobe.com/en/docs/target-dev/developer/a4t/overview-a4t?lang=en){target=_blank}. Essa alteração melhora a descoberta de conteúdo e garante que a orientação específica da solução seja mantida pela equipe apropriada do produto. (TGT-53374)

+++

**[!UICONTROL Decisões de oferta]**

+++Ver detalhes

* **A opção Offer Decision agora está consistentemente visível durante a criação da atividade inicial.** Solução de um problema na interface atualizada em que a opção [!UICONTROL Offer Decision] não aparecia durante o primeiro fluxo de criação para atividades A/B, especialmente quando acessada no modo incógnito em locatários com Offer Decisions ativadas. A opção só apareceu depois de navegar até a etapa [!UICONTROL Direcionamento] e voltar para [!UICONTROL Experiências]. Essa correção garante que a opção [!UICONTROL Offer Decision] esteja disponível imediatamente durante a configuração inicial, melhorando a usabilidade e reduzindo a confusão. (TGT-51888)

+++

**[!UICONTROL Ofertas]**

+++Ver detalhes

* **Correção de um problema em que as ofertas de redirecionamento não incluíam `redirectOptions` na carga quando `includeContent=true`.** Os clientes que recuperavam ofertas de redirecionamento com `includeContent=true ` não tinham o campo `redirectOptions` na carga da resposta. Essa inconsistência afetou os workflows, como cópia de oferta e criação de atividade. As ofertas de redirecionamento agora incluem `redirectOptions` corretamente quando o conteúdo é solicitado. (TGT-53737)

+++

**[!DNL Recommendations]**

+++Ver detalhes

* **Rastreamento de cliques restaurado para [!UICONTROL atividades do Recommendations] criadas na interface atualizada.** Solução de um problema em que as atividades de [!UICONTROL Recomendações] criadas na interface atualizada não registravam o rastreamento de cliques, resultando em zero conversões relatadas. As atividades criadas na interface herdada rastrearam os cliques corretamente e relataram conversões conforme esperado. Essa correção garante que as atividades do Recommendations criadas na interface atualizada agora incluam os atributos de rastreamento corretos, restaurando o relatório de conversão e o alinhamento com as métricas do A4T. (TGT-53287)
* **Rastreamento de cliques restaurado para atividades de Recomendação.** Solução de um problema em que as atividades de [!UICONTROL Recomendações] criadas na interface atualizada não registravam o rastreamento de cliques, resultando em zero conversões relatadas. A interface herdada aplicou corretamente uma ID de rastreamento (`at-track-click`) ao conteúdo [!UICONTROL Recommendations], enquanto a interface atualizada inseriu por engano um espaço reservado (`__recsClickTrackIdPlaceholder__`), impedindo o rastreamento de back-end. Essa correção garante que o conteúdo do [!DNL Recommendations] agora inclua a ID de rastreamento correta, restaurando o relatório de conversão e o alinhamento com as métricas do A4T. (TGT-53496)
* **Falha resolvida no editor de coleção na interface atualizada.** Correção de um problema na interface atualizada do [!UICONTROL Visual Experience Composer] (VEC), em que abrir uma coleção no painel Editor resultava em falha na página com um TypeError: não é possível ler propriedades de indefinido (lendo &#39;customLocale&#39;). Este erro ocorreu em vários tipos de atividades, incluindo [!UICONTROL Recommendations] e testes A/B. (TGT-53703)
* **Opção para remover a coleção selecionada restaurada no VEC.** Correção de um problema no VEC em que os usuários só podiam substituir uma coleção selecionada em uma atividade [!UICONTROL Recommendations], mas não podiam removê-la totalmente. Essa limitação bloqueou casos de uso que exigem uma remoção limpa da coleção sem substituição. Essa correção apresenta uma opção clara para remover a coleção selecionada, permitindo maior flexibilidade na configuração da atividade e alinhamento com o comportamento da interface herdada. (TGT-53652)
* **As coleções de critérios personalizados agora são exibidas corretamente na interface do usuário do [!UICONTROL Recommendations].** Correção de um problema na interface do Recommendations em que as coleções criadas com o uso de critérios personalizados não exibiam resultados de produtos. Embora as coleções padrão baseadas em atributos funcionassem como esperado, as que usam filtros personalizados retornavam &quot;Nenhum resultado encontrado&quot; apesar das correspondências de catálogo válidas. Essa correção garante que as coleções que usam atributos personalizados agora sejam preenchidas corretamente na guia [!UICONTROL Produto], restaurando a funcionalidade completa para fluxos de trabalho de recomendações personalizadas. (TGT-53653)
* **Correção de um problema em que as coleções não exibiam produtos ao abrir a página [!UICONTROL Produtos] pela primeira vez.** Os clientes que acessam coleções na seção [!UICONTROL Recommendations] obtiveram resultados vazios do produto ao abrir a página [!UICONTROL Produtos] pela primeira vez. Esse problema era causado por um erro de backend na consulta do GraphQL, que não carregava dados do produto para coleções com critérios personalizados. O problema foi resolvido e os produtos agora são exibidos corretamente sem a necessidade de alternância de ambiente. (TGT-53694)
* **Correção de um problema em que as coleções não podiam ser removidas nas atividades [!UICONTROL Recommendations] baseadas em formulário.** Os clientes que criam atividades do [!UICONTROL Recommendations] usando o [!UICONTROL Experience Composer baseado em formulário] não puderam desmarcar uma coleção escolhida anteriormente. A interface exigia que uma coleção fosse selecionada antes de salvar, impedindo que os usuários revertessem para &quot;Todas as coleções&quot;. Esse comportamento foi atualizado para corresponder à funcionalidade do VEC, permitindo que os clientes salvem sem uma coleção selecionada e padronizando para &quot;Todas as coleções&quot;, conforme esperado. (TGT-53708)
* **Correção de um problema em que as promoções não podiam ser definidas pelo atributo devido à ausência de valores de regras de filtragem ou coleção.** Os clientes que configuram promoções por atributo no processo de criação de atividade encontraram um erro informando que uma promoção não tinha uma ID de coleção ou valores de regra de filtragem. Esse problema de validação bloqueava a progressão mesmo quando a configuração parecia concluída. Agora, as promoções podem ser salvas com sucesso quando configuradas por atributo. (TGT-53750)
* **Correção de um problema em que não era possível salvar atividades devido a nomes de experiência duplicados.** Os clientes encontraram um erro de entrada de usuário inválido ao salvar atividades que incluíam combinações específicas de critérios e designs. O erro foi acionado por nomes de experiência duplicados, mesmo quando a configuração parecia válida. Atividades com configurações distintas agora podem ser salvas sem conflitos de nomenclatura. (TGT-53805)
* **Correção de um problema em que a validação permanecia inválida para promoções configuradas por atributo.** Os clientes encontraram erros de validação persistentes ao configurar promoções por atributo no processo de criação de atividade, mesmo quando todos os campos obrigatórios estavam preenchidos corretamente. Esse problema foi causado pela lógica de validação incorreta no fluxo de trabalho [!UICONTROL Recommendations]. As promoções baseadas em atributos agora são validadas e salvas conforme esperado. (TGT-53811)
* **Correção de um problema em que a aplicação de uma promoção a uma atividade [!UICONTROL Recommendations] em tempo real gerava um erro.** Os clientes encontraram o erro &quot;Uma promoção não tem uma ID de coleção ou valores de regra de filtragem&quot; ao tentar aplicar uma promoção principal a uma atividade [!UICONTROL Recommendations] ativa, mesmo após fornecer detalhes de configuração válidos. As promoções agora podem ser aplicadas com sucesso a atividades ativas sem acionar erros de validação, garantindo uma experiência mais suave na interface atualizada de criação de atividades. (TGT-53738)
* **Correção de um problema em que os produtos não estavam visíveis em coleções na interface do usuário do [!UICONTROL Recommendations].** Clientes de um único locatário relataram que as listas de produtos não foram carregadas ao exibir determinadas coleções na seção [!UICONTROL Recomendações] da Nova interface do usuário. O problema foi resolvido temporariamente ao alternar ambientes, mas essa solução alternativa resultou em uma experiência do usuário ruim. As entidades do produto agora são carregadas de forma consistente sem exigir alternância de ambiente. (TGT-53783)
* **Correção de um problema em que os critérios e os designs não eram exibidos em uma linha na interface de criação de atividade.** Anteriormente, os critérios e designs no processo de criação de atividade eram mostrados em um formato compactado, dificultando a visualização e o gerenciamento de itens individuais por parte dos clientes. Cada critério e design agora aparecem em sua própria linha, melhorando a legibilidade e a usabilidade na interface atualizada. (TGT-53818)

+++

**Relatórios**

+++Ver detalhes

* A métrica **[!UICONTROL Receita total] agora é incluída nas exportações de CSV dos relatórios de atividades.** Solução de um problema na interface do usuário [!UICONTROL Visão geral] atualizada, em que a receita total era exibida corretamente na exibição do relatório de atividades, mas estava ausente na exportação de CSV, mostrando como $0. Essa discrepância impedia que os usuários dependessem de dados exportados para análises e relatórios offline. (TGT-53325)
* A métrica **[!UICONTROL Vendas totais] agora está incluída nas exportações CSV dos relatórios de atividades.** Correção de um problema na interface do usuário atualizada em que a métrica [!UICONTROL Vendas totais] aparecia corretamente na exibição do relatório de atividades, mas estava ausente na exportação de CSV. Essa discrepância impedia que os usuários acessassem dados completos de desempenho nos relatórios baixados. Essa correção garante que os valores de [!UICONTROL Vendas totais] agora sejam incluídos com precisão em exportações CSV, restaurando a consistência entre os relatórios no aplicativo e a análise offline. (TGT-53330)
* **Mensagens de erro aprimoradas para [!UICONTROL Exibição de gráfico] quando as métricas não estão habilitadas.** Correção de um problema no VEC em que a [!UICONTROL Exibição de gráfico] exibia uma mensagem genérica de &quot;Algo deu errado&quot; quando uma métrica solicitada não estava habilitada no conjunto de relatórios [!DNL Analytics] associado. Esse problema foi acionado por um erro `not_enabled_metric` na resposta do GraphQL de back-end. Essa correção substitui o erro vago por uma mensagem mais informativa que ajuda os usuários a identificar problemas de configuração no [!DNL Analytics], reduzindo a confusão e os escalonamentos de suporte desnecessários. (TGT-53577)
* **Correção de um problema em que a duração do relatório excedia o limite suportado de 90 dias.** Os clientes que usam o filtro &quot;[!UICONTROL Últimos X Dias]&quot; na seção [!UICONTROL Relatórios] puderam selecionar durações superiores a 90 dias, o que pode causar problemas de desempenho e dados incompletos. O filtro foi atualizado para aplicar um intervalo máximo de 90 dias, garantindo relatórios consistentes e confiáveis. (TGT-53795)
* **Correção de um problema em que os relatórios CSV de desempenho eram gerados usando o ambiente padrão em vez do ambiente selecionado.** Anteriormente, quando os clientes alteravam o ambiente nas configurações do relatório e geravam um relatório de desempenho, o CSV resultante continha dados do ambiente padrão em vez do ambiente selecionado.  A interface agora passa corretamente o parâmetro `environmentId`, garantindo que o relatório reflita o ambiente escolhido. Além disso, o tratamento de erros foi aprimorado. Se ocorrerem erros de GraphQL durante a geração de CSV, a interface do usuário agora exibirá uma mensagem de erro clara, em vez de produzir um arquivo CSV vazio. (TGT-53064)
* **Correção de um problema em que os relatórios do Analytics for Target (A4T) não exibiam dados na [!UICONTROL Exibição de gráfico].** Os clientes que usam o [!DNL Target] com integração A4T encontraram um erro &quot;Algo deu errado&quot; ao alternar para o Modo de Exibição de Gráfico na guia Relatórios das atividades de teste A/B. Embora a [!UICONTROL Exibição de Tabela] tenha sido carregada corretamente, a [!UICONTROL Exibição de Gráfico] falhou ao renderizar tendências de métrica durante o intervalo de tempo selecionado. A [!UICONTROL Exibição em gráfico] agora exibe dados de desempenho conforme esperado para todas as métricas suportadas, melhorando a visibilidade e a precisão dos relatórios na interface atualizada. (TGT-53573)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes

* **Os metadados do elemento agora estão visíveis ao passar o mouse no menu de navegação estrutural.** Menu de navegação estrutural aprimorado no VEC para mostrar detalhes adicionais do elemento, como ID, classe e nome, ao passar o mouse sobre um item. Esse aprimoramento ajuda os usuários a identificar e diferenciar elementos com mais facilidade durante a configuração da atividade. (TGT-53409)
* **A navegação estrutural focalizada agora destaca o elemento correspondente no VEC.** O [!UICONTROL Visual Experience Composer] foi aprimorado para realçar o elemento correspondente no editor ao passar o mouse sobre os itens no menu de navegação estrutural. O tipo de elemento também é exibido, como container, texto em negrito ou botão. Esse comportamento se aplica a elementos irmãos e exclui tipos não compatíveis, como o SVG, com base na lista de validação. (TGT-53411)
* **Alerta de alterações não salvas restaurado nos fluxos de trabalho de modificação do VEC.** Correção de um problema no VEC em que os usuários não eram mais notificados sobre alterações não salvas em modificações de código personalizadas. Diferentemente da interface herdada, a nova experiência não tinha prompts ao sair ou fechar o editor de personalização, o que levou à perda acidental de progresso. Essa correção restaura os alertas para todos os tipos de modificação, incluindo o código personalizado, e garante que os usuários sejam avisados antes de sair sem salvar. (TGT-53435).
* **As alterações no código personalizado agora persistem durante a atualização da página no VEC.** Correção de um problema no VEC em que as modificações de código personalizadas eram perdidas durante as atualizações do site. Esse problema ocorria em páginas com vários recarregamentos, fazendo com que o editor redefinisse e revertesse as alterações não salvas. A correção garante que as edições de código personalizadas permaneçam intactas, mesmo que a página seja recarregada durante a edição, evitando a perda acidental de progresso. (TTGT-53501)
* **Problema de logon resolvido para acesso ao site no VEC.** Correção de um problema em que os usuários não conseguiam fazer logon em seus sites ao acessá-los por meio do VEC. O fluxo de logon redirecionava os usuários repetidamente para a página de logon, impedindo a configuração e a pré-visualização da atividade. Essa correção garante que o VEC não interfira mais no comportamento de logon, restaurando o acesso esperado para usuários autenticados. (TGT-53524)
* **Problema de duplicações de cookies resolvido na extensão do VEC Helper.** Correção de um problema em que a extensão [!UICONTROL Auxiliar de edição visual da Adobe Experience Cloud] duplicava o cookie `at_qa_mode` durante o controle de qualidade por meio de links de visualização. Ao alternar manualmente os índices de visualização, vários cookies foram criados com valores conflitantes entre os domínios, impedindo que os testadores alternassem variantes de forma confiável. Esse comportamento foi observado mesmo fora da interface do usuário do Target e afetou as contas internas e das contas do cliente. Essa correção garante a manipulação consistente de cookies, evitando entradas duplicadas e alinhando o escopo do domínio, permitindo a alternância de variante sem interrupção, sem a necessidade de limpeza manual de cookies. (TGT-53579)
* **Correção de um problema em que clicar em elementos em uma determinada página inicial causava vazamentos de memória.** Os clientes que criam atividades nesta página inicial experimentaram vazamentos de memória ao interagirem com elementos da página. O problema estava vinculado a avisos de console excessivos e aumento do uso de memória em subquadros, particularmente relacionados a atributos srcset malformados. O uso de memória agora permanece estável durante a interação. (TGT-53761)
* **Correção de um problema em que o VEC falhava e exibia uma tela em branco ao carregar determinadas atividades.** Clientes de um locatário específico relataram que o editor falhou ao carregar atividades específicas. O VEC permaneceu preso na &quot;Aplicação de modificações iniciais&quot; antes de travar e mostrar uma tela em branco. O VEC agora carrega atividades afetadas sem erros no processo de criação de atividades atualizado. (TGT-52932)
* **Correção de um problema em que o painel [!UICONTROL Gerenciar Conteúdo] das atividades do [!UICONTROL Automated Personalization] exibia rótulos de localização inconsistentes.** Os clientes relataram que o painel [!UICONTROL Gerenciar Conteúdo] mostrou números de localização incompatíveis nas guias [!UICONTROL Experiências] e [!UICONTROL Ofertas]. (por exemplo, Local 2 e Local 4 em Experiências, e Local 1 e Local 2 em Oferta) mesmo quando apenas dois locais foram configurados. Os rótulos de localização agora são consistentes e mapeados com precisão para modificações, melhorando a clareza e a usabilidade no processo de criação da atividade. (TGT-52934)
* **Correção de um problema em que as modificações no VEC eram perdidas após salvar.** Os clientes relataram que, após salvar uma modificação no VEC, a página atualizaria e reverteria a alteração para a versão anterior. Esse problema fazia com que as atualizações mais recentes fossem perdidas, a menos que toda a atividade fosse salva imediatamente. As modificações agora persistem corretamente após salvar e o editor não reverte mais as alterações inesperadamente, garantindo uma experiência confiável no fluxo de trabalho de criação da atividade. (TGT-53500)
* **Seleção de elemento aprimorada no VEC exibindo o tipo de elemento ao passar o mouse e a seleção.** Para melhorar a usabilidade durante a criação da atividade, o VEC agora decora os elementos do HTML com seu tipo quando focalizados ou selecionados. Esse aprimoramento ajuda os clientes a identificar e selecionar os elementos corretos com mais facilidade. Os elementos selecionados são realçados com uma cor distinta, e os elementos focalizados são contornados em azul. O tipo de elemento também é exibido, fornecendo um contexto mais claro durante a edição. (TGT-53502)

+++

### Atualizações de sequência de dados (19 de setembro de 2025)

A combinação da ID da sequência de dados e da sandbox deve ser exclusiva para [!DNL Adobe Target] conexões de destino.

Atualização da lógica de validação para conexões de destino [!DNL Target] para impor que a combinação da ID da sequência de dados e do nome da sandbox seja exclusiva em uma Organização IMS. Isso significa:

* O mesmo par de ID de fluxo de dados + nome de sandbox não pode ser reutilizado em várias conexões de destino [!DNL Target].
* A mesma ID de fluxo de dados pode ser usada para conexões diferentes somente se estiverem configuradas em sandboxes diferentes.
* Essa regra se aplica a todas as seleções de sequência de dados, incluindo quando &quot;Nenhum&quot; é selecionado.

Essa atualização garante uma configuração consistente e evita conflitos em ambientes de várias sandboxes. Para obter mais informações, consulte [conexão com o Adobe Target](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank} no guia *Destinos do Experience Platform*.

### [!DNL Target Standard/Premium] 25.9.1 (5 de setembro de 2025)

Esta versão inclui as seguintes atualizações e correções:

**[!UICONTROL Fragmentos de experiência]**

+++Ver detalhes

* **Atribuição de usuário aprimorada para [!UICONTROL Ofertas de Fragmento de experiência do AEM].** Solução de um problema no VEC em que o campo &quot;[!UICONTROL Última atualização]&quot; do [!UICONTROL Fragmento de experiência do AEM] (XF) oferece uma ID de código exibida incorretamente em vez do nome de usuário. Essa discrepância ocorreu durante a seleção da oferta na interface atualizada, criando inconsistência com a interface herdada e as ofertas do HTML, que mostravam corretamente o nome do último editor. Essa correção garante uma atribuição consistente do usuário em todos os tipos de oferta, melhorando a transparência e o alinhamento com o comportamento esperado. (TGT-52880 e TGT-52898)

+++

**Offer Decisioning**

+++Ver detalhes

* **Erro do Offer Decision resolvido para ofertas ODE.** Solução de um problema em que as ofertas de Mecanismo do Offer Decision (ODE) inseridas por meio do [!DNL Target] retornavam um erro 400 devido à falta de metadados de formato. A mensagem de erro indicou que o tipo MIME era nulo, impedindo o processamento bem-sucedido de decisões de oferta. Essa correção garante o manuseio adequado de metadados de oferta, restaurando a funcionalidade para a entrega de conteúdo personalizado e permitindo a execução ininterrupta de campanhas de marketing. (TGT-53635)
* **Problema de renderização de oferta ODS resolvido.** Solução de um problema em que as ofertas do [!DNL Offer Decision Service] (ODS) criadas pelo [!DNL Adobe Journey Optimizer] (AJO) não eram renderizadas quando as atividades eram criadas usando o VEC na interface atualizada. A mesma configuração funcionava corretamente na interface herdada, gerando confusão e bloqueando a execução da campanha. Essa correção garante uma entrega de oferta consistente em ambas as versões da interface do usuário, restaurando o comportamento esperado para personalização orientada pela AJO.

+++

**Relatórios**

+++Ver detalhes

* **Opção de download restaurada na seção de relatórios da interface de visão geral de relatórios atualizada.** Solução de um problema na nova interface de visão geral em que o botão [!UICONTROL Baixar] não estava na seção Relatórios, impedindo que os usuários exportassem pontuações de importância do atributo. Essa atualização restaura a funcionalidade completa de exportação, permitindo o acesso simplificado a dados para download para análise e relatórios. (TGT-53222)
* **[!UICONTROL Botão Baixar relatório CSV completo] restaurado no modo de exibição [!UICONTROL Atributos importantes].** Solução de um problema na interface de criação de atividade atualizada em que o botão [!UICONTROL Baixar relatório CSV completo] não estava presente na seção [!UICONTROL Atributos importantes] da exibição de relatórios. Essa correção restaura o acesso a insights baixáveis, garantindo uma funcionalidade consistente nas interfaces atualizadas e herdadas. (TGT-53238)
* **Problemas de interface resolvidos que afetam os relatórios do [!UICONTROL Direcionamento automático] na interface de visão geral atualizada.** Correção de vários problemas de interface do usuário na interface de visão geral atualizada que afetavam os relatórios de atividades do [!UICONTROL Direcionamento automático]. Essas correções incluem:

  * Métricas de aumento e confiança ausentes nos relatórios de resumo
  * Indicador de cor incorreto para a caixa de seleção &quot;modelos criados&quot;
  * Relatório de gráfico não funcional apesar da variação de dados em [!DNL Analytics]
  * Link de download ausente para os relatórios de [!UICONTROL Segmentos automatizados] e [!UICONTROL Atributos importantes]
  * Exibição de relatório de [!UICONTROL Segmentos automatizados] corrompidos

  Essas correções restauram o comportamento esperado dos relatórios e melhoram a visibilidade do desempenho do [!UICONTROL Direcionamento automático] na interface atualizada. (TGT-53484)

+++

**[!UICONTROL Visual Experience Composer]**

+++Ver detalhes

* **Validação de formulário corrigida para condições de presença de parâmetro na interface do usuário atualizada.** Foi resolvido um problema na interface do usuário atualizada em que a seleção de &quot;[!UICONTROL O valor do parâmetro de mbox personalizado está presente]&quot; ou &quot;[!UICONTROL O parâmetro está presente]&quot; exigia incorretamente que os clientes inserissem um valor. Esse comportamento entrou em conflito com a lógica pretendida, que simplesmente verifica a existência de um parâmetro independentemente de seu valor. A correção alinha a validação do formulário ao comportamento esperado, permitindo uma configuração de atividade mais suave e a adoção total da interface atualizada. (TGT-53638)
* **Lógica de formulário corrigida para regras de presença de parâmetro na entrega da página.&quot;** Correção de um problema na interface do usuário atualizada em que a seleção de regras de entrega de página, como &quot;[!UICONTROL Parâmetro está presente],&quot; &quot;[!UICONTROL Parâmetro não está presente],&quot;[!UICONTROL O valor do parâmetro está presente]&quot; ou &quot;[!UICONTROL O valor do parâmetro não está presente]&quot;, exigia incorretamente que os usuários inserissem um valor de parâmetro adicional. Esse comportamento era inconsistente com a interface herdada e contradizia a lógica pretendida de detectar a presença de parâmetros sem especificar um valor. Essa correção restaura o comportamento esperado de configuração da regra, simplificando a configuração da atividade e melhorando a usabilidade. (TGT-53640)
* **Lógica de validação aprimorada para o construtor de regras de várias páginas na interface atualizada.** Solução de vários problemas de validação no construtor de regras de várias páginas na interface atualizada. Essas correções incluem:

  * Como impedir a criação de regras quando o parâmetro da mbox está vazio
  * Exibição de mensagens de erro apropriadas para estados de regras inválidas
  * Correção da lógica de validação para operadores unários e baseados em parâmetros que não exigem valores de operando
  * Ativar regras de fragmento de hash com operadores unários restaurando a funcionalidade de salvar

  Essas atualizações garantem uma configuração de regra precisa e melhoram a usabilidade em cenários complexos de entrega de página. (TGT-53722)
* **Problema de renomeação de local resolvido em atividades A/B e MVT.** Correção de um bug na interface do usuário atualizada em que a renomeação de um local em uma atividade de [!UICONTROL Teste A/B] ou [!UICONTROL Teste multivariado] (MVT) não persistia após a navegação entre a lista de locais, o direcionamento e a versão posterior. Essa atualização garante que as alterações no nome da localização sejam salvas e refletidas de forma consistente em todo o fluxo de trabalho da atividade. (TGT-52367)
* **Persistência de nome de local corrigida para atividades MVT e AP na interface atualizada.** Solução de um problema na interface do usuário atualizada em que os nomes de locais editados nas atividades de [!UICONTROL Teste multivariado] (MVT) e [!UICONTROL Automated Personalization] (AP) não estavam sendo salvos corretamente. Após renomear um local, a navegação entre guias, como [!UICONTROL Direcionamento] e [!UICONTROL Experiências], fez com que os nomes fossem revertidos para seu estado anterior. Essa correção garante uma nomenclatura de localização consistente entre guias e melhora a confiabilidade durante a configuração da atividade. (TGT-52927)
* **O rótulo de local foi corrigido no painel gerenciar experiências para atividades MVT.** Solução de um problema na interface do usuário atualizada em que o painel [!UICONTROL Gerenciar experiências] nas atividades de [!UICONTROL Teste multivariado] (MVT) exibia uma numeração de local inconsistente. Essa correção garante que os rótulos de localização sejam sequenciais e alinhados corretamente com as modificações definidas pelo usuário, melhorando a clareza e a usabilidade durante a configuração da experiência. (TGT-52929)

+++

### [!DNL Target Standard/Premium] 25.8.4 (1º de setembro de 2025)

Esta versão inclui as seguintes atualizações e correções:

**[!UICONTROL Atividades]**

+++Ver detalhes

* **Os clientes não puderam copiar os nomes de atividades ou documentos da [!UICONTROL Visão geral da atividade]**: anteriormente, os clientes não conseguiam copiar o nome de uma atividade ou a oferta/documento associado diretamente da [!UICONTROL Visão geral da atividade] no processo de criação de atividades atualizado. Essa limitação afetou a usabilidade, especialmente em telas menores. Agora, os clientes podem copiar facilmente os nomes das atividades e dos documentos sem soluções alternativas. (TGT-51850)
* **Assimilação proativa de dados de clientes [!DNL Target] com curadoria durante a criação da atividade**: melhoria do processo de criação da atividade ao habilitar a coleta proativa de relatórios, conteúdo e capturas de tela de clientes [!DNL Target]. Esse aprimoramento aborda as lacunas de dados identificadas em casos de uso existentes e ajuda a garantir insights mais precisos durante a atividade e a configuração de experimentos. (TGT-52415)
* As atividades de **AP não buscaram dados prontos para modelo na seção [!UICONTROL Relatórios]**: os clientes que visualizam atividades de Automated Personalization (AP) na seção [!UICONTROL Relatórios] não conseguiram ver os indicadores prontos para modelo no nível do grupo de relatórios e da oferta. Esse problema ocorria porque os dados prontos para modelo não eram obtidos corretamente do back-end. A funcionalidade foi restaurada e os dados prontos para modelo agora são exibidos conforme esperado. (TGT-53600 e TGT-53601)
* **As atividades agendadas para o futuro exibiram incorretamente o status &quot;[!UICONTROL Online]&quot; na visão geral da [!UICONTROL Atividade]**: os clientes observaram que as atividades agendadas para iniciar no futuro foram marcadas incorretamente como &quot;[!UICONTROL Online]&quot; na visão geral da [!UICONTROL Atividade]. Esta incompatibilidade de status foi resolvida e as atividades agendadas agora são exibidas corretamente como &quot;[!UICONTROL Agendado]&quot; sem exigir uma atualização da página. (TGT-52835)

+++

**[!UICONTROL Recomendações]**

+++Ver detalhes

* A **Lista de produtos não estava visível na caixa de diálogo [!UICONTROL Exibir Coleção]:** anteriormente, os clientes não conseguiam ver a lista de produtos ao visualizar uma coleção na guia [!UICONTROL Recommendations]. A caixa de diálogo [!UICONTROL Exibir Coleção] agora exibe corretamente os produtos associados, melhorando a transparência e a usabilidade na interface atualizada do usuário do [!UICONTROL Recommendations]. (TGT-50531)
* **Correção de um problema que fazia com que a filtragem diferenciasse maiúsculas e minúsculas fosse aplicada na [!UICONTROL Pesquisa no Catálogo de Produtos], pesquisa avançada**: a filtragem de pesquisa avançada na página [!UICONTROL Pesquisa no Catálogo de Produtos] agora ignora corretamente a diferenciação entre maiúsculas e minúsculas, alinhando-se ao comportamento do back-end e dos serviços da GraphQL. Essa atualização garante resultados de sugestões consistentes e precisos para os clientes, independentemente da capitalização do texto. (TGT-53585)
* A **Pesquisa avançada na interface atualizada da [!UICONTROL Pesquisa no Catálogo de Produtos] não forneceu sugestões**: os clientes que usam o recurso de pesquisa avançada na interface atualizada da [!UICONTROL Pesquisa no Catálogo de Produtos] precisaram inserir valores exatos com ortografia correta, pois nenhuma sugestão foi exibida. Esse problema dificultava a localização eficiente dos produtos. Agora as sugestões são exibidas conforme esperado durante a entrada da pesquisa avançada. (TGT-52008)
* **Alguns aprovadores não puderam exibir produtos na [!UICONTROL Pesquisa de Catálogo de Produtos]**: Clientes com permissões de [!UICONTROL Aprovador] não puderam ver produtos na [!UICONTROL Pesquisa de Catálogo de Produtos], apesar de outros usuários com funções idênticas terem acesso. Esse problema foi causado por uma inconsistência de permissões que afetava a visibilidade do catálogo. Todos os aprovadores agora podem exibir produtos na seção [!UICONTROL Recommendations], conforme esperado. (TGT-53617)

+++ 

**[!UICONTROL Relatórios]**

+++Ver detalhes

* **Falha ao carregar relatórios para o público-alvo da área de trabalho devido a um erro de nome de público-alvo inválido**: os clientes encontraram um erro de GraphQL ao tentar exibir relatórios para o público-alvo no processo de criação de atividade. O sistema retornou uma mensagem &quot;Nome de público-alvo inválido: XXXXX&quot;, impedindo o acesso aos dados de relatórios. Agora os relatórios são carregados corretamente para o público-alvo da Área de trabalho. (TGT-53371)
* **A alternância de públicos-alvo na página Relatórios causou erros na interface do usuário de Destino**: os clientes encontraram erros ao selecionar determinados públicos-alvo na seção [!UICONTROL Relatórios]. Esse problema era causado pelo tratamento inválido de público nas chamadas de back-end do GraphQL, resultando em erros inesperados e dados ausentes. O problema foi resolvido e os públicos-alvo da área de trabalho agora são carregados sem erros, mesmo quando não há dados disponíveis. (TGT-53370)
* A **[!UICONTROL Exibição de gráfico] na seção [!UICONTROL Relatórios] não exibiu valores de[!DNL Analytics]**: os clientes que acessam a [!UICONTROL Exibição de gráfico] na seção Reportas encontraram dados ausentes, com todos os valores aparecendo como zero. Este problema foi causado pela recuperação de dados incorreta do [!UICONTROL Analytics]. A [!UICONTROL exibição em gráfico] agora exibe valores precisos conforme esperado. (TGT-52792)
+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* **Falha ao clicar em &quot;Aceitar Cookies&quot; usando o [!UICONTROL Enhanced Experience Composer] (EEC) devido a uma função ausente**: os clientes relataram que tentar aceitar cookies por meio do EEC resultava em um erro de console: `handleclickAcceptAllButton is not defined`. A funcionalidade de aceitação de cookies agora funciona conforme esperado, garantindo uma experiência mais suave durante a criação da atividade na interface atualizada. (TGT-52794)
* **A nova interface do EEC falhou ao carregar determinadas páginas que eram anteriormente compatíveis com a interface do usuário herdada**: os clientes relataram que o novo EEC não pôde carregar algumas páginas, que estavam acessíveis na interface do usuário herdada, apesar do código de interrupção de iframe presente no site. O processo de criação de atividade atualizado agora oferece suporte ao carregamento dessas páginas, restaurando a compatibilidade para fluxos de trabalho de criação de atividade. (TGT-53061)
* **O VEC exibiu uma tela em branco ao editar as experiências**: os clientes de um determinado locatário relataram que a tela do VEC ficava em branco ao tentar editar experiências no VEC atualizado. Esse problema afetava atividades recém-criadas e mais antigas, impedindo a continuidade do fluxo de trabalho. O VEC agora é carregado corretamente, permitindo que os clientes editem as experiências sem interrupção. (TGT-53547)
* **O VEC falhou e exibiu uma tela em branco ao carregar determinadas atividades**: os clientes de um determinado locatário relataram que o VEC falhou ao carregar atividades específicas. O editor de experiência permaneceu preso na &quot;Aplicação de modificações iniciais&quot; antes de travar e mostrar uma tela em branco. Erros de console indicaram uma falha na leitura de propriedades indefinidas. O editor agora carrega as atividades afetadas sem erros no VEC atualizado. (TGT-53548)
* **Limpar todos os valores de data usando o Backspace causou uma falha na página**: os clientes que agendavam atividades na seção [!UICONTROL Metas e Configurações] tiveram uma falha ao usar o Backspace para limpar todos os valores dos campos &quot;[!UICONTROL Data e Hora Especificadas]&quot;. Esse problema foi causado por um erro de referência nula na lógica de manipulação de datas. A página agora lida com as entradas de data vazias normalmente sem travar. (TGT-53624)
* **Nenhum produto apareceu na [!UICONTROL Pesquisa de Catálogo de Produtos] devido a uma carga inválida**: os clientes que acessam a seção [!UICONTROL Recomendações] da [!UICONTROL Pesquisa de Catálogo de Produtos] encontraram resultados vazios causados por uma carga inválida do GraphQL. Esse erro de backend impedia que os dados do produto fossem carregados corretamente. Os produtos agora são exibidos conforme esperado na interface atualizada. (TGT-53630)
* **[!DNL Scene7]imagens foram salvas com resolução mais baixa no VEC atualizado**: os clientes que editam experiências no VEC atualizado notaram que as URLs de imagem do [!UICONTROL Scene7] foram salvas sem parâmetros de resolução, resultando em imagens de qualidade mais baixa sendo entregues (400×400 em vez do 800×800 pretendido). Os URLs de imagem agora retêm os parâmetros corretos para garantir a resolução adequada. (TGT-52631)
* **atividades online ainda podem ser editadas no VEC**: os clientes puderam acessar opções de edição para atividades online no VEC atualizado, o que pode levar a alterações não intencionais. Esse problema foi resolvido desativando a funcionalidade de edição para atividades online. Os botões de edição agora estão ocultos na lista de atividades e na visão geral para editores, enquanto os aprovadores e outras funções permanecem inalterados. (TGT-53055)
* **Descomissionou a seção de atividades [!UICONTROL Falha] e [!UICONTROL Rascunho] no VEC atualizado**: as opções de atividades [!UICONTROL Falha] e [!UICONTROL Rascunho] foram removidas do VEC atualizado. A nova interface do usuário não é mais compatível com estados de rascunho e as campanhas com falha não são armazenadas no back-end. Essas opções não são mais relevantes. Filtros e campos de back-end relacionados (por exemplo, `uiSyncFailed`, `errorMessage`) também foram removidos para simplificar o gerenciamento de atividades. (TGT-53150)
* **Não é possível fazer logon no VEC para uma atividade**: os clientes que tentam fazer logon em seus sites por meio do VEC foram redirecionados repetidamente para a página de logon, impedindo o acesso à edição de atividades. Esse problema não era reproduzível internamente e pode ter sido relacionado ao manuseio de sessão no lado do site. O fluxo de logon foi estabilizado e os clientes agora podem acessar o VEC sem erros de redirecionamento. (TGT-53524)
* **Pressionar o botão Voltar duas vezes no modo [!UICONTROL Procurar] causou uma falha no VEC**: os clientes que navegavam pelo modo [!UICONTROL Procurar] no VEC travavam quando pressionavam o botão Voltar do navegador duas vezes. Esse problema fazia com que o editor congelasse e exigia uma atualização de página. O editor agora lida com a navegação de volta de forma confiável sem travar. (GT-53568)
* **Não foi possível editar as atividades devido a mapeamentos de local indefinidos**: os clientes encontraram um erro ao tentar editar atividades, causado por IDs de local indefinidas na lógica `LocationMapping.behaviorTargetedActivity`. Esse problema resultou em um erro 400 e bloqueou as atualizações de atividade. As atividades agora podem ser editadas sem erros de validação relacionados à localização. (TGT-53607)
* **O salvamento de atividades acionou um erro de entrada de usuário inválido**: os clientes encontraram um erro de entrada de usuário inválido ao tentar salvar atividades após fazer pequenas modificações no VEC atualizado. O erro foi causado por mapeamentos de localização incompatíveis na lógica de validação de back-end. Agora, as atividades podem ser salvas com sucesso sem acionar erros relacionados à localização. (TGT-53603)

+++

### [!DNL Target Standard/Premium] 25.8.3 (21 de agosto de 2025)

Esta versão inclui as seguintes atualizações e correções:

**[!UICONTROL Atividades]**

+++Ver detalhes

* **Correção de um problema em que o salvamento de atividades acionava um erro de entrada de usuário inválido devido a dados de propriedade malformados**: os clientes encontraram um erro crítico ao tentar salvar atividades existentes. A mensagem de erro indicava uma entrada de usuário inválida, referenciando especificamente um conteúdo de nome de propriedade não reconhecido na carga JSON. Notavelmente, novas atividades usando a mesma propriedade foram salvas com sucesso, sugerindo que o problema foi isolado aos dados de atividade herdados. O processo de criação de atividade agora lida corretamente com configurações de propriedade herdadas, evitando erros de entrada inválidos e garantindo um comportamento de salvamento consistente em atividades novas e existentes. (TGT-53507)
* **Correção de um problema que impedia os clientes de salvar uma atividade devido a um erro de InvalidProperty.Json**: os clientes encontraram um erro ao tentar salvar uma atividade na interface atualizada, mesmo sem fazer modificações. A mensagem de erro indicou uma estrutura JSON inválida: &quot;Json inválido. Nome de propriedade &#39;content&#39; não reconhecido. Local: linha - 1, coluna - 432.&quot; Esse problema foi causado por uma propriedade não reconhecida na carga da solicitação e agora foi resolvido. Os clientes podem salvar as atividades com sucesso sem encontrar esse erro. (TGT-53513)
* **Correção de um problema em que as atividades agendadas exibiam incorretamente um status [!UICONTROL Em tempo real] até a atualização da página**: os clientes observavam que, ao agendar uma atividade para entrar em funcionamento em uma data e hora futuras, o status aparecia imediatamente como [!UICONTROL Em tempo real] em vez de [!UICONTROL Agendado]. Isso causava confusão, mesmo que a mensagem de confirmação indicasse corretamente que a atividade estava programada. Atualizar a página corrigiu a exibição de status. Esse problema foi resolvido e as atividades agendadas mostram corretamente o status Agendado sem exigir uma atualização. (TGT-52937)

+++

**[!UICONTROL Analytics para Target] (A4T)**

+++Ver detalhes

* **Correção de um problema em que os clientes não podiam digitar nomes de conjunto de relatórios durante o processo de criação de atividade**: os clientes que usavam [!DNL Adobe Analytics] como fonte de relatórios durante o processo de criação de atividade não conseguiam digitar na lista suspensa [!UICONTROL Conjunto de relatórios] para procurar conjuntos de relatórios específicos. Isso afetou os fluxos de trabalho de organizações com um grande número de conjuntos de relatórios, em que a rolagem manual atrasava significativamente a configuração. A lista suspensa não era ordenada alfabeticamente e não respondia consistentemente à entrada digitada, dificultando a localização de conjuntos de relatórios como &quot;Office + Store - Web - Prod&quot;. Esse problema foi resolvido e os clientes agora podem pesquisar com eficiência digitando nomes de conjuntos de relatórios. (TGT-53345)

+++

**[!UICONTROL Públicos-alvo]**

+++Ver detalhes

* **Correção de um problema em que públicos-alvo com &quot;Intervalo de tempo&quot; expirados bloqueavam a gravação de atividades mesmo após a remoção**: os clientes não conseguiam salvar atividades na interface atualizada devido a um erro relacionado a públicos-alvo com &quot;Intervalo de tempo&quot; expirados. Mesmo após a remoção do público-alvo afetado, a mensagem de erro persistia: &quot;A atividade contém público-alvo com intervalo de tempo inválido&quot;. Esse problema ocorria porque o sistema continuava validando o público somente atividade, mesmo quando não estava mais em uso. O comportamento foi ainda mais complicado por discrepâncias de fuso horário. A lógica de validação foi corrigida e os clientes agora podem salvar atividades sem encontrar esse erro. (TGT-53517)

+++

**[!UICONTROL Fragmento de experiência]s**

+++Ver detalhes

* **Correção de um problema que impedia os clientes de inserir Fragmentos de Experiência usando [!UICONTROL Inserir Antes] ou [!UICONTROL Inserir Depois] na interface** Os clientes encontraram um erro ao tentar inserir [!UICONTROL Fragmentos de Experiência] em uma atividade usando as opções &quot;Inserir Antes&quot; ou &quot;Inserir Depois&quot; na interface atualizada. A mensagem de erro exibida foi: &quot;O conteúdo da oferta deve conter exatamente um elemento HTML&quot;. Esse problema era específico da interface atualizada e não ocorria na versão anterior. Esse problema foi resolvido e os clientes podem inserir [!UICONTROL Fragmentos de experiência] com êxito sem encontrar esse erro. (TGT-53442)

+++

**[!UICONTROL Decisões de oferta]**

+++Ver detalhes

* **Correção de um problema que impedia os clientes de editar ofertas de decisão e selecionar elementos de página específicos na interface atualizada**: no processo de criação de atividades atualizado, os clientes não conseguiam editar ofertas de decisão existentes ou selecionar elementos de página específicos no Visual Experience Composer (VEC). As ofertas de decisão eram exibidas incorretamente como ofertas do HTML e as alterações feitas durante a edição não eram salvas. Além disso, determinados URLs regionais, como o site do Japão, não foram carregados corretamente no VEC, bloqueando a criação e as atualizações da atividade. As ofertas de decisão agora são exibidas corretamente, os elementos da página podem ser selecionados conforme esperado e os URLs regionais são carregados corretamente no VEC, restaurando a funcionalidade de edição completa. (TGT-53425)
* **Correção de um problema em que os seletores [!UICONTROL Decisão de oferta] não podiam ser modificados e alterados inesperadamente após o salvamento**: no processo de criação de atividade atualizado, os clientes não conseguiam modificar o seletor [!UICONTROL Decisão de oferta] conforme pretendido. As tentativas de alterar o seletor não tiveram êxito e o seletor foi revertido para um valor incorreto após salvar. Esse comportamento fez com que a oferta de decisão desaparecesse do Visual Experience Composer (VEC), bloqueando mais edições. As alterações no seletor agora são preservadas corretamente e as ofertas de decisão permanecem visíveis e editáveis no VEC após salvar.(TGT-53433)
* **Correção de um problema em que [!UICONTROL Decisões de oferta] desapareceram da atividade após salvar**: [!UICONTROL Decisões de oferta] adicionadas durante o processo de criação da atividade não foram retidas após salvar e reabrir a atividade. Esse problema ocorria ao editar conteúdo dinâmico e inserir [!UICONTROL Decisões de oferta]com seletores e propriedades específicos. [!UICONTROL As Decisões de oferta] agora persistem corretamente após salvar, e os seletores permanecem intactos, garantindo um comportamento consistente de direcionamento e edição. (TGT-53434)

+++

**[!DNL Recommendations]**

+++Ver detalhes

* **Correção de um problema na interface do usuário [!DNL Recommendations] em que o download do CSV de critérios personalizados retornava o erro 404**: correção de um problema em que os clientes não conseguiam baixar o CSV de critérios personalizados no processo de criação de atividades. O link de download agora funciona corretamente, permitindo que os clientes exportem critérios personalizados conforme esperado. (TGT-51966)
* **Correção de carregamento de imagem inconsistente na [!UICONTROL Pesquisa no catálogo]**: correção de um problema em que as miniaturas e imagens na[!UICONTROL &#x200B; Pesquisa no catálogo] não eram carregadas de forma consistente no processo de criação da atividade. As imagens não eram exibidas a menos que a coluna &quot;URL da miniatura&quot; estivesse visível e algumas imagens do produto fossem carregadas parcialmente ou não fossem carregadas após as ações de navegação ou pesquisa. O comportamento de carregamento da imagem foi estabilizado e as miniaturas agora são exibidas de forma confiável, independentemente das ações de visibilidade da coluna ou de navegação. (TGT-52778)
* **Correção de um problema em que a edição de uma recomendação em uma experiência duplicada afetava a experiência original**: os clientes relataram que a modificação de uma recomendação em uma experiência duplicada alterava involuntariamente a experiência original. Especificamente, após a duplicação da Experiência B no processo de criação de atividade e a edição do design ou dos critérios, as mesmas alterações foram refletidas na Experiência B original, apesar de serem entidades separadas. As experiências duplicadas agora mantêm configurações separadas, garantindo que as edições em uma experiência não afetem a original. (TGT-53369)
* **Correção de um problema em que as alterações em uma experiência duplicada afetavam involuntariamente a experiência original em uma atividade**: os clientes relatavam que, ao duplicar uma experiência em uma atividade e atribuir um novo público-alvo, todas as alterações feitas no design ou nos critérios da experiência duplicada também eram refletidas na experiência original. Esse problema ocorria mesmo se nenhuma edição fosse feita diretamente na versão original, afetando a capacidade de criar variações independentes na mesma atividade. O processo de criação de atividade agora isola corretamente as experiências duplicadas, garantindo que as edições feitas em uma experiência não afetem a original. (TGT-53361)
* **Correção de um problema em que o [!UICONTROL Catálogo de Recomendação] falhava intermitentemente em exibir dados completos de atributos do produto**: na interface do usuário atualizada [!DNL Recommendations], os clientes tinham um problema em que determinados atributos de produto, como a mensagem, não eram exibidos de forma consistente nos resultados da [!UICONTROL Pesquisa de Catálogo], mesmo que os dados existissem no feed. Esse problema exigia que os clientes reconfigurassem manualmente a visibilidade da coluna para recuperar os valores ausentes. A [!UICONTROL Pesquisa no catálogo] agora exibe de forma confiável todos os atributos configurados, eliminando a necessidade de redefinições manuais de coluna. (TGT-52769)
* **Correção de um problema em que uma [!UICONTROL Promoção principal] não podia ser desabilitada em uma atividade online**: as tentativas de desabilitar uma [!UICONTROL Promoção principal] em uma atividade online não foram salvas. Depois de selecionar [!UICONTROL Alterar promoção] e desabilitá-la, a promoção permaneceu ativa ao editar novamente a atividade, impedindo atualizações nas configurações de recomendação. As configurações de promoção agora são salvas corretamente, permitindo que os clientes desativem ou modifiquem promoções em atividades ativas, conforme esperado. (TGT-53231)
* **Correção de um problema em que a habilitação de uma [!DNL Recommendations] [!UICONTROL Promoção] sem dados acionava uma mensagem de erro não clara**: a habilitação de uma [!UICONTROL Promoção principal] ou [!UICONTROL Promoção secundária] em uma atividade [!DNL Recommendations] sem especificar os valores necessários resultou em uma mensagem genérica de &quot;Erro de entrada inválido&quot;. O problema subjacente era um campo de configuração ausente, mas a mensagem de erro não indicava claramente a causa, dificultando a solução de problemas. O processo de criação de atividades agora fornece uma mensagem de erro clara e acionável quando campos obrigatórios, como `collectionId` ou regras, estão ausentes, ajudando os clientes a identificar e resolver rapidamente problemas de configuração. (TGT-52616)
* **Correção de um problema que impedia a exibição da lista de [!UICONTROL Produtos] no modal [!UICONTROL Editar] da guia [!UICONTROL Recomendações]**: os clientes não conseguiam exibir a lista de produtos filtrada ao editar uma [!UICONTROL coleção] ou uma [!UICONTROL exclusão] na guia [!UICONTROL Recomendações]. Esperava-se que a lista fosse atualizada em tempo real com base nas regras aplicadas, mas ela não parecia como esperado. Esse problema foi resolvido e a lista de produtos agora é exibida corretamente e atualizada dinamicamente à medida que as regras são modificadas. (TGT-53481)
* **Correção de um problema com o layout da caixa de diálogo Exibir Detalhes na interface do usuário atualizada**: o layout da modal Exibir Detalhes na interface do usuário atualizada foi modificado para melhorar a clareza e a usabilidade. A caixa de diálogo agora inclui duas guias:
  * Guia [!UICONTROL Detalhes]: exibe todas as informações relevantes para o item selecionado.
  * Guia [!UICONTROL Inventário]: mostra todos os produtos filtrados pelas regras atuais de coleta e exclusão.

  Esse aprimoramento ajuda os clientes a navegar e entender com mais facilidade os dados específicos do item e o contexto do inventário no processo de criação da atividade. (TGT-53503)

  * **Correção de um problema em que as promoções removidas nas atividades de recomendação reapareciam após o salvamento**: os clientes relatavam que quando as promoções [!UICONTROL front] ou [!UICONTROL back] eram removidas das atividades [!DNL Recommendations] e a atividade era salva, as promoções continuavam a aparecer após a reabertura. Esse problema ocorria nos ambientes de preparo e produção e afetava o processo de criação de atividade atualizado. O problema foi resolvido. As promoções removidas de uma atividade agora persistem corretamente após salvar. (TGT-53490)

+++

**Relatórios**

+++Ver detalhes

* **Correção de um problema em que o relatório de [!UICONTROL Segmentos automatizados] exibia valores nulos de público-alvo**: os clientes relatavam que os [!UICONTROL Segmentos automatizados] dos relatórios de atividades mostravam valores nulos de público-alvo, impedindo uma análise precisa do desempenho do segmento. Este problema ocorria ao acessar a seção [!UICONTROL Relatórios] e selecionar [!UICONTROL Segmentos Automatizados], mesmo que dados válidos de público-alvo fossem esperados. [!UICONTROL Os Segmentos automatizados] agora exibem corretamente os valores de público-alvo, garantindo informações confiáveis de relatórios e segmentação. (TGT-52793)

+++

**Aplicativos de Página Única (SPAs)**

+++Ver detalhes

* **Correção de um problema em que a alternância entre os modos [!UICONTROL Procurar] e [!UICONTROL Design] redefinia o estado do SPA na interface do usuário atualizada**: os clientes relataram que a alternância entre os modos [!UICONTROL Procurar] e [!UICONTROL Design] na interface do usuário atualizada fazia com que o editor da Web fosse recarregado, redefinindo o estado dos SPAs. Esse problema interrompeu os fluxos de trabalho e exigiu que os clientes inserissem as informações novamente. O problema foi resolvido. O estado do SPA agora é preservado ao alternar entre modos, garantindo uma experiência mais suave e consistente durante a criação da atividade. (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* **Correção de um problema no processo de criação de atividade que bloqueava a progressão para a etapa [!UICONTROL Direcionamento] nas atividades de AP**: correção de um problema no processo de criação de atividade em que os clientes não conseguiam prosseguir para a etapa [!UICONTROL Direcionamento] nas atividades de [!UICONTROL Automated Personalization] (AP), a menos que dois locais fossem adicionados. Esse comportamento foi diferente da experiência anterior, onde um único local com várias ofertas era suficiente. O requisito foi corrigido, permitindo que os clientes continuem usando configurações de local único como parte de seus workflows de AP. (TGT-53426)
* **Correção de um problema em que o novo processo de criação de atividade não definia o parâmetro fmt=png-alpha para imagens transparentes**: na interface atualizada, as imagens inseridas durante o processo de criação da atividade não incluíam mais o parâmetro `fmt=png-alpha` por padrão, resultando em perda de transparência. Esse comportamento foi diferente da interface anterior, que anexava automaticamente o parâmetro aos URLs de imagem, preservando planos de fundo transparentes. O processo de criação de atividade agora aplica corretamente o parâmetro `fmt=png-alpha` a URLs de imagem quando a transparência é necessária, garantindo uma renderização consistente de ativos transparentes. (TGT-52615)
* **Correção de um problema que impedia os clientes de pesquisar conjuntos de relatórios na interface atualizada**: Na interface atualizada, a lista suspensa [!UICONTROL Conjuntos de relatórios], na seção [!UICONTROL Metas e configurações], não permitia que os clientes digitassem e pesquisassem, dificultando a localização de conjuntos de relatórios específicos, especialmente para locatários com um grande número de entradas. Diferentemente da interface anterior, a lista não era classificada e não tinha filtragem baseada em entrada. Esse problema foi resolvido. Agora os clientes podem digitar para pesquisar e filtrar conjuntos de relatórios, restaurando a funcionalidade disponível na interface herdada. (TGT-53514)

+++

**[!UICONTROL Espaços de trabalho]**

+++Ver detalhes

* **Correção de um problema em que um cliente restrito a um único espaço de trabalho poderia exibir atividades de outros espaços de trabalho**: clientes com acesso limitado a um espaço de trabalho podiam exibir inesperadamente atividades em todos os espaços de trabalho ao selecionar [!UICONTROL Todos os Espaços de Trabalho] no processo de criação da atividade. Essa visibilidade apresentava um risco de alterações não intencionais em atividades ativas em outros espaços de trabalho, possivelmente afetando o desempenho do site. Os controles de acesso do Workspace foram reforçados para garantir que os clientes possam visualizar e interagir somente com as atividades no espaço de trabalho atribuído. (TGT-53101)
* **Correção de um problema em que um cliente podia exibir atividades da [!UICONTROL Workspace Padrão] sem ter acesso:** Um cliente com acesso limitado ao espaço de trabalho de preparo podia exibir atividades da [!UICONTROL Workspace Padrão] por meio do processo de criação de atividades. Esse comportamento ocorreu apesar da configuração correta do back-end e dos direitos de acesso. Os controles de acesso do Workspace foram reforçados para garantir que os clientes possam visualizar as atividades somente no espaço de trabalho atribuído.(TGT-53297)

+++

### [!DNL Target Standard/Premium] 25.8.2 (14 de agosto de 2025)

Esta versão do inclui as seguintes correções e atualizações:

**[!UICONTROL Atividades]**

+++Ver detalhes

* **Correção de um problema de carregamento de atividade na [!DNL Target] interface atualizada**: correção de um problema na [!DNL Target] interface atualizada em que determinadas atividades não eram carregadas ao tentar editar. Esse problema fazia com que os clientes deixassem os usuários em uma tela de carregamento indefinida. Esse problema afetou várias atividades e foi relatado para ocorrer de forma inconsistente entre os clientes. Com essa correção, as atividades afetadas agora são carregadas corretamente, permitindo uma edição perfeita e reduzindo a interrupção dos workflows de atividades. (TGT-53209)
* **Correção de um erro de salvamento no processo de criação de atividade devido à `optionLocalId` validação**: correção de um problema no processo de criação de atividade que impedia os clientes de salvar alterações devido a um erro de validação de back-end: `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:` Esse problema ocorria ao modificar elementos específicos em uma atividade, resultando em uma falha na operação de salvamento. A correção garante que as referências do `optionLocalId` agora sejam validadas corretamente, permitindo que os clientes salvem as atividades sem encontrar esse erro. (TGT-53293)
* **Correção de uma falha no processo de criação de atividade causada por referências de opção inválidas ao alternar páginas**: correção de um problema no processo de criação de atividade que causava uma falha na interface do usuário após alternar páginas três vezes durante a edição. A falha foi acionada por referências de opção inválidas, resultando em erros de console, como &quot;Opção com localId &#39;7&#39; não encontrada&quot;. Com essa atualização, os clientes agora podem alternar entre páginas e aplicar modificações sem encontrar falhas ou interrupções do sistema. (TGT-53295)
* **Correção de um erro de salvamento no processo de criação de atividade causado por entradas de usuário inválidas ao editar experiências**: correção de um problema no processo de criação de atividade em que os clientes não conseguiam salvar as alterações em uma atividade devido a um erro de entrada de usuário inválido. O erro ocorria ao modificar experiências na interface atualizada, impedindo que as atualizações fossem confirmadas. A atividade agora pode ser salva com sucesso, permitindo que os clientes editem e publiquem sem interrupção. (TGT-53267)
* **Correção de um problema de carregamento no processo de criação de atividade que bloqueava a edição na interface atualizada**: correção de um problema no processo de criação de atividade em que os clientes não conseguiam editar atividades na interface atualizada devido a uma tela de carregamento contínuo. Agora, os clientes podem abrir e modificar atividades sem encontrar falhas de carregamento. (TGT-53415)
* **Correção de um problema de requisito de experiência no processo de criação de atividades para atividades de AP na interface atualizada**: correção de um problema no processo de criação de atividades, no qual as atividades de [!UICONTROL Automated Personalization] (AP) exigiam dois locais em vez de duas experiências na interface atualizada. Esse comportamento bloqueou casos de uso em que os clientes configuravam um único local com várias ofertas, que eram compatíveis anteriormente. O requisito foi corrigido para corresponder à funcionalidade original, permitindo que os clientes continuem com atividades AP usando duas experiências, independentemente da contagem de localização. (TGT-53429)
* **Corrigido o comportamento do campo de elementos rastreados no modo de rastreamento de cliques para evitar que entradas não fossem salvas e aumentar a clareza**: corrigido um problema no processo de criação de atividades em que o campo [!UICONTROL Elemento rastreado] no modo [!DNL Click Track] era editável, mas não mantinha o nome inserido, causando confusão para os clientes. O campo agora está desativado para impedir entradas não salvas e a nomeação de elementos selecionados foi esclarecida para melhorar a configuração de metas e a precisão do rastreamento.** (TGT-53458)
* **Corrigido um problema no processo de criação de atividades que bloqueava a nomeação de componentes rastreados no modo [!UICONTROL Rastrear]**: corrigiu um problema no processo de criação de atividades em que os clientes não conseguiam nomear componentes rastreados no modo [!UICONTROL Rastrear]. Depois de inserir um nome, o campo parecia editável, mas não retinha a entrada, padronizando para rótulos genéricos como &quot;MY PRIMARY GOAL 0&quot; no modo de edição. O campo de elemento rastreado agora está desativado e o comportamento de nomenclatura foi esclarecido para melhorar a configuração da meta e a precisão do rastreamento. (TGT-51396)

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

**[!UICONTROL Recomendações]**

+++Ver detalhes

* **Correção de um problema na interface do usuário da pesquisa de catálogo em que a pesquisa avançada não fornecia sugestões**: correção de um problema na nova interface do usuário da [!UICONTROL Pesquisa de Catálogo] em que o recurso [!UICONTROL Pesquisa Avançada] não fornecia sugestões. Os usuários precisavam inserir valores exatos com ortografia precisa, tornando a experiência de pesquisa complicada e sujeita a erros. Com essa correção, a [!UICONTROL Pesquisa avançada] agora oferece sugestões relevantes à medida que os usuários digitam, melhorando a usabilidade e reduzindo o atrito na localização de produtos. (TGT-52008)
* **Solução de vários problemas de filtragem e interface de usuário para melhorar a capacidade de resposta e a interação com a entidade**: solução de vários problemas, incluindo capacidade insuficiente de resposta dos detalhes dos critérios em dispositivos de tela pequena, falta de resultados ao selecionar &quot;Todos os grupos de hosts&quot; no filtro Ambiente e incapacidade de interagir com entidades sem nome. Essas correções melhoram a usabilidade em tamanhos de tela, garantem uma filtragem precisa e permitem a interação total com todas as entidades do produto, melhorando a experiência geral para os usuários. (TGT-52992)
* **Correção de IDs de produtos ausentes na exibição detalhada do Recommendations durante a criação da atividade**: correção de um problema no processo de criação de atividades do [!DNL Recommendations], em que as IDs de produtos estavam ausentes na tela de detalhes do produto, dificultando aos clientes a cópia ou a referência às IDs de produtos durante fluxos de trabalho. As IDs de produto agora aparecem claramente na visualização de detalhes, melhorando a visibilidade e oferecendo suporte a um gerenciamento de produtos mais eficiente para os clientes. (TGT-51964)
* **Correção de um problema no processo de criação de atividade em que as mensagens do produto não eram exibidas na exibição de recomendações**: correção de um problema no processo de criação de atividade em que a coluna [!UICONTROL Mensagem] na exibição [!DNL Recommendations] não exibia dados do produto, mesmo que as mensagens estivessem presentes. Os clientes tinham que remover e adicionar novamente a coluna manualmente para revelar temporariamente o conteúdo, que muitas vezes desaparecia novamente ao rolar ou pesquisar. Essa atualização restaura a visibilidade consistente das mensagens do produto, melhorando a navegação no catálogo e os workflows de revisão. (TGT-52777)
* **Correção de um problema no processo de criação de atividade em que a seleção de &#39;Todos os grupos de hosts&#39; não retornava resultados na exibição de recomendações**: correção de um problema no processo de criação de atividade em que a seleção do ambiente &quot;Todos os grupos de hosts&quot; na exibição [!DNL Recommendations] não retornava resultados. Os clientes agora podem visualizar os dados do produto em todos os grupos de hosts conforme esperado, melhorando a visibilidade e a precisão do filtro durante a configuração da atividade. (TGT-53006)
* **Correção de um problema no processo de criação de atividade em que a alternância de promoção frontal não persistia após salvar**: correção de um problema no processo de criação de atividade em que a desabilitação da alternância de promoção frontal nas configurações de atividade não persistia após salvar. Os clientes que tentaram remover a promoção principal descobriram que o botão de alternância era reativado ao revisitar a atividade, impedindo a personalização adequada. Essa atualização permite que as alterações sejam salvas de forma confiável, dando aos clientes controle total sobre as configurações de promoção. (TGT-53215)
* **Corrigido a classificação inconsistente por [!UICONTROL Coluna Última atualização]:** Corrigido um problema no processo de criação de atividade, onde a classificação do catálogo pela coluna [!UICONTROL Última atualização] gerava resultados inconsistentes. Os clientes não conseguiam organizar de forma confiável os dados do produto com base nos carimbos de data e hora de atualização, dificultando a análise e o gerenciamento do catálogo. A classificação agora funciona conforme esperado, melhorando a precisão e a usabilidade na interface atualizada. (TGT-53116)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes

* **Corrigido o carregamento de atividades e os problemas com o botão [!UICONTROL Cancelar] no processo de criação de atividades**: corrigiu um problema no processo de criação de atividades onde certas atividades não eram carregadas, deixando os clientes impossibilitados de acessar modificações. Além disso, o botão [!UICONTROL Cancelar] não respondia, impedindo que os clientes interrompessem o processo de carregamento ou saíssem da exibição de edição. Essa correção garante que as atividades agora sejam carregadas de forma confiável, e o botão [!UICONTROL Cancelar] funcione conforme esperado, melhorando a estabilidade geral e a experiência do usuário no Visual Experience Composer. (VEC)(TGT-53218)
* **Correção de um problema de alternância de experiência na interface atualizada do VEC que bloqueava a edição e desabilitava o botão [!UICONTROL Cancelar]**: correção de um problema na interface atualizada do VEC em que as modificações falhavam ao carregar ao alternar entre experiências em uma atividade de Direcionamento de Experiência (XT). Os clientes não puderam editar experiências além da que inseriram inicialmente, e o botão [!UICONTROL Cancelar] estava ausente ou sem resposta. Essa correção garante que as modificações agora sejam carregadas corretamente em todas as experiências e que o botão [!UICONTROL Cancelar] funcione de maneira confiável, mesmo sem a extensão Auxiliar, melhorando a edição de fluxos de trabalho e reduzindo a frustração. (TGT-53256)
* **Correção de um problema de tela branca ao alternar entre várias experiências no processo de criação de atividade**: correção de um problema em que a alternância entre várias experiências causava uma tela branca. Também foi corrigido um problema no processo de criação de atividade em que os clientes encontravam uma tela branca ao tentar modificar várias experiências em uma atividade. Esse problema ocorria após aplicar alterações em duas experiências e selecionar uma terceira experiência, impedindo mais edições. A atualização garante transições tranquilas entre experiências, permitindo que os clientes façam modificações sem interrupção. (TGT-53266)
* **Correção de um problema no VEC em que as alterações de código personalizado não eram salvas de forma confiável nas sessões de edição**: correção de um problema em que as modificações de código personalizado feitas no Visual Experience Composer (VEC) não eram salvas de forma confiável em uma única tentativa. Os clientes relataram que alterações, como atualizações de estilo ou edição do HTML, estavam ausentes intermitentemente do site e dos URLs de controle de qualidade, mesmo após usar os botões [!UICONTROL Editar conteúdo] e [!UICONTROL Salvar] final. Essa regressão foi resolvida, garantindo que todas as alterações no código personalizado persistam conforme esperado nas sessões de edição.** (TGT-53418)
* **Correção de `triggerViews` ausente na interface atualizada durante a criação da atividade**: correção de um problema no processo de criação da atividade em que `triggerViews` não aparecia na interface atualizada, mesmo que ela estivesse implementada corretamente na página. Isso afetou vários clientes e dificultou a validação de acionadores baseados em visualização durante a configuração da atividade. O `TriggerViews` agora é exibido conforme esperado, permitindo que os clientes concluam e testem suas configurações de forma confiável. (TGT-53239)
* **Correção de um problema de carregamento de exibição no processo de criação de atividade para páginas da Web específicas na interface do usuário atualizada**: correção de um problema no processo de criação de atividade em que as exibições não eram carregadas na interface do usuário atualizada para páginas da Web específicas, apesar de estarem corretamente implementadas e visíveis nas chamadas de entrega ou de interação. Isso afetou vários clientes e dificultou a validação do direcionamento baseado em visualização. As exibições agora são preenchidas de forma consistente em todas as páginas compatíveis, melhorando a confiabilidade durante a configuração da atividade. (TGT-53246)
* **Correção de um problema intermitente de carregamento de exibição no processo de criação de atividade na interface do usuário atualizada**: correção de um problema no processo de criação de atividade, em que as exibições falhavam intermitentemente ao aparecer na interface do usuário atualizada durante a edição da atividade. Embora o nome de exibição correto estivesse presente na carga da rede, ele não era reconhecido consistentemente na interface, afetando a capacidade dos clientes de configurar a personalização baseada na visualização. As exibições agora são exibidas de forma confiável, oferecendo suporte a fluxos de trabalho de configuração e validação mais suaves. (TGT-53223)
* **Correção de um problema no processo de criação de atividades em que os nomes das ações rastreadas não eram salvos na interface atualizada**: correção de um problema no processo de criação de atividades em que as métricas das ações rastreadas não podiam ser salvas na interface atualizada. Depois de nomear um elemento rastreado e salvar a atividade, o nome era redefinido para um rótulo padrão quando reaberto, causando confusão e interrompendo a configuração da meta. As ações rastreadas agora mantêm seus nomes atribuídos, permitindo que os clientes definam e gerenciem métricas de conversão com precisão. (TGT-53453)

+++

### [!DNL Target Standard/Premium] 25.8.1 (7 de agosto de 2025)

Essa versão inclui os seguintes aprimoramentos e correções:

**Atividades**

+++Ver detalhes

* Correção de vários problemas com a interface atualizada, incluindo erros ao excluir tipos de página devido ao espaçamento nos valores de entrada, atividade não confiável de cópia entre espaços de trabalho e regras de entrega de página com defeito em ambientes de controle de qualidade. (TGT-52703)
* Correção de um problema na interface atualizada do usuário [!DNL Target], em que os usuários com a função de [!UICONTROL Editor] podiam acessar e tentar editar atividades ativas, que deveriam ser restritas. As telas lista de atividades e visão geral exibiam incorretamente as opções de edição para atividades ativas, resultando em possíveis alterações não intencionais. (TGT-53055)
* Correção de um problema na interface do usuário da [!UICONTROL Pesquisa Avançada] em que a seleção dos operadores &quot;valor está presente&quot; ou &quot;valor não está presente&quot; solicitava aos usuários que inserissem um operando, que não deveria ser necessário para essas condições. (TGT-51961)
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
* Correção de um problema na interface do usuário atualizada do [!DNL Target], em que as modificações de oferta do HTML feitas no [!UICONTROL Visual Experience Composer] (VEC) não persistiam após navegar da guia [!UICONTROL Direcionamento] de volta para [!UICONTROL Experiências]. (TGT-52874)
* Correção de um problema na interface atualizada do usuário [!DNL Target] em que inserir uma oferta do HTML antes e outra depois do mesmo seletor causava a geração de localização incorreta. Quando os clientes retornaram da guia [!UICONTROL Direcionamento] para a guia [!UICONTROL Experiência], apenas um seletor foi retido, resultando em modificações perdidas e entrega de conteúdo com falha. Esse comportamento diferiu da interface herdada, que preservou corretamente ambas as modificações com identificadores de localização distintos. (TGT-52891)
* Correção de um problema na interface do usuário atualizada [!DNL Target] em que um clique em uma oferta adicionada no painel [!UICONTROL Modificações] fazia com que o painel [!UICONTROL Configuração] direito aparecesse e desaparecesse intermitentemente, dificultando a interação com as configurações da oferta. (TGT-53288)
* Correção de um problema em que as ofertas do HTML adicionadas a variações específicas de público-alvo em uma atividade não eram salvas de forma consistente ou exibidas na seção de modificação. Depois de alternar entre públicos durante a edição, as ofertas aplicadas anteriormente às vezes desapareciam ou não eram renderizadas, interrompendo a validação e atrasando a preparação da atividade. (TGT-53440)
* Correção de um problema em que copiar uma atividade que incluía ofertas resultava na criação de ofertas duplicadas na nova atividade. Esse comportamento causava desordem e confusão desnecessárias, principalmente ao mover atividades entre espaços de trabalho. A correção garante que as ofertas do [!DNL Target] sejam copiadas corretamente para o espaço de trabalho de destino sem duplicação, simplificando o gerenciamento de atividades e melhorando a eficiência do fluxo de trabalho. (TGT-53454)

+++

**Aplicativos de Página Única (SPAs)**

+++Ver detalhes

* Correção de um problema no VEC atualizado que impedia os clientes de aplicar modificações nas exibições de [!UICONTROL Aplicativo de página única] (SPA). Embora as atividades criadas na interface antiga fossem compatíveis com o direcionamento específico à visualização, a nova interface não detectava ou permitia edições nessas visualizações, com os controles de troca de visualização aparecendo desativados. (TGT-52556)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes

* Correção de um problema em que as modificações feitas nas experiências no [!UICONTROL Visual Experience Composer] não eram visíveis ou apareciam de forma inconsistente na interface do usuário. (TGT-TGT-53381)
* Correção de um problema no VEC atualizado em que a seção [!UICONTROL Gerenciar conteúdo] não exibia o texto alternativo para miniaturas de experiência. Esse problema dificultava a identificação de documentos pelos usuários, especialmente quando os nomes de arquivo eram longos ou truncados. (TGT-52291)
* Correção de um erro em que os clientes encontravam erros de validação incorretos ao configurar as regras de [!UICONTROL entrega de página] nas atividades de VEC. Especificamente, operadores como &quot;é igual a qualquer um de&quot; e &quot;não é igual a qualquer um de&quot; acionaram &quot;Entrada inválida para o tipo de operador&quot; ao inserir valores de texto, mesmo que o texto deva ser compatível. (TGT-52629)
* Correção de vários problemas que causavam comportamento inconsistente no painel [!UICONTROL Modificações] da interface atualizada ao selecionar ofertas usando o botão &quot;Selecionar uma oferta&quot;. Em vez de substituir a oferta existente, a interface do usuário adicionou uma duplicata e tentou interagir com qualquer oferta, resultando em erros de console, como `selectorNotFound`. Além disso, algumas ofertas não exibem o botão &quot;Selecionar uma oferta&quot;, mostrando apenas propriedades editáveis. (TGT-53321)
* Correção de um problema na interface do usuário atualizada do [!DNL Target], em que as alterações no código HTML feitas durante a configuração da atividade não persistiam em páginas de variação, mesmo que fossem salvas corretamente para grupos de controle. Apesar das várias tentativas e da recriação de testes sem agrupamentos de páginas, as páginas de variação falharam consistentemente ao reter as modificações, afetando a entrega de conteúdo e a validação de controle de qualidade. (TGT-53436)
* Correção de um problema no VEC atualizado em que o operador &quot;igual a qualquer um de&quot; nas regras de entrega da página não aceitava valores de entrada. Ao configurar parâmetros do cliente em todas as mboxes, selecionar esse operador resultava em um erro &quot;Entrada inválida&quot;, impedindo a criação da regra. (TGT-52623)

+++

**Espaços de trabalho**

+++Ver detalhes

* Fluxo de trabalho melhorado ao copiar atividades entre espaços de trabalho. As atividades de cópia entre espaços de trabalho resultavam anteriormente em erros de sincronização devido à falta de públicos-alvo e propriedades não atribuídas. Essa atualização apresenta um fluxo de trabalho mais inteligente e intuitivo que garante que as atividades copiadas sejam configuradas corretamente e estejam prontas para publicação. (TGT-47094)
* Correção de um problema em que os clientes não conseguiam copiar atividades entre espaços de trabalho devido a uma falha na mutação `copyActivityBatchOperations`. As tentativas de duplicar atividades resultaram em um erro de servidor (500) e uma carga de resposta nula. (TGT-52405)
* Correção de um problema em que as atividades não eram sincronizadas quando as ofertas referenciadas na configuração não estavam acessíveis no espaço de trabalho selecionado. Isso causava erros de publicação e deixava as atividades em estado de falha. (TGT-52535)
* Correção de vários problemas ao copiar atividades entre espaços de trabalho na interface atualizada do usuário [!DNL Target]. Os clientes encontraram erros relacionados ao acesso ao público-alvo, especialmente com atividades ativas, e validação de privilégio incorreta, mesmo quando o usuário tinha as funções &quot;[!UICONTROL Aprovador]&quot; nos espaços de trabalho de origem e destino. (TGT-53002)
* Correção de um problema na interface do usuário atualizada em que copiar atividades no mesmo espaço de trabalho duplicava desnecessariamente ofertas e públicos associados. (TGT-53457)
* Correção de um problema para resolver casos em que os públicos-alvo ad-hoc (anônimos) não eram copiados corretamente entre espaços de trabalho não padrão ou entre espaços de trabalho não padrão e padrão. Embora as atualizações anteriores garantissem a duplicação adequada para cenários padrão para não padrão e do mesmo espaço de trabalho, esse aprimoramento se concentrou em preservar configurações de público-alvo combinadas que abrangem vários espaços de trabalho. A correção garante um comportamento consistente do público-alvo e um direcionamento preciso em todas as transições do espaço de trabalho. (TGT-53268)

+++

### [!DNL Target Standard/Premium] 25.7.4 (1º de agosto de 2025)

Esta versão resolve problemas recentes, causados principalmente por personalizações complexas de clientes e inclui as seguintes correções e melhorias:

**Atividades**

+++Ver detalhes

* Correção de um problema em que um cliente encontrava um erro &quot;Entrada de usuário inválida&quot; ao tentar salvar uma atividade ativa, mesmo sem fazer alterações. A resposta do GraphQL indica um problema de LocalId duplicado. (TGT-53329 &amp; TGT-53373 &amp; TGT-53195)
* Correção de um problema que impedia a criação de uma experiência de redirecionamento no VEC atualizado. O URL de redirecionamento foi ignorado e a página original foi exibida. (TGT-53306)

+++

**Localização**

+++Ver detalhes

* Correção de um problema de localização no modal [!UICONTROL Criar critérios], ao selecionar a opção &quot;entre os seguintes valores&quot; na lista suspensa [!UICONTROL Escolher regra de preço], a cadeia de caracteres &quot;para&quot; era deslocalizada na seção [!UICONTROL Regras de inclusão]. (TGT-49754)
* Correção de um problema de localização com a sequência &quot;[!UICONTROL Todos os grupos de hosts]&quot; na lista suspensa [!UICONTROL Ambiente] do assistente de criação de feeds não está localizada corretamente. (TGT-46737)

+++

**QA**

+++Ver detalhes

* Correção de um problema em que o ambiente de QA não carregava dados em várias guias, inutilizando a interface. (TGT-53377)
* Correção de um problema que impedia a criação de uma atividade no ambiente de controle de qualidade. O processo foi redirecionado para a página [!UICONTROL Atividades] em vez de ser concluído com êxito. (TGT-53328)

+++

**Recomendações**

+++Ver detalhes

* Correção de um problema que fazia com que a página falhasse ao passar o mouse sobre o operando de &quot;deep-learning&quot; durante a criação de uma coleção no [!DNL Recommendations]. (TGT-53305)
* Correção de um problema em que as sugestões de filtro na [!UICONTROL Pesquisa de catálogo] da interface atualizada eram imprecisas. (TGT-52007)
* Correção de um problema na interface do usuário do [!DNL Recommendations] em que o filtro Operandos era exibido ao usar os operadores &quot;valor está presente&quot; ou &quot;valor não está presente&quot;, embora devesse ser oculto. (TGT-53012)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes

* Correção de um problema quando um usuário clica em [!UICONTROL Gerenciar conteúdo] e em [!UICONTROL Concluído] ao editar uma atividade de Automated Personalization (AP), a página fica em branco e não responde. (TGT-53047 e TGT-52993)
* Correção de um problema em que selecionar a [!UICONTROL Visualizou uma métrica de conversão de mbox] em [!UICONTROL Metas e configurações] causava falha na página. (TGT-53346, TGT-53343, e TGT-53348)
* Correção de um problema em que o recurso [!UICONTROL Redirecionar para a URL] não funcionava conforme o esperado; nenhum redirecionamento ocorre mesmo com URLs válidas. (TGT-53307)

+++

**Espaços de trabalho**

+++Ver detalhes

* Correção de um problema ao copiar atividades entre espaços de trabalho que causava entradas duplicadas de &quot;Cópia de público-alvo&quot; e conflitos de ID. Agora os públicos-alvo são copiados com IDs exclusivas, contexto de espaço de trabalho e tratamento recursivo para públicos-alvo combinados (até 5 níveis). (TGT-53081)
* Correção de um problema quando o espaço de trabalho era definido como &quot;[!UICONTROL Todos os espaços de trabalho]&quot;, copiar uma atividade que já existe no espaço de trabalho padrão resultava em um erro incorreto:

  &quot;Pelo menos uma propriedade deve ser incluída para espaços de trabalho não padrão.&quot;

  Como a cópia está no espaço de trabalho padrão, nenhuma propriedade deve ser necessária. Tentar adicionar uma propriedade e salvar resulta em um segundo erro:

  &quot;Entrada de usuário inválida&quot;

+++

### [!DNL Target Standard/Premium] 25.7.3 (sexta-feira, 24 de julho de 2025)

Devido aos problemas recentes identificados, principalmente relacionados às personalizações complexas do cliente, esta versão inclui as seguintes correções e atualizações:

**Atividades**

+++Ver detalhes

* Correção de um problema em que o método `buildViews` na classe de construtor definia incorretamente `viewMaxLocalId` para a contagem total de exibições, em vez da maior `viewLocalId` atribuída. (TGT-53207)
* Correção de um problema na interface do usuário atualizada [!DNL Target], em que as ofertas excluídas nas atividades [!UICONTROL Automated Personalization] (AP) eram exibidas como `Deleted option with ID: X` em vez dos nomes originais (por exemplo, `Offer Name [Deleted]`, como mostrado na interface do usuário herdada). Essa correção restaura a rotulagem significativa de ofertas excluídas, melhorando a clareza e tornando os relatórios mais precisos e fáceis de usar. (TGT-52921)
* Correção de um problema em que algumas atividades migradas do front-end do [!DNL Target] para o [!DNL Target] Central tinham configurações de métrica inconsistentes devido a um erro de sincronização corrigido anteriormente. Especificamente, as atividades que originalmente usavam uma métrica de conversão e foram atualizadas posteriormente para uma métrica baseada em análise mantiveram valores desatualizados nos campos `primaryMetricType` e `successCriteria`. (TGT-52643)
* Correção de um problema em que todo o conteúdo de uma página de visualização de QA se tornava editável devido à inclusão não intencional do atributo `contentEditable` nas modificações do HTML. Isso permitia que os usuários clicassem e editassem qualquer texto na página, causando possivelmente problemas de layout e confusão durante o controle de qualidade. (TGT-53247)
* Correção de um problema em que mover uma modificação de [!DNL Page Load] para uma [!UICONTROL Exibição] fazia com que a modificação fosse duplicada, permanecendo no [!UICONTROL Carregamento de Página] enquanto também aparecia na [!UICONTROL Exibição]. Além disso, a remoção da modificação do [!UICONTROL Modo de Exibição] também a removeria incorretamente do [!UICONTROL Carregamento de Página]. (TGT-53270)

+++

**APIs**

+++Ver detalhes

* Correção de um problema na camada de persistência de backend em que as opções excluídas eram armazenadas corretamente, mas não acessíveis por meio de pontos de extremidade de API existentes. Como resultado, os aplicativos de front-end não podiam recuperar nomes significativos para opções excluídas, afetando as exibições de relatórios históricos. Essa correção garante que os dados de opção excluídos preservados agora possam ser exibidos corretamente na interface do usuário. (TGT-52973)
* Implementação de um novo ponto de extremidade de migração para oferecer suporte à transferência de opções de atividades excluídas de atividades baseadas em JCR para a [!DNL Target] Central. Essa funcionalidade permite o rastreamento e a geração de relatórios consistentes em todos os sistemas. Esse recurso garante que as opções excluídas sejam preservadas e sincronizadas no front-end e back-end do [!DNL Target], melhorando a integridade dos dados e dos relatórios históricos. (TGT-53217)
* Introdução de um novo endpoint de API que permite que os usuários restaurem opções de atividades excluídas anteriormente de um banco de dados secundário. Essa funcionalidade aproveita a infraestrutura existente fornecida pelas classes `RemovedCampaignElements` e `RemovedOptionInfo`, garantindo a reintegração perfeita das opções excluídas nas atividades ativas. (TGT-52903)
* Correção de um problema em que [!DNL Recommendations] atividades contendo nomes de métricas com mais de 25 caracteres não podiam ser abertas ou editadas devido a limitações de API. Essa correção garante a compatibilidade com nomes de métricas que excedem o limite de caracteres, restaurando o acesso total às atividades afetadas. (TGT-52839)

+++

**Experience Composer baseado em formulário**

+++Ver detalhes

* Correção de um problema no [!UICONTROL Experience Composer baseado em formulário] que resultava em falha do editor após clicar no ícone **[!UICONTROL Gerenciar conteúdo]** ( ![Ícone Gerenciar conteúdo](/help/main/assets/icons/Experience.svg) ) ao criar ou editar uma atividade do [!UICONTROL Automated Personalization] (AP). (TGT-53047)

+++

**Recomendações**

+++Ver detalhes

* Correção de um problema que impedia a [!UICONTROL Pesquisa no catálogo] de carregar resultados adicionais ao rolar a tela para a parte inferior da lista, restaurando o comportamento consistente com a interface herdada. (TGT-53088)
* Correção de um problema que bloqueava a exclusão de itens da caixa de diálogo [!UICONTROL Detalhes dos critérios]. (TGT-53245)
* Correção de um problema que impedia a abertura ou interação com produtos sem nome. Esse problema ocorria ao selecionar ambientes que retornavam resultados sem nome, impedindo o acesso aos detalhes do produto. (TGT-53007)
* Correção de um problema que causava a falha da página [!UICONTROL Pesquisa de catálogo] e exibia uma tela em branco ao selecionar determinados produtos. (TGT-53087)
* Correção de um problema em que os usuários não conseguiam editar a atividade [!DNL Recommendation] site_cart_z1 na interface do usuário do [!DNL Target]. A tentativa de abrir a atividade disparou um erro na página [!UICONTROL Visão geral], bloqueando o acesso ao editor. (TGT-53221)

+++

**Relatório**

+++Ver detalhes

* Correção de um problema em que o campo sandbox no banco de dados de atividades não era limpo ao alternar a fonte de relatórios de [!DNL Customer Journey Analytics] ou [!DNL Analytics] para [!DNL Target]. Anteriormente, a interface do usuário enviava a sandbox corretamente: nulo, mas o back-end ignorava esse valor, deixando dados desatualizados da sandbox no lugar. O back-end agora limpa corretamente o campo da sandbox quando nulo é recebido. (TGT-52798)
* A camada de persistência de opções excluídas foi reimplementada no back-end do Target para oferecer suporte a relatórios históricos precisos nas atividades de [!UICONTROL Automated Personalization] (AP). Anteriormente, quando uma opção era excluída, seu nome era perdido, dificultando a interpretação de dados de desempenho anteriores.

  **Principais melhorias**:

  * As opções excluídas agora são rastreadas usando a infraestrutura `RemovedCampaignElements` e `RemovedOptionInfo` existente.
  * Quando uma opção é removida de uma atividade de AP, seus metadados (por exemplo, ID e nome) são preservados.
  * A interface do usuário de relatórios agora pode exibir o nome de opção original (por exemplo, `Option Name [Deleted]`) junto com métricas históricas, melhorando a clareza e a usabilidade.

  Essa atualização garante relatórios consistentes e significativos, mesmo depois que as opções são removidas de uma atividade. (TGT-52986)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes

* Correção de um problema no VEC em que a aplicação de uma modificação em uma exibição causava duplicação e acionava um erro &quot;Entrada de usuário inválida&quot;. (TGT-52886)
* Correção de um problema com a funcionalidade [!UICONTROL Desfazer] para as opções [!UICONTROL Inserir Antes] e [!UICONTROL Inserir Depois] ao configurar ofertas de imagem no VEC.

  Anteriormente, desfazer uma ação [!UICONTROL Inserir antes] ou [!UICONTROL Inserir depois] em ofertas de imagem resultava em comportamento inconsistente ou falha ao reverter corretamente a modificação, especialmente em atividades criadas na interface herdada [!DNL Target]. Esse problema foi resolvido para garantir que as ações de desfazer agora funcionem de forma confiável para essas modificações. (TGT-52809)

* Correção de um problema em que o atributo `contentEditable` era definido involuntariamente como verdadeiro e persistia no conteúdo HTML salvo. Essa atualização garante uma saída do HTML mais limpa e esperada sem comportamento de edição não intencional. (TGT-52319)
* Para evitar a perda permanente de opções excluídas e garantir um comportamento consistente entre os serviços, a funcionalidade de exclusão reversível foi implementada para opções na interface do usuário e nos microsserviços relacionados.

  **Alterações de Chave**:

  * As opções não são mais excluídas permanentemente. Em vez disso, eles são marcados com um novo sinalizador deleted: true no objeto XML de parâmetros.
  * Esse sinalizador é usado somente pela interface atualizada do usuário [!DNL Target] para excluir opções excluídas da renderização e impedir que sejam enviadas para serviços de borda.
  * As opções excluídas permanecem como parte da carga útil da atividade durante as edições, garantindo a rastreabilidade e evitando a entrega de opções inexistentes para os clientes.

  Essa atualização melhora a integridade dos dados e se alinha às práticas recomendadas para gerenciar exclusões em sistemas distribuídos. (TGT-52726)

+++

**Espaços de trabalho**

+++Ver detalhes

* Correção de um problema ao copiar uma atividade de um espaço de trabalho não padrão para um padrão ou entre espaços de trabalho não padrão. As ofertas agora são duplicadas com rastreamento e nomenclatura aprimorados para evitar conflitos.

  **Principais melhorias**:
  * As ofertas são recriadas no espaço de trabalho de destino com IDs e metadados atualizados.
  * As ofertas copiadas são renomeadas usando o formato: &quot;Cópia do nome da oferta&quot;, além de um número aleatório ou carimbo de data e hora para garantir exclusividade.
  * O sistema atualiza os estados de oferta e atividade para refletir as novas IDs.
  * Essa funcionalidade evita erros causados por vários nomes idênticos de &quot;Cópia de oferta&quot; durante ações de cópia repetidas.
  * As ofertas podem não aparecer imediatamente na lista de ofertas do espaço de trabalho de destino, mas são processadas e exibidas adequadamente.

  Essa atualização melhora a confiabilidade e a rastreabilidade ao gerenciar ofertas em vários espaços de trabalho. (TGT-53080)

+++

### [!DNL Target Standard/Premium] 25.7.2 (sábado, 18 de julho de 2025)

Devido aos problemas recentes identificados, principalmente relacionados às personalizações complexas do cliente, esta versão inclui as seguintes correções e atualizações:

**Atividades**

+++Ver detalhes

* Adição de um aviso de confirmação adicional ao cancelar edições de atividade com alterações não salvas: &quot;Deseja realmente salvar esta atividade? Se você não salvar, todas as alterações serão perdidas.&quot; Essa mensagem ajuda a impedir a perda acidental de dados. (TGT-52865)
* Restaurada a funcionalidade herdada para o controle deslizante [!UICONTROL Prioridade] em [!UICONTROL Metas e Configurações], permitindo que os clientes insiram um valor numérico diretamente, conforme suportado na interface herdada. (TGT-53185 e TGT-53219)

+++

**Públicos-alvo**

+++Ver detalhes

* Correção de um problema que impedia salvar ou editar atividades contendo públicos-alvo personalizados. Os clientes encontraram a mensagem de erro &quot;Não podemos concluir sua solicitação. Contate [!DNL Adobe Client Care] se o problema persistir.&quot; ao tentar salvar alterações, ou até mesmo salvar sem alterações, em determinadas atividades. (TGT-53189)

+++

**[!UICONTROL Analytics para Target] (A4T)**

+++Ver detalhes

* Correção de um problema em que os clientes visualizavam relatórios para atividades específicas na página [!UICONTROL Metas e configurações], o link [!UICONTROL Exibir no Analytics] apontava incorretamente para o ambiente de controle de qualidade em vez de para o ambiente de produção. (TGT-53163)

+++

**[!UICONTROL Experiências] e [!UICONTROL Ofertas]**

+++Ver detalhes

* Correção de um problema em que invocar `triggerView` por meio de código personalizado causava um loop infinito. (TGT-52885)
* Correção de um problema que causava incompatibilidades entre `LocalIds` definido para atividades e aqueles `LocalIds` usados em definições de experiência. (TGT-52669)
* Correção de um problema em que os nomes das métricas estavam ausentes na página [!UICONTROL Visão geral] da atividade, exibindo somente &#39;Oferta&#39; em vez do nome de métrica correto. (TGT-53054)

+++

**Experience Composer baseado em formulário**

+++Ver detalhes

* Correção de um problema no [!UICONTROL Experience Composer baseado em formulário] que impedia o salvamento da atividade e acionava a mensagem de erro: &quot;Não é possível ler propriedades de indefinido (lendo &#39;map&#39;)&quot;. (TGT-53145)

+++

**Recomendações**

+++Ver detalhes

* Correção de um problema em que um clique em um produto da [!UICONTROL Pesquisa no catálogo] exibia o erro &quot;Falha ao recuperar detalhes do produto&quot; e abria um modal sem uma opção de fechamento. (TGT-53082)
* Correção de um problema em que as [recomendações como ofertas](/help/main/c-recommendations/recommendations-as-an-offer.md) em [!UICONTROL atividades de Teste A/B] não eram atualizadas corretamente ao alterar coleções ou promoções. (TGT-52884)
* Correção de um problema no ambiente de produção, em que um clique em uma entidade na interface atualizada exibia o erro: &quot;Falha ao recuperar detalhes do produto. Contate [!DNL Adobe Client Care] se o problema persistir.&quot; (TGT-53071)

+++

**Relatórios**

+++Ver detalhes

* Correção de um problema em que salvar detalhes do pedido em um arquivo CSV resultava em um arquivo vazio. (TGT-52225)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* Solução de um problema na página [!UICONTROL Metas e configurações], em que os seletores usados em várias experiências não eram realçados consistentemente como selecionados. (TGT-53062)
* Correção de um problema que impedia a edição da atividade e acionava a mensagem de erro: &quot;Não é possível ler propriedades de indefinido (lendo &#39;map&#39;)&quot;. (TGT-53161)

+++

**Espaços de trabalho**

+++Ver detalhes

* Manuseio de ofertas ad-hoc aprimorado ao alternar espaços de trabalho.
  * Ao alternar do espaço de trabalho padrão para um não padrão (ou entre espaços de trabalho não padrão), as ofertas ad-hoc agora são copiadas corretamente. Durante a inicialização, o contexto do espaço de trabalho é atualizado e uma nova ID é atribuída à oferta para garantir a exclusividade.
  * Não ocorrem alterações ao permanecer no mesmo espaço de trabalho. (TGT-53079)
* Correção de um problema que impedia os clientes de [copiar atividades entre espaços de trabalho diferentes](/help/main/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6). (TGT-52753 e TGT-47094)
* Correção de um problema ao alterar propriedades entre espaços de trabalho.
  * Ao alternar entre o espaço de trabalho padrão e um não padrão, se a propriedade atual existir no espaço de trabalho de destino, a propriedade será preservada.
  * Se a lista [!UICONTROL Propriedades] exibir um aviso (provavelmente indicando que algumas propriedades podem não ser compatíveis) e o cliente clicar em [!UICONTROL Adicionar] ou [!UICONTROL Remover] e depois em [!UICONTROL Salvar], todas as propriedades que não estiverem no espaço de trabalho de destino serão removidas. Se o cliente clicar em [!UICONTROL Cancelar], todas as propriedades permanecerão, mesmo que não existam no espaço de trabalho de destino. (TGT-47094)
  * Se você permanecer no mesmo espaço de trabalho ou alternar de um espaço de trabalho não padrão para o padrão ou outro espaço de trabalho, tudo permanecerá como está. (TGT-53078)
* Atualização da lógica de validação da entidade para respeitar o contexto original do espaço de trabalho da atividade. Entidades como [!UICONTROL Fragmentos de experiência] (XFs) agora são validadas com base no espaço de trabalho em que a atividade foi originalmente criada. Por exemplo, se um XF existir no espaço de trabalho padrão e a atividade for copiada do espaço de trabalho X para o espaço de trabalho Y, a validação ainda será transmitida, desde que o XF seja válido no espaço de trabalho original (padrão). (TGT-53196)
* Suporte aprimorado para copiar públicos-alvo ad-hoc durante a duplicação da atividade.
  * Públicos-alvo ad-hoc, incluindo métricas, relatórios, página e tipos somente atividade, agora são copiados automaticamente nos seguintes cenários:
    * Ao copiar uma atividade do espaço de trabalho padrão para um espaço de trabalho não padrão.
    * Ao copiar uma atividade no mesmo espaço de trabalho. (TGT-53197)

+++

### [!DNL Target Standard/Premium] 25.7.1 (sábado, 11 de julho de 2025)

Devido aos problemas recentes identificados, principalmente relacionados às personalizações complexas do cliente, esta versão inclui as seguintes correções e atualizações:

**Atividades**

+++Ver detalhes

* Correção de um problema em que a URL de [!UICONTROL Controle de Qualidade de Atividade] incluía um parâmetro de consulta desnecessário: `at_preview_evaluate_as_true_audience_ids`. (TGT-52907)
* Correção de um problema em que os URLs de visualização incluíam incorretamente públicos adicionais além do explicitamente digitado pelo usuário. Esse comportamento foi corrigido para garantir que somente o público-alvo especificado seja aplicado ao gerar um link de controle de qualidade ou visualização. (TGT-52912)
* Correção de um problema que impedia os usuários de criar atividades de [!UICONTROL Direcionamento automático] (AT) se a opção [!UICONTROL Alocação automática] (AA) fosse selecionada primeiro durante a configuração da alocação de tráfego. Esse problema resultou em um erro de validação de backend e impede que a atividade seja salva. (TGT-53096)

+++

**Públicos-alvo**

+++Ver detalhes

* Correção de um problema em que os usuários com a função [!UICONTROL Aprovador] não conseguiam adicionar ou salvar refinamentos de público somente atividade. A tentativa de fazer isso resultou em um erro 403 Proibido, informando que o privilégio &quot;[editor]&quot; era necessário, mesmo que o usuário tivesse permissões suficientes para aprovar e gerenciar atividades. (TGT-52984)
* Correção de um problema quando um público-alvo específico de uma atividade era removido com a opção [!UICONTROL Remover refinamento de público-alvo], o público-alvo não aparecia mais na lista de públicos-alvo para reseleção na mesma atividade. Esse comportamento impedia que os usuários adicionassem novamente o mesmo público-alvo, a menos que fosse recriado do zero. (TGT-52979)
* Correção de um problema em que os refinamentos de público-alvo somente de atividade desapareciam da interface do usuário imediatamente após serem removidos de um local, mesmo antes de a atividade ser salva. Esse comportamento contradizia a funcionalidade esperada e a orientação da dica de ferramenta, que declara: &quot;Todos os públicos-alvo não usados dessa biblioteca serão excluídos assim que a atividade for salva.&quot; (TGT-52982)
* Correção de um problema ao tentar atribuir um público-alvo diferente de [!UICONTROL Todos os visitantes] a uma atividade. Ao salvar, a seguinte mensagem de erro era exibida: &quot;Não podemos concluir sua solicitação. Entre em contato com o [!UICONTROL Atendimento ao cliente da Adobe] se o problema persistir.&quot; (TGT-53008)
* Correção de um problema que bloqueava o salvamento de uma atividade após a criação e a atribuição de um novo público-alvo no editor de atividades. A mensagem de erro exibida foi: &quot;Não foi possível concluir a solicitação. Entre em contato com o [!UICONTROL Atendimento ao cliente da Adobe] se o problema persistir.&quot; (TGT-52977)

+++

**[!UICONTROL Analytics para Target] (A4T)**

+++Ver detalhes

* Correção de um problema em que copiar uma atividade existente e alterar a fonte de relatórios para [!DNL Adobe Analytics] (A4T) resultava em um erro &quot;Entrada de usuário inválida&quot;. O erro foi disparado quando determinadas ações de métrica incompatíveis com os relatórios do [!DNL Analytics], como `restart_same_experience`, `restart_random_experience` e `restart_new_experience`, eram retidas da atividade original. (TGT-52900)
* Correção de um problema que impedia os clientes de criar ou salvar uma atividade ao selecionar [!DNL Adobe Analytics] (A4T) como fonte de relatórios na etapa [!UICONTROL Metas e configurações]. O problema ocorreu especificamente ao selecionar uma métrica [!UICONTROL Evento personalizado] (por exemplo, &quot;Evento personalizado 16&quot;), resultando no seguinte erro: &quot;Entrada de usuário inválida&quot;. (TGT-52910)
* Correção de um problema em que um clique no link &quot;[!UICONTROL Exibir no Analytics]&quot; redirecionava os usuários para a página inicial em vez do painel [!DNL Analytics] pretendido. (TGT-53092 e TGT-53093)
  <!-- * Fixed an issue when cloning an existing activity and changing the reporting source from [!DNL Target] to [!DNL Adobe Analytics], users encounter a "400 - Invalid User Input" error, preventing the activity from being saved. (TGT-52875)-->
* Correção de um problema ao visualizar uma atividade [!DNL Recommendations] na interface atualizada do usuário [!UICONTROL Visão geral], a seção [!UICONTROL Metas e configurações] falha ao carregar quando [!DNL Adobe Analytics] (A4T) é selecionado como fonte de relatórios. A seguinte mensagem de erro foi exibida: &quot;Algo deu errado. Não podemos completar o seu pedido. Entre em contato com o Atendimento ao cliente da Adobe se o problema persistir.&quot; (TGT-52999)

+++

**[!UICONTROL Experiências] e [!UICONTROL Ofertas]**

+++Ver detalhes
<!-- * Fixed an issue where using the [!UICONTROL Manage Content] feature in [!UICONTROL Automated Personalization] (AP) activities caused the page to crash and remain blank. This issue occurred after clicking [!UICONTROL Done] in the content manager, particularly in activities created or edited in the updated UI. (TGT-53047)-->
* Correção de um problema em que o recurso [!UICONTROL Gerenciar Conteúdo] não validava corretamente o estado de um local após a remoção de todas as opções de conteúdo. Esse problema pode levar a comportamentos ou erros inconsistentes ao tentar salvar ou continuar com a configuração da atividade. (TGT-52801)
* Correção de um problema em que os usuários encontravam um erro de &quot;Entrada inválida&quot; ao adicionar uma nova página e excluir elementos específicos em diferentes experiências. O erro é disparado quando `LocalIds` duplicado é gerado durante a manipulação do elemento, especialmente ao alternar entre experiências e modificar estruturas de página compartilhadas. (TGT-52720)
* Correção de um problema em que o uso do recurso [!UICONTROL Gerar Oferta Adhoc] resultava na exibição de locais indefinidos no painel [!UICONTROL Gerenciar Conteúdo]. (TGT-53076 e TGT-53070)
* Esclarecimento sobre o comportamento para o cliente em que as modificações feitas usando uma Oferta da HTML podem parecer ausentes ao navegar da etapa [!UICONTROL Direcionamento] de volta para [!UICONTROL Experiências]. Para esse cliente, o site afetado gerou dinamicamente vários seletores DOM que foram alterados a cada carregamento de página. Como resultado, o seletor originalmente usado para a modificação não pode ser encontrado quando o editor é reaberto, fazendo com que a modificação pareça ausente ou inválida. Este cenário está funcionando como projetado. Para garantir que as modificações persistam visualmente no editor, é recomendável que os clientes usem seletores estáveis e consistentes que não sejam alterados durante os recarregamentos de página. (TGT-52874)
* Correção de um problema em que a tentativa de excluir ou desativar uma oferta que fazia parte de uma experiência excluída acionava um erro &quot;Entrada de usuário inválida&quot;. Esse problema ocorria mesmo se a oferta não fosse usada ativamente nas experiências incluídas. (TGT-52917)

+++

**Experience Composer baseado em formulário**

+++Ver detalhes

* Correção de um problema em atividades baseadas em formulário em que duplicar uma experiência e editar o código personalizado em uma das experiências duplicadas aplicava involuntariamente essas alterações a todas as experiências duplicadas. Cada experiência agora mantém seu próprio código personalizado de forma independente após a duplicação. (TGT-51600)

+++

**Localização**

+++Ver detalhes

* Atualização de cadeias de caracteres de localização na nova interface do usuário para francês (fr_FR), alemão (de_DE), italiano (it_IT), coreano (ko_KO) e chinês simplificado (zh_CN).

+++

**[!DNL Recommendations]**

+++Ver detalhes

* Adição de um novo [!DNL Recommendations] feed [status](/help/main/c-recommendations/c-products/feeds.md#status): [!UICONTROL Falha na importação parcial]. (KB-2215)
* Correção de um problema que afetava o fluxo de trabalho de criação da atividade ao adicionar [!DNL Recommendations] com [!UICONTROL promoções]. Quando os usuários selecionaram &quot;[!UICONTROL Promover por atributo]&quot; e adicionaram uma regra de filtragem (por exemplo, [!UICONTROL Correspondência de Parâmetros]), o tipo de regra e os valores de operando selecionados não foram retidos após salvar e editar novamente a atividade. Após a reabertura, o tipo de regra do filtro seria alterado inesperadamente e os valores do operando estariam ausentes. (TGT-53059)
* Correção de um problema na interface do usuário do [!DNL Recommendations] em que qualquer promoção criada com uma única regra era interpretada e exibida incorretamente como um tipo de promoção &quot;Lista de itens&quot;, independentemente da lógica da regra. (TGT-53063)
* Correção de um problema ao usar a [!UICONTROL Visão geral]interface atualizada, o botão &quot;[!UICONTROL Baixar dados de recomendações]&quot; estava ausente para [!UICONTROL Direcionamento de experiência] (XT) que inclui [!DNL Recommendations]. (TGT-52730 e TGT-52756)
* Anteriormente, a interface do usuário do Recommendations exibia somente o número de entidades importadas com êxito de um feed. No entanto, o formato de mensagem de back-end inclui o número de entidades importadas e o número total de entidades no formato: `# of entities imported / # of total entities`. Devido a essa discrepância, os usuários só viam o primeiro valor (contagem importada) na interface do usuário, o que gerava confusão. A interface do usuário agora exibe ambos os números. (TGT-53073)
* Correção de um problema em que os clientes não conseguiam salvar uma regra de filtragem ao configurar uma promoção &quot;[!UICONTROL Promover por atributo]&quot; em uma atividade A/B baseada em formulário com recomendações. Após salvar e reabrir a atividade, a regra de filtragem estava ausente e a atividade não pôde ser salva com êxito. (TGT-53057)

  +++

**Relatórios**

+++Ver detalhes

* Correção de um problema em que a seleção de &quot;[!UICONTROL Exportar detalhes do pedido para CSV]&quot; na página [!UICONTROL Relatórios] resultava no download de um arquivo vazio. Esse problema ocorria mesmo quando dados de pedido válidos estavam presentes na atividade. (TGT-52225)
* Correção de um problema ao tentar salvar uma atividade após criar e atribuir um novo público-alvo de relatórios. A mensagem de erro retornada foi: &quot;Acesso negado. Para executar esta operação, todos os privilégios a seguir são necessários: [editor].&quot; Esse problema ocorria apesar de o usuário ter acesso como aprovador. (TGT-53103)

+++

**[!UICONTROL Visual Experience Composer] (VEC)**

+++Ver detalhes

* Solução de um problema em que a aplicação de uma modificação em uma exibição resultava na duplicação da exibição e a atividade retornava um erro &quot;Entrada de usuário inválida&quot;. Essa correção garante que as modificações de exibição sejam aplicadas corretamente sem disparar erros de duplicação ou validação. (TGT-52886)
* Correção de um problema em que as modificações de código personalizadas eram exibidas incorretamente para a experiência errada. Especificamente, as alterações destinadas a uma experiência foram mostradas em uma experiência diferente, levando a confusão e possível configuração incorreta de atividades ativas. (TGT-52776)
* Correção de um problema que impedia a edição ou o salvamento de modificações de código personalizadas na Nova interface do VEC. Especificamente:

  * Após editar um bloco de código personalizado e salvar, as alterações não foram refletidas na interface do usuário ou na pré-visualização de controle de qualidade.
  * Em alguns casos, as modificações não podiam ser excluídas a menos que a atividade fosse fechada e reaberta.
  * Como solução alternativa, os usuários tinham que copiar o código, excluir a modificação e recriá-lo manualmente com o conteúdo atualizado. (TGT-53072)

* Correção de um problema em que editar e salvar o código personalizado fazia com que o painel [!UICONTROL Modificações] não respondesse. (TGT-53075)
* Correção de um problema em que as modificações feitas no código personalizado em experiências de variante eram refletidas involuntariamente na experiência de [!UICONTROL Controle]. Isso causou alterações não intencionais no comportamento de delivery. A experiência de [!UICONTROL Controle] agora permanece isolada das edições de código personalizadas feitas em outras experiências. (TGT-52413)
* Correção de um problema em que as modificações feitas em uma experiência (por exemplo, Experiência B) eram duplicadas involuntariamente em outra experiência (Experiência A) se o usuário clicasse na segunda experiência antes do editor ser totalmente carregado. Esse comportamento também pode resultar na perda de modificações se a experiência selecionada inicialmente não tiver alterações. (TGT-52597)
* Correção de um problema em que as alterações feitas na etapa [!UICONTROL Modificações] da criação da atividade não eram salvas de forma consistente. Em alguns casos, após concluir todas as etapas e clicar em [!UICONTROL Salvar], o script personalizado adicionado na seção [!UICONTROL Modificações] não refletirá no site ativo, apesar de não haver erros visíveis durante o processo de salvamento. (TGT-52661)
* Correção de um problema em que as alterações de código personalizado não eram salvas corretamente e eram espelhadas involuntariamente em várias experiências na mesma atividade. Além disso, os usuários encontraram problemas de acesso ao abrir ou atualizar determinadas atividades, resultando em telas em branco. Esses problemas foram resolvidos para garantir uma edição de atividades estável e um isolamento preciso da experiência. (TGT-52594)
* Correção de um problema em que os usuários não conseguiam navegar para uma URL diferente enquanto estavam no [!UICONTROL Modo de Navegação]. Isso impedia que testadores e editores validassem ou visualizassem páginas alternativas na mesma sessão de atividade. (TGT-53052)
* Correção de um problema em que várias instâncias do [!UICONTROL Visual Experience Composer] (VEC) eram abertas simultaneamente durante a criação da atividade. Esse problema ocorria quando usuários desativavam o [!UICONTROL Enhanced Experience Composer] (EEC) e removiam a barra à direita da URL do site na etapa [!UICONTROL Entrega de página]. (TGT-52782)
* Correção de um problema em que a lista suspensa da métrica [!UICONTROL Receita] na etapa [!UICONTROL Metas e configurações] assumiria incorretamente o padrão [!UICONTROL Receita por visita] (RPVISIT), mesmo depois que o usuário selecionasse uma métrica diferente.  O problema ocorria ao recolher e expandir novamente o painel de configuração de métrica, fazendo com que o valor selecionado anteriormente fosse redefinido. (TGT-52811 e TGT-52878)
* Correção de vários problemas no fluxo de trabalho de criação da atividade relacionados à nomeação da oferta e à conversão de conteúdo nas atividades do [!UICONTROL Automated Personalization] (AP) e do [!UICONTROL Multivariate Testing] (MVT):

  Principais problemas abordados:

  * A criação de várias Ofertas da HTML com o mesmo nome (por exemplo, &quot;Experiência&quot;) acionou o erro &quot;Nomes de ofertas duplicados não são permitidos&quot;, mas a interface não indicou claramente quais ofertas estavam causando o conflito.
  * A renomeação de ofertas por meio do painel direito atualizou o nome na interface, mas a alteração não foi refletida na guia [!UICONTROL Gerenciar Conteúdo] ou na guia [!UICONTROL Ofertas], causando erros de validação persistentes.
  * Em atividades do MVT, embora o erro de nome duplicado não persistisse após a renomeação, a interface do usuário ainda não refletia os nomes de oferta atualizados de forma consistente nas guias. (TGT-52933)

  +++

### [!DNL Target Standard/Premium] 25.6.4 (sábado, 27 de junho de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Adicionada a opção [!UICONTROL Reorganizar] à interface atualizada do [!UICONTROL Visual Experience Composer] (VEC) para alinhar-se à funcionalidade disponível no VEC herdado. (TGT-46957 e TGT-52876)
* Correção de um problema em que as modificações feitas nas experiências de variante (por exemplo, Experiência B) em uma atividade [!UICONTROL Teste A/B] não eram mantidas. Depois de alternar entre experiências, as alterações na variante desapareceriam. Esse problema não afetou a experiência de controle. (TGT-52664)
* Correção de um problema em que determinados clientes não podiam criar ou salvar atividades, enquanto outros podiam executar as mesmas ações sem problema. O problema era inconsistente entre as contas.(TGT-52842)
* Correção de um problema em que, no VEC atualizado, os usuários não conseguiam mover modificações para o [!UICONTROL evento de Carregamento de página], um recurso que existia na interface herdada. (TGT-52617)
* Correção de um problema na interface do usuário atualizada em que os eventos de [!UICONTROL carregamento de página] não estavam visíveis em [!DNL Target] ao criar alterações; atualizações se aplicavam somente a exibições. (TGT-52604)
* Correção de um problema que impedia que algumas modificações de atividade fossem exibidas corretamente no VEC atualizado. (TGT-52818)
* Correção de uma exceção de ponteiro nulo que ocorria ao buscar dados de relatórios para atividades de [!UICONTROL Automated Personalization] (AP). (TGT-52362)
* Correção de um problema que impedia que detalhes no nível da oferta fossem exibidos no arquivo .CSV para atividades do [!UICONTROL Automated Personalization] (AP). (TGT-52675)
* Correção de um problema ao aplicar modificações no VEC atualizado. As alterações inicialmente aparecem corretamente, incluindo o [!UICONTROL Fragmento de experiência] esperado. No entanto, ao alternar experiências ou fazer edições adicionais, algumas modificações não são aplicadas devido a problemas do seletor. (TGT-52679)
* Correção de um problema em que, quando uma nova atividade era criada por meio da clonagem de uma atividade existente, os links de controle de qualidade na atividade clonada retinham incorretamente os URLs da página da atividade original. (TGT-52775)
* Correção de um problema que impedia involuntariamente a [!UICONTROL Decisão no dispositivo] de estar disponível no VEC atualizado. (TGT-52371)
* Correção de um problema que impedia a edição de uma atividade do produto [!DNL Recommendations]. Ao tentar acessar o VEC por meio da interface do usuário do Target, um erro apareceu na página [!UICONTROL Visão geral], impedindo edições. (TGT-52823)
* Correção de um problema que impedia salvar uma atividade [!DNL Recommendations] quando os nomes de experiência excediam 50 caracteres. (TGT-52619)
* Correção de um problema em que os clientes não conseguiam salvar uma atividade do Recommendations após modificar os critérios na nova interface do usuário. O problema parece estar relacionado à permissão e não afeta todos os usuários com funções semelhantes. (TGT-52816)
* Correção de um problema em que os usuários com a função [!UICONTROL Editor] não conseguiam editar uma atividade [!DNL Recommendations]. A tentativa de alterar o design e salvar a atividade resultou em um erro 403 Proibido, informando que o privilégio &quot;[editor]&quot; era necessário, mesmo que o usuário já tivesse essa função no espaço de trabalho relevante. (TGT-52836)

### [!DNL Target Standard/Premium] 25.6.3 (sábado, 20 de junho de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema em que copiar uma atividade de um espaço de trabalho para outro espaço de trabalho acionava erros como &quot;não deve ser nulo&quot; ou &quot;Algo deu errado&quot;. (TGT-52474)
* Correção de um problema em que os relatórios de [!UICONTROL Segmentos automatizados] e [!UICONTROL Atributos importantes] não eram gerados para determinadas atividades. (TGT-52904)
* Correção de um problema no VEC atualizado em que o controle de conteúdo padrão nas atividades do [!UICONTROL Automated Personalization] (AP) não correspondia à interface do usuário herdada. O sistema agora adiciona automaticamente um `optionGroup` padrão chamado &quot;Conteúdo padrão&quot; com `optionGroupLocalId = 0` quando nenhum grupo é explicitamente adicionado. Este grupo inclui a opção padrão (por exemplo, `optionLocalId: 0`). Se o conteúdo padrão for removido, o grupo de opções correspondente também será removido. (TGT-52651)
* Correção de um problema nas atividades de [!UICONTROL Teste multivariado] (MVT) em que não era permitido reutilizar um `experienceLocalId` de experiências removidas anteriormente. (TGT-52672)
* Correção de um problema que impedia a cópia ou edição de atividades contendo um fragmento de experiência. Isso disparou o erro: `Enum "AemOfferType" cannot represent value: "html"`. (TGT-52635)
* Correção de um problema em que os URLs nos locais de atividade falhavam em exibir parâmetros de consulta devido a caracteres inválidos, como barras (/). (TNT52845)
* Mensagem de erro de validação aprimorada para [!DNL A/B Test] atualizações de atividade por meio da API de back-end. Quando nomes de locais duplicados estão presentes, a mensagem agora diz claramente: &quot;Nomes duplicados não são permitidos&quot; para `locations.selectors`. (TGT-52589)
* Correção de um erro que ocorria ao atualizar uma atividade ao vivo do [!UICONTROL Recommendations] devido a uma propriedade não reconhecida na carga da solicitação. O sistema agora lida corretamente com o &quot;JSON inválido. Erro &quot;Nome de propriedade não reconhecido&quot;. (TGT-52723)
* Correção de um problema que impedia a criação de um design do [!DNL Recommendations]. Clicar em [!UICONTROL Criar] acionou a mensagem: &quot;Deve haver pelo menos 1 variável de entidade usada dentro do script.&quot; (TGT-52395 e TGT-52899)
* Correção de um problema em que foi bloqueado salvar novamente um design do [!DNL Recommendations] sem modificações. (TGT-52879)
* Correção de um erro de validação de backend que causava um erro &quot;400 Solicitação inválida&quot; ao salvar uma atividade [!UICONTROL Recommendations]. (TGT-52716)
* Corrigido um problema no [!UICONTROL Experience Composer baseado em formulário], onde passar o mouse sobre uma mbox com caracteres especiais no menu suspenso [!UICONTROL Local] fazia com que o editor ficasse em branco e disparasse uma &quot;Falha ao executar &#39;querySelector&#39; em &#39;Elemento&#39;.&quot; . (TGT-52717)
* Melhoria na precisão do status do feed com um novo indicador &quot;PARCIALLY_IMPORTED&quot;. Anteriormente, os feeds eram marcados como &quot;sucesso&quot; mesmo quando nem todas as linhas de um arquivo eram importadas, o que induzir em erro. (TGT-52892)
* Correção de um erro em que, após a migração para o AP V2, determinadas chamadas de API para `/admin/rest/ui/v1/campaigns` retornavam erros do lado do cliente (HTTP 4xx). (TGT-52721)

### [!DNL Target Standard/Premium] 25.6.2 (sexta-feira, 12 de junho de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Adição de um [novo artigo de perguntas frequentes](/help/main/c-intro/updated-ui-faq.md) para abordar perguntas comuns sobre a interface do usuário do [!DNL Target] atualizada e o [!UICONTROL Visual Experience Composer] (VEC).
* Correção de um problema em que a regra &quot;[!UICONTROL URL - não contém]&quot; na [!UICONTROL Entrega de página] não estava funcionando, permitindo que o conteúdo fosse exibido mesmo quando deveria ter sido bloqueado. (TGT-52754)
* Correção de um problema em que [!UICONTROL Entrega de página] exibia incorretamente a mensagem de erro: &quot;URLs de página duplicadas não são permitidas. (TGT-52765)
* Correção de um problema em que os públicos-alvo das URLs de [!UICONTROL Entrega de página] contendo fragmentos de experiência eram criados com # anexados incorretamente. (TGT-52786)
* Correção de um problema em que copiar uma atividade e editar configurações na página [!UICONTROL Metas e Configurações] fazia com que a interface do usuário [!DNL Target] ficasse sem resposta. (TGT-52797)
* Correção de um problema no [!UICONTROL Visual Experience Composer] (VEC) atualizado que permitia incorretamente o redirecionamento de uma página adicional em uma atividade de [!UICONTROL Teste A/B] para a mesma URL. (TGT-51838)
* Correção de um problema em que as alterações nas métricas na página [!UICONTROL Metas e Configurações] não eram salvas ao editar uma atividade. (TGT-52799)
* Correção de um problema em que a adição de uma nova experiência enquanto o editor da Web ainda estava carregando fazia com que a nova experiência duplicasse o conteúdo da experiência anterior. (TGT-51397)
* Restaurada a capacidade de usar código personalizado fora da tag `<head>`, um recurso anteriormente disponível na interface do usuário herdada do Target. (TGT-52304 e TGT-52300)
* Validação desnecessária removida ao selecionar o espaço de trabalho padrão durante a criação da atividade. A validação de propriedade obrigatória não se aplica mais ao espaço de trabalho padrão, mas permanece no local para espaços de trabalho não padrão. (TGT-52449)
* Correção de um problema no [!UICONTROL Visual Experience Composer] (VEC) atualizado em que `triggerView()` chamadas não eram detectadas. (TGT-52575)
* Correção de um problema no [!UICONTROL Visual Experience Composer] (VEC) atualizado que impedia os usuários de adicionar modificações às exibições do [!UICONTROL Aplicativo de página única] (SPA). (TGT-52556)
* Correção de um problema na interface atualizada do usuário do [!DNL Target] que impedia que os clientes visualizassem detalhes da oferta. (TGT-52607)
* Correção de um problema em que as atualizações feitas em ofertas na [!UICONTROL Biblioteca de ofertas] não eram refletidas no [!UICONTROL Visual Experience Composer] (VEC) atualizado. (TGT-52637)
* Correção de um problema que impedia a exibição correta da seção Ofertas ao criar uma atividade. (TGT-52773)
* Validação adicionada para garantir que todos os `optionLocalIds` referenciados em `optionGroups` existam na matriz de opções. As referências inválidas são removidas automaticamente durante a criação da atividade. (TGT-52687)
* Correção de um problema em que os grupos de relatórios e exclusões não eram retidos após a adição de uma nova oferta. (TGT-52728)
* Correção de um problema em que as atividades sem um botão [!UICONTROL Controle de qualidade da atividade] exibiam um seletor de opções vazio. (TGT-52733)
* Correção de um problema em que os links de controle de qualidade não renderizavam o conteúdo corretamente. (TGT-52718)
* Correção de um problema em que a substituição de um elemento por um fragmento de experiência não refletia as alterações corretamente no ambiente de controle de qualidade. (TGT-52762)
* Correção de um problema no [!UICONTROL Visual Experience Composer] (VEC) atualizado que causava um erro de &quot;Entrada inválida&quot; quando usuários tentavam adicionar fragmentos de experiência. (TGT-52701)
* Correção de um problema em que o modal &quot;Editar público-alvo&quot; aparecia vazio ao editar o direcionamento de público no [!UICONTROL Visual Experience Composer] (VEC) atualizado. (TGT-52749)
* Adição de uma mensagem para informar aos usuários quando uma entidade não está acessível no espaço de trabalho selecionado. (TGT-52767)
* Correção de um problema em que a interface do usuário não permitia a atribuição manual de uma ID de ambiente a um critério. Em vez disso, padronizou para a ID do [!UICONTROL Pesquisa do catálogo de produtos] grupo de hosts. Essa correção garante que as alterações de critério agora sejam aplicadas em todos os ambientes, não apenas no padrão. (TGT-52817)
* Correção de um problema em que a opção &quot;[!UICONTROL Baixar dados de recomendações]&quot; estava ausente para [!UICONTROL Direcionamento de experiência] (XT) com recomendações. (TGT-52730 e TGT-52756)

### [!DNL Target Standard/Premium] 25.6.1 (sábado, 6 de junho de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema em que os links de controle de qualidade não forneciam a experiência correta para a atividade associada. (TGT-52163 e TGT-52790)
* Correção de um problema em que os links de controle de qualidade não tinham a ID de público-alvo associada. (TGT-52722)
* Correção de um problema para garantir que as experiências fossem entregues somente quando as condições configuradas do URL de entrega da página fossem atendidas com precisão. (TGT-52696)
* Correção de um problema que impedia os clientes de criar um modelo de design do [!DNL Recommendations]. A tentativa de criar um modelo acionou o erro: &quot;Deve haver pelo menos uma variável de entidade usada dentro do script&quot;. (TGT-52395)
* Correção de um problema que impedia salvar [!DNL Recommendations] designs usando matrizes do Velocity. A mensagem de erro &quot;Deve haver pelo menos uma variável de entidade usada dentro do script&quot; foi acionada incorretamente. (TGT-52734)
* Correção de um problema em que as modificações estavam inacessíveis no [!UICONTROL Visual Experience Composer] (VEC) quando a página não era carregada para páginas da Web internas. (TGT-52488 &amp;TGT-52470)
* Correção de um problema em que o painel [!UICONTROL Modificações] não estava visível em telas menores no VEC. (TGT-52470)
* Correção de um problema no VEC atualizado em que a alternância do modo [!UICONTROL Procurar] de volta para o modo [!UICONTROL Design] causava um erro de console e impedia mais interação. (TGT-52532)
* Correção de um problema no VEC em que um clique em determinados elementos expandia involuntariamente seu tamanho. (TGT-52497)
* Correção de um problema em que determinados elementos da página não eram carregados ou reconhecidos no VEC, impedindo interações como a seleção de botões ou banners e interrompendo o rastreamento preciso de eventos nas atividades do. (TGT-52663)
* Correção de um problema que impedia os clientes de excluir ou remover ofertas em atividades do [!UICONTROL Automated Personalization] (AP). (TGT-52690)
* Correção de um problema que causava um comportamento inconsistente de qualificação de atividade em atividades de várias páginas. (TGT-52694)
* Correção de um problema que fazia com que a página [!UICONTROL Visão geral] da atividade mostrasse uma URL inválida para a [!UICONTROL Localização da atividade]. (TGT-52695)
* Correção de um problema na interface do usuário atualizada do [!DNL Target] que fazia com que entradas duplicadas fossem exibidas para os locais de atividades. (TGT-52693)
* Correção de um problema que acionava um erro `getAudiencesV3`, impedindo clientes de editar ou copiar atividades. (TGT-52709)
* Correção de um problema que causava um erro de carga inválida ao adicionar [!UICONTROL Fragmentos de experiência] ou ofertas do HTML a uma atividade. (TGT-52779 e TGT-52773)
* Correção de um problema na interface do usuário atualizada [!DNL Target] em que E[!UICONTROL Fragmentos de experiência] não eram exibidos corretamente devido a um erro de entrada inválido. (TGT-52701)
* Correção de um problema que impedia os clientes de editar atividades no [!UICONTROL Experience Composer baseado em formulário] devido a um erro de usuário inválido. (TGT-52470)
* Correção de um problema de localização no idioma coreano, em que as traduções anteriores usavam caracteres fora do Plano Multilíngue Básico. A tradução atualizada usa caracteres apropriados que transmitem com precisão o significado pretendido. (TGT-52508 e TGT-52509)
* Correção de um problema de localização no idioma coreano em que a tradução de &quot;data&quot; estava inconsistente ao selecionar datas de início e término de uma atividade. (TGT-52510)

### [!DNL Target Standard/Premium] 25.5.4 (29 de maio de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema que impedia a adição ou edição de URLs no modo de QA. (TGT-51941)
* Adição de uma configuração de Tráfego do Modo de QA em [!UICONTROL Relatórios] > [!UICONTROL Configurações de Relatório] ( ![ícone de Configurações de Relatório](/help/main/assets/icons/Setting.svg) ) para alinhar-se à funcionalidade da interface herdada [!DNL Target]. (TGT-52228 e TGT-52329)
* Correção de um problema em que a atividade baseada em formulário gerava links de controle de qualidade incorretos. O URL/local da atividade incluía um &quot;1&quot; não intencional no final, que agora foi removido para garantir a vinculação precisa. (TGT-52355 e TGT-52358)
* Correção de um problema em que a atividade baseada em formulário gerava links de controle de qualidade incorretos. A URL da atividade incluía um `http://pid-ppc` não intencional no início da URL, que agora foi removido para garantir a vinculação precisa. (TGT-52557)
* Correção de um problema em que [!DNL Target] gerava links de controle de qualidade inválidos para atividades baseadas em formulário. (TGT-52528 e TGT-52603)
* Correção de um problema em que salvar uma atividade modificada parecia ser processado, mas nunca concluído, e nenhuma mensagem de erro era exibida em [!DNL Target]. (TGT-52461)
* Correção de um problema em que o [!UICONTROL Visual Experience Composer] (VEC) atualizado não detectava automaticamente o valor `at_property`. (TGT-52347)
* Correção de um problema que fazia com que duas modificações fossem registradas quando somente uma era esperada após alternar entre os modos [!UICONTROL Procurar] e [!UICONTROL Design] no VEC ao interagir com um elemento de formulário. (TGT-52455)
* Correção de um problema que impedia a seleção da configuração [!UICONTROL Clicou em um elemento] no VEC atualizado devido a um erro informando que o seletor era inválido, já estava em uso ou não estava visível. (TGT-52467)
* Correção de um problema em que a adição de uma caixa [!UICONTROL Oferta de recomendação] no VEC atualizado causava a exibição de caixas duplicadas (fantasmas). A alternância entre a Experiência A e B adicionou repetidamente mais caixas fantasmas. (TGT-52505 e TGT-52519)
* Correção de um problema na interface atualizada do usuário [!DNL Target], em que as alterações em uma Oferta do HTML feitas por meio do menu [!UICONTROL Oferta] não eram refletidas na atividade associada, e vice-versa. Este comportamento agora corresponde à interface herdada, onde as atualizações são sincronizadas corretamente entre o menu [!UICONTROL Oferta] e a atividade. (TGT-52540 e TGT-52541)
* Correção de um problema em que atualizações recentes de [!UICONTROL Fragmentos de experiência] na [!UICONTROL Biblioteca de ofertas] não eram refletidas ao tentar usá-las em uma atividade. (TGT-52659)
* Correção de um problema de localização na tradução para chinês simplificado de uma mensagem de confirmação. A versão anterior não tinha aspas ao redor do nome do local e usava linguagem informal, ao contrário do guia de estilo do cliente. A tradução atualizada agora usa pontuação adequada e um tom formal. (TGT-52364)

### [!DNL Target Standard/Premium] 25.5.3 (22 de maio de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema em que o recurso de pesquisa por nome na lista [!UICONTROL Atividades] não funcionava corretamente com consultas de várias palavras. (TGT-52529)
* Correção de um problema que impedia a exclusão de experiências de atividades de [!UICONTROL Automated Personalization] (AP). (TGT-52383)
* Correção de um problema em que a opção &quot;[!UICONTROL Contém]&quot; estava ausente das [!UICONTROL Regras de filtro] ao gerenciar conteúdo em atividades de AP. (TGT-52384)
* Correção de uma inconsistência de relatórios em atividades de [!UICONTROL Automated Personalization] (AP), especificamente relacionadas ao modo como as ofertas padrão são rastreadas e relatadas usando valores `optionLocalId` do sistema interno de [!DNL Target].
* Correção de um problema em que os links de controle de qualidade falhavam em fornecer a experiência de atividade desejada. (TGT-52163)
* Correção de um problema em que usuários com permissões de [!UICONTROL Aprovador] eram impedidos de editar atividades online incorretamente, recebendo uma mensagem de erro de &quot;Acesso negado&quot;. (TGT-52416)
* Correção de um problema em que os refinamentos de público-alvo não eram exibidos para determinadas atividades na interface do usuário atualizada [!DNL Target]. (TGT-52057)
* Correção de um problema que fazia com que refinamentos de público-alvo e públicos-alvo de atividades fossem revertidos na interface do usuário atualizada. (TGT-52158)
* Correção de um problema em que a geração de ofertas ad-hoc resultava em ofertas duplicadas. (TGT-51938)
* Correção de um problema que bloqueava atualizações de ofertas e exibia incorretamente um erro &quot;Usuário inválido&quot;. (TGT-52361)
* Correção de um problema que impedia o salvamento de atividades existentes, acionando um erro &quot;Entrada de usuário inválida&quot;. (TGT-52422)
* Correção de um problema que bloqueava a edição de ofertas existentes do HTML, acionando um erro &quot;Entrada de usuário inválida&quot; ao salvar, mesmo quando nenhuma alteração de código era feita. (TGT-52351)
* Correção de um problema que impedia [!DNL Target] de reconhecer o caractere &quot;#&quot; na URL de um site. (TGT-52093)
* Correção de um problema que impedia a edição de atividades [!DNL Recommendations] para adicionar ou atualizar promoções, o que causava falhas no salvamento e promoções duplicadas. (TGT-52343)
* Correção de um problema que impedia alterações em critérios ou designs nas atividades [!DNL Recommendations], resultando em um erro &quot;JSON inválido: nome de propriedade não reconhecido&quot;. (TGT-52375)
* Correção de um problema em que os critérios de sequência não eram exibidos corretamente no [!UICONTROL Visual Experience Composer] (VEC) para [!DNL Recommendations] atividades. (TGT-52435)
* Correção de um problema em que os modos de exibição não eram identificados corretamente em páginas do SPA ao usar o [!DNL Adobe Experience Platform Web SDK]. (TGT-52106)
* Correção de um problema em que os detalhes da Decisão no dispositivo (ODS) não eram salvos corretamente, apesar de serem incluídos na carga da operação em lote. (TGT-52406)
* Adição de um campo `audienceMetadata` às atividades, permitindo que ele seja lido e atualizado durante a edição. (TGT-51004)
* Adição de uma mensagem de erro para alertar os usuários quando um período de público-alvo for inválido. (TGT52522)
* Atualização da estrutura da atividade para oferecer suporte a públicos-alvo duplicados de diferentes tipos. (TGT-51200)

<!--
### [!DNL Adobe Target] [!DNL AI Assistant] release (May 16, 2025)

We are thrilled to announce the launch of the [!DNL AI Assistant] in [!DNL Adobe Target]! This powerful user interface feature is designed to help you navigate and understand [!DNL Target] concepts with ease. Available across multiple products in [!DNL Adobe Experience Cloud], including [!DNL Target], [!DNL AI Assistant] is here to revolutionize your experience.

[!DNL AI Assistant] in [!UICONTROL Target] is a conversational tool that you can use to accelerate your workflows with [!DNL Experience Platform] applications and services. Use [!DNL AI Assistant] to boost your overall productivity and amplify your understanding of product knowledge

In [!DNL Target], the first phase of [!DNL AI Assistant] provides invaluable product knowledge grounded in [!DNL Experience League] documentation. Whether you are setting up a profile script, troubleshooting errors, or considering an upgrade to the AEP Web SDK, [!DNL AI Assistant] has you covered.

For more information, see [Coworker skills for Adobe Target](/help/main/c-intro/coworker-skills.md).
-->

### [!DNL Target Standard/Premium] 25.5.2 (8 de maio de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* [!DNL Target] usuários com direitos de [!UICONTROL Administrador do Produto] e [!UICONTROL Administrador do Sistema] agora podem editar todas as configurações nas páginas [!UICONTROL Administração], independentemente de sua função no [!DNL Target]. Os usuários sem essas permissões têm acesso somente leitura a essas configurações. Esta atualização garante um controle de acesso mais rigoroso sobre [Configurações de administração](/help/main/administrating-target/administrating-target.md). (TGT-48179)
* Correção de um problema de cache que impedia salvar a atividade [Preferências do site](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings). (TGT-52213)
* Correção de um problema em que os clientes não podiam habilitar a seleção por ID e classe na seção [!UICONTROL Preferências do site] após carregar o site no VEC. A configuração [!UICONTROL Preferências do Site] foi revertida automaticamente para desabilitada mesmo depois de ser habilitada. (TGT-52207)
* Correção de um problema em que o [!UICONTROL Visual Experience Composer] (VEC) não exibia a página correta quando as URLs de [entrega de página](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings) terminavam com uma barra (/). (TGT-52237)
* Correção de um problema que impedia a remoção de modificações de código personalizadas ao alterar experiências. (TGT-52240)
* Correção de um problema em que as modificações do HTML no VEC sobrepunham elementos de página existentes. (TGT-52265)
* Correção de um problema que impedia a edição do código personalizado no VEC atualizado porque o código personalizado existente não estava visível no editor. (TGT-52272)
* Correção de um problema que causava uma mensagem de erro &quot;Nomes duplicados não são permitidos&quot; ao salvar uma atividade do Recommendations. (TGT-52318)
* Correção de um problema no VEC atualizado que impedia os clientes de editar elementos de texto ou remover objetos de contêiner. (TGT-52348)
* Correção de um problema que impedia [!DNL Customer Journey Analytics] de ser exibido corretamente em uma página de [!UICONTROL Visão geral] da atividade. (TGT-52359)
* Correção de um problema que impedia que os grupos de relatórios persistissem nas atividades de [!UICONTROL Automated Personalization] (AP). (TGT-52368)
* Correção de um problema que impedia o salvamento de atividades que incluíam o Offer Decisioning. (TGT-52390)
* Correção de um problema em que a oferta padrão era selecionada, mas o outro conteúdo da oferta era exibido nas atividades de [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Teste multivariado] (MVT). (TGT-52372)
* Correção da lógica de permissões GET para verificar com OU entre o acesso completo à organização e o acesso específico à organização + usuário. (TGT-52374)
* Correção de um problema em que os nomes de público-alvo não eram exibidos após selecionar um público-alvo para [!UICONTROL Conteúdo gerenciado] e [!UICONTROL Relatórios de públicos-alvo], mesmo que [!UICONTROL Mostrar apenas selecionados] estivesse habilitado. (TGT-52393)

### [!DNL Target Standard/Premium] 25.5.1 (5 de maio de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema que impedia que refinamentos de público-alvo fossem exibidos para determinadas atividades na interface atualizada. (TGT-52057)
* Correção de um problema que impedia o uso de públicos-alvo combinados em atividades do. (TGT-52346)
* Correção de um problema que impedia a criação de uma nova atividade em um espaço de trabalho não padrão usando um público somente atividade do mesmo espaço de trabalho. (TGE-52349)
* Correção de um problema que fazia com que os públicos-alvo somente de atividades desaparecessem da interface atualizada após criar e selecionar um novo público-alvo. (TGT=52091)
* Correção de um problema que impedia o uso de públicos-alvo duplicados em atividades do. (TGT-51200 e TGT-52057)
* Correção de um problema que fazia com que refinamentos de público-alvo e públicos-alvo de atividades fossem revertidos na interface do usuário atualizada. (TGT-52158)
* Correção de um problema que impedia a criação de uma nova atividade devido ao erro de entrada do usuário: &quot;espaço de trabalho não padrão não permitido para este usuário&quot;. (TGT-52267)
* Correção de um problema que impedia a exibição de ofertas na interface atualizada para espaços de trabalho padrão e não padrão. [!DNL Target] agora exibe ofertas de ambos os espaços de trabalho. (TGT-52339)
* Correção de um problema em que [!DNL Target] não avisava os clientes ao editar uma atividade e alterar um elemento de site modificado. (TGT-52100)
* Correção de um problema em que a edição de uma oferta com ofertas ad-hoc criava uma nova oferta em vez de atualizar a existente. (TGT-52135)
* Correção de um problema que causava um erro de carga inválida ao mover ofertas para pastas. (TGT-52325)
* Correção de um problema que causava um erro de entrada do usuário ao mover ofertas para pastas. (TGT-52296)
* Adicionado um campo `audienceMetadata` para cada atividade, e verificado se ele é lido e atualizado ao editar a atividade. (TGT-51004)

### [!DNL Target Standard/Premium] 25.4.5 (25 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema que gerava discrepâncias nas listagens de público entre a página de configurações [!UICONTROL Atividade] e a página de visão geral [!UICONTROL Relatórios]. (TGT-52203)
* Correção de um problema que impedia a adição de uma nova página a uma atividade devido a um erro de entrada de usuário inválido. (TGT-52263)
* Correção de um problema que fazia com que `OptionLocalIDs` fosse incrementado incorretamente quando a opção permanecesse inalterada. (TGT-52187)
* Correção de um problema que fazia com que `location` e `OptionLocalIDs` fossem incrementados incorretamente quando a opção permanecesse inalterada. (TGT-52188)
* Correção de um problema que fazia com que o local na página [!UICONTROL Visão geral] da atividade estivesse incorreto. (TGT-52182)
* Correção de um problema em que um aviso de seletor inválido não era exibido para um local inválido. (TGT-52110)
* Correção de um problema para que os arquivos de relatórios baixados mostrassem corretamente os dados presentes na interface do usuário dos relatórios. (TGT-52068)
* Correção de um problema para que as operações em lote não falhassem após a adição das regras de entrega de página. (TGT-52097)
* Correção de um problema que fazia com que [!DNL Target] cortasse todos os parâmetros de consulta da URL do site. (TGT-52100)
* Correção de um erro de console que impedia os clientes de criar atividades na interface herdada e atualizada do [!DNL Target]. (TGT-52181)
* Correção de um problema que impedia os clientes de adicionar novas páginas, causando um erro de entrada de usuário inválido. (TGT-52258)
* Correção de um problema que fazia com que as modificações desaparecessem após adicionar outras páginas e, em seguida, navegar de volta para a guia [!UICONTROL Experiências]. (TGT-52264)
* Correção de um problema que impedia os clientes de alterar o público-alvo em uma atividade de [!UICONTROL Direcionamento de experiência] (XT). (TGT-52191)
* Correção de um erro que impedia a edição de uma atividade de XT devido a uma regra de interface do usuário não compatível. (TGT-52273)
* Correção de um problema no [!UICONTROL Visual Experience Composer] (VEC) atualizado em que as navegações estruturais nem sempre eram exibidas na parte inferior do editor, causando dificuldades para selecionar elementos com precisão. (TGT-52169)
* Correção de um problema em que a lista suspensa [!UICONTROL Público-alvo] não exibia todos os públicos-alvo devido à paginação. (TGT-52204)
* Correção de um problema que causava uma mensagem de entrada de usuário inválida ao adicionar novas ofertas em atividades de [!UICONTROL Automated Personalization] (AP). (TGT-52210)
* Correção de um problema em que o [!UICONTROL Analytics for Target] (A4T) era selecionado incorretamente como fonte de relatórios, mesmo que o cliente não tivesse acesso ao A4T. (TGT-52226)
* Correção de um problema que impedia salvar uma atividade com a métrica de URL [!UICONTROL Exibir uma página]. (TGT-52260)
* Correção de um problema que impedia os clientes de selecionar espaços de trabalho ao criar ofertas em uma atividade. (TGT-52289)
* Correção de um problema que impedia os clientes de criar atividades em todos os espaços de trabalho. (Tgt-52218)
* Correção de um problema em que as modificações de uma experiência eram exibidas incorretamente ao alternar para outra experiência. (TGT-52184)
* Correção de um problema em que a oferta padrão era exibida incorretamente na interface do usuário do [!DNL Target] ao abrir a atividade. (TGT-52198)

### Atualização de permissões do Target (22 de abril de 2025)

Essa atualização futura melhora o controle organizacional sobre as configurações da instância [!DNL Target], evitando atualizações acidentais que podem afetar a entrega da atividade em várias equipes de teste e personalização.

A partir de 22 de abril de 2025, somente administradores do [!UICONTROL Produto] e das [!UICONTROL Soluções] poderão atualizar configurações nas seções de [!UICONTROL Administração], independentemente de suas funções nos espaços de trabalho do [!DNL Target]. Os usuários sem esta permissão terão acesso somente leitura às seções [!UICONTROL Administração].

Para obter mais informações, consulte [Administrar Target](/help/main/administrating-target/start-target.md).

### [!DNL Target Standard/Premium] 25.4.4 (17 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Adição de uma mensagem de erro para orientar os usuários sobre a resolução de opções de duplicação em uma atividade. (TGT-51927)
* Correção de um problema em que `ClickTrack` seletores não eram removidos ao excluir páginas ou experiências com ofertas de redirecionamento. (TGT-51952)
* Correção de um problema causado pela permissão de seletores `ClickTrack` vazios. [!DNL Target] agora exige que o campo seletor não esteja em branco. (TGT-52107)
* Correção de um problema que permitia incorretamente métricas com nomes duplicados. Métricas agora exigem nomes exclusivos. (TGT-52201)
* Correção de um problema em que as definições de público-alvo não estavam visíveis ao editar o direcionamento no nível de oferta nas atividades do [!UICONTROL Automated Personalization] (AP). (TGT-52148)
* Correção de um problema que impedia que clientes com direitos de [!UICONTROL Editor] salvassem atividades. (TGT-52227)
* `OptionLocalIDs` não incrementa mais incorretamente quando a opção permanece inalterada. (TGT-52139)
* Correção de um problema que causava uma mensagem &quot;Inválido `optionLocalIds`&quot; ao tentar criar uma atividade. (TGT-52154)
* Foram corrigidas discrepâncias entre `OptionLocalIDs` definidas para uma atividade e aquelas usadas para definir experiências. (TGT-52215)
* Correção de um problema que causava uma falha de validação que ocorria ao tentar criar uma atividade A/B. (TGT-51923)

### [!DNL Target Standard/Premium] 25.4.3 (11 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um erro que impedia os clientes de abrirem o pop-up de informações de público-alvo para determinadas [!UICONTROL atividades de Direcionamento de experiência] (XT). (TGT-52049)
* Correção de um problema em que a configuração de público-alvo era revertida para &quot;[!UICONTROL Todos os visitantes]&quot; após as alterações feitas no [!UICONTROL Visual Experience Composer] (VEC). (TGT-52132)
* Correção de um problema em que os refinamentos de público-alvo não eram exibidos para atividades específicas (TGT-52057)
* Correção de um problema que impedia os clientes de inserir um [!UICONTROL Fragmento de experiência] no espaço de trabalho padrão. (TGT-52073)
* Correção de um problema em que uma oferta era exibida como &quot;Conteúdo não encontrado&quot; e não era exibida na página [!UICONTROL Ofertas] para uma atividade do [!UICONTROL Automated Personalization] (AP). (TGT-52150)
* Adição da capacidade de permitir públicos-alvo duplicados em uma atividade. (TGT-51200)
* Correção de um problema em que o nome incorreto da mbox era exibido na página [!UICONTROL Metas e configurações] para uma atividade de XT após a edição. (TGT-52026)
* Correção de um problema em que `defaultContent` era exibido nas opções, apesar de não estar em `experiences/optionLocations`. (TGT-52036)
* Correção de um problema para garantir que cadeias de caracteres vazias não fossem convertidas em valores nulos. (TGT-52037)
* Correção de um problema que exigia que os clientes reconfigurassem a [!UICONTROL Meta de otimização] em [!UICONTROL Configurações de relatórios] na página [!UICONTROL Metas e configurações] após as edições. (TGT-52071)
* Correção de um problema em que uma atividade sem regras de entrega de página exibia várias regras na página [!UICONTROL Visão geral]. (TGT-52084)
* Adição de uma mensagem de erro para usuários que tentam salvar uma oferta com caracteres fora do plano multilíngue básico, como emojis. (TGT-52105)
* Correção de um problema em que a abertura de uma atividade acionava a mensagem de erro: &quot;Esta atividade está usando um ou mais públicos-alvo excluídos na origem&quot;. (TGT-52120)
* Correção de um problema em que as métricas ClickTrack não eram exibidas no [!UICONTROL Visual Experience Composer] (VEC) atualizado durante a edição. (TGT-52152)
* Correção de um problema em que um URL com um parâmetro de consulta como o local da atividade não exibia o parâmetro de consulta na página [!UICONTROL Visão geral] da atividade. (TGT-51635)
* Correção de um problema que impedia que toda a URL de experiência fosse exibida no [!UICONTROL modo de Navegação] no [!UICONTROL Visual Experience Composer] (VEC). (TGT-52101)
* Correção de um problema em que a edição de uma atividade fazia com que a entrega da página adicionasse &quot;/&quot; ao final do URL, tornando-a inválida. (TGT-52114)
* Correção de um problema em que o link [!UICONTROL Controle de qualidade da atividade] no [!UICONTROL Experience Composer baseado em formulário] era redirecionado incorretamente para a página inicial [!DNL Adobe Experience Cloud]. (TGT-52055)
* Correção de um problema em que páginas adicionais adicionadas à atividade [!UICONTROL Teste A/B] não eram retidas após salvar e reabrir. (TGT-51994)
* Correção de um problema que impedia os clientes de excluir estilos na seção de estilo em linha. (TGT-52070)
* Restauração do acesso a [cartões de definição de público-alvo](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) na caixa de diálogo [!UICONTROL Controle de qualidade da atividade], semelhante à interface herdada. (TGT-52056)
* A interface atualizada não salva páginas ou públicos-alvo sem modificações. Se os clientes adicionaram novas páginas ou públicos-alvo a uma atividade, mas não fizeram alterações, [!DNL Target] descartou os públicos-alvo não modificados ao salvar. Foram adicionadas notificações em locais relevantes para informar os usuários sobre esse comportamento. (TGT-52104)

### [!DNL Target Standard/Premium] 25.4.1 (2 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema que fazia com que os públicos-alvo da experiência desaparecessem das atividades. (TGT-52003)
* Correção de um problema que causava elementos inesperados durante a entrega. (TGT-52011)
* Correção de um problema que impedia os clientes de visualizar o público no gráfico de direcionamento na página de exibição Mover[!UICONTROL r]e durante a edição da atividade. (TGT-52050)
* Correção de um problema que impedia os clientes de reordenar as experiências em ordem de prioridade nas atividades de [!UICONTROL Direcionamento de experiência] (XT). (TGT-52054)
* Correção de um problema que causava renderização incorreta ao desfazer alterações no estilo do texto. (TGT-51876)
* Correção de um problema que, ao modificar uma oferta de redirecionamento, [!DNL Target] também remove todos os seletores [!UICONTROL ClickTrack] associados a essa oferta. (TGT-51936)
* Correção de um problema que fazia com que [!DNL Target] salvasse incorretamente o seletor ao cancelar [!UICONTROL ClickTrack]. (TGT-51937)
* Correção de um problema que disparava um erro de nome inválido depois de abrir e fechar o seletor de mbox na página [!UICONTROL Metas e configurações] sem fazer alterações. (TGT-51983)
* Correção de um problema que bloqueava a edição de ofertas ad hoc criadas na interface herdada do usuário [!DNL Target]. (TGT-51984)
* Correção de um problema que bloqueava atividades de edição com ofertas ad hoc que continham código personalizado. (TGT-51995)
* Correção de um problema que fazia com que as regras de exclusão fossem exibidas como regras de inclusão ao editar definições combinadas de público-alvo. (TGT-51999)
* Correção de um problema que impedia a exibição correta do código personalizado durante a edição da experiência. (TGT-52005)
* Correção de um problema que tornava a opção [!UICONTROL Inserir Antes] indisponível para inserir conteúdo antes da barra de navegação. (TGT-52031)
* Correção de um problema que impedia o realce correto da experiência padrão nos relatórios. (TGT-51716)
* Correção de um problema que acionava uma mensagem `default message [Invalid optionLocalIds: xx]]` ao criar uma atividade. (TGT-52038)

### Versão 2.11.8 da at.js (31 de março de 2025)

* Solução da vulnerabilidade identificada pelo CodeQL na validação do sufixo da cadeia de caracteres para evitar casos de borda durante operações de redimensionamento e movimentação. (TNT-51516)

### [!DNL Target Standard/Premium] 25.3.8 (28 de março de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Solução de um problema que fazia com que a página [!UICONTROL Atividades] carregasse lentamente. (TGT-51151)

### [!DNL Target Standard/Premium] 25.3.7 (26 de março de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema que bloqueava o salvamento de atividades de várias páginas se uma página fosse excluída após as modificações. (TGT-51988)
* Correção de um erro que ocorria ao editar uma atividade: `default message [Invalid optionLocalIds: xx]]`. (TGT-51985)
* Solução de um problema em que a adição de novas modificações a uma atividade removia as modificações existentes. (TGT-51981)
* Foi resolvido um problema em que a substituição de um público por &quot;[!UICONTROL Todos os visitantes]&quot; durante a criação ou edição da atividade causava um erro &quot;Públicos duplicados não são permitidos&quot;. (TGT-51978)
* Solução de um problema que causava um erro de &quot;Entrada de usuário inválida&quot; ao salvar uma atividade de [!UICONTROL Teste A/B]. (TGT-51976)
* Solução de um problema que impedia a exibição correta das métricas calculadas na página [!UICONTROL Metas e configurações]. (TGT-51975)
* Solução de um problema que impedia a correspondência de `companyName` e `reportSuite` na configuração [!DNL Analytics] para a métrica `pageviews`. (TGT-51965)
* Solução de um problema em que a troca de experiências em uma atividade removia as modificações. (TGT-51945)
* Solução de um problema em que a remoção de um público-alvo de página também removia os seletores [!UICONTROL ClickTrack]. (TGT-51935)
* Solução de um problema que tornava uma atividade não editável após abrir sua página [!UICONTROL Visão geral]. (TGT-51931)
* Solução de um problema que causava um erro `[Unused optionLocalIds: 0]]` durante a criação da atividade. (TGT-51920)
* Solução de um problema em que algumas alterações não eram traduzidas corretamente após a remoção das alterações de estilo do texto. (TGT-51876)
* Solução de um problema que impedia a atualização correta de públicos-alvo no [!UICONTROL Experience Composer baseado em formulário]. (TGT-51845)
* Solução de um problema em que a URL no [!UICONTROL Visual Experience Composer] não era atualizada corretamente durante a navegação da atividade. (TGT-51832)
* Correção de um problema que impedia a exibição de ofertas na interface do usuário do [!UICONTROL Offers], apesar de serem exibidas corretamente ao criar uma atividade e adicionar ofertas. (TGT-51805)
* Solução de um problema em que algumas atividades não tinham uma tela de fallback para exibir o conteúdo padrão quando o conteúdo personalizado ou direcionado não podia ser entregue. (TGT-51638)
* Solução de um problema que impedia que ofertas ativas e determinadas pastas fossem exibidas corretamente na interface do usuário [!UICONTROL Ofertas]. (TGT-51628)
* Solução de um problema que impedia que algumas cadeias de caracteres de URL e goURLs fossem localizadas corretamente. (TGT-35741)
* Correção de um problema que impedia que as funções ([!UICONTROL Aprovador], [!UICONTROL Editor] e [!UICONTROL Observador]) fossem localizadas corretamente na interface do usuário do [!DNL Target]. (TGT-29925)

### [!DNL Target Standard/Premium] 25.3.6 (14 de março de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção do erro &quot;Entrada de usuário inválida&quot; em [!UICONTROL atividades do Visual Experience Composer] (VEC) com o [!UICONTROL Rastreamento de cliques] habilitado quando o mesmo seletor [!UICONTROL ClickTrack] é usado várias vezes. (TGT-51921)
* Correção do erro &quot;Entrada de usuário inválida&quot; em atividades do VEC com locais compartilhados (por exemplo, seletor HEAD) e ofertas idênticas. (TGT-51879)
* Correção de um problema que fazia com que as modificações na experiência fossem compartilhadas entre os públicos-alvo. (TGT-51815)
* Correção de erros de validação ao criar atividades devido a conflitos de ID de segmento. Os erros ocorreram quando [!DNL Target] detectou atividades existentes usando segmentos anônimos. (TGT-51784)
* Solução de um problema que impedia [!DNL Target] de salvar atividades com regras de exclusão em um público-alvo. (TGT-51581)
* Solução de um problema que impedia os clientes de criar, excluir ou mover pastas sem acesso ao espaço de trabalho padrão. (TGT-51499)
* Solução do problema que fazia com que as solicitações GET falhassem ao recuperar a lista de métricas [!DNL Analytics]. (TGT-51106)

### [!DNL Target Standard/Premium] 25.3.5 (11 de março de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Solução de um problema que impedia os usuários de alterar ofertas no painel [!UICONTROL Modificações]. (TGT-51800)
* Solução de um problema em que as ações eram exibidas incorretamente no painel esquerdo para experiências e públicos, incluindo no modo [!UICONTROL ClickTrack]. (TGT-51895)
* Solução de um problema em que os seletores [!UICONTROL ClickTrack] não foram aplicados à página de público-alvo correta. (TGT-51871)

### [!DNL Target Standard/Premium] 25.3.4 (7 de março de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Solução de um problema em que públicos somente atividade não estavam visíveis no painel [!UICONTROL Públicos-alvo], impedindo sua edição ou reutilização. (TGT-51860)
* Correção de um problema que impedia [!DNL Target Standard] clientes de criar atividades usando os relatórios do [!UICONTROL Analytics for Target] (A4T). (TGT-51854)
* Correção de um problema que excluía os contadores de ID local da carga durante as operações de criação e edição de lote. (TGT-51867)

### [!DNL Target Standard/Premium] 25.3.2 (6 de março de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema em que a cópia de uma atividade com um público-alvo somente de atividade não criava uma nova atividade, usando erroneamente o público-alvo da atividade original. (TGT-51855)
* Correção de um problema que impedia a edição de [!UICONTROL atividades de Direcionamento de experiência] (XT) com públicos somente atividade. (TGT-51846)
* Correção de um problema em que o [!UICONTROL Visual Experience Composer] (VEC) não aplicava modificações em uma experiência corretamente na primeira edição. (TGT-51843)
* Correção de um problema que acionava um erro de &quot;ID&quot; ao clicar em determinados elementos no VEC. (TGT-51814)
* Atualização do tratamento de erros no VEC durante a criação da atividade. (TGT-51759)
* Correção de um problema em que uma exibição ausente no painel [!UICONTROL Modificações] causava um erro de &#39;entrada de usuário inválida&#39; ao salvar a atividade. (TGT-51827)
* Correção de um problema que impedia a criação de critérios de recomendações. (TGT-51834)
* Adição de uma mensagem de confirmação antes de redirecionar para um URL diferente. (TGT-51703)
* Correção de problemas com testes de integração do GraphQL em ofertas e pastas. (TGT-51839)

### [!DNL Target Standard/Premium] 25.3.1 (3 de março de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Um público-alvo combinado pode incluir subgrupos, cada um contendo vários públicos-alvo. Esta versão corrigiu um problema que impedia que públicos-alvo de subgrupos fossem exibidos na caixa de diálogo [!UICONTROL Regras]. (TGT-51813)
* Solução de um problema em que alguns públicos-alvo de experiência eram substituídos por [!UICONTROL Todos os visitantes] ao abrir atividades mais antigas. (TGT-51812)
* Solução de um problema que impedia a edição de atividades com públicos somente atividade. (TGT-51807)
* Solução de um problema que impedia a edição de modificações no cabeçalho da página na interface atualizada do usuário do [!DNL Target]. (TGT-51797)
* Correção de um erro nulo que ocorria ao duplicar uma experiência, excluir outra experiência e tentar salvar a atividade. (TGT-51796)
* Correção de um problema que impedia a exibição de regras de exclusão de público-alvo no painel de informações do público-alvo durante a etapa [!UICONTROL Direcionamento] da criação de atividades. (TGT-51579)
* Mensagens de erro atualizadas localizadas em coreano. (TGT-51701 e TGT-51699)

### [!DNL Target Standard/Premium] 25.2.3 (26 de fevereiro de 2025)

Esta versão do inclui as seguintes atualizações:

* Solução de um problema que impedia as atualizações de atividade após a versão [!DNL Target] 25.2.1 para algumas atividades. (TGT-51781)
* Solução de um problema em que todas as alterações de público-alvo no estado eram removidas ao cancelar o processo de criação de atividade (selecionando [!UICONTROL Cancelar] em vez de [!UICONTROL Adicionar público-alvo]). (TGT-51769 e TGT-51770)
* Solução de um problema em que o [!UICONTROL Visual Experience Composer] (VEC) não era carregado para algumas atividades, principalmente quando um código personalizado era usado.  O problema fez com que o VEC exibisse uma tela em branco ou a interface do usuário do [!DNL Target] revertesse para sua versão mais antiga. (TGT-51758)
* Correção de um problema em que as modificações eram descartadas após a edição da entrega de página para públicos-alvo. (TGT-51756)
* Solução de um problema em que todos os públicos-alvo não métricos (públicos-alvo de páginas e experiências) eram removidos das atividades ao alterar um tipo de métrica na página [!UICONTROL Metas e configurações]. (TGT-51753)
* Solução de um problema em que clicar em [!UICONTROL Cancelar] ao editar uma atividade navegava pela interface do usuário do Target para a [!UICONTROL Lista de Atividades] em vez da página [!UICONTROL Detalhes da Atividade]. (TGT-51731)
* Solução de um problema que impedia os clientes de baixar relatórios por meio da opção [!UICONTROL Exportar relatórios para CSV]. (TGT-51708)
* Solução de um problema no Experience Composer baseado em formulário, no qual [!DNL Target Standard] clientes eram exibidos incorretamente ao usar [!UICONTROL Propriedades], um recurso [!DNL Target Premium]. (TGT-51678)
* Correção de um problema que impedia a exibição de atributos do [!DNL Adobe Experience Platform] ao criar novas ofertas. (TGT-51665)
* Todos os filtros ativos do inventário [!DNL Recommendations] foram movidos para a pesquisa rápida, alinhando a interface com a [!UICONTROL Pesquisa de Catálogo] em vez do painel [!UICONTROL Filtro]. (TGT-50723)

### at.js versão 2.11.7 (26 de fevereiro de 2025)

Esta versão inclui a seguinte atualização:

* Log de Telemetria Corrigida quando `localStorage` não está disponível. A telemetria estava causando um problema para alguns clientes que tinham o `localStorage` desativado nos navegadores.

Para obter informações sobre esta versão e versões anteriores da at.js, consulte [detalhes de versão da at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank}.

### Target Standard/Premium 25.2.1 (terça-feira, 17 de fevereiro de 2025) {#ui-update-2}

Esta versão do inclui as seguintes atualizações:

* Atualização da interface do usuário de [!UICONTROL Atividades]
* [!DNL Recommendations] atualização da interface do usuário

#### Atualização da interface do usuário de [!UICONTROL Atividades]

Conforme o esforço de modernização da interface do usuário do [!DNL Adobe Target] continua, temos o prazer de anunciar a disponibilidade geral da interface do usuário das [!UICONTROL Atividades] atualizadas.

>[!NOTE]
>
>A partir de 17 de fevereiro, os clientes terão gradualmente acesso à nova interface de [!UICONTROL Atividades]. Para garantir uma implantação perfeita para todos os clientes, esta versão será implantada em estágios controlados. O primeiro estágio atualizará o grupo inicial de clientes [!DNL Target] para a nova interface de usuário de [!UICONTROL Atividades]. Os estágios subsequentes atualizarão os clientes restantes.

>[!IMPORTANT]
>
>Para obter informações importantes sobre o plano para alternar o fim da vida útil da versão da interface do [!DNL Target], consulte [[!DNL Target] desativação da alternância de versão da interface do usuário](/help/main/r-release-notes/release-notes.md#toggle).

Com base no sistema de design [!DNL Adobe Spectrum] mais recente, a atualização padroniza padrões de design anteriormente inconsistentes, além de adicionar novas melhorias, como:

* [Relatórios reprojetados](/help/main/administrating-target/reporting.md) para obter melhores insights sobre os resultados da atividade.
* [[!UICONTROL Atualização da página Log de Alterações]](/help/main/c-activities/change-log.md), obtendo agora as informações de [[!DNL Audit Query API]](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/audit-logs/audit-api/overview){target=_blank} para insights em tempo real.
* [Exibições de lista personalizáveis](/help/main/c-activities/activities.md) para maior flexibilidade entre diferentes necessidades de equipe.
* [Triagens de detalhes e informações rápidas](/help/main/c-activities/activities.md) aprimoradas para facilitar o acesso às informações.
* [Opções de filtro e pesquisa persistentes em sessão](/help/main/c-activities/activities.md).
* O [reconstruiu completamente o [!UICONTROL Visual Editing Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) com suporte para as últimas atualizações de segurança de provedores de navegador e uma interface de usuário moderna.

  Para obter informações sobre como o VEC atualizado difere da versão anterior, consulte:

  * [Alterações no Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)
  * [Opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)

* [Atualização [!DNL Chrome] extensão](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) com suporte para Manifest V3 para maior segurança e suporte aprimorado para cookies próprios.

![Atividades atualizadas](/help/main/r-release-notes/assets/activities-refresh.png)

#### [!DNL Recommendations] atualização da interface do usuário

Conforme o esforço de modernização da interface do usuário do [!DNL Adobe Target] continua, temos o prazer de anunciar a disponibilidade geral da interface do usuário do [!DNL Recommendations] atualizada.

>[!NOTE]
>
>A partir de 17 de fevereiro, os clientes terão gradualmente acesso à nova interface do usuário do [!UICONTROL Recommendations]. Para garantir uma implantação perfeita para todos os clientes, esta versão será implantada em estágios controlados. O primeiro estágio atualizará o grupo inicial de clientes [!DNL Target] para a nova interface de usuário de [!UICONTROL Atividades]. Os estágios subsequentes atualizarão os clientes restantes.

Com base no sistema de design [!DNL Adobe Spectrum] mais recente, a atualização padroniza padrões de design anteriormente inconsistentes, além de adicionar novas melhorias, como:

* A [pesquisa no catálogo de produtos](/help/main/c-recommendations/c-products/catalog-search.md) agora apresenta um banco de dados atualizado que permite a sincronização de produtos em tempo real.
* Objetos [!UICONTROL Recommendations] ([!UICONTROL Critérios], [!UICONTROL Designs], [!UICONTROL Coleções] e [!UICONTROL Exclusões]) [criados sobre a API agora estão disponíveis na interface](/help/main/c-recommendations/c-recommendations-faq/recommendations-faq.md).
* [As configurações de recomendações](/help/main/administrating-target/recommendations-settings.md) foram consolidadas na seção [!UICONTROL Administração].
* Exibições de lista personalizáveis para maior flexibilidade entre diferentes necessidades da equipe.
* Editores de código HTML e JSON atualizados com [realce de sintaxe e numeração de linha](/help/main/c-experiences/c-manage-content/create-json-offer.md).
* Melhorias nas telas de detalhes e informações rápidas para facilitar o acesso às informações.
* Opções de filtro e pesquisa persistentes na sessão.

![Atualização da interface do usuário do Recommendations](/help/main/r-release-notes/assets/recs-ui-refresh.png)

### Target Standard/Premium 25.1.1 (sexta-feira, 9 de janeiro de 2025) {#ui-update-1}

Esta versão do inclui as seguintes atualizações:

#### Atualização da interface de usuário da [!UICONTROL Biblioteca de Ofertas]

Para aprimorar a experiência do usuário para [!DNL Adobe Target] usuários, esta versão atualiza a interface do usuário da [!UICONTROL Biblioteca de Ofertas].

>[!NOTE]
>
>Para garantir uma implantação perfeita para todos os clientes, esta versão será implantada em estágios controlados. O primeiro estágio atualizou o grupo inicial de clientes do Target para a nova interface do usuário de ofertas. Os estágios subsequentes atualizarão os clientes restantes.

>[!IMPORTANT]
>
>Para obter informações importantes sobre o plano para alternar o fim da vida útil da versão da interface do [!DNL Target], consulte [[!DNL Target] desativação da alternância de versão da interface do usuário](/help/main/r-release-notes/release-notes.md#toggle).

Usando o sistema de design [!DNL Adobe Spectrum] mais recente, esta atualização padroniza padrões de design inconsistentes e introduz novas melhorias, incluindo as seguintes:

* **Gerenciamento de ofertas em massa**: selecione e exclua ou mova várias ofertas simultaneamente.

* **[!UICONTROL Atualizações do &#x200B;] Editor de código**: editores HTML e JSON atualizados com realce de sintaxe e numeração de linha.

* **Cartões de oferta aprimorados**: cartões de informações e detalhes rápidos aprimorados para facilitar o acesso às informações.

* **Pesquisa e filtros persistentes**: adiciona opções de pesquisa e filtro persistentes na sessão.

Para obter mais informações, consulte [Ofertas](/help/main/c-experiences/c-manage-content/manage-content.md) e os subartigos desta seção. Todos os artigos de Ofertas nesta seção foram atualizados para refletir essas alterações na interface.

Este é um vídeo curto que destaca as alterações nesta versão:

![Vídeo de atualização da interface do usuário das ofertas](/help/main/r-release-notes/assets/offers-video-v2.gif)
