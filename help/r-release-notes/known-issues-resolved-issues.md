---
description: Informações sobre problemas conhecidos para esta versão do Target. Também inclui informações sobre problemas que foram resolvidos.
keywords: problemas conhecidos, problemas resolvidos, notas de versão;bugs;issues;fixes
seo-description: Informações sobre problemas conhecidos desta versão do Adobe Target. Também inclui informações sobre problemas que foram resolvidos.
seo-title: Problemas conhecidos e problemas resolvidos no Adobe Target
solution: Target
title: Problemas conhecidos e problemas resolvidos
topic: Premium
uuid: f8e8e057-1842-4922-ab7f-4d5441048573
translation-type: tm+mt
source-git-commit: 89f3cc4a6fe5ea34398cf56824fa699e19cc56fc

---


# Problemas conhecidos e problemas resolvidos{#known-issues-and-resolved-issues}

Informações sobre problemas conhecidos para esta versão do Target. Também inclui informações sobre problemas que foram resolvidos.

>[!NOTE]
>
>Os números de edição entre parênteses são para uso interno da Adobe.

## Problemas conhecidos {#section_AEDC98B67CF24C9F8E0CF0D2EB9ACAEF}

As seguintes seções listam os problemas conhecidos do [!DNL Target]:

### Links de visualização de QA da atividade {#preview}

Os links de [visualização de QA da atividade](/help/c-activities/c-activity-qa/activity-qa.md) para atividades salvas podem não ser carregados se houver muitas atividades salvas em sua conta. Tentar novamente os links de visualização deve funcionar. Para impedir que isso continue acontecendo, arquive as atividades salvas que não são mais usadas ativamente. (TNT-32697)

### Ofertas de redirecionamento {#redirect}

Os problemas a seguir são problemas conhecidos com ofertas redirecionadas:

* Em algumas condições, um número limitado de clientes relatou graus mais altos de variação na distribuição do tráfego ao usar uma oferta de redirecionamento em atividades configuradas com o Analytics for Target (A4T). Os engenheiros da Adobe estão trabalhando atualmente nesse problema.
* As atividades de redirecionamento nas implementações da at.js podem fazer com que o URL de visualização entre em loop (a oferta é entregue repetidamente). Você pode usar o [Modo de controle de qualidade](../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) para realizar a Visualização e o QA. Esse problema não afeta o recebimento real da oferta. (TGT-23019)

### Falha na renderização do relatório de gráfico de uma atividade de direcionamento automático ao usar uma experiência personalizada como controle

O relatório de gráfico de uma atividade de direcionamento automático não é renderizado para modos "diferenciais" (aumento médio e aumento diário) se não houver dados (0 visitas) em nenhuma experiência. Essa situação pode ocorrer durante o estágio inicial de uma atividade, se a experiência de controle estiver definida como personalizada. Para os outros modos (Execução de controle médio e direcionado, Controle diário e Segmentação e Visitas) funciona bem. Assim que houver alguns dados (visitas diferentes de zero), o relatório ser a renderizado como esperado.

### Cancelar carregamento de uma página no VEC {#cancel}

* O seguinte problema conhecido existe ao cancelar o carregamento de uma atividade de [!UICONTROL Teste A/B] ou [!UICONTROL Direcionamento de experiência] (XT) no VEC que contém um URL de redirecionamento.

   Na etapa um do fluxo de trabalho guiado de três partes no VEC, ao cancelar o carregamento da página, o painel [!UICONTROL Modificações] no VEC é exibido e o redirecionamento para o modelo de URL é aplicado na experiência (por exemplo, "Experiência B"). Ao avançar para etapas dois ou três e retornar à etapa um, ocorre a seguinte situação.

   Por padrão, na "Experiência B", o modelo de carregamento do site cancelado é renderizado e o painel [!UICONTROL Modificações] fica acessível, o que não deve ser o caso, pois essa experiência tem um redirecionamento para o modelo de URL aplicado. O redirecionamento para o modelo de URL deve ser exibido.

   Para mostrar o estado correto da experiência no VEC:

   Se você alternar para outra experiência e alternar de volta para a "Experiência B", o [!DNL Target] exibe o redirecionamento para o modelo de URL aplicado nessa experiência e o painel [!UICONTROL Modificações] não estará acessível. (TGT-32138)

