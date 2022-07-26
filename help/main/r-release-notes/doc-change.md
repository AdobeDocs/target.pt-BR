---
keywords: registro de alterações da documentação do target;atualizações da documentação;novos tópicos;edições;atualizações;atualização
description: Mantenha-se atualizado com as adições e as alterações importantes à documentação do  [!DNL Adobe Target] .
title: Onde posso ver as atualizações da documentação do [!DNL Target]?
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 7de7bb1b3bc70a559d41edece8cae2d388cb0dda
workflow-type: tm+mt
source-wordcount: '1778'
ht-degree: 99%

---

# Alterações de documentação

Essa página lista alterações importantes feitas na documentação do [!DNL Adobe Target].

## [!DNL Adobe Target] Standard/Premium 22.10.1 (lançamento escalonado de 10 a 13 de outubro de 2022)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 14 de dezembro | [Configurações do relatório](/help/main/c-reports/c-report-settings/report-settings.md#environment) | Adição de uma observação na seção &quot;Ambiente&quot; sobre o uso de [!DNL Adobe Experience Platform] (AEP) para enviar dados de métrica para [!DNL Target]. |
| 29 de novembro | [Geografia](/help/main/c-target/c-audiences/c-target-rules/geo.md) | O texto foi esclarecido com a adição do seguinte parágrafo:<ul><li>As informações geográficas de um visitante são determinadas a partir do endereço IP de origem de uma solicitação de localização do [!DNL Target] (solicitação de mbox). A resolução “IP para informações geográficas” é feita para a primeira chamada de uma nova sessão. Isso significa que, se o endereço IP de um visitante mudar no meio de uma sessão de visita, as informações geográficas ainda serão baseadas no endereço IP da primeira chamada.</li></ul> |
| 28 de novembro | [Visão geral da API de modelos (inclusão na lista de bloqueios)](https://developer.adobe.com/target/before-administer/models-api/){target=_blank} no *Guia do desenvolvedor do Adobe Target*. | Nova API de modelos.<br>Os recursos podem ser bloqueados de algoritmos de aprendizado de máquina do [!DNL Target], impedindo que sejam usados em qualquer modelo ou atividade de [!UICONTROL Direcionamento automático] ou do [!UICONTROL Automated Personalization]. |
|  | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Adição de informações sobre a versão da API de modelos (23 de novembro de 2022). |
| 23 de novembro | [Antes de implementar o Analytics for Target (A4T) com a at.js](/help/main/c-integrating-target-with-mac/a4t/before-implement.md) | Atualização do link para o [Formulário de provisionamento de Integrações do Experience Cloud](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}. |
| 16 de novembro | [Anúncios e eventos do Adobe Target](/help/main/r-release-notes/target-announcements.md) | Foram adicionadas informações de inscrição para o seguinte evento:<ul><li>[!DNL Adobe Target] Sessão de perguntas e respostas da comunidade (29 de novembro)</li></ul> |
| 8 de novembro | [Por quanto tempo você deve executar um teste A/B?](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) | Foi adicionada uma observação importante de que, para obter resultados precisos, você deve recarregar a página antes de alterar qualquer valor de parâmetro na [!UICONTROL Calculadora de tamanho da amostra] do [!DNL Adobe Target]. Também foi adicionada uma observação na [calculadora](https://experienceleague.adobe.com/tools/calculator/testcalculator.html?lang=pt-BR) real{target=_blank}. |
|  | [Ofertas de redirecionamento - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682) | Atualização da descrição do parâmetro `adobe_mc_sdid` na tabela. |
|  | [Atividades de solução de problemas](/help/main/c-activities/c-troubleshooting-activities/troubleshooting-activities.md) | Nova seção adicionada: “Após a conversão da atividade, o visitante não está em nenhuma experiência”. |
|  | [Parâmetros personalizados](/help/main/c-target/c-audiences/c-target-rules/custom-parameters.md) | Foi adicionada uma observação informando que a mbox selecionada na lista suspensa [!UICONTROL Filtrar por] não é salva ao criar a atividade. Essa opção permite filtrar os parâmetros com base na mbox selecionada. |
| 2 de novembro | Problemas conhecidos e problemas resolvidos | A página foi removida e os problemas relevantes foram realocados para as páginas apropriadas para que as informações estivessem no contexto. |
| 25 de outubro | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 22.10.3 do [!DNL Target Standard/Premium]. |
| 19 de outubro | [Afinidade de categorias](/help/main/c-target/c-visitor-profile/category-affinity.md#section_8B86C7FF50294208866ABF16F07D5EB9) | Adição de uma observação que explica sobre a pontuação quando várias categorias são transmitidas em uma única chamada de mbox. |
| 18 de outubro | [Criar uma atividade de [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) | O texto foi atualizado para indicar que embora seja possível criar até 30.000 experiências em um teste de AP, o algoritmo tem melhor desempenho quando são usadas menos de 10.000 experiências distintas. Esse mesmo limite é aplicado mesmo quando a atividade tiver ativado a opção [!UICONTROL Não permitir duplicações]. |
|  | [Perguntas frequentes do Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization-faq.md) | O texto foi atualizado para indicar que embora seja possível criar até 30.000 experiências em um teste de AP, o algoritmo tem melhor desempenho quando são usadas menos de 10.000 experiências distintas. Esse mesmo limite é aplicado mesmo quando a atividade tiver ativado a opção [!UICONTROL Não permitir duplicações]. |
| 14 de outubro | [[!DNL Adobe Target] Anúncios e eventos](/help/main/r-release-notes/target-announcements.md) | Foram adicionadas informações de registro sobre a Sessão de perguntas e respostas da comunidade do [!DNL Adobe Target] (26 de outubro de 2022). |
| 10 de outubro | Extensão [[!UICONTROL Auxiliar de edição visual]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) | Novo artigo. |
|  | [Solução de problemas relacionados ao Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md) | Atualização da seção “[Minha página não é exibida no VEC (somente VEC)](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md#does-not-load)”. |
| 4 de outubro | [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md) | Novo tópico.<br>As informações contidas neste artigo substituem o arquivo PDF *Cálculos do Adobe Target para testes A/B* anteriormente disponível para download neste site. |
|  | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 22.10.1 do [!DNL Target Standard/Premium]. |

## [!DNL Adobe Target] Standard/Premium 22.9.1 (lançamento escalonado de 13 a 15 de setembro de 2022)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 3 de outubro | [Notas de versão do Target (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Atualização das datas da versão 22.10.1 do [!DNL Target Standard/Premium]. |
| 22 de setembro | [[!DNL Adobe Target] Anúncios e eventos](/help/main/r-release-notes/target-announcements.md) | Foram adicionadas informações sobre o seguinte evento:<ul><li>[!DNL Adobe Target] Sessão de perguntas e respostas da comunidade (28 de setembro de 2022) </li></ul> |
| 15 de setembro | [[!DNL Adobe Target] Anúncios e eventos](/help/main/r-release-notes/target-announcements.md) | Foram adicionadas informações sobre o seguinte webinário:<ul><li>Ajuste da personalização alimentada por IA: Novos recursos do [!DNL Adobe Target] (11 de outubro de 2022)</li></ul> |
| 13 de setembro | [Compreensão da  [!DNL Target] interface](/help/main/c-intro/understand-the-target-ui.md)  | Adição de informações sobre notificações de falhas nos feeds do [!DNL Recommendations]. |
|  | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 22.9.1 do [!DNL Target Standard/Premium]. |

## Adobe Target Standard/Premium 22.8.1 (lançamento escalonado: 17 a 18 de agosto de 2022)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 22 de agosto | [[!DNL Adobe Target] Anúncios e eventos](/help/main/r-release-notes/target-announcements.md) | Adição de informações sobre o seguinte anúncio:<ul><li>[!DNL Target] nomeado líder no Gartner Magic Quadrant for Personalization Engines (2022)</li></ul>Adição de informações sobre os seguintes eventos futuros:<ul><li>Sessão de perguntas e respostas da comunidade do [!DNL Adobe Target] (31 de agosto de 2022)</li><li>Coleção do Chef: receitas para personalização (30 de agosto de 2022)</li><li>Construtores de habilidades do [!DNL Adobe Target] - Otimização da experiência móvel (6 de setembro de 2022)</li><li>Construtores de habilidades do [!DNL Adobe Target] - Personalização orientada por IA e recomendações (15 de setembro de 2022)</li></ul>Adição do link da gravação da seguinte sessão de webinário anterior:<ul><li>Adobe: Insider do setor de personalização - Varejo (11 de agosto de 2022)</li></ul> |
| 22 de agosto | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 22.8.1 do [!DNL Target Standard/Premium]. |

## Adobe Target Standard/Premium 22.6.1 (versão escalonada: 7 a 9 de junho de 2022)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 30 de junho | [Guia do desenvolvedor do Adobe Target](https://developer.adobe.com/target/){target=_blank} | Lançamento do *Guia do desenvolvedor do Adobe Target* para consolidar todos os conteúdos para desenvolvedores do [!DNL Target] em um portal conveniente. O portal inclui informações sobre a implementação do [!DNL Target] e [!DNL Recommendations], SDKs do [!DNL Target] e APIs do [!DNL Target]. |
|  | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 22.6.2 do [!DNL Target Standard/Premium]. |
|  | [Anúncios e eventos do Target](/help/main/r-release-notes/target-announcements.md) | Adicionados links de gravações de sessões de webinário anteriores. |
| 14 de junho | [Planejar e implementar o Recommendations](https://developer.adobe.com/target/implement/recommendations/){target=_blank} | Exemplos de código atualizados nas seguintes seções:<ul><li>Páginas de inclusão do carrinho/exibição do carrinho/check-out</li><li>Excluir itens que já estão no carrinho do visitante</li></ul> |
| 7 de junho | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 22.6.1 do [!DNL Target Standard/Premium]. |

## Adobe Target Standard/Premium 22.5.1 (lançamento em etapas; 11-13 de maio de 2022)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 7 de junho | [Notas de versão do Target (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento sobre a versão 22.6.1 do [!DNL Target Standard/Premium]. |
| 31 de maio | [Anúncios e eventos do Target](/help/main/r-release-notes/target-announcements.md#webinar-series) | Foram adicionadas informações sobre o próximo Coffee-break da comunidade do [!DNL Adobe Target] (29 de junho de 2022) |
| 25 de maio | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Foram adicionadas informações sobre a versão da plataforma do [!DNL Target] (25 de maio de 2022) e a versão 2.9.0 do at.js (27 de maio de 2022). |
|  | [Detalhes de versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Adição de informações sobre a versão 2.9.0 da at.js. |
|  | [User-agent e Client Hints](https://developer.adobe.com/target/implement/client-side/atjs/user-agent-and-client-hints/){target=_blank} | Novo tópico. |
|  | [Anúncios e eventos do Target](/help/main/r-release-notes/target-announcements.md#webinar-series) | Foi adicionado um link para a gravação do seguinte webinário: Dick&#39;s Sporting Goods: personalização e mudanças no setor do varejo (19 de maio de 2022) |
| 23 de maio | [Notas de versão do Target (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de notas de pré-lançamento para a at.js versão 2.9.0 (25 de maio de 2022). |
| 11 de maio | [Anúncios e eventos do Target](/help/main/r-release-notes/target-announcements.md#webinar-series) | Adição de informações e links de inscrição para os seguintes webinars:<ul><li>Dick&#39;s Sporting Goods: Personalização e a mudança de cenário no varejo</li><li>Adobe: Insider do setor de personalização - Serviços financeiros e seguros</li><li>City National Bank: Como alcançar o 1% entre os melhores em otimização digital</li><li>Adobe: Personalização com precisão - [!DNL Adobe Analytics] e [!DNL Target]</li><li>City National Bank: a virada de jogo - Início e dimensionamento de um programa de personalização</li><li>Adobe: Descubra as oportunidades de otimização de alto impacto</li><li>Adobe: Insider do setor de personalização - Varejo</li></ul>Adição da gravação para o seguinte webinário:<ul><li>Personalização em tempo real com o [!DNL Adobe Target]</li></ul> |
|  | [Diretivas da Política de segurança de conteúdo (CSP)](https://developer.adobe.com/target/before-implement/privacy/content-security-policy/){target=_blank} | Adição da seção de perguntas frequentes. |
|  | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Foram adicionadas informações sobre os lançamentos do [!DNL Target Standard/Premium] 22.5.1 e da plataforma Target (11-13 de maio de 2022). |

## Adobe Target Standard/Premium 22.4.1 (28 de abril)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 10 de maio | [Notas de versão do Target (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento sobre a versão 22.5.1 do [!DNL Target Standard/Premium]. |
| 28 de abril | [Permissões de usuário empresarial](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#move-audience) | Adição das seguintes perguntas frequentes:<ul><li>Posso mover um público-alvo de um espaço de trabalho para outro?</li></ul> |
|  | Visão geral da [[!UICONTROL Alocação automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#section_0E72C1D72DE74F589F965D4B1763E5C3) | Foram adicionadas as seguintes perguntas frequentes:<ul><li>Uma atividade de [!UICONTROL Alocação automática] pode ajustar a janela de pesquisa ao longo de um teste para considerar a mudança de tendências com o passar do tempo?</li><li>A [!UICONTROL Alocação automática] mostra uma experiência vencedora a um visitante recorrente se a experiência vencedora for diferente do que o visitante viu ao se qualificar para a atividade?</li></ul> |
|  | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Foram adicionadas informações sobre os lançamentos do [!DNL Target Standard/Premium] 22.4.1 e da plataforma Target (27 de abril de 2022). |

## Adobe Target Standard/Premium 22.3.1 (5 de abril)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 26 de abril | [Anúncios e eventos do Target](/help/main/r-release-notes/target-announcements.md) | Foram adicionadas informações sobre os seguintes eventos:<ul><li>Webinário: Personalização em tempo real com o Adobe Target (28 de abril de 2022)</li><li>Sessão de perguntas e respostas da comunidade do [!DNL Adobe Target] (25 de maio de 2022)</li></ul> |
|  | [Ofertas de redirecionamento - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#discrepancies) | Adição das seguintes perguntas frequentes:<ul><li>Como posso minimizar as discrepâncias na distribuição de tráfego ao usar ofertas de redirecionamento em atividades do A4T?</li></ul> |
|  | [Fragmentos de experiência do AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | Adição da seguinte seção:<ul><li>Remoção de ClientLibs e HTML extras dos Fragmentos de experiência exportados para o Target</li></ul> |
| 21 de abril | [Notas de versão do Target (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento sobre a versão da plataforma [!DNL Target] programada para 17 de abril de 2022. |
| 20 de abril | [Notas de versão do Target (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento sobre a versão 22.4.1 do [!DNL Target Standard/Premium]. |
| 14 de abril | [Opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) | Foram adicionadas informações à seção Reorganizar para explicar como lidar com o comportamento inconsistente do VEC com as ações [!UICONTROL Mover] e [!UICONTROL Reorganizar] devido ao carregamento lento de elementos DOM. |
| 13 de abril | [Anúncios e eventos do Target](/help/main/r-release-notes/target-announcements.md) | Foram adicionadas informações sobre o seguinte evento:<ul><li>[!DNL Adobe Target] Sessão de Perguntas&amp;respostas da comunidade (27 de abril de 2022)</li></ul> |
|  | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Foram adicionadas informações sobre a versão da [!DNL Target] Platform. |
| 4 de abril | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Atualização de informações sobre a versão 22.3.1 do [!DNL Target Standard/Premium]. |

## Adobe Target Standard/Premium 22.2.1 (1 de fevereiro de 2022)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 30 de março | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Foram adicionadas informações sobre a versão da [!DNL Target] Platform. |
| 28 de março | [Notas de versão do Target (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Foram adicionadas informações sobre o pré-lançamento da [!DNL Target] Platform. |
| 22 de março | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Foram adicionadas informações sobre a versão do [!DNL Target Standard/Premium] de correções de engenharia do cliente. |
|  | [Notas de versão do Target (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento sobre a versão 22.3.1 do [!DNL Target Standard/Premium]. |
| 17 de março | [Notas de versão do Target (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento sobre a versão do [!DNL Target Standard/Premium] de correções de engenharia do cliente. |
|  | [Sincronização de perfil em tempo real para mbox3rdPartyId](/help/main/c-target/c-visitor-profile/3rd-party-id.md) | Atualização da seguinte frase em relação à sincronização de perfil: “As atualizações são sincronizadas com o armazenamento de perfil a cada 5-10 minutos.” |
| 8 de março | [Anúncios e eventos do Target](/help/main/r-release-notes/target-announcements.md) | Foram adicionadas informações sobre o seguinte evento:<ul><li>[!DNL Adobe Target] Sessão de Perguntas&amp;respostas da comunidade (30 de março de 2022)</li></ul> |
| 7 de março | [Criar públicos-alvo](/help/main/c-target/c-audiences/audiences.md#aep) | Nova seção adicionada em “Usar públicos-alvo da [!DNL Adobe Experience Platform]”:<ul><li>Casos de uso de personalização</li></ul> |
| 25 de fevereiro | [Suporte do A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) | Atualização das seguintes seções:<ul><li>[Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#both)</li><li>[Alocação automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa)</li></ul> |
|  | [Interpretar relatórios de autoalocação](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Novas perguntas frequentes adicionadas:<ul><li>Os emblemas “Sem vencedor”, “Vencedor” e “estrela” estão disponíveis para atividades de [!UICONTROL Alocação automática] que usam o [!UICONTROL Analytics como fonte de relatórios] (A4T)?</li></ul> |
|  | [Criar um público somente com atividades](/help/main/c-target/creating-activity-only-audience.md) | Foram adicionadas informações na seção “Considerações” sobre regras de exclusão. |
| 10 de fevereiro | [Extensão auxiliar do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) | Foram adicionadas informações sobre o carregamento de sites com Service Workers no Visual Experience Composer (VEC). |
| 7 de fevereiro | [Anúncios e eventos do Target](/help/main/r-release-notes/target-announcements.md) | Foram adicionadas informações sobre o seguinte evento:<ul><li>[!DNL Adobe Target] Sessão de Perguntas&amp;respostas da comunidade (23 de fevereiro de 2022)</li></ul> |
| 3 de fevereiro | [Criar públicos-alvo](/help/main/c-target/c-audiences/audiences.md#RTCDP) | Nova seção e vídeo adicionados: “Vídeo: Personalização de próxima ocorrência com o Real-time CDP e [!DNL Adobe Target]”. |
| 2 de fevereiro | [Soluções de problemas da entrega de conteúdo](/help/main/c-activities/c-troubleshooting-activities/content-trouble.md#escape) | Inclusão da seguinte seção: “Evitar aspas duplas no valor do atributo de perfil do [!DNL Target] não está funcionando como o esperado”. |
| 1 de fevereiro | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Adição de informações sobre a versão 22.2.1 do [!DNL Target Standard/Premium]. |

## [!DNL Adobe Target Standard/Premium] 22.1.1 (12 de janeiro de 2022)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 31 de janeiro | [Notas de versão do Target (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento sobre a versão 22.2.1 do [!DNL Target Standard/Premium]. |
| 28 de janeiro | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Adição de informações sobre a versão 2.8.1 da at.js. |
|  | [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Adição de informações sobre a versão 2.8.1 da at.js. |
| 27 de Janeiro | [Fragmentos de experiência do AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | Tópico atualizado e informações adicionadas sobre o [!DNL AEM as a Cloud Service] e o [!DNL Adobe I/0]. |
| 26 de Janeiro | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Adição de informações sobre a versão 22.1.2 do [!DNL Target Standard/Premium]. |
|  | [Criar públicos-alvo](/help/main/c-target/c-audiences/audiences.md) | Adição de informações sobre públicos-alvo da [!DNL Adobe Experience Platform]. |
|  | [Combinar vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md) | Adição de informações sobre públicos-alvo da [!DNL Adobe Experience Platform]. |
| 21 de Janeiro | [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Adição de informações sobre a versão 1.8.3 da at.js. |
| 19 de janeiro | [Atualização da at.js 1.*x* para a at.js 2.*x*](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | Adição da seguinte seção: “A at.js 2.*x* não oferece suporte à criação de públicos-alvo usando parâmetros de vst.*” |
| 12 de janeiro | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Adição de informações sobre a versão 22.1.1 do [!DNL Target Standard/Premium]. |
|  | [SDK da Web da Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank} | Link adicionado ao tutorial com instruções para implementar a [!DNL Adobe Experience Cloud] com o SDK da Web. |
