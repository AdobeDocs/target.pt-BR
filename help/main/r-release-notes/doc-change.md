---
keywords: registro de alterações da documentação do target;atualizações da documentação;novos tópicos;edições;atualizações;atualização
description: Mantenha-se atualizado com as adições e as alterações importantes à documentação do  [!DNL Adobe Target] .
title: Onde posso ver as atualizações da documentação do [!DNL Target]?
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 7d84ce530081c20f7cdcb6e89010baef6f638647
workflow-type: tm+mt
source-wordcount: '1361'
ht-degree: 100%

---

# Alterações de documentação

Essa página lista alterações importantes feitas na documentação do [!DNL Adobe Target].

## [!DNL Target] Standard/Premium 24.1.1 (22, 23 e 25 de janeiro de 2024)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 8 de fevereiro | [Pré-busca](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/prefetch.html?lang=pt-BR){target=_blank} | Nova seção adicionada: “Buscar antecipadamente mBoxes com métricas de clickTrack ao usar o Analytics for Target (A4T)” |
| 5 de fevereiro | [Crie uma atividade que use o Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/a4t/campaign-creation.md) | Adição de texto especificando que não é possível usar o mesmo nome de atividade para duas atividades de espaços de trabalho separados usando o [!UICONTROL Analytics for Target] (A4T) como fonte de relatórios. |
|  | [Configurações de atividade – Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md) | Adição de texto especificando que não é possível usar o mesmo nome de atividade para duas atividades de espaços de trabalho separados usando o [!UICONTROL Analytics for Target] (A4T) como fonte de relatórios. |
|  | Anúncios e eventos do [[!DNL Adobe Target] ](/help/main/r-release-notes/target-announcements.md) | Adição de informações sobre a sessão de Perguntas e respostas da comunidade do Adobe Target, programada para 7 de fevereiro de 2024. |
| 24 de janeiro | [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Adição das notas de versão para a at.js versão 2.11.4. |
|  | [Navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | Informamos que os dois novos perfis ainda não estão disponíveis. Essas notas serão atualizadas quando esses perfis estiverem disponíveis. |
|  | [Perguntas frequentes sobre at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-faq.html?lang=pt-BR){target=_blank} | Adição de perguntas frequentes sobre a at.js em um ambiente de aplicativo Ionic. Esta implementação não foi testada ou é recomendada. |
| 22 de Janeiro | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Adição de informações importantes sobre a descontinuação do iPad e iPhone do atributo de público-alvo do [!UICONTROL Navegador], que requer alterações de sua parte antes de 30 de abril de 2024. |
|  | [Navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation) | Adição de uma nova seção: <ul><li>Descontinuação do iPad e iPhone do atributo de público-alvo do navegador (30 de abril de 2024)</li></ul> |
|  | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 24.1.1 do [!DNL Target Standard/Premium]. |

## [!DNL Target] Standard/Premium 23.11.1 (13 e 14 de novembro de 2023)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 18 de janeiro | Notas de versão do [[!DNL Target]  (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento para a versão 24.1.1 do [!DNL Target Standard/Premium]. |
| 13 de dezembro | Anúncios e eventos do [[!DNL Adobe Target] ](/help/main/r-release-notes/target-announcements.md) | Adição de informações sobre a série de webinários sobre maturidade de personalização do [!DNL Adobe Target] 2024. |
|  | [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html?lang=pt-BR){target=_blank} | Adição de duas novas configurações opcionais: <ul><li>aepSandboxId</li><li>aepSandboxName</li></ul> |
| 4 de dezembro | Anúncios e eventos do [[!DNL Adobe Target] ](/help/main/r-release-notes/target-announcements.md) | Adição de informações de registro para a sessão de Coffee Break “Aprendizado de máquina e Relatórios e análise de IA” do [!DNL Adobe Target Community]: quarta-feira, 6 de dezembro de 2023. |
| 1º de dezembro | [APIs de atualização de perfil do Adobe Target](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html?lang=pt-BR){target=_blank} | A documentação da API herdada foi movida para os seguintes artigos:<ul><li>[Visão geral das APIs de perfil do Adobe Target](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html?lang=pt-BR){target=_blank}</li><li>[API de atualização de perfil único do Adobe Target](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-single-api.html?lang=pt-BR){target=_blank}</li><li>[API de atualização de perfil em massa do Adobe Target](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-bulk-api.html?lang=pt-BR){target=_blank}</li></ul> |
| 29 de novembro | [API de atualização de perfil em massa](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html?lang=pt-BR){target=_blank} | Esclarecimento sobre as diferenças entre a [!UICONTROL API de atualização de perfil em massa] v2 e a v1 em como o [!DNL Target] lida com atributos do cliente ao criar um perfil para uma pessoa que o [!DNL Target] ainda não tenha visto. |
| 21 de novembro | [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Adição das notas de versão para a at.js 2.11.3. |
| 17 de novembro | [Primeiros passos de administrador](/help/main/administrating-target/start-target.md) | Adicionada a seguinte nota importante:<ul><li>Pessoas com direitos de [!UICONTROL Administrador do produto] ou [!UICONTROL Administrador do sistema] no [!DNL Adobe Admin Console] podem editar ou alterar todas as configurações na página [!UICONTROL Administração] do [!DNL Target], independentemente da sua função no [!DNL Target]. Pessoas sem direitos de [!UICONTROL Administrador do produto] ou [!UICONTROL Administrador do sistema] no [!DNL Adobe Admin Console] precisam ter a função específica do [!DNL Target] para fazer essas alterações.1</li></ul> |
|  | [Limites](/help/main/r-troubleshooting-target/target-limits.md#in-mbox) | A seção foi atualizada com informações sobre como o [!DNL Target] lida com o truncamento no at.js 2.*x* e o [!DNL Adobe Experience Platform Web SDK]. |
|  | [API de entrega](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html?lang=pt-BR){target=_blank} | Adição de redirecionamentos à documentação atual da API de entrega e a descontinuação da documentação herdada (`http://developers.adobetarget.com/api/delivery-api/`). Atualize os favoritos, conforme necessário. |
| 16 de novembro | [API de atualização de perfil em massa](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html?lang=pt-BR){target=_blank} | Adição do seguinte aviso: “As atualizações geralmente ocorrem em menos de uma hora, mas podem levar até 24 horas para serem refletidas.” |
| 13 de novembro | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 23.11.1 do [!DNL Target Standard/Premium]. |

## [!DNL Target] Standard/Premium 23.10.2 (24 de outubro de 2023)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 10 de novembro | [Referência da API do Recommendations](https://developer.adobe.com/target/administer/recommendations-api/){target=_blank} | A API do [!DNL Adobe Target] [!DNL Recommendations] foi realocada para o site do [!DNL Adobe Developer]. Atualize seus marcadores, se necessário. |
|  | [Intervalo de tempo](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | Adição de uma observação informando que o horário de públicos-alvo do [!DNL Target] não considera as alterações do horário de verão. Será necessário atualizar os públicos-alvo manualmente para que levem em conta as alterações do horário de verão. |
| 8 de novembro | Notas de versão do [[!DNL Target]  (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento para a versão 23.11.1 do [!DNL Target Standard/Premium]. |
| 28 de outubro | [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Adição de informações sobre a versão 2.11.2 da at.js. |
| 25 de outubro | Notas de versão (atuais) do [[!DNL Target] ](/help/main/r-release-notes/release-notes.md) | Adição de informações sobre a atualização da interface da página [!UICONTROL Atividades] (25 de outubro de 2023) |
| 24 de outubro | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 23.10.2 do [!DNL Target Standard/Premium]. |

## [!DNL Target] Standard/Premium 23.9.1 (6 a 11 de setembro de 2023)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 17 de outubro | [Perguntas frequentes sobre relatórios](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B) | Atualização das seguintes perguntas frequentes: “Por que não há dados disponíveis para meu relatório de atividade? “ |
| 11 de outubro | [[!DNL Adobe Analytics]  como origem de relatórios do  [!DNL Adobe Target]  (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) | Informações atualizadas sobre a compatibilidade do A4T com o [!DNL Adobe Experience Platform Web SDK]. |
| 10 de outubro | [Detalhes da versão de at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Adição das notas de versão para a at.js versão 2.11.0. |
| 6 de outubro | [Tokens de resposta](/help/main/administrating-target/response-tokens.md) | Todos as amostras de código foram atualizadas. |
|  | [Configuração de relatórios do A4T no  [!DNL Analysis Workspace]  para as atividades de [!UICONTROL Alocação automática]](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=pt-BR){target=_blank} | Tutorial completo atualizado no guia *[!UICONTROL Tutoriais do Adobe Target]*. |
| 4 de outubro | [Atividades](/help/main/c-activities/activities.md) | O texto e as imagens foram modificados para refletir a atualização da interface incluída na versão 23.9.4 do [!DNL Target]. |
|  | [Feeds](/help/main/c-recommendations/c-products/feeds.md) | O texto e as imagens foram modificados para refletir a atualização da interface incluída na versão 23.9.4 do [!DNL Target]. |
| 2 de outubro | Notas de versão (atuais) do [[!DNL Target] ](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 23.9.3 do [!DNL Target Standard/Premium]. |
|  | Padrão de implementação do [[!DNL Recommendations] ](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html?lang=pt-BR){target=_blank} | Os novos artigos da seção *Padrão de implementação do Recommendations com o uso da at.js* ajudam você a entender e criar uma implementação do [!DNL Adobe Target Recommendations] usando a biblioteca JavaScript da at.js.<P>Para obter informações gerais sobre padrões do [!DNL Target], consulte [Visão geral dos padrões de implementação](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/pattern-overview.html?lang=pt-BR){target=_blank} no *Guia de desenvolvimento do Adobe Target*.<P>O novo padrão de implementação do Recommendations é composto pelos seguintes artigos:<ul><li>[Visão geral do padrão de implementação do Recommendations com o uso da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html?lang=pt-BR){target=_blank}</li><ul><li>[Inicializar SDKs](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/initialize-sdk.html?lang=pt-BR){target=_blank}</li><li>[Configurar a coleção de dados](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/data-collection.html?lang=pt-BR){target=_blank}</li><li>[Renderizar experiências](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/render-experiences.html?lang=pt-BR){target=_blank}</li><li>[Notificar o  [!DNL Target]](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/notify-target.html?lang=pt-BR){target=_blank}</li></ul></ul> |
| 29 de setembro | Notas de versão do [[!DNL Target]  (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento para a versão 23.9.3 do [!DNL Target Standard/Premium]. |
|  | [Inicializar o SDK Java](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html?lang=pt-BR){target=_blank} | Adição dos seguintes novos parâmetros à tabela:<ul><li>`connectionTtlMs`</li><li>`idleConnectionValidationMs`</li><li>`evictIdleConnectionsAfterSecs`</li></ul> |
| 22 de setembro | [Solução de problemas relacionados ao [!UICONTROL Enhanced Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF) | Atualização da lista de endereços IP na lista de permissões. |
| 18 de setembro | Notas de versão (atuais) do [[!DNL Target] ](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 23.9.3 do [!DNL Target Standard/Premium]. |
| 15 de setembro | Notas de versão do [[!DNL Target]  (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento para a versão 23.9.3 do [!DNL Target Standard/Premium]. |
| 12 de setembro | Notas de versão (atuais) do[[!DNL Target] ](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 23.9.2 do [!DNL Target Standard/Premium]. |
|  | [Detalhes da versão de at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Adição das notas de versão do at.js versão 2.10.3. |
| 11 de setembro | Notas de versão do [[!DNL Target]  (pré-lançamento)](/help/main/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento para a versão 23.9.2 do [!DNL Target Standard/Premium]. |
| 6 de setembro | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 23.9.1 do [!DNL Target Standard/Premium]. |

## [!DNL Target] Standard/Premium 23.8.1 (9 de agosto de 2023)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 1 de setembro | [Ambientes](/help/main/administrating-target/environments.md##section_4F8539B07C0C45E886E8525C344D5FB0) | Atualização da observação em “Definir o ambiente padrão para relatórios”. |
| 30 de agosto | [Privacidade](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/privacy.html?lang=pt-BR#aep){target=_blank} | Nova seção adicionada: “Ofuscação de IP no nível da sequência de dados ao usar o SDK da Web da Adobe Experience Platform” |
|  | [Configurações de atividade - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md#section_9F8092BE4225442896F926540292F221) | Correção do intervalo de tempo esperado para que os dados sejam exibidos em relatórios nas seguintes perguntas frequentes: “Acabei de criar uma atividade. Por que não vejo nenhum dado chegando?” |
| 29 de agosto | [Recursos compatíveis com a decisão no dispositivo](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/supported-features.html?lang=pt-BR){target=_blank} | Adição da lista de atributos geográficos compatíveis com o direcionamento ao usar a decisão no dispositivo (ODD) no lado do cliente. |
|  | [Visão geral da decisão no dispositivo](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=pt-BR){target=_blank} | Adição da lista de atributos geográficos compatíveis com o direcionamento ao usar a decisão no dispositivo (ODD) no lado do servidor. |
|  | [Implementação do Target com o SDK móvel da AEP em um aplicativo nativo com visualizações da Web](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/native-app.html?lang=pt-BR){target=_blank} | Novo artigo. |
|  | Anúncios e eventos do [[!DNL Adobe Target] ](/help/main/r-release-notes/target-announcements.md) | Adição de informações sobre a próxima sessão de perguntas e respostas da comunidade do Adobe Target (30 de agosto de 2023): acompanhamento do webinário “Criação de estratégias para obter o máximo impacto sobre o ROI com a preparação para a alta temporada”. |
| 14 de agosto | [Controle de qualidade da atividade](/help/main/c-activities/c-activity-qa/activity-qa.md) | Foram adicionadas informações esclarecendo que carregar uma página no seu site com um valor vazio *não* remove o cookie de controle de qualidade do navegador com at.js 2.*x* é implantado(a). |
|  | [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md) | Atualização da definição de “Confiança”. |
|  | [Ofertas](/help/main/c-experiences/c-manage-content/manage-content.md) | Foi adicionada uma observação explicando que as ofertas de imagem não fazem parte do modelo [!UICONTROL Permissões para usuários empresariais]. |
| 9 de agosto | [Visualização do Target Mobile](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=pt-BR){target=_blank} | Tópico atualizado com informações sobre as versões atuais do [!DNL Adobe Experience Platform Mobile SDK]. |
| 9 de agosto | [Visualização do Target Mobile](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=pt-BR){target=_blank} | Tópico atualizado com informações sobre as versões atuais do [!DNL Adobe Experience Platform Mobile SDK]. |
|  | Anúncios e eventos do [[!DNL Adobe Target] ](/help/main/r-release-notes/target-announcements.md) | Adição de informações sobre o seguinte webinário agendado para 17 de agosto de 2023: *Criação de estratégias para obter o máximo impacto sobre o ROI com a preparação para a alta temporada*. |
|  | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 23.8.1 do [!DNL Target Standard/Premium]. |

## [!DNL Target] Standard/Premium 23.7.1 (24-26 de julho, 2023)

| Data | Tópico | Alterações |
| --- | --- | --- |
|  | Anúncios e eventos do [[!DNL Adobe Target] ](/help/main/r-release-notes/target-announcements.md) | Adição de informações sobre o seguinte webinário agendado para 17 de agosto de 2023: *Criação de estratégias para obter o máximo impacto sobre o ROI com a preparação para a alta temporada*. |
| 7 de agosto | [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Esclarecimento de informações sobre as versões compatíveis da at.js. |
| 25 de julho | Notas de versão (atuais) do [[!DNL Target] ](/help/main/r-release-notes/release-notes.md#edge) | Adição de informações sobre a atualização planejada da infraestrutura de borda para 9 de agosto de 2023. |
|  | [Lista de permissões de nós de borda no Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=pt-BR){target=_blank} | Atualização do NAT e IP/domínios para implantações de borda 41-48. |
| 24 de julho | [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md) | Notas de versão adicionadas para a versão 23.7.1 do [!DNL Target Standard/Premium]. |
