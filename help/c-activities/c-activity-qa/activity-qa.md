---
keywords: qa; modo qa; qa da atividade, url de qa, urls de qa, url de visualização, url de visualização
description: Saiba como usar URLs de controle de qualidade do Adobe [!DNL Target] para realizar um controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real.
title: Como faço para garantir a qualidade das atividades?
feature: Atividades
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 0d24bcf335980291891e3198a13ec283d1dd325f
workflow-type: tm+mt
source-wordcount: '1785'
ht-degree: 37%

---

# Controle de qualidade da atividade

Use URLs de controle de qualidade em [!DNL Adobe Target] para realizar o controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real.

[!UICONTROL O ] Controle de qualidade da atividade permite testar completamente suas  [!DNL Target] atividades antes de iniciá-las ao vivo. A funcionalidade [!UICONTROL Controle de qualidade da atividade] inclui:

* Links para compartilhar com membros da equipe que nunca mudam ou exigem regeneração, independentemente das atualizações feitas nas experiências ou atividades. Esse recurso permite que você teste completamente suas atividades em toda a jornada do usuário.
* As condições do público-alvo são respeitadas opcionalmente, para que os profissionais de marketing possam testar os critérios de direcionamento ou ignorá-los para garantir a qualidade da aparência das experiências sem precisar atender a essas condições.
* Os relatórios de controle de qualidade são capturados para que os profissionais de marketing possam confirmar que as métricas estão sendo incrementadas conforme esperado e os dados do relatório de controle de qualidade são mantidos separados dos relatórios de produção (para relatórios não-A4T).
* A capacidade de visualizar uma experiência de forma isolada ou com outras atividades ativas que satisfaçam os critérios de entrega (página/solicitação do Target/público-alvo).
* A habilidade de garantir a qualidade de toda a jornada do usuário. Você pode acessar seu site uma vez com o link de controle de qualidade e, em seguida, navegar pelo site inteiro enquanto estiver no Controle de qualidade da atividade. Você permanece no Controle de qualidade da atividade até terminar a sessão ou até usar o  [Bookmarklet de controle de qualidade do Target](/help/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)[!UICONTROL  para forçar você a sair do controle de qualidade da atividade]. Esse recurso é útil se você tiver uma atividade abrangendo várias páginas da Web.

   >[!NOTE]
   >
   >Essa funcionalidade é verdadeira para implementações da at.js com a versão 2.** xor later. Para at.js 1.** implementações, essa funcionalidade é verdadeira somente se o navegador do visitante não bloquear cookies de terceiros.

## Acesso e compartilhamento de um URL de controle de qualidade  {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. Na página [!UICONTROL Visão geral] de uma atividade, clique no link **[!UICONTROL Controle de qualidade da atividade]**.

   ![Link de controle de qualidade da atividade](assets/qa_link.png)

1. Configure as seguintes definições:

   ![Opções de configuração do Link de controle de qualidade](assets/qa_link_config.png)

   * **[!UICONTROL Combinar as regras do público-alvo para ver as experiências]:** algumas vezes, você quer confirmar se a combinação de público-alvo funciona. Outras vezes você deseja verificar a aparência da atividade. Se essa configuração for alternada para a posição &quot;ativada&quot;, os testadores deverão atender aos requisitos de direcionamento para se qualificarem para ver as experiências. Para as atividades do Direcionamento de experiência (XT), um único URL de atividade será fornecido. A experiência que você vê é determinada pela sua qualificação para uma das regras de direcionamento.

      Se essa configuração for colocada na posição &quot;off&quot;, você verá as experiências ao clicar nos links, independente do fato de você se qualificar ou não. Ao executar o controle de qualidade, você pode alternar entre exigir ou não exigir que o direcionamento do público-alvo seja respeitado.

   * **Mostrar conteúdo padrão para todas as outras atividades:** se essa opção for alternada para a posição &quot;ativada&quot;, o conteúdo padrão será exibido para todas as outras atividades. Por exemplo, a visualização é mostrada de forma isolada sem considerar todas as outras atividades ativas na mesma solicitação de página/[!DNL Target].

      Se essa configuração for configurada como &quot;desativada&quot;, considere o seguinte:

      * Se houver colisões entre a atividade que você está testando e outras atividades ao vivo,  [as regras normais de prioridade](/help/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) serão aplicadas. Devido a colisões, é possível que você não possa ver a atividade desejada para o controle de qualidade.
      * Aumento de métricas para as atividades visualizadas, mas apenas no ambiente de relatório de controle de qualidade.

