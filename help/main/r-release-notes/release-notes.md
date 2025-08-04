---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações;atualizações atuais;release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates;current updates
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f00cec3194863bb7187d4cdc91c39a87b624e9bd
workflow-type: tm+mt
source-wordcount: '4816'
ht-degree: 11%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abrangem atualizações para APIs do [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## Atualizações sensíveis ao tempo que você precisa saber {#time-sensitive}

[!BADGE Importante]{type=Informative}

Para atualizações com limite de tempo relacionadas ao [!DNL Adobe Target] e à sua implementação, o [!DNL Adobe] fornece notas de versão e documentação detalhadas por meio do [!UICONTROL Experience League]. Estes são alguns dos principais destaques relevantes para sua implementação:

### Desativação da alternância de versão da interface do usuário [!DNL Target]

+++Ver detalhes
A equipe do [!DNL Target] está oferecendo um recurso temporário que permite alternar entre a interface atualizada do usuário do [!DNL Target] e a versão herdada usando um botão de alternância. Essa opção está disponível somente durante a fase final de implantação da interface.

![Alternância da versão da interface do usuário de destino](/help/main/r-release-notes/assets/toggle.png)

Quando a implantação for concluída, o botão de alternância será removido e todos os usuários farão a transição permanentemente para a interface atualizada. A [!DNL Adobe] recomenda um planejamento antecipado, pois esse recurso será eliminado em breve.

#### Linha do tempo de descontinuação

Devido aos problemas recentes identificados, relacionados principalmente a personalizações complexas de clientes, a equipe do [!DNL Target] ajustou a linha do tempo de desativação:

* **17 de junho de 2025**: todas as Organizações IMS foram habilitadas para a interface do usuário [!DNL Target] atualizada, para usuários específicos ou em toda a organização, para começar a testar a nova experiência.

* **30 de junho de 2025**: a [interface atualizada [!DNL Target] 4} se tornou a experiência padrão para todas as organizações IMS que habilitaram a alternância de versão da interface do usuário.](/help/main/c-intro/understand-the-target-ui.md)

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
* **Consistência dos detalhes da atividade**: as alterações mais recentes, independentemente da interface do usuário usada, são refletidas no seu site ativo. No entanto, a interface herdada mostra apenas as alterações mais recentes feitas nessa versão. Essa situação pode causar confusão se as atividades editadas na interface atualizada forem diferentes do que você vê na interface herdada.

#### Mais recursos para saber mais sobre a interface atualizada

