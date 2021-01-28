---
keywords: known issues;resolved issues;release notes;bugs;issues;fixes
description: Informações sobre problemas conhecidos para esta versão do Adobe Target. Também inclui informações sobre problemas que foram resolvidos.
title: Problemas conhecidos e problemas resolvidos no Adobe Target
feature: known issues
translation-type: tm+mt
source-git-commit: 4ea0a50b2b37fc23fa9c60730af9a41c80cf2082
workflow-type: tm+mt
source-wordcount: '4365'
ht-degree: 69%

---


# Problemas conhecidos e problemas resolvidos

Informações sobre problemas conhecidos de [!DNL Adobe Target]. Também inclui informações sobre problemas que foram resolvidos.

>[!NOTE]
>
>Os números de edição entre parênteses são para uso interno da Adobe.

## Problemas conhecidos {#section_AEDC98B67CF24C9F8E0CF0D2EB9ACAEF}

As seguintes seções listam os problemas conhecidos do [!DNL Target]:

### Métricas do Analytics para Públicos alvos (A4T) para alocação automática e atividades de Público alvo automático

Existe um problema conhecido atual na interface do usuário [!DNL Target] que permite que os usuários selecionem métricas de envolvimento e receita não suportadas como sua métrica principal de objetivo para otimização em [!UICONTROL Autoalocar] e [!UICONTROL Público alvo automático] atividades. As métricas de conversão são suportadas; as métricas de envolvimento e receita são *não* suportadas. Se você selecionar as métricas de envolvimento ou objetivo de receita, um modelo de otimização não será criado (mesmo que a interface do usuário [!DNL Target] atualmente permita selecionar métricas de objetivo não suportadas).

Para obter uma lista de métricas de objetivo compatíveis e não compatíveis, consulte [Métricas de objetivo compatíveis](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa) em *Criar uma atividade que use o Analytics como a fonte do relatórios*. (TNT-38409)

### Delivery de página {#page-delivery}

Se você adicionar uma regra de modelo, como URL contém (/checkout, /cart) no delivery [da](/help/c-activities/t-experience-target/t-xt-create/xt-activity-url.md) página, espaços adicionais recebem o prefixo de suas regras. Esse é um problema superficial e não afeta a criação de definição de públicos e o delivery de ofertas. (TGT-35920)

### Links de pré-visualização do controle de qualidade

Os links de visualização de QA da atividade para atividades salvas podem não ser carregados se houver muitas atividades salvas em sua conta. Tentar novamente os links de visualização deve funcionar. Arquive atividades salvas que não são mais usadas ativamente para impedir que esse problema continue. (TNT-37294)

### Modo de QA para Recommendations atividade

Um problema conhecido impede a pré-visualização se os critérios usados na atividade forem baseados em itens ou em categorias. (TNT-37455)

### Ofertas de redirecionamento {#redirect}

Os problemas a seguir são problemas conhecidos com ofertas redirecionadas:

* Em algumas condições, um número limitado de clientes relatou graus mais altos de variação na distribuição do tráfego ao usar uma oferta de redirecionamento em atividades configuradas com o Analytics for Target (A4T). Os engenheiros da Adobe estão trabalhando atualmente nesse problema.
* As atividades de redirecionamento nas implementações da at.js podem fazer com que o URL de visualização entre em loop (a oferta é entregue repetidamente). Você pode usar o [Modo de controle de qualidade](/help/c-activities/c-activity-qa/activity-qa.md) para realizar a Visualização e o QA. Esse problema não afeta o recebimento real da oferta. (TGT-23019)

### Cancelar carregamento de uma página no VEC {#cancel}

* O seguinte problema conhecido existe ao cancelar o carregamento de uma atividade de [!UICONTROL Teste A/B] ou [!UICONTROL Direcionamento de experiência] (XT) no VEC que contém um URL de redirecionamento.

   Na etapa um do fluxo de trabalho guiado de três partes no VEC, ao cancelar o carregamento da página, o painel [!UICONTROL Modificações] no VEC é exibido e o redirecionamento para o modelo de URL é aplicado na experiência (por exemplo, &quot;Experiência B&quot;). Ao avançar para etapas dois ou três e retornar à etapa um, ocorre a seguinte situação.

   Por padrão, na &quot;Experiência B&quot;, o modelo de carregamento do site cancelado é renderizado e o painel [!UICONTROL Modificações] fica acessível, o que não deve ser o caso, pois essa experiência tem um redirecionamento para o modelo de URL aplicado. O redirecionamento para o modelo de URL deve ser exibido.

   Para mostrar o estado correto da experiência no VEC:

   Se você alternar para outra experiência e alternar de volta para a &quot;Experiência B&quot;, o [!DNL Target] exibe o redirecionamento para o modelo de URL aplicado nessa experiência e o painel [!UICONTROL Modificações] não estará acessível. (TGT-32138)