1. Clique em **[!UICONTROL Concluído]** para salvar suas alterações.
1. Compartilhe os URLs do link de atividade com os membros de sua organização para testar.

   Os links de atividades nunca expiram e você não precisa reenviar links se alguém alterar uma atividade ou experiência. No entanto, se você aplicar um público-alvo diferente da [!UICONTROL Biblioteca de público-alvo], em vez de simplesmente editar a atividade, um novo link será gerado e você deverá compartilhá-lo novamente.

   Cada URL de link de atividade (para Experiência A, Experiência B e assim por diante) permite iniciar a jornada do usuário a partir da experiência correspondente. Clique no URL gerado para uma experiência e continue com a navegação normal do site para ver experiências em várias páginas (se houver várias páginas). Apenas um URL é gerado por experiência, mesmo que a experiência abranja várias páginas (teste de modelo ou teste de várias páginas).

   Você pode navegar pelo site para ver as outras páginas porque o modo [!UICONTROL Controle de qualidade da atividade] é aderente. Essa situação é verdadeira para implementações da at.js com a versão 2.** xor later. Para at.js 1.** implementações, essa situação é verdadeira somente se o navegador do visitante não bloquear cookies de terceiros.

1. Para ver os relatórios gerados a partir dos URLs do link de atividade, clique na página **[!UICONTROL Relatórios]** da atividade, clique no ícone **[!UICONTROL Configurações]** ( ![](assets/icon_gear.png) ) e selecione **[!UICONTROL Tráfego do modo de QA]** na lista suspensa **[!UICONTROL Ambiente]**.

## Considerações {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* O link [!UICONTROL Controle de qualidade da atividade] é exibido na página [!UICONTROL Visão geral] de todos os tipos de atividades, exceto para [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] (AP).
* [!UICONTROL Os links de visualização de QA da atividade para atividades salvas podem não ser carregados se houver muitas atividades salvas em sua conta. ] Tentar novamente os links de visualização deve funcionar. Para evitar que essa situação continue acontecendo, arquive as atividades salvas que não são mais usadas ativamente.
* [!UICONTROL Os URLs de controle de qualidade de atividades estão disponíveis com atividades com o Analytics como fonte de geração de relatórios (A4T).] As ocorrências geradas durante a execução do controle de qualidade usando o [!UICONTROL Controle de qualidade da atividade] fluem para o mesmo conjunto de relatórios, onde os dados da atividade fluem mesmo depois que a atividade entra em vigor.
* [!UICONTROL O Controle de qualidade da atividade não exibe o conteúdo para atividades arquivadas ou atividades que estão além das datas de término.] Se você desativar uma atividade finalizada, deverá salvá-la novamente para que [!UICONTROL Controle de qualidade da atividade] funcione.
* Atividades importadas para [!DNL Target Standard/Premium] (de [!DNL Target Classic], por exemplo) não são compatíveis com URLs de controle de qualidade.
* Nas atividades de [!UICONTROL Alocação automática] e [!UICONTROL Recommendations], o modelo não é afetado pelas visitas capturadas no [!UICONTROL Controle de qualidade da atividade].
* [!UICONTROL O ] Controle de qualidade da atividade é aderente. Depois de navegar em um site no [!UICONTROL Controle de qualidade da atividade], sua sessão [!DNL Target] deve expirar ou você deve ter [!DNL Target] liberado você do [!UICONTROL Controle de qualidade da atividade] antes de visualizar seu site como um visitante típico. Use o [bookmarklet de controle de qualidade do Target](/help/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) para forçar você a sair do [!UICONTROL Controle de qualidade da atividade].

   Você também pode forçar a sua saída manualmente carregando uma página em seu site com o parâmetro `at_preview_token` com um valor vazio (por exemplo, `https://www.mysite.com/?at_preview_token=`).

