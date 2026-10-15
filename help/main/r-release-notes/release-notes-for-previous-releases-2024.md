---
keywords: Notas de versão;notas de pré-lançamento;aprimoramentos futuros;correções futuras;recursos futuros;versão futura
description: Veja uma lista de recursos, aprimoramentos e correções incluídos em versões anteriores do Adobe Target.
title: Quais recursos estão incluídos nas versões anteriores?
feature: Release Notes
source-git-commit: 53cd01d2406b8a2f8560fe380ebb5044872e6711
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 15%
---
# Notas de versão para versões anteriores

Notas de versão referentes a versões anteriores do [!DNL Adobe Target], incluindo notas de versão para o [!DNL Target Standard/Premium], a plataforma do [!DNL Target] e a biblioteca JavaScript do [!DNL Target] (at.js).

As notas de versão estão listadas em ordem decrescente por mês e ano da versão.

>[!NOTE]
>
>Consulte [Notas de versão do Target (atual)](/help/main/r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A) para obter informações sobre as versões do Target para o mês vigente (plataforma e Target Standard/Premium).

## Notas de versão - 2024

### [!DNL Adobe Experience Platform Web SDK] Otimização de escopo do `__view__` (22 de outubro de 2024)

Entre 22 de julho de 2024 e 15 de agosto de 2024, a equipe do [!DNL Target] otimizou o escopo do `__view__`, melhorando a precisão da impressão da atividade, da visita e dos relatórios de visitantes. Essa otimização tem como objetivo capturar automaticamente dados de relatórios para apresentações renderizadas automaticamente e deve ser transparente para a maioria das contas.

Todos os novos clientes do [!DNL Adobe Experience Platform Web SDK] terão essa otimização habilitada. No entanto, os clientes que migraram da at.js e não seguiram as etapas de implementação abaixo têm a otimização desativada. Recomendamos que esses clientes analisem suas implementações até 3 de fevereiro de 2025. Após essa data, habilitaremos a otimização para todos os clientes. Falhas ao revisar e ajustar as implementações até lá podem afetar os relatórios, conforme mencionado abaixo. Entre em contato com [!DNL Adobe Customer Care] se precisar confirmar se a implementação foi afetada ou se precisar de mais tempo para ajustar a implementação.

>[!IMPORTANT]
>
>Se não conseguir concluir sua análise de implementação e resolver qualquer problema até 3 de fevereiro de 2025, você poderá solicitar uma extensão única de seis meses. Verifique se sua solicitação foi enviada até 31 de janeiro de 2025. O Adobe analisará e decidirá sua solicitação.

Para se beneficiar dessa otimização em caso de renderização manual de propostas, revise seu [[!DNL Platform Web SDK implementation]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank} para garantir que você esteja enviando notificações após renderizar experiências manualmente ou ao usar o método `applyPropositions` (ou a ação [!DNL Launch] correspondente como auxiliar) para renderizar experiências.

Os cenários mais comuns quando as experiências são renderizadas manualmente incluem:

* Uso de ofertas JSON
* Usando um escopo de decisão personalizado em uma atividade criada no [[!UICONTROL Experience Composer baseado em formulário]](/help/main/c-experiences/form-experience-composer.md)
* O `renderDecisions: true` não está sendo usado ao buscar uma atividade criada usando o [!UICONTROL Experience Composer baseado em formulário] que usa o escopo `__view__` global

