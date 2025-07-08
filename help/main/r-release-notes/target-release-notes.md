---
keywords: notas de versão;versões;atualizações;versão futura;aprimoramentos;novos recursos;correções;atualizações;pré-lançamento;acesso antecipado;release notes;releases;updates;future release;enhancements;new features;fixes;updates;prerelease;Early access
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 3bae9b212182cbbe9a801a1e2cdb401162fa1eb6
workflow-type: tm+mt
source-wordcount: '1893'
ht-degree: 11%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 7 de julho de 2025**

>[!NOTE]
>
>* As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>* Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md).
>
>* Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target Standard/Premium] 25.7.1 (quarta-feira, 8 de julho de 2025)

Devido aos problemas recentes identificados, principalmente relacionados às personalizações complexas do cliente, esta versão inclui as seguintes correções e atualizações:

* Correção de um problema em que os refinamentos de público-alvo somente de atividade desapareciam da interface do usuário imediatamente após serem removidos de um local, mesmo antes de a atividade ser salva. Esse comportamento contradizia a funcionalidade esperada e a orientação da dica de ferramenta, que declara: &quot;Todos os públicos-alvo não usados dessa biblioteca serão excluídos assim que a atividade for salva.&quot; (TGT-52982)
* Correção de um problema ao tentar atribuir um público-alvo diferente de [!UICONTROL All Visitors] a uma atividade. Ao salvar, a seguinte mensagem de erro era exibida: &quot;Não podemos concluir sua solicitação. Entre em contato com o atendimento ao cliente da Adobe se o problema persistir.&quot; (TGT-53008)
* Correção de um problema que bloqueava o salvamento de uma atividade após a criação e a atribuição de um novo público-alvo no editor de atividades. A mensagem de erro exibida foi: &quot;Não foi possível concluir a solicitação. Entre em contato com o atendimento ao cliente da Adobe se o problema persistir.&quot; (TGT-52977)
* Correção de um problema ao tentar salvar uma atividade após criar e atribuir um novo público-alvo de relatórios. A mensagem de erro retornada foi: &quot;Acesso negado. Para executar esta operação, todos os privilégios a seguir são necessários: [editor].&quot; Esse problema ocorria apesar de o usuário ter acesso como aprovador. (TGT-53103)
* Correção de um problema em que os usuários com a função [!UICONTROL Approver] não conseguiam adicionar ou salvar refinamentos de público-alvo somente de atividade. A tentativa de fazer isso resultou em um erro 403 Proibido, informando que o privilégio &quot;[editor]&quot; era necessário, mesmo que o usuário tivesse permissões suficientes para aprovar e gerenciar atividades. (TGT-52984)
* Correção de um problema quando um público-alvo específico de uma atividade era removido usando a opção [!UICONTROL Remove Audience Refinement], o público-alvo não aparecia mais na lista de públicos-alvo para reseleção dentro da mesma atividade. Esse comportamento impedia que os usuários adicionassem novamente o mesmo público-alvo, a menos que fosse recriado do zero. (TGT-52979)
* Correção de um problema que impedia os usuários de criar atividades de [!UICONTROL Auto-Target] (AT) se [!UICONTROL Auto-Allocate] (AA) fosse selecionado primeiro durante a configuração da alocação de tráfego. Esse problema resultou em um erro de validação de backend e impede que a atividade seja salva. (TGT-53096)
* Correção de um problema em que os usuários não conseguiam navegar para uma URL diferente no [!UICONTROL Browse Mode]. Isso impedia que testadores e editores validassem ou visualizassem páginas alternativas na mesma sessão de atividade. (TGT-53052)
* Correção de um problema em que o uso do recurso [!UICONTROL Manage Content] em atividades de [!UICONTROL Automated Personalization] (AP) fazia com que a página falhasse e ficasse em branco. Esse problema ocorria depois de clicar em [!UICONTROL Done] no gerenciador de conteúdo, especialmente em atividades criadas ou editadas na interface atualizada. (TGT-53047)
* Correção de um problema em que o recurso [!UICONTROL Manage Content] não validava corretamente o estado de um local após a remoção de todas as opções de conteúdo. Isso pode levar a comportamentos ou erros inconsistentes ao tentar salvar ou continuar com a configuração da atividade. (TGT-52801)
* Correção de um problema em que várias instâncias do [!UICONTROL Visual Experience Composer] (VEC) eram abertas simultaneamente durante a criação da atividade. Esse problema ocorria quando usuários desabilitavam o [!UICONTROL Enhanced Experience Composer] (EEC) e removiam a barra à direita da URL do site na etapa [!UICONTROL Page Delivery]. (TGT-52782)
* Correção de um problema em que os usuários encontravam um erro de &quot;Entrada inválida&quot; ao adicionar uma nova página e excluir elementos específicos em diferentes experiências. O erro foi disparado porque `LocalIds` duplicado estava sendo gerado durante a manipulação do elemento, principalmente ao alternar entre experiências e modificar estruturas de página compartilhadas. (TGT-52720)
* Solução de um problema em que a aplicação de uma modificação em uma exibição resultava na duplicação da exibição e a atividade retornava um erro &quot;Entrada de usuário inválida&quot;. Essa correção garante que as modificações de exibição sejam aplicadas corretamente sem disparar erros de duplicação ou validação. (TGT-52886)
* Correção de um problema em que as modificações de código personalizadas eram exibidas incorretamente para a experiência errada. Especificamente, as alterações destinadas a uma experiência foram mostradas em uma experiência diferente, levando a confusão e possível configuração incorreta de atividades ativas. (TGT-52776)
* Correção de um problema que impedia a edição ou o salvamento de modificações de código personalizadas na Nova interface do VEC. Especificamente:

   * Após editar um bloco de código personalizado e salvar, as alterações não foram refletidas na interface do usuário ou na pré-visualização de controle de qualidade.
   * Em alguns casos, as modificações não podiam ser excluídas a menos que a atividade fosse fechada e reaberta.
   * Como solução alternativa, os usuários tinham que copiar o código, excluir a modificação e recriá-lo manualmente com o conteúdo atualizado. (TGT-53072)