* [[!DNL Target] Perguntas frequentes sobre atualização da interface do usuário](/help/main/c-intro/updated-ui-faq.md): estas perguntas frequentes abordam perguntas comuns sobre a nova interface do usuário do [!DNL Target] e do [!UICONTROL Visual Experience Composer] (VEC), incluindo alterações na navegação, locais de recursos e substituição da versão temporária da interface do usuário. Seja você um profissional de marketing, desenvolvedor ou administrador, essas Perguntas frequentes ajudarão a fazer a transição descomplicada e a aproveitar ao máximo a interface atualizada.
* Notas de versão do [[!DNL Target Standard/Premium] 25.2.1 (17 de fevereiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para [!UICONTROL Activities], [!UICONTROL Recommendations] e o [!UICONTROL Visual Experience Composer] (VEC).
* Notas de versão do [[!DNL Target Standard/Premium] 25.1.1 (9 de janeiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para o [!UICONTROL Offers Library].
* [Compreender a [!DNL Target] Interface](/help/main/c-intro/understand-the-target-ui.md): fornece uma breve visão geral para ajudá-lo a se familiarizar com o [!DNL Target] e fornece links para informações mais detalhadas e instruções passo a passo.
* [[!UICONTROL Visual Experience Composer] alterações](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): a versão [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de fevereiro de 2015) introduz um [!UICONTROL Visual Experience Composer] (VEC) atualizado. Este artigo explica as diferenças entre as versões herdadas e atualizadas do VEC.
* [[!UICONTROL Visual Experience Composer] opções](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): este artigo explica a interface do usuário do VEC atualizada e suas opções.

+++

## [!DNL Target Standard/Premium] 25.7.4 (1º de agosto de 2025)

Esta versão resolve problemas recentes, causados principalmente por personalizações complexas de clientes e inclui as seguintes correções e melhorias:

**Atividades**

+++Ver detalhes
* Correção de um problema em que um cliente encontrava um erro &quot;Entrada de usuário inválida&quot; ao tentar salvar uma atividade ativa, mesmo sem fazer alterações. A resposta do GraphQL indica um problema de LocalId duplicado. (TGT-53329 &amp; TGT-53373 &amp; TGT-53195)
* Correção de um problema que impedia a criação de uma experiência de redirecionamento no VEC atualizado. O URL de redirecionamento foi ignorado e a página original foi exibida. (TGT-53306)

+++

**Localização**

+++Ver detalhes
* Correção de um problema de localização no modal [!UICONTROL Create Criteria], ao selecionar a opção &quot;entre os seguintes valores&quot; na lista suspensa [!UICONTROL Choose Price Rule], a cadeia de caracteres &quot;para&quot; era deslocalizada na seção [!UICONTROL Inclusion Rules]. (TGT-49754)
* Correção de um problema de localização com a cadeia de caracteres &quot;[!UICONTROL All host groups]&quot; na lista suspensa [!UICONTROL Environment] do assistente de Criação de feeds que não está localizada corretamente. (TGT-46737)

+++

**QA**

+++Ver detalhes
* Correção de um problema em que o ambiente de QA não carregava dados em várias guias, inutilizando a interface. (TGT-53377)
* Correção de um problema que impedia a criação de uma atividade no ambiente de controle de qualidade. O processo foi redirecionado para a página [!UICONTROL Activities] em vez de ser concluído com êxito. (TGT-53328)

+++

**Recommendations**

+++Ver detalhes
* Correção de um problema que fazia com que a página falhasse ao passar o mouse sobre o operando de &quot;deep-learning&quot; durante a criação de uma coleção no [!DNL Recommendations]. (TGT-53305)
* Correção de um problema em que as sugestões de filtro em [!UICONTROL Catalog Search] na interface atualizada eram imprecisas. (TGT-52007)
* Correção de um problema na interface do usuário do [!DNL Recommendations] em que o filtro Operandos era exibido ao usar os operadores &quot;valor está presente&quot; ou &quot;valor não está presente&quot;, embora devesse ser oculto. (TGT-53012)

+++

**Visual Experience Composer (VEC)**

+++Ver detalhes
* Correção de um problema em que um usuário clica em [!UICONTROL Manage Content] e depois em [!UICONTROL Done] ao editar uma atividade de Automated Personalization (AP). A página fica em branco e não responde. (TGT-53047 e TGT-52993)
* Correção de um problema em que a seleção da métrica de conversão [!UICONTROL Viewed an mbox] em [!UICONTROL Goals & Settings] causava uma falha na página. (TGT-53346, TGT-53343, e TGT-53348)
* Correção de um problema em que o recurso [!UICONTROL Redirect to URL] não funcionava conforme o esperado — nenhum redirecionamento ocorre mesmo com URLs válidas. (TGT-53307)

+++

**Espaços de trabalho**

+++Ver detalhes
* Correção de um problema ao copiar atividades entre espaços de trabalho que causava entradas duplicadas de &quot;Cópia de público-alvo&quot; e conflitos de ID. Agora os públicos-alvo são copiados com IDs exclusivas, contexto de espaço de trabalho e tratamento recursivo para públicos-alvo combinados (até 5 níveis). (TGT-53081)
* Correção de um problema em que o espaço de trabalho estava definido como &quot;[!UICONTROL All Workspaces]&quot;. Copiar uma atividade que já existe no espaço de trabalho padrão resulta em um erro incorreto:

  &quot;Pelo menos uma propriedade deve ser incluída para espaços de trabalho não padrão.&quot;

  Como a cópia está no espaço de trabalho padrão, nenhuma propriedade deve ser necessária. Tentar adicionar uma propriedade e salvar resulta em um segundo erro:

  &quot;Entrada de usuário inválida&quot;

+++

## [!DNL Target Standard/Premium] 25.7.3 (sexta-feira, 24 de julho de 2025)

Devido aos problemas recentes identificados, principalmente relacionados às personalizações complexas do cliente, esta versão inclui as seguintes correções e atualizações:

**Atividades**

+++Ver detalhes
* Correção de um problema em que o método `buildViews` na classe de construtor definia incorretamente `viewMaxLocalId` para a contagem total de exibições, em vez da maior `viewLocalId` atribuída. (TGT-53207)
* Correção de um problema na interface do usuário atualizada do [!DNL Target], em que as ofertas excluídas nas atividades do [!UICONTROL Automated Personalization] (AP) eram exibidas como `Deleted option with ID: X` em vez de seus nomes originais (por exemplo, `Offer Name [Deleted]`, como mostrado na interface do usuário herdada). Essa correção restaura a rotulagem significativa de ofertas excluídas, melhorando a clareza e tornando os relatórios mais precisos e fáceis de usar. (TGT-52921)
* Correção de um problema em que algumas atividades migradas do front-end do [!DNL Target] para o [!DNL Target] Central tinham configurações de métrica inconsistentes devido a um erro de sincronização corrigido anteriormente. Especificamente, as atividades que originalmente usavam uma métrica de conversão e foram atualizadas posteriormente para uma métrica baseada em análise mantiveram valores desatualizados nos campos `primaryMetricType` e `successCriteria`. (TGT-52643)
* Correção de um problema em que todo o conteúdo de uma página de visualização de QA se tornava editável devido à inclusão não intencional do atributo `contentEditable` nas modificações do HTML. Isso permitia que os usuários clicassem e editassem qualquer texto na página, causando possivelmente problemas de layout e confusão durante o controle de qualidade. (TGT-53247)
* Correção de um problema em que mover uma modificação de [!DNL Page Load] para [!UICONTROL View] fazia com que a modificação fosse duplicada, permanecendo em [!UICONTROL Page Load] enquanto também aparecia em [!UICONTROL View]. Além disso, a remoção da modificação de [!UICONTROL View] também a removeria incorretamente de [!UICONTROL Page Load]. (TGT-53270)

+++

**APIs**

+++Ver detalhes
* Correção de um problema na camada de persistência de backend em que as opções excluídas eram armazenadas corretamente, mas não acessíveis por meio de pontos de extremidade de API existentes. Como resultado, os aplicativos de front-end não puderam recuperar nomes significativos para opções excluídas, afetando as exibições de relatórios históricos. Essa correção garante que os dados de opção excluídos preservados agora possam ser exibidos corretamente na interface do usuário. (TGT-52973)
* Implementação de um novo ponto de extremidade de migração para oferecer suporte à transferência de opções de atividades excluídas de atividades baseadas em JCR para a [!DNL Target] Central. Essa funcionalidade permite o rastreamento e a geração de relatórios consistentes em todos os sistemas. Esse recurso garante que as opções excluídas sejam preservadas e sincronizadas no front-end e back-end do [!DNL Target], melhorando a integridade dos dados e dos relatórios históricos. (TGT-53217)
* Introdução de um novo endpoint de API que permite que os usuários restaurem opções de atividades excluídas anteriormente de um banco de dados secundário. Essa funcionalidade aproveita a infraestrutura existente fornecida pelas classes `RemovedCampaignElements` e `RemovedOptionInfo`, garantindo a reintegração perfeita das opções excluídas nas atividades ativas. (TGT-52903)
* Correção de um problema em que [!DNL Recommendations] atividades contendo nomes de métricas com mais de 25 caracteres não podiam ser abertas ou editadas devido a limitações de API. Essa correção garante a compatibilidade com nomes de métricas que excedem o limite de caracteres, restaurando o acesso total às atividades afetadas. (TGT-52839)

+++

**Experience Composer baseado em formulário**

+++Ver detalhes
* Correção de um problema no [!UICONTROL Form-Based Experience Composer] que causava a falha do editor após clicar no ícone **[!UICONTROL Manage Content]** ( ![Ícone Gerenciar conteúdo](/help/main/assets/icons/Experience.svg) ) ao criar ou editar uma atividade de [!UICONTROL Automated Personalization] (AP). (TGT-53047)

+++

**Recommendations**

+++Ver detalhes
* Correção de um problema que impedia [!UICONTROL Catalog Search] de carregar resultados adicionais ao rolar a tela para a parte inferior da lista, restaurando o comportamento consistente com a interface herdada. (TGT-53088)
* Correção de um problema que bloqueava a exclusão de itens da caixa de diálogo [!UICONTROL Criteria Details]. (TGT-53245)
* Correção de um problema que impedia a abertura ou interação com produtos sem nome. Esse problema ocorria ao selecionar ambientes que retornavam resultados sem nome, impedindo o acesso aos detalhes do produto. (TGT-53007)
* Correção de um problema que causava a falha da página [!UICONTROL Catalog Search] e exibia uma tela em branco ao selecionar determinados produtos. (TGT-53087)
* Correção de um problema em que os usuários não conseguiam editar a atividade [!DNL Recommendation] site_cart_z1 na interface do usuário do [!DNL Target]. A tentativa de abrir a atividade disparou um erro na página [!UICONTROL Overview], bloqueando o acesso ao editor. (TGT-53221)

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
* Correção de um problema com a funcionalidade [!UICONTROL Undo] para as opções [!UICONTROL Insert Before] e [!UICONTROL Insert After] ao configurar ofertas de imagem no VEC.

  Anteriormente, desfazer uma ação de [!UICONTROL Insert Before] ou [!UICONTROL Insert After] em ofertas de imagem resultava em um comportamento inconsistente ou na falha ao reverter corretamente a modificação, especialmente em atividades criadas na interface herdada [!DNL Target]. Esse problema foi resolvido para garantir que as ações de desfazer agora funcionem de forma confiável para essas modificações. (TGT-52809)

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

## [!DNL Target Standard/Premium] 25.7.2 (sábado, 18 de julho de 2025)

Devido aos problemas recentes identificados, principalmente relacionados às personalizações complexas do cliente, esta versão inclui as seguintes correções e atualizações:

**Atividades**

+++Ver detalhes
* Adição de um aviso de confirmação adicional ao cancelar edições de atividade com alterações não salvas: &quot;Deseja realmente salvar esta atividade? Se você não salvar, todas as alterações serão perdidas.&quot; Essa mensagem ajuda a impedir a perda acidental de dados. (TGT-52865)
* Restaurada a funcionalidade herdada para o controle deslizante [!UICONTROL Priority] em [!UICONTROL Goals & Settings], permitindo que os clientes insiram um valor numérico diretamente, conforme suportado na interface herdada. (TGT-53185 e TGT-53219)

+++

**Públicos-alvo**

+++Ver detalhes
* Correção de um problema que impedia salvar ou editar atividades contendo públicos-alvo personalizados. Os clientes encontraram a mensagem de erro &quot;Não podemos concluir sua solicitação. Contate [!DNL Adobe Client Care] se o problema persistir.&quot; ao tentar salvar alterações, ou até mesmo salvar sem alterações, em determinadas atividades. (TGT-53189)

+++

**[!UICONTROL Analytics for Target](A4T)**

+++Ver detalhes
* Correção de um problema em que os clientes visualizavam relatórios para atividades específicas na página [!UICONTROL Goals & Settings]. O link [!UICONTROL View in Analytics] aponta incorretamente para o ambiente de controle de qualidade em vez do ambiente de produção. (TGT-53163)

+++

**[!UICONTROL Experiences]e[!UICONTROL Offers]**

+++Ver detalhes
* Correção de um problema em que invocar `triggerView` por meio de código personalizado causava um loop infinito. (TGT-52885)
* Correção de um problema que causava incompatibilidades entre `LocalIds` definido para atividades e aqueles `LocalIds` usados em definições de experiência. (TGT-52669)
* Correção de um problema em que os nomes das métricas estavam ausentes na página da atividade [!UICONTROL Overview], exibindo somente &quot;Oferta&quot; em vez do nome de métrica correto. (TGT-53054)

+++

**Experience Composer baseado em formulário**

+++Ver detalhes
* Correção de um problema no [!UICONTROL Form-Based Experience Composer] que impedia o salvamento da atividade e acionava a mensagem de erro: &quot;Não é possível ler propriedades de indefinido (lendo &#39;map&#39;)&quot;. (TGT-53145)

+++

**Recommendations**

+++Ver detalhes
* Correção de um problema em que um clique em um produto do [!UICONTROL Catalog Search] exibia o erro &quot;Falha ao recuperar detalhes do produto&quot; e abria uma modal sem uma opção de fechamento. (TGT-53082)
* Correção de um problema em que as [recomendações como ofertas](/help/main/c-recommendations/recommendations-as-an-offer.md) em [!UICONTROL A/B Test] atividades não eram atualizadas corretamente ao alterar coleções ou promoções. (TGT-52884)
* Correção de um problema no ambiente de produção, em que um clique em uma entidade na interface atualizada exibia o erro: &quot;Falha ao recuperar detalhes do produto. Contate [!DNL Adobe Client Care] se o problema persistir.&quot; (TGT-53071)

+++

**Relatórios**

+++Ver detalhes
* Correção de um problema em que salvar detalhes do pedido em um arquivo CSV resultava em um arquivo vazio. (TGT-52225)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Ver detalhes
* Solução de um problema na página [!UICONTROL Goals & Settings] em que os seletores usados em várias experiências não eram realçados consistentemente como selecionados. (TGT-53062)
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
   * Se a lista [!UICONTROL Properties] exibir um aviso (provavelmente indicando que algumas propriedades podem não ser compatíveis) e o cliente clicar em [!UICONTROL Add] ou [!UICONTROL Remove] e depois em [!UICONTROL Save], todas as propriedades que não estiverem no espaço de trabalho de destino serão removidas. Se o cliente clicar em [!UICONTROL Cancel], todas as propriedades permanecerão, mesmo que não existam no espaço de trabalho de destino. (TGT-47094)
   * Se você permanecer no mesmo espaço de trabalho ou alternar de um espaço de trabalho não padrão para o padrão ou outro espaço de trabalho, tudo permanecerá como está. (TGT-53078)
* Atualização da lógica de validação da entidade para respeitar o contexto original do espaço de trabalho da atividade. Entidades como [!UICONTROL Experience Fragments] (XFs) agora são validadas com base no espaço de trabalho em que a atividade foi originalmente criada. Por exemplo, se um XF existir no espaço de trabalho padrão e a atividade for copiada do espaço de trabalho X para o espaço de trabalho Y, a validação ainda será transmitida, desde que o XF seja válido no espaço de trabalho original (padrão). (TGT-53196)
* Suporte aprimorado para copiar públicos-alvo ad-hoc durante a duplicação da atividade.
   * Públicos-alvo ad-hoc, incluindo métricas, relatórios, página e tipos somente atividade, agora são copiados automaticamente nos seguintes cenários:
      * Ao copiar uma atividade do espaço de trabalho padrão para um espaço de trabalho não padrão.
      * Ao copiar uma atividade no mesmo espaço de trabalho. (TGT-53197)

+++

## [!DNL Target Standard/Premium] 25.7.1 (sábado, 11 de julho de 2025)

Devido aos problemas recentes identificados, principalmente relacionados às personalizações complexas do cliente, esta versão inclui as seguintes correções e atualizações:

**Atividades**

+++Ver detalhes
* Correção de um problema em que a URL [!UICONTROL Activity QA] incluía um parâmetro de consulta desnecessário: `at_preview_evaluate_as_true_audience_ids`. (TGT-52907)
* Correção de um problema em que os URLs de visualização incluíam incorretamente públicos adicionais além do explicitamente digitado pelo usuário. Esse comportamento foi corrigido para garantir que somente o público-alvo especificado seja aplicado ao gerar um link de controle de qualidade ou visualização. (TGT-52912)
* Correção de um problema que impedia os usuários de criar atividades de [!UICONTROL Auto-Target] (AT) se [!UICONTROL Auto-Allocate] (AA) fosse selecionado primeiro durante a configuração da alocação de tráfego. Esse problema resultou em um erro de validação de backend e impede que a atividade seja salva. (TGT-53096)

+++

**Públicos-alvo**

+++Ver detalhes
* Correção de um problema em que os usuários com a função [!UICONTROL Approver] não conseguiam adicionar ou salvar refinamentos de público-alvo somente de atividade. A tentativa de fazer isso resultou em um erro 403 Proibido, informando que o privilégio &quot;[editor]&quot; era necessário, mesmo que o usuário tivesse permissões suficientes para aprovar e gerenciar atividades. (TGT-52984)
* Correção de um problema quando um público-alvo específico de uma atividade era removido usando a opção [!UICONTROL Remove Audience Refinement], o público-alvo não aparecia mais na lista de públicos-alvo para reseleção dentro da mesma atividade. Esse comportamento impedia que os usuários adicionassem novamente o mesmo público-alvo, a menos que fosse recriado do zero. (TGT-52979)
* Correção de um problema em que os refinamentos de público-alvo somente de atividade desapareciam da interface do usuário imediatamente após serem removidos de um local, mesmo antes de a atividade ser salva. Esse comportamento contradizia a funcionalidade esperada e a orientação da dica de ferramenta, que declara: &quot;Todos os públicos-alvo não usados dessa biblioteca serão excluídos assim que a atividade for salva.&quot; (TGT-52982)
* Correção de um problema ao tentar atribuir um público-alvo diferente de [!UICONTROL All Visitors] a uma atividade. Ao salvar, a seguinte mensagem de erro era exibida: &quot;Não podemos concluir sua solicitação. Contate [!UICONTROL Adobe Client Care] se o problema persistir.&quot; (TGT-53008)
* Correção de um problema que bloqueava o salvamento de uma atividade após a criação e a atribuição de um novo público-alvo no editor de atividades. A mensagem de erro exibida foi: &quot;Não foi possível concluir a solicitação. Contate [!UICONTROL Adobe Client Care] se o problema persistir.&quot; (TGT-52977)

+++

**[!UICONTROL Analytics for Target](A4T)**

+++Ver detalhes
* Correção de um problema em que copiar uma atividade existente e alterar a fonte de relatórios para [!DNL Adobe Analytics] (A4T) resultava em um erro &quot;Entrada de usuário inválida&quot;. O erro foi disparado quando determinadas ações de métrica incompatíveis com os relatórios do [!DNL Analytics], como `restart_same_experience`, `restart_random_experience` e `restart_new_experience`, eram retidas da atividade original. (TGT-52900)
* Correção de um problema que impedia os clientes de criar ou salvar uma atividade ao selecionar [!DNL Adobe Analytics] (A4T) como fonte de relatórios na etapa [!UICONTROL Goals & Settings]. O problema ocorreu especificamente ao selecionar uma métrica [!UICONTROL Custom Event] (por exemplo, &quot;Evento personalizado 16&quot;), resultando no seguinte erro: &quot;Entrada de usuário inválida&quot;. (TGT-52910)
* Correção de um problema em que um clique no link &quot;[!UICONTROL View in Analytics]&quot; redirecionava os usuários para a página inicial em vez do painel [!DNL Analytics] pretendido. (TGT-53092 e TGT-53093)
  <!-- * Fixed an issue when cloning an existing activity and changing the reporting source from [!DNL Target] to [!DNL Adobe Analytics], users encounter a "400 - Invalid User Input" error, preventing the activity from being saved. (TGT-52875)-->
* Correção de um problema ao visualizar uma atividade [!DNL Recommendations] na interface atualizada do usuário [!UICONTROL Overview]. Falha ao carregar a seção [!UICONTROL Goals & Settings] quando [!DNL Adobe Analytics] (A4T) é selecionado como fonte de relatórios. A seguinte mensagem de erro foi exibida: &quot;Algo deu errado. Não podemos completar o seu pedido. Entre em contato com o Atendimento ao cliente da Adobe se o problema persistir.&quot; (TGT-52999)

+++

**[!UICONTROL Experiences]e[!UICONTROL Offers]**

+++Ver detalhes
<!-- * Fixed an issue where using the [!UICONTROL Manage Content] feature in [!UICONTROL Automated Personalization] (AP) activities caused the page to crash and remain blank. This issue occurred after clicking [!UICONTROL Done] in the content manager, particularly in activities created or edited in the updated UI. (TGT-53047)-->
* Correção de um problema em que o recurso [!UICONTROL Manage Content] não validava corretamente o estado de um local após a remoção de todas as opções de conteúdo. Esse problema pode levar a comportamentos ou erros inconsistentes ao tentar salvar ou continuar com a configuração da atividade. (TGT-52801)
* Correção de um problema em que os usuários encontravam um erro de &quot;Entrada inválida&quot; ao adicionar uma nova página e excluir elementos específicos em diferentes experiências. O erro é disparado quando `LocalIds` duplicado é gerado durante a manipulação do elemento, especialmente ao alternar entre experiências e modificar estruturas de página compartilhadas. (TGT-52720)
* Correção de um problema em que o uso do recurso [!UICONTROL Generate Adhoc Offer] resultava na exibição de locais indefinidos no painel [!UICONTROL Manage Content]. (TGT-53076 e TGT-53070)
* Esclarecimento sobre o comportamento para o cliente em que as modificações feitas usando uma Oferta da HTML podem parecer ausentes ao navegar da etapa [!UICONTROL Targeting] de volta para [!UICONTROL Experiences]. Para esse cliente, o site afetado gerou dinamicamente vários seletores DOM que foram alterados a cada carregamento de página. Como resultado, o seletor originalmente usado para a modificação não pode ser encontrado quando o editor é reaberto, fazendo com que a modificação pareça ausente ou inválida. Este cenário está funcionando como projetado. Para garantir que as modificações persistam visualmente no editor, é recomendável que os clientes usem seletores estáveis e consistentes que não sejam alterados durante os recarregamentos de página. (TGT-52874)
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
* Adicionado um novo [!DNL Recommendations] feed [status](/help/main/c-recommendations/c-products/feeds.md#status): [!UICONTROL Partial Import Failed]. (KB-2215)
* Correção de um problema que afetava o fluxo de trabalho de criação da atividade ao adicionar [!DNL Recommendations] com [!UICONTROL promotions]. Quando usuários selecionaram &quot;[!UICONTROL Promote by Attribute]&quot; e adicionaram uma regra de filtragem (por exemplo, [!UICONTROL Parameter Matching]), o tipo de regra e os valores de operando selecionados não foram retidos após salvar e editar novamente a atividade. Após a reabertura, o tipo de regra do filtro seria alterado inesperadamente e os valores do operando estariam ausentes. (TGT-53059)
* Correção de um problema na interface do usuário do [!DNL Recommendations] em que qualquer promoção criada com uma única regra era interpretada e exibida incorretamente como um tipo de promoção &quot;Lista de itens&quot;, independentemente da lógica da regra. (TGT-53063)
* Correção de um problema ao usar a [!UICONTROL Overview]IU atualizada, o botão &quot;[!UICONTROL Download Recommendations Data]&quot; estava ausente para atividades [!UICONTROL Experience Targeting] (XT) que incluem [!DNL Recommendations]. (TGT-52730 e TGT-52756)
* Anteriormente, a interface do usuário do Recommendations exibia somente o número de entidades importadas com êxito de um feed. No entanto, o formato de mensagem de back-end inclui o número de entidades importadas e o número total de entidades no formato: `# of entities imported / # of total entities`. Devido a essa discrepância, os usuários só viam o primeiro valor (contagem importada) na interface do usuário, o que gerava confusão. A interface do usuário agora exibe ambos os números. (TGT-53073)
* Correção de um problema em que os clientes não conseguiam salvar uma regra de filtragem ao configurar uma promoção &quot;[!UICONTROL Promote by attribute]&quot; em uma atividade A/B baseada em formulário com recomendações. Após salvar e reabrir a atividade, a regra de filtragem estava ausente e a atividade não pôde ser salva com êxito. (TGT-53057)

+++

**Relatórios**

+++Ver detalhes
* Correção de um problema em que selecionar &quot;[!UICONTROL Export order details to CSV]&quot; na página [!UICONTROL Reports] resultava no download de um arquivo vazio. Esse problema ocorria mesmo quando dados de pedido válidos estavam presentes na atividade. (TGT-52225)
* Correção de um problema ao tentar salvar uma atividade após criar e atribuir um novo público-alvo de relatórios. A mensagem de erro retornada foi: &quot;Acesso negado. Para executar esta operação, todos os privilégios a seguir são necessários: [editor].&quot; Esse problema ocorria apesar de o usuário ter acesso como aprovador. (TGT-53103)

+++

**[!UICONTROL Visual Experience Composer](VEC)**

+++Ver detalhes
* Solução de um problema em que a aplicação de uma modificação em uma exibição resultava na duplicação da exibição e a atividade retornava um erro &quot;Entrada de usuário inválida&quot;. Essa correção garante que as modificações de exibição sejam aplicadas corretamente sem disparar erros de duplicação ou validação. (TGT-52886)
* Correção de um problema em que as modificações de código personalizadas eram exibidas incorretamente para a experiência errada. Especificamente, as alterações destinadas a uma experiência foram mostradas em uma experiência diferente, levando a confusão e possível configuração incorreta de atividades ativas. (TGT-52776)
* Correção de um problema que impedia a edição ou o salvamento de modificações de código personalizadas na Nova interface do VEC. Especificamente:

   * Após editar um bloco de código personalizado e salvar, as alterações não foram refletidas na interface do usuário ou na pré-visualização de controle de qualidade.
   * Em alguns casos, as modificações não podiam ser excluídas a menos que a atividade fosse fechada e reaberta.
   * Como solução alternativa, os usuários tinham que copiar o código, excluir a modificação e recriá-lo manualmente com o conteúdo atualizado. (TGT-53072)

* Correção de um problema em que editar e salvar o código personalizado fazia com que o painel [!UICONTROL Modifications] ficasse sem resposta. (TGT-53075)
* Correção de um problema em que as modificações feitas no código personalizado em experiências variantes eram refletidas involuntariamente na experiência [!UICONTROL Control]. Isso causou alterações não intencionais no comportamento de delivery. A experiência do [!UICONTROL Control] agora permanece isolada das edições de código personalizado feitas em outras experiências. (TGT-52413)
* Correção de um problema em que as modificações feitas em uma experiência (por exemplo, Experiência B) eram duplicadas involuntariamente em outra experiência (Experiência A) se o usuário clicasse na segunda experiência antes do editor ser totalmente carregado. Esse comportamento também pode resultar na perda de modificações se a experiência selecionada inicialmente não tiver alterações. (TGT-52597)
* Correção de um problema em que as alterações feitas na etapa [!UICONTROL Modifications] da criação da atividade não eram salvas de forma consistente. Em alguns casos, depois de concluir todas as etapas e clicar em [!UICONTROL Save], o script personalizado adicionado na seção [!UICONTROL Modifications] não refletia no site ativo, apesar de não haver erros visíveis durante o processo de salvamento. (TGT-52661)
* Correção de um problema em que as alterações de código personalizado não eram salvas corretamente e eram espelhadas involuntariamente em várias experiências na mesma atividade. Além disso, os usuários encontraram problemas de acesso ao abrir ou atualizar determinadas atividades, resultando em telas em branco. Esses problemas foram resolvidos para garantir uma edição de atividades estável e um isolamento preciso da experiência. (TGT-52594)
* Correção de um problema em que os usuários não conseguiam navegar para uma URL diferente no [!UICONTROL Browse Mode]. Isso impedia que testadores e editores validassem ou visualizassem páginas alternativas na mesma sessão de atividade. (TGT-53052)
* Correção de um problema em que várias instâncias do [!UICONTROL Visual Experience Composer] (VEC) eram abertas simultaneamente durante a criação da atividade. Esse problema ocorria quando usuários desabilitavam o [!UICONTROL Enhanced Experience Composer] (EEC) e removiam a barra à direita da URL do site na etapa [!UICONTROL Page Delivery]. (TGT-52782)
* Correção de um problema em que a lista suspensa de métricas [!UICONTROL Revenue] na etapa [!UICONTROL Goals & Settings] assumia incorretamente o padrão [!UICONTROL Revenue per Visit] (RPVISIT), mesmo após o usuário selecionar uma métrica diferente.  O problema ocorria ao recolher e expandir novamente o painel de configuração de métrica, fazendo com que o valor selecionado anteriormente fosse redefinido. (TGT-52811 e TGT-52878)
* Correção de vários problemas no fluxo de trabalho de criação da atividade relacionados à nomeação da oferta e à conversão de conteúdo em [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Multivariate Testing] (MVT) atividades:

  Principais problemas abordados:

   * A criação de várias Ofertas da HTML com o mesmo nome (por exemplo, &quot;Experiência&quot;) acionou o erro &quot;Nomes de ofertas duplicados não são permitidos&quot;, mas a interface não indicou claramente quais ofertas estavam causando o conflito.
   * A renomeação de ofertas por meio do painel direito atualizou o nome na interface, mas a alteração não foi refletida na guia [!UICONTROL Manage Content] ou na guia [!UICONTROL Offers], causando erros de validação persistentes.
   * Em atividades do MVT, embora o erro de nome duplicado não persistisse após a renomeação, a interface do usuário ainda não refletia os nomes de oferta atualizados de forma consistente nas guias. (TGT-52933)

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