Se as notificações não forem implementadas conforme documentado em [Renderizar conteúdo personalizado](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/personalization/rendering-personalization-content){target=_blank} no guia *Coleta de dados*, os dados de relatório poderão estar ausentes em [!DNL Target] e em [Relatórios do Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Em determinados cenários, você pode notar uma divisão de tráfego incorreta, pois os dados de relatório não são capturados. Ou, em outros cenários, relatar o mesmo evento repetidamente.

Dependendo da sua implementação, verifique se há [!DNL Analytics] e impactos dos relatórios do A4T.

O [!DNL Platform Web SDK] oferece suporte a dois tipos de implementação para renderização de experiências e personalizações:

* **Chamada única para personalização e medição.**

  Inicialmente recomendada, a abordagem de chamada única para [!DNL Platform Web SDK] está agendada para ser descontinuada em favor da abordagem de chamada dividida. A Adobe aconselha todas as novas implementações a usarem a nova abordagem de chamada dividida e recomenda que os clientes existentes também façam a transição para o método de chamada dividida.

  Se você continuar usando a abordagem de chamada única, poderá observar as seguintes alterações inesperadas em seus relatórios do [!DNL Analytics]:

  * Um declínio nas rejeições.
  * As ocorrências do A4T e da [!UICONTROL Exibição de página] não são compiladas, tornando desafiador executar determinados detalhamentos e correlações dos relatórios do A4T usando eVars e eventos do [!DNL Analytics].

* **Dividir chamadas (também conhecido como eventos da parte superior e inferior da página).**

  Este tipo de implementação é a nova [abordagem de implementação split-call](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/use-cases/top-bottom-page-events){target=_blank} recomendada por [!DNL Adobe]. Com esta abordagem, a nova otimização não afeta os relatórios do [!DNL Analytics] ou do A4T.

Em caso de dúvidas, entre em contato com o [Atendimento ao cliente da Adobe](/help/main/cmp-resources-and-contact-information.md##reference_ACA3391A00EF467B87930A450050077C). (KB-2179)

### at.js versão 2.11.6 (segunda-feira, 29 de setembro de 2024)

* Correção de um problema que impedia o [!DNL Target] de operar corretamente com ofertas de redirecionamento no [!UICONTROL Visual Experience Composer] (VEC) ou [!UICONTROL Experience Composer baseado em formulário].

Para obter mais informações sobre as versões da at.js, consulte [detalhes da versão da at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank} no *Guia do Desenvolvedor do Adobe Target*.

### [!DNL Target] relatórios em [!DNL Adobe Customer Journey Analytics] (8 de maio de 2024)

A integração entre o [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} e o [!DNL Target] fornece ferramentas poderosas de análise e economia de tempo para o seu programa de otimização.

Os principais benefícios de usar o [!DNL Customer Journey Analytics] como fonte de relatórios para o [!DNL Target] são:

* Profissionais de marketing podem aplicar dinamicamente as métricas de sucesso do [!DNL Customer Journey Analytics] nos relatórios de atividades do [!DNL Target] a qualquer momento. Não há necessidade de especificar tudo antes de executar a atividade.
* Os profissionais de marketing podem aproveitar os recursos do [!DNL Customer Journey Analytics], como o [Painel de experimentação](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}, para analisar ainda mais a personalização do site.

Para obter mais informações, consulte [Relatórios do Target no Adobe Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

### Extensão auxiliar do [!UICONTROL Visual Experience Composer] (23 de abril de 2024)

A extensão auxiliar herdada [!DNL Target] do Visual Experience Composer foi criada usando Manifest V2. [!DNL Google] anunciou que não permitirá mais extensões criadas usando o Manifest V2 a partir de junho de 2024. Para obter mais informações, consulte [[!UICONTROL Extensão de assistente do Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

A [!DNL Adobe] recomenda que os clientes mudem para a [extensão Auxiliar de edição visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) mais recente assim que possível.

### Atualizações para `Browser:iPad` e `Browser:iPhone` nos atributos de público-alvo [!UICONTROL Navegador] (30 de abril de 2024)

| Atualizações | Detalhes |
|--- |--- |
| [!UICONTROL Navegador:iPad] e [!UICONTROL Navegador:iPhone] atualizados em [Atributos do navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) usados ao criar públicos-alvo. | O [!DNL Adobe Target] permite [segmentar qualquer um dos vários atributos de categoria](/help/main/c-target/c-audiences/c-target-rules/target-rules.md), incluindo visitantes que usam [opções específicas de navegador ou navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) quando visitam sua página.<P>A partir do [!DNL Target] Standard/Premium 24.3.1 (4-6 de março de 2024), os públicos-alvo internos criados usando a interface do usuário do Target, como `Browser:iPad` e `Browser:iPhone`, serão atualizados para executar o direcionamento adequado para [!DNL iPad] e [!DNL iPhone] usando `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` e `profile.mobile.isTablet`.<P>Esta atualização não requer nenhuma ação por parte dos clientes.<p><B>Importante</b>: para que os clientes executem o direcionamento adequado para [!DNL iPad] e [!DNL iPhone] em scripts de perfil (e segmentos do JavaScript), as alterações manuais devem ser feitas pelo cliente até **30 de abril de 2024**. Para obter exemplos de configurações alternativas que devem ser alteradas manualmente, consulte [Atualizações para [!DNL iPad] e [!DNL iPhone] em [!UICONTROL Navegador] atributos de público-alvo](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

### Extensão [!UICONTROL Auxiliar de edição visual] (14 de março de 2024)

Esta versão contém os seguintes aprimoramentos e correções para a extensão do [[!DNL Adobe Experience Cloud Editing Helper]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) para o [!DNL Google Chrome]:

* O mecanismo de carregamento do iFrame foi aprimorado ao executar a criação nos sites dos clientes.
* Correção de um problema que fazia com que a extensão duplicasse cookies ao executar a criação no [!UICONTROL Visual Experience Composer] (VEC).

### [!DNL Target] Standard/Premium 24.3.1 (4-6 de março de 2024)

Essa versão conta com os seguintes aprimoramentos e correções:

* Correção da lógica que calcula o número de seletores únicos em uma atividade. (TGT-47878)
* Correção de um problema que fazia com que as atividades do [!UICONTROL Multivariate] (MVT) configuradas com os relatórios do [!UICONTROL Analytics for Target] (A4T) não fossem exibidas corretamente. (TGT-47490)
* Mensagem de aviso exibida nos relatórios quando uma experiência sem tráfego é usada como a experiência de controle. (TGT-47537)
* Adição de muitas correções de back-end e localização.

### [!DNL Target] Standard/Premium 24.1.1 (22, 23 e 25 de janeiro de 2024)

Essa versão conta com os seguintes aprimoramentos e correções:

* As atividades do [!UICONTROL Analytics for Target] (A4T) com métricas de meta de receita não exibiram &quot;Receita&quot;, pois o nome da coluna e a métrica de receita não eram exibidas no formato ($) no relatório. Era um problema superficial que foi corrigido. (TGT-46995)
* Correção de um problema que fazia com que os intervalos de datas do relatório não funcionassem corretamente. (TGT-47396)
* Correção de um problema que fazia com que o status incorreto fosse exibido na página [!UICONTROL Todas as atividades] depois que os clientes ativavam ou desativavam uma atividade usando o ícone [!UICONTROL Mais ações]. (TGT-47367)
* Correção de um problema que fazia com que o relatório de [!UICONTROL Atributos importantes] não fosse exibido para um único cliente. (TGT-47272)
* Correção de um problema que fazia com que uma mensagem “Conteúdo inválido” fosse exibida quando um único cliente tentava habilitar a opção “Exigir autenticação”. (TGT-47195)
* Atualização de várias strings localizadas na interface do [!DNL Target].
