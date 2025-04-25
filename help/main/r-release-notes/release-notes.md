---
keywords: notas de versão;novos recursos;versões;atualizações;atualizar;versão;aprimoramento;aprimoramentos;correções;correções de erros;atualizações,atualizações atuais
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do  [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
landing-page-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
short-description: Saiba mais sobre os novos recursos, aprimoramentos e correções incluídos na versão atual do  [!DNL Adobe Target].
title: O que está incluído na versão atual?
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 579ebd9bebd3faa724f0d1d542f4d23766adefe3
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 24%

---

# Notas de versão do [!DNL Target] (atuais)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão do [!DNL Adobe Target Standard] e do [!DNL Target Premium]. Além disso, as notas de versão para APIs [!DNL Target], SDKs, o [!DNL Adobe Experience Platform Web SDK], at.js e outras alterações de plataforma também estão incluídas, quando aplicável.

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe]).

## [!DNL Target Standard/Premium] 25.4.5 (25 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema que gerava discrepâncias nas listagens de público entre a página de configurações [!UICONTROL Activity] e a página de visão geral [!UICONTROL Reporting]. (TGT-52203)
* Correção de um problema que impedia a adição de uma nova página a uma atividade devido a um erro de entrada de usuário inválido. (TGT-52263)
* Correção de um problema que fazia com que `OptionLocalIDs` fosse incrementado incorretamente quando a opção permanecesse inalterada. (TGT-52187)
* Correção de um problema que fazia com que `location` e `OptionLocalIDs` fossem incrementados incorretamente quando a opção permanecesse inalterada. (TGT-52188)
* Correção de um problema que fazia com que o local na página [!UICONTROL Overview] da atividade estivesse incorreto. (TGT-52182)
* Correção de um problema em que um aviso de seletor inválido não era exibido para um local inválido. (TGT-52110)
* Correção de um problema para que os arquivos de relatórios baixados mostrassem corretamente os dados presentes na interface do usuário dos relatórios. (TGT-52068)
* Correção de um problema para que as operações em lote não falhassem após a adição das regras de entrega de página. (TGT-52097)
* Correção de um problema que fazia com que [!DNL Target] cortasse todos os parâmetros de consulta da URL do site. (TGT-52100)
* Correção de um erro de console que impedia os clientes de criar atividades na interface herdada e atualizada do [!DNL Target]. (TGT-52181)
* Correção de um problema que impedia os clientes de adicionar novas páginas, causando um erro de entrada de usuário inválido. (TGT-52258)
* Correção de um problema que fazia com que as modificações desaparecessem após adicionar outras páginas e navegar de volta para a guia [!UICONTROL Experiences]. (TGT-52264)
* Correção de um problema que impedia os clientes de alterar o público-alvo em uma atividade [!UICONTROL Experience Targeting] (XT). (TGT-52191)
* Correção de um erro que impedia a edição de uma atividade de XT devido a uma regra de interface do usuário não compatível. (TGT-52273)
* Correção de um problema no [!UICONTROL Visual Experience Composer] (VEC) atualizado em que as navegações estruturais nem sempre eram exibidas na parte inferior do editor, causando dificuldades na seleção precisa de elementos. (TGT-52169)
* Correção de um problema em que a lista suspensa [!UICONTROL Audience] não exibia todos os públicos-alvo devido à paginação. (TGT-52204)
* Correção de um problema que causava uma mensagem de entrada de usuário inválida ao adicionar novas ofertas em [!UICONTROL Automated Personalization] atividades (AP). (TGT-52210)
* Correção de um problema em que [!UICONTROL Analytics for Target] (A4T) era selecionado incorretamente como fonte de relatórios, mesmo que o cliente não tivesse acesso ao A4T. (TGT-52226)
* Correção de um problema que impedia salvar uma atividade com a métrica de URL [!UICONTROL View a Page]. (TGT-52260)
* Correção de um problema que impedia os clientes de selecionar espaços de trabalho ao criar ofertas em uma atividade. (TGT-52289)
* Correção de um problema que impedia os clientes de criar atividades em todos os espaços de trabalho. (Tgt-52218)
* Correção de um problema em que as modificações de uma experiência eram exibidas incorretamente ao alternar para outra experiência. (TGT-52184)
* Correção de um problema em que a oferta padrão era exibida incorretamente na interface do usuário do [!DNL Target] ao abrir a atividade. (TGT-52198)

