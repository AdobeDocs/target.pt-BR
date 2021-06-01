---
keywords: registro de alterações da documentação do target; atualizações da documentação; novos tópicos; edições; atualizações; atualização
description: Mantenha-se atualizado com adições e alterações importantes na documentação do produto do Adobe [!DNL Target] .
title: Onde posso exibir as atualizações de documentação do Target?
feature: Notas de versão
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 7bb1f896dd92b41d04eb0dfd39116ff1c132fe50
workflow-type: tm+mt
source-wordcount: '1349'
ht-degree: 53%

---

# Alterações de documentação

Essa página lista alterações importantes feitas na documentação do [!DNL Adobe Target].

## Adobe [!DNL Target] Standard/Premium 21.4.1 (19 de abril de 2021)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 1 de junho | [CNAME e [!DNL Target]](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | Adição das seguintes perguntas frequentes:<ul><li>Como usar um link para opção de não participação com CNAME</li></ul> |
|  | [Privacidade](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | Atualização da seção &quot;Link de não participação&quot; para explicar como usar o link de não participação com CNAME. |
|  | [[!DNL Adobe Analytics] as the reporting source for [!DNL Adobe Target] (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | Adição de informações sobre o [!DNL Adobe Experience Platform Web SDK]. |
|  | [Analytics  [!DNL Target] para implementação](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform) | Adição de uma nova seção:<ul><li>Etapas de implementação para uma implementação [!DNL Adobe Experience Platform Web SDK]</li></ul> |
|  | [Ofertas de redirecionamento - Perguntas frequentes sobre o A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) | Adição de informações sobre o uso de ofertas de redirecionamento com o A4T e o SDK da Web da plataforma. |
|  | [Tokens de resposta](/help/administrating-target/response-tokens.md) | Adição de informações sobre o uso de tokens de resposta com o [!DNL Adobe Experience Platform Web SDK]. |
|  | [Notas de versão do Target (atual)](/help/r-release-notes/release-notes.md) | Adição de informações sobre a versão 2.6.0 do SDK da Web da Adobe Experience Platform (1 de junho de 2021). |
| Maio de 27 | [Limites](/help/r-troubleshooting-target/target-limits.md) | Adição de seção para chamadas de API [!DNL Target]. O limite é de 50 chamadas por minuto. |
| Maio de 20 | [Decisão no dispositivo](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md) | Adição de um link para a seguinte postagem do blog no Adobe Tech Blog:<ul><li>Adobe Tech Blog - Parte 2: Execute [!DNL Adobe Target] o SDK do NodeJS para experimentação e personalização em plataformas de borda (AWS Lambda@Edge)</li></ul> |
|  | [Problemas conhecidos e problemas resolvidos](/help/r-release-notes/known-issues-resolved-issues.md) | Adição dos seguintes problemas conhecidos: &quot;O arquivamento de [!UICONTROL atividades de Direcionamento automático] pode causar problemas de sincronização.&quot; |
| Maio de 17 | [Notas de versão do Target (atual)](/help/r-release-notes/release-notes.md) | Adição de informações sobre a versão 2.5.0 da at.js. |
|  | [Controle de qualidade da atividade ](/help/c-activities/c-activity-qa/activity-qa.md) | Atualização do tópico para indicar que os links de visualização estão disponíveis para atividades [!UICONTROL Automated Personalization] (AP) com at.js 2.5.0 (e posterior). |
|  | [Navegadores compatíveis](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md) | Indicado que a versão da at.js 2.5.0 remove o suporte ao Microsoft Internet Explorer 10, Internet Explorer 11 e todas as versões mais antigas. O Microsoft Edge continua sendo compatível com a at.js 2.5.0 e posteriores. |
|  | [Solução de problemas relacionados ao  [!UICONTROL Enhanced Experience Composer]](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md) | Atualização da lista de endereços IP para lista de permissões. |
| Maio de 12 | [[!DNL Target] notas de versão (pré-lançamento)](/help/r-release-notes/target-release-notes.md) | Adição de notas pré-lançamento para o seguinte:<ul><li>SDK da Web da Adobe Experience Platform (17 de maio de 2021)</li><li>Target Standard Premium 21.5.2</li></ul> |
| Maio de 10 | [[!DNL Recommendations] Perguntas frequentes](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | Adição das seguintes perguntas frequentes: &quot;Posso usar um algoritmo criado em [!DNL Adobe Recommendations Classic] em [!DNL Recommendations Premium]?&quot; |
|  | [Implementar o [!DNL Target] using [!DNL Dynamic Tag Manager]  (DTM)](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md) | Indicado que [!DNL Adobe Dynamic Tag Manager] não é mais suportado. Em vez disso, [!DNL Adobe] recomenda implementar com [[!DNL Adobe Experience Platform Launch]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). |
| Maio de 6 | [Perguntas frequentes do Recommendations](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | Foram adicionadas as seguintes perguntas frequentes:<ul><li>Quanto tempo leva para que uma alteração na configuração da minha atividade, oferta, promoções ou configurações de critérios do [!UICONTROL Recommendations] seja refletida no meu site?</li><li>Quanto tempo leva para o comportamento de um usuário (por exemplo, clicar no produto A e comprar o produto B) ser refletido nas recomendações *que o usuário* recebe?</li><li>Quanto tempo leva para o comportamento de um usuário (por exemplo, clicar no produto A e comprar o produto B) ser refletido nas recomendações *outros* que os usuários recebem?</li></ul> |
|  | [Decisão no dispositivo](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md) | Adição de um link para a seguinte postagem do blog no Adobe Tech Blog:<ul><li>Parte 1: Execute o SDK do Adobe Target NodeJS para Experimentação e Personalização em Plataformas de Borda (Trabalhadores do Akamai Edge)</li></ul> |
| Maio de 5 | [Anúncios e eventos do Target](/help/r-release-notes/target-announcements.md) | Adição de informações sobre o intervalo de tempo das perguntas e respostas da comunidade do Adobe Target, que será realizado quarta-feira, 12 de maio de 2021, às 8h. (TFD, GMT-7). |
| Abril de 27 | [Configurações de cookie](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-cookies.md) | Atualização do tópico para indicar que a duração do cookie (configuração `deviceIdLifetime`) é substituível na at.js versão 2.3.1 ou posterior. |
|  | [Guia do Adobe Target](/help/target-home.md) | Foram adicionadas informações sobre o Adobe Summit. |
| Abril de 26 | [Solução de problemas no dispositivo para at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/troubleshooting-on-device-decisioning.md) | Novo tópico. |
| Abril de 19 | [Decisão no dispositivo](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) | Os seguintes novos artigos foram adicionados:<ul><li>[Decisão no dispositivo](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)</li><li>[Recursos compatíveis com a tomada de decisão no dispositivo](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)</li><li>[Artefato da regra de decisão no dispositivo](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md)</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#on-device-decisioning) | Adição de informações sobre `decisioningMethod`. |
|  | [adobe.target.getOffers() - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | Adição do seguinte:<ul><li>Informações sobre a chave `decisioningMethod`.</li><li>Um exemplo para &quot;getCallOffers() para tomar uma decisão no dispositivo&quot;.</li></ul> |
|  | [Eventos personalizados da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | Foram adicionadas as seguintes informações:<ul><li>O artefato de decisão no dispositivo foi bem-sucedido</li><li>Falha no artefato de decisão no dispositivo</li></ul> |
|  | [Atividades](/help/c-activities/activities.md) | Adição de informações sobre a tomada de decisão no dispositivo. |
|  | [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adição de informações sobre a at.js 2.5.0. |
|  | [Implementação do Target sem um gerenciador de tags](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md) | Adição de informações sobre a tomada de decisão no dispositivo. |
|  | [Controle de qualidade da atividade ](/help/c-activities/c-activity-qa/activity-qa.md) | O suporte para links de visualização para atividades [!UICONTROL Automated Personalization] foi adicionado com [at.js 2.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
|  | [Uso das regras de inclusão estática e dinâmica](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators) | Foram adicionadas informações sobre os seguintes novos operadores:<ul><li>Está Contido Na Lista</li><li> Não Está Contido Na Lista</li><li>A Lista Contém Um Item Em</li><li>A Lista Não Contém Um Item Em</li><li>A Lista Contém Todos Os Itens Em</li><li>A Lista Não Contém Todos Os Itens Em</li></ul> |
|  | [Cookies do Adobe Target](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html)<br> (*Experience Cloud Services and* Administration guide) | Adição de mais informações sobre a &quot;ID da sessão&quot;. |
|  | [Notas de versão](/help/r-release-notes/release-notes.md): 21.4.1 | Essa versão inclui aprimoramentos e correções. Você pode ler sobre eles e acessar a documentação a partir das notas de versão. Esta versão também inclui muitas atualizações da documentação na seção de ajuda. |

## Adobe [!DNL Target] Standard/Premium 21.2.1 (9 de março de 2021)

| Data | Tópico | Alterações |
| --- | --- | --- |
| Abril de 9 | [Notas de versão do Target (pré-lançamento)](/help/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento para a at.js versão 2.5.0 (19 de abril de 2021) |
| Abril de 9 | [Notas de versão do Target (pré-lançamento)](/help/r-release-notes/target-release-notes.md) | Adição de informações de pré-lançamento para o Target Standard/Premium versão 21.4.1 (19 de abril de 2021) |
|  | [Integração do Recommendations ao email](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | Foi adicionada uma observação descrevendo as diretrizes de capacidade para as opções 1 e 2. |
| 29 de março | [Perguntas frequentes do Recommendations](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md#persist-across-devices) | Novas perguntas frequentes adicionadas:<ul><li>As recomendações baseadas em itens visualizados recentemente persistem em vários dispositivos para um único visitante?</li></ul> |
| 23 de março | [Notas de versão](/help/r-release-notes/release-notes.md) | Adição das notas de versão para a at.js versão 2.4.1. |
|  | [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adição das notas de versão para a at.js versão 2.4.1. |
|  | [Perguntas frequentes do Recommendations](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | Atualização das seguintes perguntas frequentes:<ul><li>Quanto tempo demora para que as atualizações nos itens do meu catálogo sejam refletidas no meu site?</li></ul> |
| 22 de março | [Endereços IP usados pelos servidores de processamento de feed do Recommendations](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md) | Atualização da lista de endereços IP. |
|  | [Limites](/help/r-troubleshooting-target/target-limits.md) | Atualização da seção &quot;Número de entidades&quot; em &quot;Entidades&quot;. |
|  | [Geografia](/help/c-target/c-audiences/c-target-rules/geo.md) | Adição de informações sobre a at.js 2.** xunder &quot;Como posso testar minhas atividades se sou um usuário proveniente de uma localidade diferente?&quot; |
|  | [Notas de versão](/help/r-release-notes/release-notes.md): 21.2.1 | Adição da seguinte seção: <ul><li>Alterações de endereço IP para servidores de processamento de feed do Recommendations (16 de março de 2021)</li></ul> |
| 19 de março | [Exibição de relatórios - Perguntas frequentes sobre o A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md#deactivated) | Adição das seguintes perguntas frequentes:<ul><li>Por que continuo vendo mais impressões depois que minha atividade é desativada?</li></ul> |
| 12 de março | [Suporte do A4T para atividades de Alocação automática e Direcionamento automático](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md#tutorial) | Adição do seguinte tutorial novo:<ul><li>Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático</li></ul> |
| 9 de março | [Limites](/help/r-troubleshooting-target/target-limits.md#offer-size) | <ul><li>Atualização dos limites de tamanho de oferta permitidos.</li><li>Limite de caracteres corrigido para o parâmetro categoryId.</li></ul> |
|  | [Nós de borda permitidos no Target](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | Atualização de endereços IP de borda do [!DNL Target]. |
|  | [Atributos da entidade](/help/c-recommendations/c-products/entity-attributes.md) | Adição de texto para indicar que entity.value deve estar em formato decimal (por exemplo, 15.99 em vez de 15,99). |
|  | [Notas de versão](/help/r-release-notes/release-notes.md): 21.2.1 | Essa versão inclui aprimoramentos e correções. Você pode ler sobre eles e acessar a documentação a partir das notas de versão. Esta versão também inclui muitas atualizações da documentação na seção de ajuda. |

## Adobe [!DNL Target] Standard/Premium 21.1.1 (19 de janeiro de 2021)

| Data | Tópico | Alterações |
| --- | --- | --- |
| 22 de fevereiro | [Exibição de relatórios - Perguntas frequentes sobre o A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Atualização das seguintes perguntas frequentes:<ul><li>Onde os segmentos podem ser aplicados no Analysis Workspace?</li></ul> |
| 16 de fevereiro | [Notas de versão do Target (pré-lançamento)](/help/r-release-notes/target-release-notes.md) | Atualização do texto para o tamanho do limite da oferta nas notas de pré-lançamento. |
| 11 de fevereiro | [Como o Target funciona](/help/c-intro/how-target-works.md) | Atualização da seção &quot;Bots&quot;. |
| 10 de fevereiro | [Anúncios e eventos do Target](/help/r-release-notes/target-announcements.md) | Adição de informações sobre o coffee break de perguntas da comunidade do Adobe Target na quarta-feira, 24 de fevereiro de 2021. |
| 8 de fevereiro | [Visualização do Target Mobile](/help/c-target-mobile-app/target-mobile-preview.md) | Adição do trecho de código que deve ser adicionado ao arquivo AndroidManifest.xml para a versão 4 do SDK do Adobe Mobile. |
|  | [Problemas conhecidos e problemas resolvidos](/help/r-release-notes/known-issues-resolved-issues.md) | Esclarecimento dos seguintes problemas conhecidos:<ul><li>Coleções, exclusões, critérios e projetos criados por API não estão visíveis na interface do usuário do Target e podem ser editados por meio da API. Da mesma forma, se você criar qualquer um desses itens na interface do usuário do Target e depois editá-los por meio da API, essas alterações não serão refletidas na interface do usuário do Target. Os itens editados por meio da API devem continuar sendo editados por meio da API para evitar a perda de modificações.</li></ul> |
| 1º de fevereiro | [Relatórios de resumo de Automated Personalization](/help/c-reports/reports-ap.md) | Nova seção adicionada: &quot;Perguntas frequentes&quot;. |
| 27 de Janeiro | [Criar Ofertas de redirecionamento](/help/c-experiences/c-manage-content/offer-redirect.md) | Tópico atualizado. |
|  | [Criar ofertas remotas](/help/c-experiences/c-manage-content/about-remote-offers.md) | Tópico atualizado. |
| 26 de Janeiro | [Índice de conversão](/help/c-reports/conversion-rate.md) | Esclarecimento sobre como o Target usa a &quot;soma dos quadrados&quot; nos testes t de Estudante. |
| 22 de Janeiro | [Índice de conversão](/help/c-reports/conversion-rate.md#t-test) | Adição da seguinte seção: &quot;Por que o Target recomenda usar os testes t de Estudante?&quot; |
| 21 de Janeiro | [Solução de problemas na integração do Analytics e do Target (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md) | Nova seção adicionada: &quot;Os relatórios de atividade do A4T incluem uma linha com um grande número de eventos &quot;não especificados&quot;.&quot; |
|  | [Exibição de relatórios - Perguntas frequentes sobre o A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | Atualização da seguinte seção: &quot;Por que vejo &quot;não especificado&quot; nos relatórios do Analytics? O que isso significa?&quot; |
| Janeiro de 20 | [SDK da Web da Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) | Novo tópico. |
| Janeiro de 19 | [Notas de versão do Target (atual)](/help/r-release-notes/release-notes.md) | Adição de informações sobre a versão 21.1.1 do Target (19 de janeiro de 2021). |
|  | [Limites](/help/r-troubleshooting-target/target-limits.md) | Texto atualizado do parâmetro `productPurchasedID`. |
|  | [Problemas conhecidos e problemas resolvidos](/help/r-release-notes/known-issues-resolved-issues.md) | Adição de um problema conhecido ao copiar uma atividade de [!UICONTROL Recomendação] com uma promoção ativa. Qualquer alteração na atividade duplicada também afeta a atividade original e vice-versa. Uma solução alternativa temporária é incluída. |
|  | [Notas de versão](/help/r-release-notes/release-notes.md): 21.1.1 | Essa versão inclui aprimoramentos e correções. Você pode ler sobre eles e acessar a documentação a partir das notas de versão. Esta versão também inclui muitas atualizações da documentação na seção de ajuda. |