* Para os sites de Aplicativo de página única (SPA), cancelar o carregamento não permite editar ações no painel [!UICONTROL Modificações].

### Recommendations

Estes são problemas conhecidos das atividades [!UICONTROL Recommendations]:

* Ao copiar uma atividade [!UICONTROL Recommendation] com uma promoção ativa, qualquer alteração na atividade do duplicado atualmente também afeta a atividade original e vice-versa. (TGT-39155)

   Como uma solução temporária:

   * Desativar promoções de atividade
   * Duplicado da atividade
   * Habilitar promoções novamente em cada atividade

* Quando [!DNL Target] retorna uma oferta JSON com getOffer(), ela retorna com o tipo JSON. No entanto, se você retornar um design JSON Recommendations, ele retornará com um tipo de HTML.
* As entidades expiraram corretamente após 60 dias sem receber nenhuma atualização via feed ou API; no entanto, as entidades expiradas não são removidas do índice da Pesquisa de catálogo após a expiração. (IRI-857)
* As sobreposições &quot;Informações de uso&quot; para critérios e desenhos não refletem seu uso nas atividades A/B e direcionamento de experiência (TGT-34331)
* As ofertas de recomendações nas atividades A/B e direcionamento de experiência não mostram uma exibição visual da bandeja de recomendações (TGT-33426)
* Coleções, exclusões, critérios e projetos criados por API não estão visíveis na interface do usuário Público-alvo e podem ser editados por meio da API. (TGT-35777)
* As atividades do Recommendations criadas por meio da API podem ser visualizadas na interface do usuário, mas só podem ser editadas por meio da API.
* O status do feed de Critérios personalizados exibido na visualização da lista de critérios (cartão) é atualizado a cada dez minutos e pode estar desatualizado em mais de dez minutos em raras circunstâncias. O status exibido na visualização de edição de Critérios personalizados é buscado em tempo real e está sempre atualizado. (TGT-35896, TGT-36173)
* Critérios e cartões de design não mostram o número correto de atividades em que estão sendo usados. Se o critério ou design for usado em uma atividade A/B, o cartão pode mostrar incorretamente que o design ou o critério não é usado, mesmo quando o design ou o critério é usado na atividade. (TGT-36621, TGT-37217)

### Atividades de teste multivariado (MVT)

Em uma atividade de MVT, os vencedores mostrados na tabela e no gráfico não são consistentes ao verificar a métrica. Isso ocorre se um usuário mudar de visualização de Resumo para Gráfico, depois voltar para Resumo, alterar uma métrica e voltar para Gráfico. Quando esse problema ocorre, a visualização de resumo sempre exibe o vencedor correto. Se o usuário nunca alternar para a visualização de gráfico entre visualizações de resumo, a visualização de gráfico exibirá o vencedor correto.

### at.js {#atjs}

A seguir, os problemas conhecidos com at.js:

* Ao usar as versões do at.js anteriores à 2.2.0, o rastreamento de cliques não relata conversões no Analytics for Target (A4T) se o código do Adobe Analytics não estiver presente nos elementos da página (como botões). Uma correção foi introduzida para esse problema no at.js 2.2.0. [Atualize para a versão](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) mais recente do at.js se você encontrar esse problema.
* Se você criar uma experiência sem modificações usando o at.js 2.1.1 ou anterior (por exemplo, uma experiência padrão), a experiência pode não ser contada nos relatórios, no Analytics for Target (A4T), no Adobe Analytics ou no Google Analytics. Além disso, o [plug-in ttMeta](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md) pode não funcionar corretamente.

   Como alternativa, use um espaço em branco no conteúdo da experiência. (TNT-33366)

   >[!NOTE]
   >
   >Uma correção para esse problema foi incluída no at.js 2.2.0. Você deve atualizar para a versão [mais recente ou para o at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) ou usar a solução alternativa mencionada acima apenas para as versões do at.js anteriores à versão 2.2.0.

