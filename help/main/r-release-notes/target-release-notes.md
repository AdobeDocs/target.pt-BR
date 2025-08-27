---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: be371f3631d79c65c632a23776ab08de21b031eb
workflow-type: tm+mt
source-wordcount: '2610'
ht-degree: 7%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 27 de agosto de 2025**

>[!NOTE]
>
>* As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio. As informações neste artigo são atualizadas com frequência, especialmente antes das versões do.
>
>* Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md).
>
>* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.8.4 (28 de agosto de 2025)

Esta versão inclui as seguintes atualizações e correções:

**[!UICONTROL Activities]**

+++Ver detalhes
* **Correção de um problema em que as atividades agendadas exibiam incorretamente um status &quot;[!UICONTROL Live]&quot; na interface atualizada durante o processo de criação da atividade**: as atividades com datas de ativação futuras agora mostram corretamente um status &quot;[!UICONTROL Scheduled]&quot;. (TGT-53187)
* **As atividades agendadas exibiam incorretamente um status [!UICONTROL Live] até que a página fosse atualizada**: os clientes relataram que, ao agendar uma atividade para entrar no ar em uma data e hora futuras, o status aparecia inicialmente como [!UICONTROL Live] em vez de [!UICONTROL Scheduled]. Isso causou confusão apesar da mensagem de confirmação indicar o comportamento de agendamento correto. O status da atividade agora reflete com precisão [!UICONTROL Scheduled] imediatamente após salvar, sem exigir uma atualização de página. (TGT-52937)
* **As alterações nas experiências duplicadas afetaram involuntariamente a experiência original**: os clientes relataram que, ao duplicar uma experiência em uma atividade e atribuir um novo público-alvo, quaisquer alterações feitas na experiência duplicada, como design ou critérios, também foram refletidas na experiência original. Isso impedia a criação de variações independentes e afetava os workflows de produção. As experiências duplicadas agora podem ser editadas de forma independente, sem afetar a versão original. (TGT-53361)
* **Correção de um problema que impedia os clientes de salvar uma atividade devido a um `InvalidProperty.Json` erro**: anteriormente, os clientes encontravam um erro &quot;Entrada de usuário inválida&quot; ao tentar salvar uma atividade sem fazer alterações. O erro foi causado por um nome de propriedade não reconhecido &quot;conteúdo&quot; na carga JSON. Esse problema foi resolvido e agora as atividades podem ser salvas com êxito na interface atualizada, mesmo quando não são feitas modificações. (TGT-53513)

+++

**Analytics for Target (A4T)**