## Atualização de permissões do Target (22 de abril de 2025)

Essa atualização futura melhora o controle organizacional sobre as configurações da instância [!DNL Target], evitando atualizações acidentais que podem afetar a entrega da atividade em várias equipes de teste e personalização.

A partir de 22 de abril de 2025, somente [!UICONTROL Product] e [!UICONTROL Solutions] administradores poderão atualizar as configurações nas seções [!UICONTROL Administration], independentemente de suas funções nos espaços de trabalho [!DNL Target]. Os usuários sem esta permissão terão acesso somente leitura às seções [!UICONTROL Administration].

Para obter mais informações, consulte [Administrar Target](/help/main/administrating-target/start-target.md).

## [!DNL Target Standard/Premium] 25.4.4 (17 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Adição de uma mensagem de erro para orientar os usuários sobre a resolução de opções de duplicação em uma atividade. (TGT-51927)
* Correção de um problema em que `ClickTrack` seletores não eram removidos ao excluir páginas ou experiências com ofertas de redirecionamento. (TGT-51952)
* Correção de um problema causado pela permissão de seletores `ClickTrack` vazios. [!DNL Target] agora exige que o campo seletor não esteja em branco. (TGT-52107)
* Correção de um problema que permitia incorretamente métricas com nomes duplicados. Métricas agora exigem nomes exclusivos. (TGT-52201)
* Correção de um problema em que as definições de público-alvo não estavam visíveis ao editar o direcionamento no nível de oferta nas atividades de [!UICONTROL Automated Personalization] (AP). (TGT-52148)
* Correção de um problema que impedia clientes com direitos de [!UICONTROL Editor] de salvar atividades. (TGT-52227)
* `OptionLocalIDs` não incrementa mais incorretamente quando a opção permanece inalterada. (TGT-52139)
* Correção de um problema que causava uma mensagem &quot;Inválido `optionLocalIds`&quot; ao tentar criar uma atividade. (TGT-52154)
* Foram corrigidas discrepâncias entre `OptionLocalIDs` definidas para uma atividade e aquelas usadas para definir experiências. (TGT-52215)
* Correção de um problema que causava uma falha de validação que ocorria ao tentar criar uma atividade A/B. (TGT-51923)

## [!DNL Target Standard/Premium] 25.4.3 (11 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um erro que impedia os clientes de abrirem o pop-up de informações de público-alvo para determinadas atividades do [!UICONTROL Experience Targeting] (XT). (TGT-52049)
* Correção de um problema em que a configuração de público-alvo era revertida para &quot;[!UICONTROL All Visitors]&quot; após as alterações feitas no [!UICONTROL Visual Experience Composer] (VEC). (TGT-52132)
* Correção de um problema em que os refinamentos de público-alvo não eram exibidos para atividades específicas (TGT-52057)
* Correção de um problema que impedia os clientes de inserir um [!UICONTROL Experience Fragment] no espaço de trabalho padrão. (TGT-52073)
* Correção de um problema em que uma oferta era exibida como &quot;Conteúdo não encontrado&quot; e não era exibida na página [!UICONTROL Offers] para uma atividade [!UICONTROL Automated Personalization] (AP). (TGT-52150)
* Adição da capacidade de permitir públicos-alvo duplicados em uma atividade. (TGT-51200)
* Correção de um problema em que o nome incorreto da mbox era exibido na página [!UICONTROL Goals & Settings] para uma atividade XT após a edição. (TGT-52026)
* Correção de um problema em que `defaultContent` era exibido nas opções, apesar de não estar em `experiences/optionLocations`. (TGT-52036)
* Correção de um problema para garantir que cadeias de caracteres vazias não fossem convertidas em valores nulos. (TGT-52037)
* Correção de um problema que exigia que os clientes reconfigurassem o [!UICONTROL Optimization Goal] em [!UICONTROL Reporting Settings] na página [!UICONTROL Goals & Settings] após as edições. (TGT-52071)
* Correção de um problema em que uma atividade sem regras de entrega de página exibia várias regras na página [!UICONTROL Overview]. (TGT-52084)
* Adição de uma mensagem de erro para usuários que tentam salvar uma oferta com caracteres fora do plano multilíngue básico, como emojis. (TGT-52105)
* Correção de um problema em que a abertura de uma atividade acionava a mensagem de erro: &quot;Esta atividade está usando um ou mais públicos-alvo excluídos na origem&quot;. (TGT-52120)
* Correção de um problema em que as métricas ClickTrack não eram exibidas no [!UICONTROL Visual Experience Composer] (VEC) atualizado durante a edição. (TGT-52152)
* Correção de um problema em que um URL com um parâmetro de consulta como o local da atividade não exibia o parâmetro de consulta na página [!UICONTROL Overview] da atividade. (TGT-51635)
* Correção de um problema que impedia que a URL de toda a experiência fosse exibida no [!UICONTROL Browse mode] no [!UICONTROL Visual Experience Composer] (VEC). (TGT-52101)
* Correção de um problema em que a edição de uma atividade fazia com que a entrega da página adicionasse &quot;/&quot; ao final do URL, tornando-a inválida. (TGT-52114)
* Correção de um problema em que o link [!UICONTROL Activity QA] em [!UICONTROL Form-Based Experience Composer] era redirecionado incorretamente para a página inicial [!DNL Adobe Experience Cloud]. (TGT-52055)
* Correção de um problema em que páginas adicionais adicionadas à atividade [!UICONTROL A/B Test] não eram mantidas após salvar e reabrir. (TGT-51994)
* Correção de um problema que impedia os clientes de excluir estilos na seção de estilo em linha. (TGT-52070)
* Restaurado o acesso a [cartões de definição de público-alvo](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) na caixa de diálogo [!UICONTROL Activity QA], semelhante à interface herdada. (TGT-52056)
* A interface atualizada não salva páginas ou públicos-alvo sem modificações. Se os clientes adicionaram novas páginas ou públicos-alvo a uma atividade, mas não fizeram alterações, [!DNL Target] descartou os públicos-alvo não modificados ao salvar. Foram adicionadas notificações em locais relevantes para informar os usuários sobre esse comportamento. (TGT-52104)