* Quando uma página é carregada no Visual Experience Composer (VEC), o Target precisa determinar se a configuração global da mbox está ativada ou desativada e se há presença de entityID ou categoryID na localidade onde o usuário está tentando aplicar a recomendação no VEC. A lista de critérios é filtrada com base nestas informações. A lista padrão tem algoritmos filtrados, mas a [caixa de verificação de compatibilidade](/help/c-recommendations/t-create-recs-activity/algo-select-recs.md) permite que você visualize a lista completa de algoritmos.

   Ao usar at.js, a caixa de marcação Compatibilidade é ocultada para quer você não possa ver algoritmos.

   Esse problema se aplica somente às atividades de recomendações que usam o VEC.

   **Solução alternativa**: desative a opção [!UICONTROL Filtrar critérios incompatíveis] em [!UICONTROL Recommendations > Configurações]. Depois de desativar essa configuração, todos os critérios (compatíveis e incompatíveis) serão exibidos no seletor de critérios. (TGT-25949)

* Mboxes não disparam em navegadores Microsoft Explorer 11 depois do upgrade para at.js versão 1.0 por causa da interação entre at.js e a API de visitante API 2.2.0. Esse problema afeta a at.js versão 0.9.6 e posteriores. (TNT-27600)
* at.js pode não funcionar com aplicativos Cordova/Hybrid porque os cookies próprios atualmente não são compatíveis com eles. (TNT-26166)

   **Solução alternativa**: configure at.js com a opção &quot;somente x&quot; ativada e transmita `mboxThirdPartyId` em chamadas para gerenciar usuários.

### Métricas de sucesso

Métrica de sucesso com opção avançada &quot;Como a contagem será incrementada&quot; definida como &quot;a cada impressão&quot; ou &quot;a cada impressão (exceto atualizações)&quot; não pode ser usada como uma métrica de sucesso da qual dependeria outra métrica.

Quando uma métrica de sucesso é definida para incrementação a cada impressão, o Target conta o visitante novamente toda vez que ele visitar a métrica de sucesso. O Target reinicia, então, a métrica de sucesso &quot;associação&quot; para 0, para que ela possa contar novamente na próxima impressão. Portanto, se outra métrica exigir que essa métrica tenha sido definida primeiro, o Target nunca reconhecerá que o usuário viu a primeira métrica.

### Analytics for Target (A4T)

Ao usar impressões e conversões de atividades de Públicos alvos no Analysis Workspace, aplique o modelo de Attribution IQ &quot;Mesmo toque&quot; às métricas para garantir uma contagem precisa. Para aplicar um [modelo de atribuição não padrão](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html), clique com o botão direito do mouse na métrica para **modificar Configurações de coluna > ativar Usar modelo de atribuição não padrão > selecionar Modelo de mesmo toque**. Sem esse modelo aplicado, as métricas são sobrestimadas.

Todos os pacotes atuais do Analytics têm a capacidade de adicionar esse modelo com o Attribution IQ. Se você não tiver acesso ao Attribution IQ, confie nos dados A4T no Relatórios e análises.

### APIs do Target

Os clientes não podem realizar operações CRUD em atividades de Alocação automática com a versão v3 da API de Atividades A/B no Adobe I/O.

### Definição de metas GEO

No dia 10 de maio de 2020, atualizamos nossos arquivos do provedor GEO, o que introduziu algumas inconsistências. Por exemplo, alguns valores contendo vírgulas foram adicionados; no entanto, os valores nas audiências existentes não tinham vírgula. Nem todos os nossos servidores de delivery foram afetados por esta mudança. Como resultado, as audiências que usam esses valores podem não ter qualificado todos os visitantes corretos entre 10 de maio e 22 de julho de 2020.

### Relatórios - dados inconsistentes no relatório .csv baixável versus o relatório exibido na interface do Público alvo. {#csv}

Os relatórios gerados para download como arquivos .csv são inconsistentes se a atividade usar mais de uma métrica. O relatório que pode ser baixado é gerado somente com base nas configurações do relatório e considera o mesmo valor para qualquer outra métrica usada.

A fonte da verdade é sempre o relatório exibido na interface do usuário [!DNL Target].

## Problemas resolvidos {#section_FD2FC86E7C734D60B1EDC9DEF60E1014}

Quando os problemas acima são resolvidos, são movidos para as seções a seguir e as notas adicionais, se necessário, serão adicionadas.