* Correção de um problema em que editar e salvar o código personalizado fazia com que o painel [!UICONTROL Modifications] ficasse sem resposta. (TGT-53075)
* Correção de um problema em que as modificações feitas no código personalizado em experiências variantes eram refletidas involuntariamente na experiência [!UICONTROL Control]. Isso causou alterações não intencionais no comportamento de delivery. A experiência do [!UICONTROL Control] agora permanece isolada das edições de código personalizado feitas em outras experiências. (TGT-52413)
* Correção de um problema no fluxo de trabalho de criação da atividade em que as modificações feitas em uma experiência (por exemplo, Experiência B) eram duplicadas involuntariamente para outra experiência (Experiência A) se o usuário clicasse na segunda experiência antes do editor ser totalmente carregado. Esse comportamento também pode resultar na perda de modificações se a experiência selecionada inicialmente não tiver alterações. (TGT-52597)
* Correção de um problema em que as alterações feitas na etapa [!UICONTROL Modifications] da criação da atividade não eram salvas de forma consistente. Em alguns casos, depois de concluir todas as etapas e clicar em [!UICONTROL Save], o script personalizado adicionado na seção [!UICONTROL Modifications] não refletia no site ativo, apesar de não haver erros visíveis durante o processo de salvamento. (TGT-52661)
* Correção de um problema em que as alterações de código personalizado não eram salvas corretamente e eram espelhadas involuntariamente em várias experiências na mesma atividade. Além disso, os usuários encontraram problemas de acesso ao abrir ou atualizar determinadas atividades, resultando em telas em branco. Esses problemas foram resolvidos para garantir uma edição de atividades estável e um isolamento preciso da experiência. (TGT-52594)
* Correção de um problema em que o uso do recurso [!UICONTROL Generate Adhoc Offer] resultava na exibição de locais indefinidos no painel [!UICONTROL Manage Content]. (TGT-53076 e TGT-53070)
* Esclarecimento sobre o comportamento para o cliente em que as modificações feitas usando uma Oferta da HTML podem parecer ausentes ao navegar da etapa [!UICONTROL Targeting] de volta para [!UICONTROL Experiences]. Para esse cliente, o site afetado gerou dinamicamente vários seletores DOM que foram alterados a cada carregamento de página. Como resultado, o seletor originalmente usado para a modificação não pode ser encontrado quando o editor é reaberto, fazendo com que a modificação pareça ausente ou inválida. Isto está funcionando como projetado. Para garantir que as modificações persistam visualmente no editor, é recomendável que os clientes usem seletores estáveis e consistentes que não sejam alterados durante os recarregamentos de página. (TGT-52874)
* Correção de um problema em que a tentativa de excluir ou desativar uma oferta que fazia parte de uma experiência excluída acionava um erro &quot;Entrada de usuário inválida&quot;. Esse problema ocorria mesmo se a oferta não fosse usada ativamente nas experiências incluídas. (TGT-52917)
* Correção de um problema em que a lista suspensa de métricas [!UICONTROL Revenue] na etapa [!UICONTROL Goals & Settings] assumia incorretamente o padrão [!UICONTROL Revenue per Visit] (RPVISIT), mesmo após o usuário selecionar uma métrica diferente.  ocorreu um problema ao recolher e expandir novamente o painel de configuração de métrica, fazendo com que o valor selecionado anteriormente fosse redefinido. (TGT-52811 e TGT-52878)
* Correção de um problema que bloqueava
* Correção de vários problemas no fluxo de trabalho de criação da atividade relacionados à nomeação da oferta e à conversão de conteúdo em [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Multivariate Testing] (MVT) atividades:

  Principais problemas abordados:

   * A criação de várias Ofertas da HTML com o mesmo nome (por exemplo, &quot;Experiência&quot;) acionou o erro &quot;Nomes de ofertas duplicados não são permitidos&quot;, mas a interface não indicou claramente quais ofertas estavam causando o conflito.
   * A renomeação de ofertas por meio do painel direito atualizou o nome na interface, mas a alteração não foi refletida na guia [!UICONTROL Manage Content] ou na guia [!UICONTROL Offers], causando erros de validação persistentes.
   * Em atividades do MVT, embora o erro de nome duplicado não persistisse após a renomeação, a interface do usuário ainda não refletia os nomes de oferta atualizados de forma consistente nas guias. (TGT-52933)

