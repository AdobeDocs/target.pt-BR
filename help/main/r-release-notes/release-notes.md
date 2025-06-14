---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações,atualizações atuais
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 1d72a708ce68d34a603f750010caa4eb68290f7a
workflow-type: tm+mt
source-wordcount: '1701'
ht-degree: 21%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

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

## Desativação do alternador de versão da interface do usuário do Target (23 de maio de 2025) {#toggle}

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
