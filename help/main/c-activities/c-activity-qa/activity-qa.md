---
keywords: qa; modo qa; qa da atividade, url de qa, urls de qa, url de visualização, url de visualização
description: Saiba como usar o Adobe [!DNL Target] URLs de controle de qualidade para realizar o controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real.
title: Como faço para garantir a qualidade das atividades?
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 38%

---

# Controle de qualidade da atividade

Usar URLs de controle de qualidade em [!DNL Adobe Target] para realizar o controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real.

[!UICONTROL Controle de qualidade da atividade] permite testar totalmente a [!DNL Target] antes de iniciá-las ao vivo. O [!UICONTROL Controle de qualidade da atividade] inclui:

* Links para compartilhar com membros da equipe que nunca mudam ou exigem regeneração, independentemente das atualizações feitas nas experiências ou atividades. Esse recurso permite que você teste completamente suas atividades em toda a jornada do usuário.
* As condições do público-alvo são respeitadas opcionalmente, para que os profissionais de marketing possam testar os critérios de direcionamento ou ignorá-los para garantir a qualidade da aparência das experiências sem precisar atender a essas condições.
* Os relatórios de controle de qualidade são capturados para que os profissionais de marketing possam confirmar que as métricas estão sendo incrementadas conforme esperado e os dados do relatório de controle de qualidade são mantidos separados dos relatórios de produção (para relatórios não-A4T).
* A capacidade de visualizar uma experiência de forma isolada ou com outras atividades ativas que satisfaçam os critérios de entrega (página/solicitação do Target/público-alvo).
* A habilidade de garantir a qualidade de toda a jornada do usuário. Você pode acessar seu site uma vez com o link de controle de qualidade e, em seguida, navegar pelo site inteiro enquanto estiver no Controle de qualidade da atividade. Você permanece no Controle de qualidade da atividade até terminar a sessão ou até usar o  [Bookmarklet de controle de qualidade do Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879)[!UICONTROL  para forçar você a sair do controle de qualidade da atividade]. Esse recurso é útil se você tiver uma atividade abrangendo várias páginas da Web.

   >[!NOTE]
   >
   >Essa funcionalidade é verdadeira para implementações da at.js com a versão 2.*x* ou posterior. Para at.js 1.*x* Essa funcionalidade é verdadeira somente se o navegador do visitante não bloquear cookies de terceiros.

## Acesso e compartilhamento de um URL de controle de qualidade  {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. De uma atividade [!UICONTROL Visão geral] clique no botão **[!UICONTROL Controle de qualidade da atividade]** link .

   ![Link de controle de qualidade da atividade](assets/qa_link.png)

1. Configure as seguintes definições:

   ![Opções de configuração do Link de controle de qualidade](assets/qa_link_config.png)

   * **[!UICONTROL Combinar as regras do público-alvo para ver as experiências]:** Às vezes, você quer confirmar que a combinação de público-alvo funciona. Outras vezes você deseja verificar a aparência da atividade. Se essa configuração for alternada para a posição &quot;ativada&quot;, os testadores deverão atender aos requisitos de direcionamento para se qualificarem para ver as experiências. Para as atividades do Direcionamento de experiência (XT), um único URL de atividade será fornecido. A experiência que você vê é determinada pela sua qualificação para uma das regras de direcionamento.

      Se essa configuração for colocada na posição &quot;off&quot;, você verá as experiências ao clicar nos links, independente do fato de você se qualificar ou não. Ao executar o controle de qualidade, você pode alternar entre exigir ou não exigir que o direcionamento do público-alvo seja respeitado.

   * **Mostrar conteúdo padrão para todas as outras atividades:** Se essa opção for alternada para a posição &quot;ativada&quot;, o conteúdo padrão será exibido para todas as outras atividades. Por exemplo, a visualização é mostrada de forma isolada sem considerar todas as outras atividades ativas na mesma página/[!DNL Target] solicitação.

      Se essa configuração for configurada como &quot;desativada&quot;, considere o seguinte:

      * Se houver colisões entre a atividade que você está testando e outras atividades ao vivo,  [as regras normais de prioridade](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) serão aplicadas. Devido a colisões, é possível que você não possa ver a atividade desejada para o controle de qualidade.
      * Aumento de métricas para as atividades visualizadas, mas apenas no ambiente de relatório de controle de qualidade.

1. Clique em **[!UICONTROL Concluído]** para salvar suas alterações.
1. Compartilhe os URLs do link de atividade com os membros de sua organização para testar.

   Os links de atividades nunca expiram e você não precisa reenviar links se alguém alterar uma atividade ou experiência. No entanto, se você aplicar um público-alvo diferente do [!UICONTROL Biblioteca de público-alvo], em vez de simplesmente editar a atividade, um novo link é gerado e você deve compartilhar novamente.

   Cada URL de link de atividade (para Experiência A, Experiência B e assim por diante) permite iniciar a jornada do usuário a partir da experiência correspondente. Clique no URL gerado para uma experiência e continue com a navegação normal do site para ver experiências em várias páginas (se houver várias páginas). Apenas um URL é gerado por experiência, mesmo que a experiência abranja várias páginas (teste de modelo ou teste de várias páginas).

   Você pode navegar pelo site para ver as outras páginas porque a variável [!UICONTROL Controle de qualidade da atividade] O modo é aderente. Essa situação é verdadeira para implementações da at.js com a versão 2.*x* ou posterior. Para at.js 1.*x* Essa situação é verdadeira somente se o navegador do visitante não bloquear cookies de terceiros.