* Para os sites de Aplicativo de página única (SPA), cancelar o carregamento não permite editar ações no painel [!UICONTROL Modificações].

### Suporte a permissões empresariais nas APIs do Target {#api}

As ofertas de código criadas na interface do usuário do Target na biblioteca de ofertas podem ser exibidas no espaço de trabalho padrão se a lista de ofertas for obtida usando APIs GET. Esse problema será corrigido na primeira semana de março de 2019. Após essa correção, as ofertas de código serão exibidas no espaço de trabalho apropriado quando obtidas das APIs. Esse problema *não* afeta as ofertas criadas com as APIs. Por exemplo, as ofertas de código criadas nas APIs são exibidas no espaço de trabalho em que foram criadas, seja por meio de APIs GET ou da interface do usuário do Target.

### Recommendations

A seguir, os problemas conhecidos com atividades de recomendações:

* As entidades expiraram corretamente após 60 dias de não receberem atualizações através de feed ou API; no entanto, as entidades expiradas não são removidas do índice de Pesquisa de catálogo após a expiração. (IRI-857)
* As sobreposições "Informações de uso" para Critérios e Designs não refletem seu uso em atividades A/B e direcionamento de experiência (TGT-34331)
* As ofertas do Recommendations nas atividades A/B e direcionamento de experiência não mostram uma visualização da bandeja do Recommendations (TGT-33426)
* Coleções, exclusões, critérios e designs criados por meio da API não estão visíveis na interface do usuário do Target e só podem ser editados por meio da API. (TGT-35777)
* As atividades do Recommendations criadas por meio da API podem ser visualizadas na interface do usuário, mas só podem ser editadas por meio da API.

### Atividades de teste multivariado (MVT)

Em uma atividade de MVT, os vencedores mostrados na tabela e no gráfico não são consistentes ao verificar a métrica. Isso ocorre se um usuário mudar de visualização de Resumo para Gráfico, depois voltar para Resumo, alterar uma métrica e voltar para Gráfico. Quando esse problema ocorre, a visualização de resumo sempre exibe o vencedor correto. Se o usuário nunca alternar para a visualização de gráfico entre visualizações de resumo, a visualização de gráfico exibirá o vencedor correto.

### at.js

A seguir, os problemas conhecidos com at.js:

* Se você criar uma experiência sem modificações usando o at.js 2.*x* (por exemplo, uma experiência padrão), a experiência pode não ser contada em relatórios, no Analytics for Target (A4T), no Analytics ou no Google Analytics. Além disso, o plug-in [ttMeta](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md) pode não funcionar corretamente.

   Como solução, use um espaço em branco no conteúdo da experiência. (TNT-33366)

* Quando uma página é carregada no Visual Experience Composer (VEC), o Target precisa determinar se a configuração global da mbox está ativada ou desativada e se há presença de entityID ou categoryID na localidade onde o usuário está tentando aplicar a recomendação no VEC. A lista de critérios é filtrada com base nestas informações. A lista padrão tem algoritmos filtrados, mas a [caixa de verificação de compatibilidade](/help/c-recommendations/t-create-recs-activity/algo-select-recs.md) permite que você visualize a lista completa de algoritmos.

   Ao usar at.js, a caixa de marcação Compatibilidade é ocultada para quer você não possa ver algoritmos.

   Esse problema se aplica somente às atividades de recomendações que usam o VEC.

   **Solução alternativa**: desative a opção [!UICONTROL Filtrar critérios incompatíveis] em [!UICONTROL Recommendations &gt; Configurações]. Depois de desativar essa configuração, todos os critérios (compatíveis e incompatíveis) serão exibidos no seletor de critérios. (TGT-25949)