### Ofertas de imagem mostrando o rótulo &quot;Processamento&quot;

As ofertas de imagem na página do Oferta às vezes retêm o rótulo de &quot;processamento&quot; por várias horas depois que as imagens são carregadas. Na maioria dos casos, isso é um problema apenas com o rótulo: as ofertas de imagem ainda podem ser usadas no atividade e entregues. (MCUI-10264, TGT-37458)

Isso foi corrigido na versão Target Standard/Premium 20.10.1.

### Relatórios do Analytics for Target (A4T)

Os seguintes problemas relacionados ao A4T foram resolvidos:

* Um problema que afetou as atividades A4T usando uma métrica de meta [!DNL Analytics] que fazia com que os relatórios A4T mostrassem uma divisão de tráfego inesperada ou conversões infladas artificialmente.

   Esse problema afetou o relatórios A4T sob as seguintes condições:

   * A atividade foi criada ou salva entre 15 de setembro e 5 de novembro de 2020 (4 horas PST), e
   * A atividade tinha uma métrica [!DNL Analytics] selecionada como a métrica de objetivo.

   [!DNL Target] dividir corretamente o tráfego durante esse período. No entanto, uma divisão 50/50 na configuração da atividade pode ser exibida, por exemplo, como uma divisão 90/10 nos relatórios A4T.

   Para atividades impactadas, a divisão de tráfego correta é visível para visitantes pela primeira vez na atividade após 5 de novembro (4 horas PST). As novas atividades criadas ou salvas depois desse tempo relatarão a divisão de tráfego corretamente.

* Um problema que afetou as atividades A4T usando uma métrica de meta [!DNL Target] que fazia com que os relatórios A4T relatassem conversões baixas ou inexistentes.

   >[!NOTE]
   >
   >Esse problema afetava apenas o relatórios A4T. Não afetou o delivery da atividade.

   Esse problema afetou o relatórios A4T sob as seguintes condições:

   * A atividade A4T estava em funcionamento entre 22 de setembro e 11 de novembro de 2020 (14:30 PST), e
   * A atividade tinha uma métrica [!DNL Target] selecionada como métrica de objetivo e
   * Quando um visitante atingir o evento alvo da atividade (por exemplo, [!UICONTROL Clicado em um Elemento]), também havia uma atividade não A4T de prioridade mais baixa que correspondia ao evento de conversão. Isso pode acontecer se a atividade não A4T for configurada com a mesma métrica da atividade A4T ou se for configurada com a métrica &quot;any mbox&quot;.

   Esse problema afetou o relatórios das atividades A4T que estavam ativas entre 22 de setembro e 11 de novembro de 2020 (14:30 PST). O relatórios para atividades A4T impactadas mostrará conversões corretamente fora desse intervalo de datas. O relatórios para atividades não-A4T não foi afetado.

Caso tenha outras dúvidas, entre em contato com o Gerente de sucesso do cliente (CSM) ou [Atendimento ao cliente do Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). (CSO 20201110016)

### Relatórios de Público alvo automático {#at-metrics}

Foi resolvido um problema que afetava o relatórios [!DNL Adobe Target Premium] dos usuários [!UICONTROL Público alvo automático] a partir de 15 de setembro, 14:30. (PDT) para 6 de outubro, 9:25 (TFD). Ao exibir relatórios para as métricas de conversão afetadas (configuradas usando a opção &quot;[!UICONTROL Exibida uma página]&quot; ou &quot;[!UICONTROL Clicadas em mbox]&quot;), as taxas de conversão são reportadas incorretamente. Não há nenhum problema de delivery conhecido no momento.

Para ressincronizar e corrigir seu relatórios:

1. Copie e salve as atividades [!UICONTROL Público alvo automático] impactadas.
1. Ative as atividades recém-salvas (se as atividades impactadas estiverem ativas).
1. Exclua as atividades originais (impactadas).

(TGT-38522, CSO 20201006007)

### Relatório {#conversions-audiences}

Atualmente, as conversões incrementam de forma diferente com base na audiência usada.

Por exemplo, para o mesmo visitante, se a contagem de conversão estiver definida para incrementar &quot;Uma vez por participante:&quot;

* Audiência: &quot;Todos os Visitantes qualificados&quot; para conversões no nível de visita aumentam apenas uma vez. Esse é o comportamento esperado.
* Audiência: &quot;Novos Visitantes&quot; para conversões em nível de visita aumentam incorretamente todas as vezes, em vez de aumentarem apenas uma vez. Esse não é o comportamento esperado.