* Se você tiver especificado &quot;URL é&quot; ao criar a atividade [refinamentos no Composer baseado em formulário](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) ou [opções de entrega de página no Visual Experience Composer)](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81), o URL de QA não funcionará porque o [!UICONTROL Controle de qualidade da atividade] anexa parâmetros de URL. Para resolver esse problema, clique no URL do Controle de qualidade para acessar seu site, remover os parâmetros anexados do URL e, em seguida, carregar o novo URL.
* Se você tiver o at.js 1.*x*, o  [!UICONTROL Activity ] QAmode não é aderente se você usar o Safari ou outro navegador que bloqueia cookies de terceiros. Nesses casos, você deve adicionar os parâmetros de visualização a cada URL para o qual você navega. O mesmo é verdadeiro se você implementou [CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md).
* Se uma atividade usar vários públicos-alvo de experiência (por exemplo, um site dos EUA e do Reino Unido incluídos na mesma atividade), os links de controle de qualidade não serão gerados para as quatro combinações (Experiência A/US Site, Experiência A/UK Site, Experiência B/US Site, Experiência B/UK Site). Apenas dois links de Controle de qualidade (Experiência A e Experiência B) são criados e os usuários devem se qualificar para o público-alvo apropriado para ver a página. Uma pessoa do Controle de qualidade do Reino Unido não pode ver o site dos EUA.
* Todos os parâmetros `at_preview` e valores já estão codificados com URL. Na maioria das vezes, tudo funciona conforme o esperado. No entanto, alguns clientes devem carregar balanceadores ou servidores da Web que tentam codificar os parâmetros da cadeia de caracteres de consulta novamente.

   Devido a essa codificação dupla, quando [!DNL Target] tenta decodificar o `at_preview_token`, [!DNL Target] não pode extrair o valor do token correto, resultando em uma visualização que não funciona.

   O Adobe recomenda que você converse com sua equipe de TI para garantir que todos os parâmetros de visualização sejam incluir na lista de permissões para que esses valores não sejam transformados de forma alguma.

   A tabela a seguir lista os parâmetros que podem ser incluir na lista de permissões no seu domínio:

   | Parâmetro | Tipo | Valor | Descrição |
   |--- |--- |--- |--- |
   | `at_preview_token` | Sequência de caracteres criptografada | Obrigatório; sem valor padrão | Uma entidade criptografada que contém a lista de IDs de campanhas que podem ser executadas no modo QA. |
   | `at_preview_index` | String | Empty | O formato do parâmetro é `<campaignIndex>` ou `<campaignIndex>_< experienceIndex>`<br>Ambos os índices começam com 1. |
   | `at_preview_listed_activities_only` | Booleano (true/false) | Valor padrão: false | Se &quot;true&quot;, todas as campanhas especificadas nos parâmetros `at_preview_index` serão processadas.<br>Se &quot;false&quot;, todas as campanhas da página serão processadas, mesmo que não tenham sido especificadas no token de visualização. |
   | `at_preview_evaluate_as_true_audience_ids` | String | Empty | Lista de segmentId-s separada por sublinhado (&quot;_&quot;) que deve sempre (no nível de direcionamento e relatório) ser avaliada como &quot;true&quot; no escopo da solicitação [!DNL Target]. |
   | `_AT_Debug` | String | Janela ou console | Logon no console ou nova janela. |
   | `adobe_mc_ref` |  |  | Passa o URL de referência da página padrão para a nova página. Quando usado com a versão 2.1 (ou posterior) do `AppMeasurement.js`, o [!DNL Adobe Analytics] usa esse valor de parâmetro como o URL de referência na nova página. |
   | `adobe_mc_sdid` |  |  | Passa os [!DNL Supplemental Data Id] (SDID) e [!DNL Experience Cloud Org Id] da página padrão para a nova página. Transmitir essas IDs permite que o [!UICONTROL Analytics for Target] (A4T) &quot;junte&quot; a solicitação [!DNL Target] na página padrão com a solicitação [!DNL Analytics] na nova página. |