## [!DNL Target Standard/Premium] 25.4.1 (2 de abril de 2025)

Esta versão do inclui as seguintes correções e atualizações:

* Correção de um problema que fazia com que os públicos-alvo da experiência desaparecessem das atividades. (TGT-52003)
* Correção de um problema que causava elementos inesperados durante a entrega. (TGT-52011)
* Correção de um problema que impedia os clientes de visualizar o público-alvo no gráfico de direcionamento na página Mover[!UICONTROL r]exibir e durante a edição da atividade. (TGT-52050)
* Correção de um problema que impedia os clientes de reordenar as experiências em ordem de prioridade nas atividades [!UICONTROL Experience Targeting] (XT). (TGT-52054)
* Correção de um problema que causava renderização incorreta ao desfazer alterações no estilo do texto. (TGT-51876)
* Correção de um problema que, ao modificar uma oferta de redirecionamento, [!DNL Target] também removia todos os seletores [!UICONTROL ClickTrack] associados a essa oferta. (TGT-51936)
* Correção de um problema que fazia com que [!DNL Target] salvasse incorretamente o seletor ao cancelar [!UICONTROL ClickTrack]. (TGT-51937)
* Correção de um problema que acionava um erro de nome inválido após abrir e fechar o seletor de mbox na página [!UICONTROL Goals & Settings] sem fazer alterações. (TGT-51983)
* Correção de um problema que bloqueava a edição de ofertas ad hoc criadas na interface herdada do usuário [!DNL Target]. (TGT-51984)
* Correção de um problema que bloqueava atividades de edição com ofertas ad hoc que continham código personalizado. (TGT-51995)
* Correção de um problema que fazia com que as regras de exclusão fossem exibidas como regras de inclusão ao editar definições combinadas de público-alvo. (TGT-51999)
* Correção de um problema que impedia a exibição correta do código personalizado durante a edição da experiência. (TGT-52005)
* Correção de um problema que tornava a opção [!UICONTROL Insert Before] indisponível para inserir conteúdo antes da barra de navegação. (TGT-52031)
* Correção de um problema que impedia o realce correto da experiência padrão nos relatórios. (TGT-51716)
* Correção de um problema que acionava uma mensagem `default message [Invalid optionLocalIds: xx]]` ao criar uma atividade. (TGT-52038)

## Versão 2.11.8 da at.js (31 de março de 2025)

* Solução da vulnerabilidade identificada pelo CodeQL na validação do sufixo da cadeia de caracteres para evitar casos de borda durante operações de redimensionamento e movimentação. (TNT-51516)

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