Se a contagem de conversão estiver definida para incrementar &quot;Em cada impressão:&quot;

* Audiência: &quot;Todos os Visitantes qualificados&quot; para conversões em nível de visitante aumentam incorretamente apenas uma vez, em vez de aumentar cada vez. Esse não é o comportamento esperado.
* Audiência: &quot;Novos Visitantes&quot; para conversões em nível de visitante aumentam cada vez. Esse é o comportamento esperado.

Observe que esse problema está relacionado somente ao relatórios [!DNL Target]. Esse não é um problema ao usar o relatórios [!UICONTROL Analytics para Público alvo] (A4T).

Esse problema foi resolvido.

### Páginas que não são carregadas no Visual Experience Composer (VEC) ou no Enhanced Experience Composer (EEC) ao usar o Google Chrome versão 80+

Esse problema conhecido é relacionado à decisão do Google de alterar o comportamento padrão de cookies sem o Atributo SameSite a partir da versão 80 do Chrome. Antes da alteração, o Chrome padronizava todos os cookies sem o atributo SameSite para &quot;SameSite=None&quot; e agora o padrão é &quot;SameSite=Lax&quot;, o que altera a forma como os cookies são enviados em solicitações de GET e POST. Consulte [Atualizações do mesmo site](https://www.chromium.org/updates/same-site).

Para obter mais informações e uma correção, consulte &quot;Como as políticas de aplicação de cookies do Google Chrome SameSite recentemente anunciadas afetam o VEC e o EEC?&quot; em [Solução de problemas relacionados ao Visual Experience Composer e Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

### Falha na renderização do relatório de gráfico de uma atividade de direcionamento automático ao usar uma experiência personalizada como controle

O relatório de gráfico de uma atividade de direcionamento automático não é renderizado para modos &quot;diferenciais&quot; (aumento médio e aumento diário) se não houver dados (0 visitas) em nenhuma experiência. Essa situação pode ocorrer durante o estágio inicial de uma atividade, se a experiência de controle estiver definida como personalizada. Para os outros modos (Execução de controle médio e direcionado, Controle diário e Segmentação e Visitas) funciona bem. Assim que houver alguns dados (visitas diferentes de zero), o relatório ser a renderizado como esperado.

Este problema foi corrigido no Target versão 19.7.1.

### mbox.js

A biblioteca mbox.js não é compatível com linguagens de modelos do lado do cliente, como Handlebars e Mustache. A biblioteca at.js *oferece* suporte a esses idiomas.

**Observação:** a biblioteca mbox.js não será mais desenvolvida. Todos os clientes devem migrar da mbox.js para a at.js. Para obter mais informações, consulte [Migrar para at.js do mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

### Implementação: criação automática de mbox global

Na guia Implementação ([!UICONTROL Administração > Implementação]), o campo [!UICONTROL Criação automática de mbox global] será &quot;false&quot; por padrão para um locatário recém-provisionado.

Quando a mbox.js é baixada pela primeira vez depois do provisionamento, o campo [!UICONTROL Criação automática da Mbox global] é definido como &quot;true&quot; no arquivo mbox.js baixado e no back-end do [!DNL Target], mas continuará sendo exibido como &quot;false&quot; na página [!UICONTROL Implementação] na IU até que a página seja atualizada (depois da atualização da página, o status será &quot;true&quot;).

at.js será baixado com `global_mbox_autocreate = false` no caso de um inquilino recém-provisionado. Se mbox.js for baixada primeiro, global\_mbox\_autocreate será definido como &quot;true&quot; e a at.js também será baixada com `global_mbox_autocreate = true`. (TGT-15929)

### Suporte a permissões empresariais nas APIs do Target {#api}

As ofertas de código criadas na interface do usuário do Target na biblioteca de ofertas podem ser exibidas no espaço de trabalho padrão se a lista de ofertas for obtida usando APIs GET. Esse problema será corrigido na primeira semana de março de 2019. Após essa correção, as ofertas de código serão exibidas no espaço de trabalho apropriado quando obtidas das APIs. Esse problema *não* afeta as ofertas criadas com as APIs. Por exemplo, as ofertas de código criadas nas APIs são exibidas no espaço de trabalho em que foram criadas, seja por meio de APIs GET ou da interface do usuário do Target.

### Relatórios e pedidos extremos

De 25 de novembro de 2019 a 26 de abril de 2020, um servidor Público alvo apresentou um problema que fazia com que valores extremos de pedido fossem contados em métricas de relatório baseadas em receita (AOV, RPV). De 19 de dezembro de 2019 a 23 de abril de 2020, outro servidor enfrentou o mesmo problema. Esse problema não afetou todos os servidores de Públicos alvos ou todos os clientes de Públicos alvos.

Você não foi *afetado* se:

* A implementação do Público alvo usa servidores diferentes.
* Seus relatórios não excluíram pedidos extremos.
* Você usou uma métrica de conversão para medir suas atividades.
* As atividades do Público alvo usam o Analytics para Públicos alvos (A4T).
* Você está localizado na região Ásia-Pacífico (APAC).

Para determinar se esse problema afetou seu relatórios de Público alvo, entre em contato com [Client Care](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB).

### Recommendations

* O índice do feed do Recommendations pode exibir &quot;Aguardando índice&quot; se os itens do feed forem iguais aos da execução anterior. A ingestão do produto para entrega não é afetada. (RECS-6663)

   Este problema foi corrigido no Target versão 19.4.2.

* Os feeds do Recommendations demoram mais tempo para serem processados do que o esperado. (COR-2836)

   Corrigido na versão 16.10.1 do Target.

* A IU de feeds de recomendação não mostra o status de indexação correto. As tarefas de back-end estão funcionando corretamente, mas a IU não é capaz de obter e exibir o estado atual.

   Isso foi corrigido na versão 17.10.1.

### Ofertas de redirecionamento

Uma condição de corrida na sua página pode fazer com que as visualizações de página na página original e na página de redirecionamento sejam contadas. As atualizações para a implementação da at.js estão planejadas para garantir que essa condição de corrida possa ser evitada.

Este problema foi corrigido no at.js versão 1.6.3.

### Grupos de exclusão

* Quando a deduplicação automática é aplicada depois da criação dos grupos de exclusão, a contagem no diagrama de atividades pode estar incorreta na IU.
* Quando uma atividade existente com grupo de exclusão é editada, as inclusões manuais não podem ser refletidas corretamente na IU.

Esses problemas foram resolvidos.

### APIs do Target

A versão v1 da API de oferta no Adobe I/O trata todas as ofertas criadas no Target como estando no espaço de trabalho padrão. (TTTEAM-41957)

Esse problema foi resolvido.

### at.js {#at-js-2}

Mboxes não disparam em navegadores Microsoft Explorer 11 depois do upgrade para at.js versão 1.0 por causa da interação entre at.js e a API de visitante API 2.2.0. Esse problema afeta a at.js versão 0.9.6 e posteriores. (TNT-27600)

Corrigido na versão da API 2.3.0 ou posterior.

### Geografia   direcionamento

A pesquisa de uma string que contenha caracteres especiais (como um espaço ou uma vírgula) não está funcionando no momento ao criar públicos de geolocalização. Esse problema aparece, por exemplo, ao criar públicos baseados em cidades, estados, países etc. Por exemplo, ao pesquisar por &quot;nova york&quot;, a pesquisa não retorna resultados válidos.

Corrigido em novembro de 2018.

### at.js  {#at-js-3}

Ao usar a at.js versão 1.6.0, ocorrem redirecionamentos do Analytics for Target (A4T), mas sem a atividade de qualificação.

Corrigido na versão da at.js 1.6.2.

### Atividades, Espaços de trabalho e Excluir API de atividade

As atividades no espaço de trabalho padrão excluídas via API continuam sendo exibidas na interface de usuário de destino. Como solução alternativa, exclua todas as atividades no espaço de trabalho padrão usando a interface de usuário de destino. (TGT-31315)

Corrigido em 25 de outubro de 2018

### Relatório de nível de oferta de Automated Personalization (AP)

Quando você clica na experiência direcionada em um relatório da atividade de Automated Personalization (AP) para exibir relatórios no nível da oferta, atualmente visualiza resultados vazios, uma mensagem de erro ou um ícone giratório. (TNT-30695)

Corrigido em 27 de setembro de 2018.

### Editor de códigos

Se você recarregar o VEC na etapa 1 do fluxo de trabalho guiado de três etapas, enquanto estiver trabalhando com o Editor de código no Firefox e no Internet Explorer, a guia Modificações não será renderizada corretamente; no entanto, a funcionalidade do VEC não é afetada. (TGT-28730)

Isso foi corrigido na versão 18.9.1.

### Atividade de recomendações que usa uma regra de Promoção do atributo

Ao editar ou copiar uma atividade Recommendations que use uma regra de promoção de atributo, o erro &quot;Campo ausente&quot; é exibido ao clicar em Salvar.

Isso foi corrigido na versão 17.8.1.

### Recommendations de backup

As recomendações de backup exibem erroneamente &quot;Ativado&quot; nos cartões de Itens visualizados recentemente na interface do usuário do Target. (TGT-29308)

Isso foi corrigido na versão 18.4.1 para que &quot;Desabilitado&quot; fosse exibido.

### Atividades de Direcionamento automático e públicos-alvo de relatórios

Quando um nome de público-alvo de relatório usado em uma atividade de Direcionamento automático é alterado, as atualizações futuras do Target para essa atividade poderão falhar com uma mensagem de erro.

Este problema foi corrigido na versão 18.5.1 (22 de maio de 2018).

### at.js {#at-js-4}

O algoritmo para extrair o domínio de nível superior que deve ser usado ao salvar cookies foi alterado na at.js versão 0.9.6. Por causa dessa alteração, os cookies não pode ser salvos em endereços que usam IP. Na maioria das vezes, os endereços IP são usados &#x200B;&#x200B;para fins de teste, mas, como solução alternativa, é possível usar entradas de DNS ou ajustar o arquivo de hosts em uma caixa local. Também é possível usar a função da at.js targetGlobalSettings() para inserir um fragmento de código para oferecer suporte a endereços IP.

Este problema foi remediado na at.js versão 1.2.

### Permissões de usuário empresarial para o Target Premium

Como parte da migração das migrações empresariais, todo o gerenciamento de usuário do Target Premium foi movido da IU do Adobe Target para o Adobe Admin Console.

Como resultado da migração, há dois potenciais problemas dos quais você deveria estar ciente:

* Usuários não administradores receberam um email indicando que agora eles teriam acesso ao Adobe Target. Isso indica que a migração foi concluída na sua organização. O email pode ser desconsiderado.
* Após a migração, houve relatos de reaparecimento de usuários anteriormente desativados no Adobe Admin Console. Sua organização teria um problema se usuários desativados no Adobe Admin Console ainda estivessem aparecendo na sua lista de usuários no Target antes da migração. Recomendamos que os administradores revisem a lista de usuários no Admin Console para validar o acesso.

Esse problema foi corrigido em 30 de agosto de 2017

### Criação da atividade

Um problema com a versão 17.6.2 pode ter afetado as atividades criadas e/ou atualizadas entre 22 de junho de 2017 e 29 de junho de 2017. As seguintes atividades foram afetadas:

* Quaisquer experiências que foram reorganizadas no direcionamento de experiência (XT) seriam revertidas para o pedido original
* Quaisquer regras de segmento locais à atividade (não salvas dentro de um público-alvo) teriam sido perdidas: públicos-alvo combinados, ajustes de localização e quaisquer regras relacionadas a métrica de sucesso.

Nenhuma outra atividade foi afetada.

**Importante:** esse problema não é corrigido automaticamente. Você precisa salvar novamente uma atividade que foi afetada pela correção do problema.

Esse problema foi corrigido em 29 de junho de 2017

### Experience Composer baseado em formulário

Os seguintes problemas conhecidos foram relatados ao usar o Experience Composer baseado em formulário:

* Se você usar o Experience Composer baseado em formulário com uma mbox diferente da mbox global criada automaticamente (target-global-mbox) e escolher uma métrica de envolvimento como métrica de sucesso, a métrica será incrementada apenas nas páginas em que a mbox é usada na atividade. Como exemplo, se sua mbox for homepage\_mbox, a métrica Páginas por visita será o número de ocorrências para homepage\_mbox durante a visita. (TGT-22789)
* Uma exceção de JavaScript é lançada ao excluir uma experiência em uma atividade de Direcionamento de experiência (XT) usando o Experience Composer baseado em formulário durante a etapa 1 do processo. (TGT-24366)

O primeiro problema foi corrigido na versão 17.3.1 do Target (Março de 2017).

O segundo problema foi corrigido na versão 17.6.1 do Target (Junho de 2017).

### at.js {#at-js-5}

Desde o lançamento do Target 17.4.1 (27 de abril de 2017), o uso da ação Inserir imagem no Visual Experience Composer (VEC) fazia com que o conteúdo da oferta não fosse entregue ao usar a biblioteca at.js.

Uma correção para esse problema foi feita na at.js versão 0.9.7 lançada em 22 de maio de 2017.

### Criação de relatórios: atividades de A/B e direcionamento de experiência (XT)

Entre 21:00 PST de 27 de abril e 6:00 PST do dia 5 de maio, atividades de A/B e XT criadas ou editadas com qualquer métrica usando a ação de conversão &quot;Visualizou uma página&quot; (que não foram baseadas em outras métricas), podem ter registrado conversões incorretamente. Este problema agora foi resolvido, entretanto, os relatos sobre a ação de conversão &quot;Visualizou uma página&quot; nessas atividades durante o período de tempo impactado podem não ser precisos e, infelizmente, não podem ser corrigidos. Recomendamos que, para quaisquer decisões baseadas nas ações de conversão &quot;Visualizou uma página&quot; nessas atividades, você confie apenas nos dados registrados antes ou depois do período impactado.

A criação de relatórios de dados para outras métricas ainda pode ser usada, pois elas não foram impactadas.

Correção no hotfix do Target 17.4.3.

### Ofertas: atividades de A/B e direcionamento de experiência (XT)

A entrega e a visualização foram afetadas para ofertas em atividades A/B e XT com, pelo menos, duas experiências e que foram criadas ou editadas usando o Experience Composer baseado em formulário entre a sexta-feira, 28 de abril (21h PT), e a segunda-feira, 1° de maio (21h15 PT). Apenas ofertas com conteúdo padrão eram exibidas.

Correção no hotfix do Target 17.4.3.

### at.js {#at-js-6}

As seguintes ações faziam com que a oferta não fosse entregue ao usar o Visual Experience Composer (VEC) e a at.js: Mover e Reorganizar.

Uma correção para esse problema foi feita na at.js versão 0.9.6.

### Relatórios

A capacidade de exibir várias métricas em um relatório, incluída no Target versão 17.3.1 (30 de março de 2017), foi removida devido a um comportamento inesperado. Esse recurso estará disponível novamente em uma versão futura.

A capacidade de exibir várias métricas em um relatório foi incluída no Target versão 17.4.1 (27 de abril de 2017).

### Ofertas

As imagens excluídas da biblioteca de Oferta de imagem (Ofertas > Ofertas de imagem) permanecem visíveis na interface. Em uma oferta futura, essas imagens excluídas não serão mais exibidas. Enquanto isso, as imagens excluídas são exibidas na IU, mas têm um status de Excluída. (TGT-23793)

Corrigido na versão 17.4.1 do Target (27 de abril de 2017).

### Ofertas de redirecionamento

Para os critérios Visualizados recentemente, as regras dinâmicas baseadas em entidade não levarão a nenhuma recomendação se o parâmetro entity.id não for transmitido na solicitação da mbox. (RECS-6241)

Esse problema foi corrigido depois da versão das recomendações (22 de março de 2018). Depois do lançamento das recomendações, o Target ignora as regras dinâmicas baseadas na entidade se entity.id não for transmitido na solicitação da mbox.

### at.js  {#at-js-7}

Quando os usuários tentam fazer o download da at.js a partir da página de detalhes da implementação depois de atualizar as configurações da at.js, a mbox.js é baixada em vez da at.js. (TGT-23069)

Corrigido na versão 17.3.1 do Target (30 de março de 2017).

### Regras de exclusão globais

As regras de exclusão globais estão demorando 10 a 20 minutos para se propagarem para a borda para recomendações do Premium. (RECS-5270)

Corrigido na versão 17.2.2.0 das recomendações (6 de março de 2017).

### Relatórios do Analytics for Target (A4T)

Os relatórios não são atualizados quando a métrica de criação de relatórios é trocada. Esse é um problema de interface do usuário. Não há impacto sobre a entrega ou coleta de dados de criação de relatórios. (TGT-22970)

Corrigido na versão 17.2.2.0 do Target (24 de fevereiro de 2017).

### Relatórios em CSV

Os relatórios baixados não respeitam a configuração Excluir pedidos extremos. (TGT-21871)

Corrigido na versão 17.2.1.0 do Target.