* A interface do usuário do [!UICONTROL Modo de QA do Target] mostra apenas o primeiro URL de uma experiência em uma atividade de várias páginas. A suposição é que você esteja criando um teste de jornada e mova de URL1 para URL2. No entanto, se você quiser ir independentemente para o URL 2, copie todos os parâmetros de URL fornecidos em relação ao URL 1 e aplique-os ao URL 2 após colocar um &quot;?&quot; exatamente como você vê no URL 1.

## Compatibilidade da biblioteca JavaScript do Target [!UICONTROL Modo de QA]

[!DNL Target] O suporta as seguintes bibliotecas JavaScript:

* [at.js 1.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)
* [at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)
* [SDK da Web da Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)

A tabela a seguir lista os vários tipos de atividades e indica se o modo [!UICONTROL Controle de qualidade da atividade] é compatível com cada biblioteca:

| Tipo de atividade | at.js 1.x | at.js 2.x | SDK da Web da plataforma |
| --- | --- | --- | --- |
| [!UICONTROL Teste A/B] | Sim | Sim | Sim |
| [!UICONTROL Alocação automática] | Sim | Sim | Sim |
| [!UICONTROL Direcionamento automático] | Não | Não | Não |
| [!UICONTROL Personalização automatizada] (AP) | Não | Não | Não |
| [!UICONTROL Direcionamento de experiência] (XT) | Sim | Sim | Sim |
| [!UICONTROL Teste multivariado] (MVT) | Sim | Sim | Sim |
| [!UICONTROL Recommendations] | Sim | Sim | Sim |

## Visualizar URLs {#preview}

Os URLs de visualização da experiência podem ser gerados para todos os tipos de atividades [!DNL Target] . Os URLs de visualização permitem que você veja o conteúdo da experiência diretamente do site antes que a atividade esteja ativa para fins de visualização e controle de qualidade. Os URLs de visualização de experiência ignoram o direcionamento para forçar a visualização de uma experiência específica.

Para obter informações sobre como os URLs de visualização funcionam com as atividades [!UICONTROL Automated Personalization] (AP), consulte [Visualizar atividades do Automated Personalization com URLs de visualização de experiência](/help/c-activities/t-automated-personalization/experience-preview.md).

Para acessar e compartilhar um URL de visualização, na página **[!UICONTROL Visão geral]** de uma atividade, clique no link **[!UICONTROL Controle de qualidade da atividade]**.

>[!NOTE]
>
>O link [!UICONTROL Controle de qualidade da atividade] e o URL de visualização são os mesmos para todas as atividades diferentes de [!DNL Target] atividades de AP.

A tabela a seguir lista os vários tipos de atividades e indica se o recurso de visualização de URLs é compatível com cada biblioteca ou API:

| Tipo de atividade | at.js 1.x | at.js 2.x | SDK da Web da plataforma | API de entrega | API de administração |
| --- | --- | --- | --- | --- | --- |
| [!UICONTROL Teste A/B] | Sim | Sim | Sim | Não aplicável | Sim |
| [!UICONTROL Alocação automática] | Sim | Sim | Sim | Não aplicável | Sim |
| [!UICONTROL Direcionamento automático] | Sim | Sim | Sim | Não aplicável | Sim |
| [!UICONTROL Personalização automatizada] (AP) | Sim | Sim | Não | Não aplicável | Sim |
| [!UICONTROL Direcionamento de experiência] (XT) | Sim | Sim | Sim | Não aplicável | Sim |
| [!UICONTROL Teste multivariado] (MVT) | Sim | Sim | Sim | Não aplicável | Sim |
| [!UICONTROL Recommendations] | Sim | Sim | Sim | Não aplicável | Sim |






