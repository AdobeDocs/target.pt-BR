---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações,atualizações atuais
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: f8e91caa133a1addc12ab1834d7e178df7e7a3ce
workflow-type: tm+mt
source-wordcount: '2725'
ht-degree: 14%

---

# Notas de versão do [!DNL Target] (atuais)

Explore os recursos, aprimoramentos e correções mais recentes no [!DNL Adobe Target]. Essas notas de versão também abordam atualizações de [!DNL Target] APIs, SDKs, A[!DNL dobe Experience Platform Web SDK], at.js e outros componentes da plataforma, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target Standard/Premium] 25.6.4 (sábado, 27 de junho de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Adicionada a opção [!UICONTROL Rearrange] à interface do VEC ([!UICONTROL Visual Experience Composer]) atualizada para alinhar-se à funcionalidade disponível no VEC herdado. (TGT-46957 e TGT-52876)
* Correção de um problema em que as modificações feitas nas experiências de variante (por exemplo, Experiência B) em uma atividade [!UICONTROL A/B Test] não eram retidas. Depois de alternar entre experiências, as alterações na variante desapareceriam. Esse problema não afetou a experiência de controle. (TGT-52664)
* Correção de um problema em que determinados clientes não podiam criar ou salvar atividades, enquanto outros podiam executar as mesmas ações sem problema. O problema era inconsistente entre as contas.(TGT-52842)
* Correção de um problema em que, no VEC atualizado, os usuários não conseguiam mover modificações para o [!UICONTROL Page Load event], um recurso que existia na interface do usuário herdada. (TGT-52617)
* Correção de um problema na interface do usuário atualizada em que os eventos [!UICONTROL page load] não estavam visíveis em [!DNL Target] ao criar alterações. Atualizações aplicadas apenas a exibições. (TGT-52604)
* Correção de um problema que impedia que algumas modificações de atividade fossem exibidas corretamente no VEC atualizado. (TGT-52818)
* Correção de uma exceção de ponteiro nulo que ocorria ao buscar dados de relatórios para [!UICONTROL Automated Personalization] atividades (AP). (TGT-52362)
* Correção de um problema que impedia que detalhes no nível da oferta fossem exibidos no arquivo .CSV para atividades de [!UICONTROL Automated Personalization] (AP). (TGT-52675)
* Correção de um problema ao aplicar modificações no VEC atualizado. As alterações inicialmente aparecem corretamente, incluindo a [!UICONTROL Experience Fragment] esperada. No entanto, ao alternar experiências ou fazer edições adicionais, algumas modificações não são aplicadas devido a problemas do seletor. (TGT-52679)
* Correção de um problema em que, quando uma nova atividade era criada por meio da clonagem de uma atividade existente, os links de controle de qualidade na atividade clonada retinham incorretamente os URLs da página da atividade original. (TGT-52775)
* Correção de um problema que impedia involuntariamente a disponibilização do [!UICONTROL On-device Decisioning] no VEC atualizado. (TGT-52371)
* Correção de um problema que impedia a edição de uma atividade do produto [!DNL Recommendations]. Ao tentar acessar o VEC por meio da interface do usuário do Target, um erro apareceu na página [!UICONTROL Overview], impedindo edições. (TGT-52823)
* Correção de um problema que impedia salvar uma atividade [!DNL Recommendations] quando os nomes de experiência excediam 50 caracteres. (TGT-52619)
* Correção de um problema em que os clientes não conseguiam salvar uma atividade do Recommendations após modificar os critérios na nova interface do usuário. O problema parece estar relacionado à permissão e não afeta todos os usuários com funções semelhantes. (TGT-52816)
* Correção de um problema em que os usuários com a função [!UICONTROL Editor] não conseguiam editar uma atividade [!DNL Recommendations]. A tentativa de alterar o design e salvar a atividade resultou em um erro 403 Proibido, informando que o privilégio &quot;[editor]&quot; era necessário, mesmo que o usuário já tivesse essa função no espaço de trabalho relevante. (TGT-52836)

## [!DNL Target Standard/Premium] 25.6.3 (sábado, 20 de junho de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema em que copiar uma atividade de um espaço de trabalho para outro espaço de trabalho acionava erros como &quot;não deve ser nulo&quot; ou &quot;Algo deu errado&quot;. (TGT-52474)
* Correção de um problema em que os relatórios [!UICONTROL Automated Segments] e [!UICONTROL Important Attributes] não eram gerados para determinadas atividades. (TGT-52904)
* Correção de um problema no VEC atualizado em que o manuseio de conteúdo padrão em atividades de [!UICONTROL Automated Personalization] (AP) não correspondia à interface do usuário herdada. O sistema agora adiciona automaticamente um `optionGroup` padrão chamado &quot;Conteúdo padrão&quot; com `optionGroupLocalId = 0` quando nenhum grupo é explicitamente adicionado. Este grupo inclui a opção padrão (por exemplo, `optionLocalId: 0`). Se o conteúdo padrão for removido, o grupo de opções correspondente também será removido. (TGT-52651)
* Correção de um problema nas atividades [!UICONTROL Multivariate Test] (MVT) em que o reuso de um `experienceLocalId` de experiências removidas anteriormente não era permitido incorretamente. (TGT-52672)
* Correção de um problema que impedia a cópia ou edição de atividades contendo um fragmento de experiência. Isso disparou o erro: `Enum "AemOfferType" cannot represent value: "html"`. (TGT-52635)
* Correção de um problema em que os URLs nos locais de atividade falhavam em exibir parâmetros de consulta devido a caracteres inválidos, como barras (/). (TNT52845)
* Mensagem de erro de validação aprimorada para [!DNL A/B Test] atualizações de atividade por meio da API de back-end. Quando nomes de locais duplicados estão presentes, a mensagem agora diz claramente: &quot;Nomes duplicados não são permitidos&quot; para `locations.selectors`. (TGT-52589)
* Correção de um erro que ocorria ao atualizar uma atividade [!UICONTROL Recommendations] em tempo real devido a uma propriedade não reconhecida na carga da solicitação. O sistema agora lida corretamente com o &quot;JSON inválido. Erro &quot;Nome de propriedade não reconhecido&quot;. (TGT-52723)
* Correção de um problema que impedia a criação de um design do [!DNL Recommendations]. Clicar em [!UICONTROL Create] acionou a mensagem: &quot;Deve haver pelo menos 1 variável de entidade usada dentro do script.&quot; (TGT-52395 e TGT-52899)
* Correção de um problema em que foi bloqueado salvar novamente um design do [!DNL Recommendations] sem modificações. (TGT-52879)
* Correção de um erro de validação de backend que causava um erro &quot;400 Solicitação inválida&quot; ao salvar uma atividade [!UICONTROL Recommendations]. (TGT-52716)
* Correção de um problema no [!UICONTROL Form-Based Experience Composer] em que passar o mouse sobre uma mbox com caracteres especiais no menu suspenso [!UICONTROL Location] fazia com que o editor ficasse em branco e disparasse uma &quot;Falha ao executar &#39;querySelector&#39; em &#39;Elemento&#39;.&quot; . (TGT-52717)
* Melhoria na precisão do status do feed com um novo indicador &quot;PARCIALLY_IMPORTED&quot;. Anteriormente, os feeds eram marcados como &quot;sucesso&quot; mesmo quando nem todas as linhas de um arquivo eram importadas, o que induzir em erro. (TGT-52892)
* Correção de um erro em que, após a migração para o AP V2, determinadas chamadas de API para `/admin/rest/ui/v1/campaigns` retornavam erros do lado do cliente (HTTP 4xx). (TGT-52721)

## Atualizado: Desativação da alternância de versão da interface do usuário [!DNL Target] (17 de junho de 2025) {#revised}

A partir de 17 de junho de 2025, todas as Organizações IMS devem ter sido habilitadas para a interface do usuário atualizada [!DNL Target], para usuários específicos ou em toda a organização, para começar a testar a nova experiência.

Devido aos problemas recentes identificados, relacionados principalmente a personalizações complexas de clientes, a equipe do [!DNL Target] ajustou a linha do tempo de desativação:

* **30 de junho de 2025**: a [interface atualizada [!DNL Target] 4&rbrace; se tornará a experiência padrão para todas as organizações IMS que habilitaram a alternância de versão da interface do usuário.](/help/main/c-intro/understand-the-target-ui.md)

   * Os clientes que atualmente veem a interface herdada, por padrão, agora verão a interface atualizada ao fazer logon.
   * O botão de alternância da versão da interface do usuário permanecerá disponível até o final de julho, permitindo que os usuários alternem de volta, se necessário.

  >[!IMPORTANT]
  >
  > A [!DNL Adobe] recomenda o uso da interface atualizada do usuário do [!DNL Target]. Retorne à interface herdada somente se ocorrer um problema de bloqueador. Consulte [[!DNL Target] Desativação da alternância de versão da interface do usuário (23 de maio de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#toggle) nas notas de versão de versões anteriores para obter informações importantes sobre a alternância.

* **15 de julho a 30 de julho de 2025**: o botão de alternância da versão da interface do usuário será desabilitado permanentemente em fases. As organizações IMS afetadas não poderão mais reverter para a interface do usuário herdada.

   * As exceções serão analisadas caso a caso.
   * Atrasos na desativação do botão serão concedidos apenas brevemente (alguns dias) enquanto problemas de bloqueador são resolvidos.

Entre em contato com o [Atendimento ao cliente da Adobe](/help/main/cmp-resources-and-contact-information.md#/help/main/cmp-resources-and-contact-information.md) se tiver dúvidas ou se antecipar problemas durante essa transição.

## [!DNL Target Standard/Premium] 25.6.2 (sexta-feira, 12 de junho de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Adição de um [novo artigo de perguntas frequentes](/help/main/c-intro/updated-ui-faq.md) para abordar perguntas comuns sobre a interface do usuário do [!DNL Target] e o [!UICONTROL Visual Experience Composer] (VEC) atualizados.
* Correção de um problema em que a regra &quot;[!UICONTROL URL - does not contain]&quot; em [!UICONTROL Page Delivery] não funcionava, permitindo que o conteúdo fosse exibido mesmo quando deveria ter sido bloqueado. (TGT-52754)
* Correção de um problema em que [!UICONTROL Page Delivery] exibia incorretamente a mensagem de erro: &quot;URLs de página duplicadas não são permitidas. (TGT-52765)
* Correção de um problema em que os públicos-alvo de [!UICONTROL Page Delivery] URLs contendo fragmentos de experiência eram criados com # anexados incorretamente. (TGT-52786)
* Correção de um problema em que copiar uma atividade e editar configurações na página [!UICONTROL Goals and Settings] fazia com que a interface do usuário [!DNL Target] ficasse sem resposta. (TGT-52797)
* Correção de um problema no VEC ([!UICONTROL Visual Experience Composer]) atualizado que permitia incorretamente o redirecionamento de uma página adicional em uma atividade [!UICONTROL A/B Test] para a mesma URL. (TGT-51838)
* Correção de um problema em que as alterações nas métricas na página [!UICONTROL Goals and Settings] não eram salvas ao editar uma atividade. (TGT-52799)
* Correção de um problema em que a adição de uma nova experiência enquanto o editor da Web ainda estava carregando fazia com que a nova experiência duplicasse o conteúdo da experiência anterior. (TGT-51397)
* Restaurada a capacidade de usar código personalizado fora da tag `<head>`, um recurso anteriormente disponível na interface do usuário herdada do Target. (TGT-52304 e TGT-52300)
* Validação desnecessária removida ao selecionar o espaço de trabalho padrão durante a criação da atividade. A validação de propriedade obrigatória não se aplica mais ao espaço de trabalho padrão, mas permanece no local para espaços de trabalho não padrão. (TGT-52449)
* Correção de um problema no [!UICONTROL Visual Experience Composer] (VEC) atualizado em que `triggerView()` chamadas não eram detectadas. (TGT-52575)
* Correção de um problema no VEC ([!UICONTROL Visual Experience Composer]) atualizado que impedia os usuários de adicionarem modificações nas exibições [!UICONTROL Single Page Application] (SPA). (TGT-52556)
* Correção de um problema na interface atualizada do usuário do [!DNL Target] que impedia que os clientes visualizassem detalhes da oferta. (TGT-52607)
* Correção de um problema em que as atualizações feitas nas ofertas no [!UICONTROL Offers Library] não eram refletidas no [!UICONTROL Visual Experience Composer] (VEC) atualizado. (TGT-52637)
* Correção de um problema que impedia a exibição correta da seção Ofertas ao criar uma atividade. (TGT-52773)
* Validação adicionada para garantir que todos os `optionLocalIds` referenciados em `optionGroups` existam na matriz de opções. As referências inválidas são removidas automaticamente durante a criação da atividade. (TGT-52687)
* Correção de um problema em que os grupos de relatórios e exclusões não eram retidos após a adição de uma nova oferta. (TGT-52728)
* Correção de um problema em que as atividades sem um botão [!UICONTROL Activity QA] exibiam um seletor de opção vazio. (TGT-52733)
* Correção de um problema em que os links de controle de qualidade não renderizavam o conteúdo corretamente. (TGT-52718)
* Correção de um problema em que a substituição de um elemento por um fragmento de experiência não refletia as alterações corretamente no ambiente de controle de qualidade. (TGT-52762)
* Correção de um problema no [!UICONTROL Visual Experience Composer] (VEC) atualizado que causava um erro de &quot;Entrada inválida&quot; quando os usuários tentavam adicionar fragmentos de experiência. (TGT-52701)
* Correção de um problema em que o modal &quot;Editar público-alvo&quot; aparecia vazio ao editar o direcionamento de público no [!UICONTROL Visual Experience Composer] (VEC) atualizado. (TGT-52749)
* Adição de uma mensagem para informar aos usuários quando uma entidade não está acessível no espaço de trabalho selecionado. (TGT-52767)
* Correção de um problema em que a interface do usuário não permitia a atribuição manual de uma ID de ambiente a um critério. Em vez disso, padronizou para a ID do grupo de hosts [!UICONTROL Product Catalog Search]. Essa correção garante que as alterações de critério agora sejam aplicadas em todos os ambientes, não apenas no padrão. (TGT-52817)
* Correção de um problema em que a opção &quot;[!UICONTROL Download Recommendations data]&quot; estava ausente para atividades [!UICONTROL Experience Targeting] (XT) com recomendações. (TGT-52730 e TGT-52756)

## [!DNL Target Standard/Premium] 25.6.1 (sábado, 6 de junho de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema em que os links de controle de qualidade não forneciam a experiência correta para a atividade associada. (TGT-52163 e TGT-52790)
* Correção de um problema em que os links de controle de qualidade não tinham a ID de público-alvo associada. (TGT-52722)
* Correção de um problema para garantir que as experiências fossem entregues somente quando as condições configuradas do URL de entrega da página fossem atendidas com precisão. (TGT-52696)
* Correção de um problema que impedia os clientes de criar um modelo de design do [!DNL Recommendations]. A tentativa de criar um modelo acionou o erro: &quot;Deve haver pelo menos uma variável de entidade usada dentro do script&quot;. (TGT-52395)
* Correção de um problema que impedia salvar [!DNL Recommendations] designs usando matrizes do Velocity. A mensagem de erro &quot;Deve haver pelo menos uma variável de entidade usada dentro do script&quot; foi acionada incorretamente. (TGT-52734)
* Correção de um problema em que as modificações estavam inacessíveis no [!UICONTROL Visual Experience Composer] (VEC) quando a página não podia ser carregada para páginas da Web internas. (TGT-52488 &amp;TGT-52470)
* Correção de um problema em que o painel [!UICONTROL Modifications] não estava visível em telas menores no VEC. (TGT-52470)
* Correção de um problema no VEC atualizado em que a alternância do modo [!UICONTROL Browse] de volta para o modo [!UICONTROL Design] causava um erro de console e impedia mais interação. (TGT-52532)
* Correção de um problema no VEC em que um clique em determinados elementos expandia involuntariamente seu tamanho. (TGT-52497)
* Correção de um problema em que determinados elementos da página não eram carregados ou reconhecidos no VEC, impedindo interações como a seleção de botões ou banners e interrompendo o rastreamento preciso de eventos nas atividades do. (TGT-52663)
* Correção de um problema que impedia os clientes de excluir ou remover ofertas nas atividades de [!UICONTROL Automated Personalization] (AP). (TGT-52690)
* Correção de um problema que causava um comportamento inconsistente de qualificação de atividade em atividades de várias páginas. (TGT-52694)
* Correção de um problema que fazia com que a página [!UICONTROL Overview] da atividade mostrasse uma URL inválida para o [!UICONTROL Activity Location]. (TGT-52695)
* Correção de um problema na interface do usuário atualizada do [!DNL Target] que fazia com que entradas duplicadas fossem exibidas para os locais de atividades. (TGT-52693)
* Correção de um problema que acionava um erro `getAudiencesV3`, impedindo clientes de editar ou copiar atividades. (TGT-52709)
* Correção de um problema que causava um erro de carga inválida ao adicionar [!UICONTROL Experience Fragments] ou ofertas do HTML a uma atividade. (TGT-52779 e TGT-52773)
* Correção de um problema na interface do usuário atualizada [!DNL Target] em que E[!UICONTROL xperience Fragments] não era exibido corretamente devido a um erro de entrada inválido. (TGT-52701)
* Correção de um problema que impedia os clientes de editar atividades no [!UICONTROL Form-based Experience Composer] devido a um erro de usuário inválido. (TGT-52470)
* Correção de um problema de localização no idioma coreano, em que as traduções anteriores usavam caracteres fora do Plano Multilíngue Básico. A tradução atualizada usa caracteres apropriados que transmitem com precisão o significado pretendido. (TGT-52508 e TGT-52509)
* Correção de um problema de localização no idioma coreano em que a tradução de &quot;data&quot; estava inconsistente ao selecionar datas de início e término de uma atividade. (TGT-52510)

## Desativação da alternância de versão da interface do usuário do [!DNL Target] (23 de maio de 2025) {#toggle}

>[!IMPORTANT]
>
>A equipe do [!DNL Target] ajustou a linha do tempo para a desativação da versão da interface do usuário. Consulte [Atualizado: [!DNL Target] Desativação da alternância de versão da interface do usuário (17 de junho de 2025)](#revised) para obter mais informações.

A implantação da nova interface de usuário do [!DNL Target] será concluída em **27 de maio de 2025**. Nesse momento, todos os clientes terão acesso à versão mais recente da interface do usuário.

A partir de **22 de junho de 2025**, a alternância de versão da interface do usuário será removida. Todos os usuários farão a transição permanente para a nova interface, sem a opção de reverter para a versão anterior.

>[!NOTE]
>
>Os clientes com casos especiais que precisam manter a opção após 22 de junho podem entrar em contato com o Atendimento ao cliente da Adobe para obter assistência.

### Informações importantes sobre a alternância da versão da interface do usuário

Estamos oferecendo um recurso temporário que permite alternar entre a interface atualizada do usuário do [!DNL Target] e a versão herdada usando um botão de alternância. Essa opção está disponível somente durante a fase final de implantação da interface.

![Alternância da versão da interface do usuário de destino](/help/main/r-release-notes/assets/toggle.png)

Quando a implantação for concluída, o botão de alternância será removido e todos os usuários farão a transição permanente para a interface atualizada em **22 de junho de 2025**. A Adobe recomenda um planejamento antecipado, pois esse recurso será descontinuado em breve.

### Limitações do comportamento de alternância da interface

* **Visibilidade das novas atividades**: as atividades criadas na interface atualizada não estarão visíveis se você voltar para a interface herdada.
* **Editar atividades existentes**: as alterações feitas nas atividades existentes (originalmente criadas na interface herdada) ao usar a interface atualizada serão publicadas no seu site. No entanto, essas atualizações não estarão visíveis na interface herdada se você voltar; somente as últimas atualizações feitas na interface herdada aparecerão lá.
* **Consistência dos detalhes da atividade**: as alterações mais recentes, independentemente da interface do usuário usada, serão refletidas no seu site ativo. No entanto, a interface herdada mostrará apenas as alterações mais recentes feitas nessa versão. Isso pode causar confusão se as atividades editadas na interface atualizada forem diferentes do que você vê na interface herdada.

### Mais informações sobre a interface atualizada

* Notas de versão do [[!DNL Target Standard/Premium] 25.2.1 (17 de fevereiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para [!UICONTROL Activities], [!UICONTROL Recommendations] e o [!UICONTROL Visual Experience Composer] (VEC).

* Notas de versão do [[!DNL Target Standard/Premium] 25.1.1 (9 de janeiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para o [!UICONTROL Offers Library].

* [Compreender a [!DNL Target] Interface](/help/main/c-intro/understand-the-target-ui.md): fornece uma breve visão geral para ajudá-lo a se familiarizar com o [!DNL Target] e fornece links para informações mais detalhadas e instruções passo a passo.

* [[!UICONTROL Visual Experience Composer] alterações](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): a versão [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de fevereiro de 2015) introduz um [!UICONTROL Visual Experience Composer] (VEC) atualizado. Este artigo explica as diferenças entre as versões herdadas e atualizadas do VEC.

* [[!UICONTROL Visual Experience Composer] opções](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): este artigo explica a interface do usuário do VEC atualizada e suas opções.

* [[!DNL Target] Perguntas frequentes sobre atualização da interface do usuário](/help/main/c-intro/updated-ui-faq.md): estas perguntas frequentes abordam perguntas comuns sobre a nova interface do usuário do [!DNL Target] e do [!UICONTROL Visual Experience Composer] (VEC), incluindo alterações na navegação, locais de recursos e substituição da versão temporária da interface do usuário. Seja você um profissional de marketing, desenvolvedor ou administrador, essas Perguntas frequentes ajudarão a fazer a transição descomplicada e a aproveitar ao máximo a interface atualizada.

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