* Mboxes não disparam em navegadores Microsoft Explorer 11 depois do upgrade para at.js versão 1.0 por causa da interação entre at.js e a API de visitante API 2.2.0. Esse problema afeta a at.js versão 0.9.6 e posteriores. (TNT-27600)
* at.js pode não funcionar com aplicativos Cordova/Hybrid porque os cookies próprios atualmente não são compatíveis com eles. (TNT-26166)

   **Solução alternativa**: configure at.js com a opção "somente x" ativada e transmita `mboxThirdPartyId` em chamadas para gerenciar usuários.

### mbox.js

A biblioteca mbox.js não é compatível com linguagens de modelos do lado do cliente, como Handlebars e Mustache. A biblioteca at.js *oferece* suporte a esses idiomas.

**Observação:** a biblioteca mbox.js não será mais desenvolvida. Todos os clientes devem migrar da mbox.js para a at.js. Para obter mais informações, consulte [Migrar para at.js do mbox.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

### Implementação: criação automática de mbox global

Na guia Implementação ([!UICONTROL Configurar &gt; Implementação]), o campo [!UICONTROL Criação automática da Mbox global] será "false" por padrão no caso de um inquilino recém-provisionado.

Quando a mbox.js é baixada pela primeira vez depois do provisionamento, o campo [!UICONTROL Criação automática da Mbox global] é definido como "true" no arquivo mbox.js baixado e no back-end do [!DNL Target], mas continuará sendo exibido como "false" na página [!UICONTROL Implementação] na IU até que a página seja atualizada (depois da atualização da página, o status será "true").

at.js será baixado com `global_mbox_autocreate = false` no caso de um inquilino recém-provisionado. Se mbox.js for baixada primeiro, global\_mbox\_autocreate será definido como "true" e a at.js também será baixada com `global_mbox_autocreate = true`. (TGT-15929)

### Métricas de sucesso

Métrica de sucesso com opção avançada "Como a contagem será incrementada" definida como "a cada impressão" ou "a cada impressão (exceto atualizações)" não pode ser usada como uma métrica de sucesso da qual dependeria outra métrica.

Quando uma métrica de sucesso é definida para incrementação a cada impressão, o Target conta o visitante novamente toda vez que ele visitar a métrica de sucesso. O Target reinicia, então, a métrica de sucesso "associação" para 0, para que ela possa contar novamente na próxima impressão. Portanto, se outra métrica exigir que essa métrica tenha sido definida primeiro, o Target nunca reconhecerá que o usuário viu a primeira métrica.

### Analytics for Target (A4T)

Atualmente, as impressões e as conversões das atividades do Target são contadas incorretamente na Analysis Workspace.

Como solução alternativa, confie nos dados do A4T em Reports &amp; Analytics até que esse problema seja corrigido.

### APIs do Target

Os clientes não podem realizar operações CRUD em atividades de Alocação automática com a versão v3 da API de Atividades A/B no Adobe I/O.

## Problemas resolvidos {#section_FD2FC86E7C734D60B1EDC9DEF60E1014}

Quando os problemas acima são resolvidos, são movidos para as seções a seguir e as notas adicionais, se necessário, serão adicionadas.

### Recommendations

* O índice do feed do Recommendations pode exibir "Aguardando índice" se os itens do feed forem iguais aos da execução anterior. A ingestão do produto para entrega não é afetada. (RECS-6663)

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

### at.js

Mboxes não disparam em navegadores Microsoft Explorer 11 depois do upgrade para at.js versão 1.0 por causa da interação entre at.js e a API de visitante API 2.2.0. Esse problema afeta a at.js versão 0.9.6 e posteriores. (TNT-27600)

Corrigido na versão da API 2.3.0 ou posterior.

### Geografia  direcionamento

A pesquisa de uma string que contenha caracteres especiais (como um espaço ou uma vírgula) não está funcionando no momento ao criar públicos de geolocalização. Esse problema aparece, por exemplo, ao criar públicos baseados em cidades, estados, países etc. Por exemplo, ao pesquisar por "nova york", a pesquisa não retorna resultados válidos.

Corrigido em novembro de 2018.

### at.js

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

Ao editar ou copiar uma atividade Recommendations que use uma regra de promoção de atributo, o erro "Campo ausente" é exibido ao clicar em Salvar.

Isso foi corrigido na versão 17.8.1.

### Recommendations de backup

As recomendações de backup exibem erroneamente "Ativado" nos cartões de Itens visualizados recentemente na interface do usuário do Target. (TGT-29308)

Isso foi corrigido na versão 18.4.1 para que "Desabilitado" fosse exibido.

### Atividades de Direcionamento automático e públicos-alvo de relatórios

Quando um nome de público-alvo de relatório usado em uma atividade de Direcionamento automático é alterado, as atualizações futuras do Target para essa atividade poderão falhar com uma mensagem de erro.

Este problema foi corrigido na versão 18.5.1 (22 de maio de 2018).

### at.js

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

### at.js

Desde o lançamento do Target 17.4.1 (27 de abril de 2017), o uso da ação Inserir imagem no Visual Experience Composer (VEC) fazia com que o conteúdo da oferta não fosse entregue ao usar a biblioteca at.js.

Uma correção para esse problema foi feita na at.js versão 0.9.7 lançada em 22 de maio de 2017.

### Criação de relatórios: atividades de A/B e direcionamento de experiência (XT)

Entre 21:00 PST de 27 de abril e 6:00 PST do dia 5 de maio, atividades de A/B e XT criadas ou editadas com qualquer métrica usando a ação de conversão "Visualizou uma página" (que não foram baseadas em outras métricas), podem ter registrado conversões incorretamente. Este problema agora foi resolvido, entretanto, os relatos sobre a ação de conversão "Visualizou uma página" nessas atividades durante o período de tempo impactado podem não ser precisos e, infelizmente, não podem ser corrigidos. Recomendamos que, para quaisquer decisões baseadas nas ações de conversão "Visualizou uma página" nessas atividades, você confie apenas nos dados registrados antes ou depois do período impactado.

A criação de relatórios de dados para outras métricas ainda pode ser usada, pois elas não foram impactadas.

Correção no hotfix do Target 17.4.3.

### Ofertas: atividades de A/B e direcionamento de experiência (XT)

A entrega e a visualização foram afetadas para ofertas em atividades A/B e XT com, pelo menos, duas experiências e que foram criadas ou editadas usando o Experience Composer baseado em formulário entre a sexta-feira, 28 de abril (21h PT), e a segunda-feira, 1° de maio (21h15 PT). Apenas ofertas com conteúdo padrão eram exibidas.

Correção no hotfix do Target 17.4.3.

### at.js

As seguintes ações faziam com que a oferta não fosse entregue ao usar o Visual Experience Composer (VEC) e a at.js: Mover e Reorganizar.

Uma correção para esse problema foi feita na at.js versão 0.9.6.

### Relatórios

A capacidade de exibir várias métricas em um relatório, incluída no Target versão 17.3.1 (30 de março de 2017), foi removida devido a um comportamento inesperado. Esse recurso estará disponível novamente em uma versão futura.

A capacidade de exibir várias métricas em um relatório foi incluída no Target versão 17.4.1 (27 de abril de 2017).

### Ofertas

As imagens excluídas da biblioteca de Oferta de imagem (Ofertas \&gt; Ofertas de imagem) permanecem visíveis na interface. Em uma oferta futura, essas imagens excluídas não serão mais exibidas. Enquanto isso, as imagens excluídas são exibidas na IU, mas têm um status de Excluída. (TGT-23793)

Corrigido na versão 17.4.1 do Target (27 de abril de 2017).

### Ofertas de redirecionamento

Para os critérios Visualizados recentemente, as regras dinâmicas baseadas em entidade não levarão a nenhuma recomendação se o parâmetro entity.id não for transmitido na solicitação da mbox. (RECS-6241)

Esse problema foi corrigido depois da versão das recomendações (22 de março de 2018). Depois do lançamento das recomendações, o Target ignora as regras dinâmicas baseadas na entidade se entity.id não for transmitido na solicitação da mbox.

### at.js

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