* Correção de um problema em que selecionar &quot;[!UICONTROL Export order details to CSV]&quot; na página [!UICONTROL Reports] resultava no download de um arquivo vazio. Esse problema ocorria mesmo quando dados de pedido válidos estavam presentes na atividade. (TGT-52225)
* Correção de um problema em que copiar uma atividade existente e alterar a fonte de relatórios para [!DNL Adobe Analytics] (A4T) resultava em um erro &quot;Entrada de usuário inválida&quot;. O erro foi disparado quando determinadas ações de métrica incompatíveis com os relatórios do [!DNL Analytics], como `restart_same_experience`, `restart_random_experience` e `restart_new_experience`, eram retidas da atividade original. (TGT-52900)
* Correção de um problema que impedia os clientes de criar ou salvar uma atividade ao selecionar [!DNL Adobe Analytics] (A4T) como fonte de relatórios na etapa [!UICONTROL Goals & Settings]. O problema ocorreu especificamente ao selecionar uma métrica [!UICONTROL Custom Event] (por exemplo, &quot;Evento personalizado 16&quot;), resultando no seguinte erro: &quot;Entrada de usuário inválida&quot;. (TGT-52910)
* Correção de um problema em que um clique no link &quot;[!UICONTROL View in Analytics]&quot; redirecionava os usuários para a página inicial em vez do painel [!DNL Analytics] pretendido. (TGT-53092 e TGT-53093)
* Correção de um problema ao clonar uma atividade existente e alterar a fonte de relatórios de [!DNL Target] para [!DNL Adobe Analytics], os usuários encontravam o erro &quot;400 - Entrada de usuário inválida&quot;, impedindo que a atividade fosse salva. (TGT-52875)
* Correção de um problema em que os URLs de visualização incluíam incorretamente públicos adicionais além do explicitamente digitado pelo usuário. Esse comportamento foi corrigido para garantir que somente o público-alvo especificado seja aplicado ao gerar um link de controle de qualidade ou visualização. (TGT-52912)
* Correção de um problema em que a URL [!UICONTROL Activity QA] incluía um parâmetro de consulta desnecessário: `at_preview_evaluate_as_true_audience_ids`. (TGT-52907)
* Correção de um problema em atividades baseadas em formulário em que duplicar uma experiência e editar o código personalizado em uma das experiências duplicadas aplicava involuntariamente essas alterações a todas as experiências duplicadas. Cada experiência agora mantém seu próprio código personalizado de forma independente após a duplicação. (TGT-51600)
* Correção de um problema que afetava o fluxo de trabalho de criação da atividade ao adicionar [!DNL Recommendations] com [!UICONTROL promotions]. Quando usuários selecionaram &quot;[!UICONTROL Promote by Attribute]&quot; e adicionaram uma regra de filtragem (por exemplo, [!UICONTROL Parameter Matching]), o tipo de regra e os valores de operando selecionados não foram retidos após salvar e editar novamente a atividade. Após a reabertura, o tipo de regra do filtro seria alterado inesperadamente e os valores do operando estariam ausentes. (TGT-53059)
* Correção de um problema ao visualizar uma atividade [!DNL Recommendations] na interface atualizada do usuário [!UICONTROL Overview]. Falha ao carregar a seção [!UICONTROL Goals & Settings] quando [!DNL Adobe Analytics] (A4T) é selecionado como fonte de relatórios. A seguinte mensagem de erro foi exibida: &quot;Algo deu errado. Não podemos completar o seu pedido. Entre em contato com o Atendimento ao cliente da Adobe se o problema persistir.&quot; (TGT-52999)
* Correção de um problema na interface do usuário do [!DNL Recommendations] em que qualquer promoção criada com uma única regra era interpretada e exibida incorretamente como um tipo de promoção &quot;Lista de itens&quot;, independentemente da lógica da regra. (TGT-53063)
* Correção de um problema ao usar a [!UICONTROL Overview]IU atualizada, o botão &quot;[!UICONTROL Download Recommendations Data]&quot; estava ausente para atividades [!UICONTROL Experience Targeting] (XT) que incluem [!DNL Recommendations]. (TGT-52730 e TGT-52756)
* Anteriormente, a interface do usuário do Recommendations exibia somente o número de entidades importadas com êxito de um feed. No entanto, o formato de mensagem de backend inclui o número de entidades importadas e o número total de entidades no formato:

  `# of entities imported / # of total entities`

  Devido a essa discrepância, os usuários só viam o primeiro valor (contagem importada) na interface do usuário, o que gerava confusão. A interface do usuário agora exibe ambos os números. (TGT-53073)

* Correção de um problema de tradução contextual no local coreano (ko-KR) para a cadeia de caracteres &quot;Experiência de visualização&quot;. (TGT-52928)
* Correção de inconsistências de terminologia identificadas na tradução do chinês simplificado (zh_CN) de várias cadeias de caracteres de texto. (TGT-52954 e TGT-52955)

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: Adobe Target Platform Experience Web SDK]&#x200B;(https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=e n) | Detalhes sobre alterações em cada versão do SDK da Web da plataforma. |
| [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