1. Para ver os relatórios gerados a partir dos URLs do link de atividade, clique no link da atividade **[!UICONTROL Relatórios]** clique no botão **[!UICONTROL Configurações]** ícone (  ![](assets/icon_gear.png) ) e, em seguida, selecione **[!UICONTROL Tráfego do modo de controle de qualidade]** do **[!UICONTROL Ambiente]** lista suspensa.

## Considerações {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* O [!UICONTROL Controle de qualidade da atividade] é exibido na [!UICONTROL Visão geral] página de todos os tipos de atividade exceto para [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] (AP).
* [!UICONTROL Os links de visualização de QA da atividade para atividades salvas podem não ser carregados se houver muitas atividades salvas em sua conta. ] Tentar novamente os links de visualização deve funcionar. Para evitar que essa situação continue acontecendo, arquive as atividades salvas que não são mais usadas ativamente.
* [!UICONTROL Os URLs de controle de qualidade de atividades estão disponíveis com atividades com o Analytics como fonte de geração de relatórios (A4T).] Ocorrências geradas ao executar o controle de qualidade usando [!UICONTROL Controle de qualidade da atividade] fluxo para o mesmo conjunto de relatórios em que os dados da atividade fluem mesmo depois que a atividade entra em vigor.
* [!UICONTROL O Controle de qualidade da atividade não exibe o conteúdo para atividades arquivadas ou atividades que estão além das datas de término.] Se você desativar uma atividade finalizada, deverá salvar a atividade novamente para [!UICONTROL Controle de qualidade da atividade] para trabalhar.
* Atividades importadas para [!DNL Target Standard/Premium] de [!DNL Target Classic], por exemplo) não são compatíveis com URLs de controle de qualidade.
* Em [!UICONTROL Alocação automática] e [!UICONTROL Recommendations] , o modelo não é afetado pelas visitas capturadas em [!UICONTROL Controle de qualidade da atividade].
* [!UICONTROL Controle de qualidade da atividade] é aderente. Depois de navegar em um site na [!UICONTROL Controle de qualidade da atividade], seu [!DNL Target] a sessão deve expirar ou você deve ter [!DNL Target] liberte-o de [!UICONTROL Controle de qualidade da atividade] antes de visualizar seu site como um visitante típico. Use o [Bookmarklet de controle de qualidade do Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) para forçar você a sair de [!UICONTROL Controle de qualidade da atividade].

   Você também pode forçar a sua saída manualmente carregando uma página em seu site com o parâmetro `at_preview_token` com um valor vazio (por exemplo, `https://www.mysite.com/?at_preview_token=`).