+++Ver detalhes
* **Não é possível digitar nomes de conjunto de relatórios ao criar atividades do A4T**: os clientes não conseguiram digitar no menu suspenso [!UICONTROL Report Suite] ao selecionar [!UICONTROL Analytics] como fonte de relatórios na interface atualizada.  Esse problema dificultava a localização de conjuntos de relatórios específicos, especialmente para organizações com listas grandes. O menu suspenso agora permite digitar e pesquisar por nome, melhorando a eficiência durante o processo de criação da atividade. (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++Ver detalhes
* **Públicos-alvo do tipo &quot;Intervalo de tempo&quot; expirados bloquearam a gravação da atividade mesmo após a remoção**: anteriormente, os clientes não conseguiam salvar uma atividade se ela tivesse incluído um público-alvo do tipo &quot;Intervalo de tempo&quot; expirado, mesmo após a remoção desse público-alvo. Esse problema era causado pela validação persistente no público somente atividade, que continuava a acionar erros. As atividades agora podem ser salvas conforme esperado depois que os públicos-alvo expirados forem removidos. (TGT-53517)
* **Páginas adicionais e vários públicos-alvo desapareceram após salvar uma atividade**: anteriormente, os clientes que criavam uma atividade [!UICONTROL A/B Test] no processo de criação de atividade tinham uma perda de páginas adicionais configuradas e vários públicos-alvo após salvar. Esse comportamento foi inesperado e causou confusão durante a configuração. Essas configurações agora persistem corretamente após salvar a atividade. (TGT-52357)

+++

**Ofertas de decisão**

+++Ver detalhes
* **Não é possível editar ofertas de decisão ou selecionar elementos de página específicos no VEC atualizado**: os clientes encontraram vários problemas na interface atualizada que bloquearam sua capacidade de atualizar atividades existentes ou criar novas:

   * As ofertas de decisão eram exibidas incorretamente como ofertas do HTML, impedindo edições.
   * Não foi possível selecionar elementos de página específicos no VEC.
   * As alterações feitas durante a edição não foram salvas.
   * Determinados URLs regionais não foram carregados corretamente no VEC, o que exigiu ajustes manuais de cookies.

  Os clientes agora podem editar as ofertas de decisão, selecionar os elementos da página com precisão e salvar as alterações conforme esperado. As páginas regionais também são carregadas corretamente no VEC. (TGT-53425)

* **Os seletores do Offer Decision não puderam ser modificados e alterados inesperadamente após salvar**: os clientes relataram que, ao aplicar Decisões de oferta na interface de usuário atualizada, o seletor não podia ser alterado de seu valor padrão. Tentativas de modificar o seletor (por exemplo, para `#tf-cq-hr or body`) foram ignoradas e, após salvar a atividade, o seletor foi substituído por um valor genérico como `#cdq_element_0`. Esse problema fazia com que a oferta desaparecesse do Visual Experience Composer (VEC) e bloqueasse mais edições. Agora os clientes podem modificar os seletores do Offer Decisioning conforme esperado e os seletores salvos persistem corretamente sem alterações inesperadas. (TGT-53433)
* **As Decisões de oferta desapareceram das atividades após salvar**: os clientes relataram que as Decisões de oferta aplicadas aos elementos da página na interface atualizada não estavam mais visíveis após salvar a atividade. Em alguns casos, o seletor foi alterado inesperadamente e a oferta não foi renderizada no VEC após a reedição. As Decisões de oferta agora persistem corretamente após salvar e os seletores permanecem estáveis, garantindo que as ofertas estejam visíveis e editáveis conforme esperado. (TGT-53434)

+++

**Fragmentos de experiência**

+++Ver detalhes
* **Os clientes receberam um erro ao inserir [!UICONTROL Experience Fragments] usando [!UICONTROL Insert Before] ou[!UICONTROL Insert After]**: os clientes encontraram um erro ao tentar inserir [!UICONTROL Experience Fragments] em uma atividade usando as opções [!UICONTROL Insert Before] ou [!UICONTROL Insert After] na interface atualizada. A mensagem de erro exibida foi:

  &quot;O conteúdo da oferta deve conter exatamente um elemento HTML.&quot;

  Esse problema era específico da interface atualizada e não ocorria na versão anterior. O problema foi resolvido e os clientes podem inserir [!UICONTROL Experience Fragments] com êxito sem encontrar esse erro. (TGT-53432)

* **Mensagem de erro ao adicionar [!UICONTROL Experience Fragment] a uma atividade**: anteriormente, os clientes que tentavam inserir um [!UICONTROL Experience Fragment] usando a opção [!UICONTROL Insert Before] ou [!UICONTROL Insert After] encontravam o erro: &quot;O conteúdo da oferta deve conter exatamente um elemento HTML.&quot; Esse erro apareceu apesar de o fragmento ser válido e aceito na interface herdada, que incluía um botão para dar suporte a essa configuração. O problema foi resolvido no VEC atualizado. (TGT-53442)

+++

**Localização**

+++Ver detalhes
* **As mensagens da notificação do sistema na etapa [!UICONTROL Goals & Settings] não foram localizadas**: anteriormente, os clientes encontravam uma mensagem da notificação do sistema não localizada ao inserir caracteres sem suporte, como emojis, no campo [!UICONTROL Objective] durante o processo de criação da atividade. As mensagens do sistema agora estão corretamente localizadas em todos os idiomas compatíveis, garantindo uma experiência consistente e acessível para clientes globais. (TGT-52251)
* **Uma cadeia de caracteres na caixa de diálogo [!UICONTROL Create Audience] não foi localizada**: anteriormente, a mensagem &quot;Escolher pelo menos uma data de início ou término para &#39;não se repete&#39;&quot; aparecia deslocalizada no modal [!UICONTROL Create Audience] ao configurar atributos de intervalo de tempo. A cadeia de caracteres agora está corretamente localizada em todos os idiomas com suporte, garantindo uma experiência consistente para os clientes globais no fluxo de trabalho [!UICONTROL Audiences]. (TGT-52253)
* **A dica de ferramenta na caixa de diálogo [!UICONTROL Create Audience] não foi localizada**: anteriormente, quando os clientes passavam o mouse sobre a dica de ferramenta de erro após inserir caracteres sem suporte, como emojis, no campo de nome de público, a dica de ferramenta aparecia deslocalizada. A dica de ferramenta agora exibe mensagens localizadas corretamente em todos os idiomas com suporte, garantindo uma experiência consistente e acessível no fluxo de trabalho do [!UICONTROL Audiences]. (TGT-52254)

+++

**[!DNL Recommendations]**

+++Ver detalhes
* **Não é possível desabilitar [!UICONTROL Front Promotion] na atividade online**: correção de um problema em que os clientes não conseguiam desabilitar [!UICONTROL Front Promotion] nas atividades online usando a interface atualizada. As alterações feitas na seção de promoção durante o processo de criação da atividade agora persistem conforme esperado, garantindo uma configuração precisa das atividades ativas em [!UICONTROL Product Catalog Search]. (TGT-53231)
* **A edição da recomendação de uma experiência duplicada afetou a experiência original**: os clientes relataram que, ao duplicar uma experiência em uma atividade e modificar o design da recomendação ou os critérios na duplicata, essas alterações foram aplicadas involuntariamente à experiência original.  Esse problema impedia a criação de variações independentes e interrompia o comportamento esperado no processo de criação de atividades atualizado. As experiências duplicadas agora podem ser editadas de forma independente, sem afetar a versão original. (TGT-53369)
* **Não é possível exibir a lista de produtos ao editar uma coleção ou exclusão na guia [!UICONTROL Recommendations]** Anteriormente, a lista de produtos filtrada pelas regras aplicadas não estava visível no modal de edição, dificultando para os clientes a confirmação de quais produtos foram incluídos ou excluídos. A lista de produtos agora é exibida corretamente e atualizada em tempo real à medida que as regras são modificadas, melhorando a visibilidade e a usabilidade na interface atualizada do usuário do [!DNL Recommendations]. (TGT-53481)
* **Atualização do layout da caixa de diálogo [!UICONTROL View Details] na guia [!UICONTROL Recommendations]**: anteriormente, a caixa de diálogo [!UICONTROL View Details] não tinha uma estrutura clara, dificultando o acesso de clientes a informações específicas de item e relacionadas ao inventário. O layout foi atualizado para incluir duas guias: uma guia exibe detalhes do item selecionado e a segunda guia mostra o inventário filtrado pelas regras atuais da coleção ou exclusão. Essa melhoria melhora a clareza e a usabilidade da interface do usuário atualizada do [!DNL Recommendations]. (TGT-53503)
* **Os clientes não puderam pesquisar conjuntos de relatórios no menu suspenso [!UICONTROL Goals & Settings]**: anteriormente, o menu suspenso de conjuntos de relatórios na seção [!UICONTROL Goals & Settings] do processo de criação de atividades não oferecia suporte à entrada de texto para pesquisa, dificultando aos clientes com um grande número de conjuntos de relatórios a localização do correto. Essa funcionalidade, disponível na interface herdada, foi restaurada. Agora os clientes podem digitar para pesquisar e selecionar conjuntos de relatórios com mais eficiência. (TGT-53514)
* **Os clientes não podem baixar o CSV de critérios personalizados na [!DNL Recommendations] interface do usuário**: anteriormente, clicar no link de download para CSVs de critérios personalizados na guia [!UICONTROL Recommendations] retornou um erro 404 e não pôde abrir em uma nova guia. O link de download agora abre em uma nova guia e serve corretamente o arquivo CSV, melhorando a acessibilidade e a usabilidade para clientes que gerenciam critérios personalizados. (TGT-51966)
* **Habilitar uma promoção de [!UICONTROL Recommendations] sem dados de entrada disparou uma mensagem de erro genérica**: anteriormente, os clientes habilitando uma promoção frontal ou posterior em uma atividade Recomendarações sem especificar os campos obrigatórios encontravam um &quot;Erro de entrada inválido&quot; vago com o código `error.restapi.missingFields`. O sistema agora fornece uma mensagem de erro clara e acionável, indicando quais campos estão ausentes, melhorando a usabilidade e reduzindo a confusão durante o processo de criação da atividade. (TGT-52616)
* **As miniaturas e imagens do produto não eram carregadas de forma consistente no[!UICONTROL Catalog Search]**: os clientes relataram que as miniaturas e imagens em tamanho normal do produto no [!UICONTROL Catalog Search] estavam ausentes ou quebradas intermitentemente, especialmente depois de navegar ou modificar a visibilidade da coluna. As miniaturas e imagens agora são carregadas de forma confiável, independentemente das configurações de coluna ou do comportamento de navegação, melhorando a experiência geral no fluxo de trabalho [!UICONTROL Recommendations]. (TGT-52778)
* **Não é possível criar [!UICONTROL Designs] e [!UICONTROL Criteria] no ambiente [!UICONTROL Stage]**: os clientes encontraram um erro de &quot;Entrada de usuário inválida&quot; ao tentar criar [!UICONTROL Designs] ou [!UICONTROL Criteria] na guia [!UICONTROL Recommendations] no ambiente [!UICONTROL Stage]. Os clientes agora podem criar [!UICONTROL Designs] e [!UICONTROL Criteria] com êxito, sem erros, no ambiente [!UICONTROL Stage]. (TGT-53205)
* **[!UICONTROL Promotions]não foram removidos das atividades [!UICONTROL Recommendations] após salvar**: Os clientes relataram que as promoções adicionadas às atividades [!DNL Recommendation] continuaram a aparecer mesmo após serem removidas e salvas. Esse problema afetou os ambientes de preparo e produção e persistiu em várias tentativas de salvamento. As promoções agora refletem corretamente as alterações feitas durante a edição da atividade no processo de criação de atividade atualizado. (TGT-53490)

+++

**[!UICONTROL Reports]**

+++Ver detalhes
* **[!UICONTROL Automated Segments]exibia um público-alvo nulo nos relatórios de atividade**: os clientes observaram que ao visualizar [!UICONTROL Automated Segments] na seção [!UICONTROL Reports] de uma atividade, o campo de público-alvo parecia nulo, mesmo que dados de segmento válidos fossem esperados. Esse problema afetou a visibilidade do direcionamento de público-alvo e a precisão dos relatórios. [!UICONTROL Automated Segments] agora exibe corretamente as informações de público associadas nos relatórios de atividade. (TGT-52793)
* **Falha ao baixar os relatórios de atividade no formato CSV**: os clientes que tentavam exportar relatórios de atividade da guia [!UICONTROL Reports] encontraram uma falha ao selecionar a opção de download CSV. Esse problema afetava as exportações de relatórios padrão e detalhes do pedido. Agora os relatórios são baixados corretamente no formato CSV. (TGT-53464)

+++

**Aplicativos de Página Única (SPAs)**

+++Ver detalhes
* **A alternância entre os modos [!UICONTROL Browse] e [!UICONTROL Design] redefine os estados do aplicativo de página única (SPA) no editor da Web**: os clientes relataram que a alternância entre os modos [!UICONTROL Browse] e [!UICONTROL Design] no VEC fez com que o editor da Web fosse recarregado, redefinindo o estado do SPA e interrompendo o processo de criação da atividade. O editor agora preserva o estado de navegação de SPA ao alternar modos, garantindo uma experiência de edição mais suave e consistente. (TGT-53074)

+++

**[!UICONTROL Visual Experience Composer (VEC)]**

+++Ver detalhes
* **A renomeação de um local em uma atividade [!UICONTROL Automated Personalization] (AP) ou [!UICONTROL Multivariate Test] (MVT) não persistiu após navegar até a etapa [!UICONTROL Targeting] e retornar.** Os clientes agora podem editar e salvar com êxito os nomes das localizações, e as alterações permanecem visíveis durante todo o processo de criação da atividade. (TGT-52367)
* **A interface do VEC herdada exibida nos locatários no ambiente [!UICONTROL Stage]**: correção de um problema ao acessar determinados locatários no ambiente [!UICONTROL Stage] exibia incorretamente a interface do VEC herdada em vez do VEC atualizado. Esse problema podia ser reproduzido em vários caminhos de logon e afetava a seção [!UICONTROL Activities]. A interface atualizada agora é exibida corretamente para ambos os locatários no ambiente [!UICONTROL Stage]. (TGT-52261)
* **Selecionar uma cor de plano de fundo causou uma falha na página no VEC atualizado**:
Correção de um problema em que selecionar uma cor de fundo no painel [!UICONTROL Style] no VEC atualizado fazia com que a página falhasse e ficasse em branco. Erros de console indicaram uma falha na leitura de propriedades de um elemento indefinido, especificamente relacionado a `querySelector`. Agora, os clientes podem selecionar com segurança as cores do plano de fundo sem disparar uma falha. (TGT-53561)
* **Não foi possível salvar as atividades devido a um erro de entrada de usuário inválido**: correção de um erro ao tentar salvar atividades existentes no VEC atualizado. O erro apareceu somente durante as edições, não ao criar novas atividades com a mesma propriedade. A mensagem de erro incluía:

  `Invalid Json. Unrecognized property name 'content'. Location: line - 1, column - 432.`

  As atividades que usam a propriedade afetada agora podem ser salvas com sucesso após a edição. (TGT-53507)

* **Imagens transparentes não incluíram mais o parâmetro &quot;fmt=png-alpha&quot; no VEC atualizado**: os clientes relataram que, ao substituir imagens na interface atualizada, os planos de fundo transparentes não eram mais preservados. As URLs de imagem geradas pelo VEC atualizado omitiram o parâmetro `fmt=png-alpha`, que anteriormente assegurava a transparência na interface antiga. A interface atualizada agora anexa corretamente o parâmetro `fmt=png-alpha` para imagens transparentes, restaurando o comportamento de renderização esperado. (TGT-52615)
* **Os clientes não puderam prosseguir para a seção de direcionamento em atividades AP sem adicionar dois locais**: os clientes que criavam atividades [!UICONTROL Automated Personalization] (AP) na interface atualizada não conseguiam prosseguir para a seção de direcionamento, a menos que dois locais fossem adicionados. Esse comportamento foi diferente da interface anterior, na qual um único local era suficiente. O problema bloqueou a criação e o salvamento de atividades para clientes que preferiam usar apenas uma localização. Os clientes agora podem prosseguir para o direcionamento e salvar atividades de AP com um único local, restaurando a funcionalidade esperada. (TGT-53426)
* **Ofertas do HTML duplicadas no espaço de trabalho ao alternar experiências**: anteriormente, os clientes inseriam ofertas do HTML em conteúdo duplicado experiente no espaço de trabalho após alternar entre experiências. Esse problema também fazia com que o espaço de trabalho se tornasse não rolável, afetando a usabilidade. O HTML Offers não é mais duplicado e o espaço de trabalho permanece rolável ao alternar experiências no VEC atualizado. (TGT-53487)
* **A atualização manual de um seletor de CSS deixou a tela do VEC em branco**: os clientes relataram que, ao editar uma oferta no VEC, a atualização manual do seletor de CSS acionou uma tela em branco, mesmo quando o seletor era válido e estava presente na página. A tela do VEC agora permanece estável quando os seletores são atualizados manualmente durante o processo de criação da atividade. (TGT-53553)
* **Problema de truncamento no campo Data de início ao selecionar &#39;data e hora especificadas&#39; em[!UICONTROL Goals & Settings]**: os clientes tiveram um problema de truncamento no campo [!DNL Start date] ao escolher a opção de data e hora especificadas na seção de duração da página [!UICONTROL Goals & Settings] durante a criação da atividade. A data e a hora completas agora são exibidas corretamente nas localidades compatíveis. (TGT-47843)
* **O ícone de filtro desapareceu ao minimizar o navegador no painel [!UICONTROL Manage Content]**: os clientes relataram que o ícone de filtro no painel [!UICONTROL Manage Content] do fluxo de criação de atividade [!UICONTROL Automated Personalization] desapareceu quando a janela do navegador foi redimensionada ou minimizada. O ícone de filtro agora permanece visível e acessível, independentemente do tamanho do navegador, melhorando a usabilidade nas resoluções de tela. (TGT-51449)

+++

**[!UICONTROL Workspaces]**

+++Ver detalhes
* **Clientes restritos a um único espaço de trabalho podem exibir atividades de outros espaços de trabalho**: os clientes com acesso limitado a um espaço de trabalho específico ainda podem selecionar [!UICONTROL All Workspaces] na interface atualizada e exibir atividades de outros espaços de trabalho. Esse comportamento representava um risco de alterações não intencionais em atividades ativas fora do escopo atribuído. As restrições do Workspace agora são aplicadas corretamente e os clientes podem exibir as atividades somente no espaço de trabalho atribuído. (TGT-53101)
* **Os clientes podem ver as atividades de [!UICONTROL Default Workspace] sem acesso**: os clientes podem ver as atividades de [!UICONTROL Default Workspace] apesar de não terem acesso a elas. As permissões do Workspace agora são aplicadas corretamente na interface atualizada, garantindo que os clientes vejam apenas as atividades associadas ao espaço de trabalho atribuído. (TGT-53297)

+++

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