* Se você especificou &quot;URL é&quot; ao criar a atividade [refinamentos no Criador baseado em formulário](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) ou [opções de entrega de página no Visual Experience Composer)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81), o URL de controle de qualidade não funciona porque [!UICONTROL Controle de qualidade da atividade] anexa parâmetros de URL. Para resolver esse problema, clique no URL do Controle de qualidade para acessar seu site, remover os parâmetros anexados do URL e, em seguida, carregar o novo URL.
* Se você tiver o at.js 1.*x*, [!UICONTROL Controle de qualidade da atividade] O modo não é aderente se você usar o Safari ou outro navegador que bloqueia cookies de terceiros. Nesses casos, você deve adicionar os parâmetros de visualização a cada URL para o qual você navega. O mesmo é verdadeiro se tiver implementado o [CNAME](https://developer.adobe.com/target/before-implement/implement-cname-support-in-target/).
* Se uma atividade usar vários públicos-alvo de experiência (por exemplo, um site dos EUA e do Reino Unido incluídos na mesma atividade), os links de controle de qualidade não serão gerados para as quatro combinações (Experiência A/US Site, Experiência A/UK Site, Experiência B/US Site, Experiência B/UK Site). Apenas dois links de Controle de qualidade (Experiência A e Experiência B) são criados e os usuários devem se qualificar para o público-alvo apropriado para ver a página. Uma pessoa do Controle de qualidade do Reino Unido não pode ver o site dos EUA.
* Todos os parâmetros `at_preview` e valores já estão codificados com URL. Na maioria das vezes, tudo funciona conforme o esperado. No entanto, alguns clientes devem carregar balanceadores ou servidores da Web que tentam codificar os parâmetros da cadeia de caracteres de consulta novamente.

   Devido a essa codificação dupla, quando [!DNL Target] tenta decodificar a variável `at_preview_token`, [!DNL Target] não é possível extrair o valor do token correto, resultando em uma visualização que não funciona.

   O Adobe recomenda que você converse com sua equipe de TI para garantir que todos os parâmetros de visualização sejam incluir na lista de permissões para que esses valores não sejam transformados de forma alguma.

   A tabela a seguir lista os parâmetros que podem ser incluir na lista de permissões no seu domínio:

   | Parâmetro | Tipo | Valor | Descrição |
   |--- |--- |--- |--- |
   | `at_preview_token` | Sequência de caracteres criptografada | Obrigatório; sem valor padrão | Uma entidade criptografada que contém a lista de IDs de campanhas que podem ser executadas no modo QA. |
   | `at_preview_index` | String | Empty | O formato do parâmetro é `<campaignIndex>` ou `<campaignIndex>_< experienceIndex>`<br>Ambos os índices começam com 1. |
   | `at_preview_listed_activities_only` | Booleano (true/false) | Valor padrão: false | Se &quot;true&quot;, todas as campanhas especificadas nos parâmetros `at_preview_index` serão processadas.<br>Se &quot;false&quot;, todas as campanhas da página serão processadas, mesmo que não tenham sido especificadas no token de visualização. |
   | `at_preview_evaluate_as_true_audience_ids` | String | Empty | Lista de segmentId-s separada por sublinhado (&quot;_&quot;) que deve sempre (no nível de direcionamento e relatório) ser avaliada como &quot;true&quot; no escopo do [!DNL Target] solicitação. |
   | `_AT_Debug` | String | Janela ou console | Logon no console ou nova janela. |
   | `adobe_mc_ref` |  |  | Passa o URL de referência da página padrão para a nova página. Quando usado com a versão 2.1 (ou posterior) do `AppMeasurement.js`, o [!DNL Adobe Analytics] usa esse valor de parâmetro como o URL de referência na nova página. |
   | `adobe_mc_sdid` |  |  | Passa o [!DNL Supplemental Data Id] (SDID) e [!DNL Experience Cloud Org Id] da página padrão para a nova página. O envio dessas IDs permite [!UICONTROL Analytics para Target] (A4T) para &quot;unir&quot; a [!DNL Target] na página padrão com o [!DNL Analytics] na nova página. |

* O [!UICONTROL Modo de controle de qualidade do Target] A interface do usuário mostra apenas o primeiro URL de uma experiência em uma atividade de várias páginas. A suposição é que você esteja criando um teste de jornada e mova de URL1 para URL2. No entanto, se você quiser ir independentemente para o URL 2, copie todos os parâmetros de URL fornecidos em relação ao URL 1 e aplique-os ao URL 2 após colocar um &quot;?&quot; exatamente como você vê no URL 1.
* Os links de visualização de QA da atividade para atividades salvas podem não ser carregados se houver muitas atividades salvas em sua conta. Tente novamente os links de pré-visualização. Arquive atividades salvas que não são mais usadas ativamente para impedir que esse problema continue acontecendo.

## Compatibilidade da biblioteca JavaScript do Target [!UICONTROL Modo de QA] {#compatibility}

[!DNL Target] O suporta as seguintes bibliotecas JavaScript:

* [at.js 1.x](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/)
* [at.js 2.x](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/)
* [SDK da Web da Adobe Experience Platform](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/)

A tabela a seguir lista os vários tipos de atividades e indica se [!UICONTROL Controle de qualidade da atividade] o modo é compatível com cada biblioteca:

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

Os URLs de visualização de experiência podem ser gerados para todos [!DNL Target] tipos de atividades. Os URLs de visualização permitem que você veja o conteúdo da experiência diretamente do site antes que a atividade esteja ativa para fins de visualização e controle de qualidade. Os URLs de visualização de experiência ignoram o direcionamento para forçar a visualização de uma experiência específica.

Para obter informações sobre como os URLs de visualização funcionam com o [!UICONTROL Automated Personalization] (AP), consulte [Visualizar atividades do Automated Personalization com URLs de visualização da experiência](/help/main/c-activities/t-automated-personalization/experience-preview.md).

Para acessar e compartilhar um URL de visualização, no **[!UICONTROL Visão geral]** clique no botão **[!UICONTROL Controle de qualidade da atividade]** link .

>[!NOTE]
>
>O [!UICONTROL Controle de qualidade da atividade] o link e o URL de visualização são os mesmos para todas as atividades diferentes de [!DNL Target] Atividades de AP.

A tabela a seguir lista os vários tipos de atividades e indica se o recurso de visualização de URLs é compatível com cada biblioteca ou API:

| Tipo de atividade | at.js 1.x | at.js 2.x | SDK da Web da plataforma |
| --- | --- | --- | --- |
| [!UICONTROL Teste A/B] | Sim | Sim | Sim |
| [!UICONTROL Alocação automática] | Sim | Sim | Sim |
| [!UICONTROL Direcionamento automático] | Sim | Sim | Sim |
| [!UICONTROL Personalização automatizada] (AP) | Sim | Sim | Sim |
| [!UICONTROL Direcionamento de experiência] (XT) | Sim | Sim | Sim |
| [!UICONTROL Teste multivariado] (MVT) | Sim | Sim | Sim |
| [!UICONTROL Recommendations] | Sim | Sim | Sim |

