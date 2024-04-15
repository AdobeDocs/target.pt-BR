---
keywords: qa;modo qa; atividade qa;qa url;qa urls;visualizar url;visualizar urls
description: Saiba como usar o Adobe [!DNL Target] URLs de controle de qualidade para realizar o controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real.
title: Como faço para testar as atividades?
feature: Activities
exl-id: 5c606d61-6d13-4a9b-9a23-4840f1754d3c
source-git-commit: 4b7c6d82e6988c64ace401d8f749b181b8dc1866
workflow-type: tm+mt
source-wordcount: '1665'
ht-degree: 27%

---

# Controle de qualidade da atividade

Usar URLs de controle de qualidade no [!DNL Adobe Target] para realizar o controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real.

[!UICONTROL Activity QA] O permite testar totalmente [!DNL Target] atividades antes de iniciá-las em tempo real. A variável [!UICONTROL Activity QA] A funcionalidade inclui:

* Links para compartilhar com membros da equipe que nunca mudam ou exigem regeneração, independentemente das atualizações feitas nas experiências ou atividades. Esse recurso permite testar totalmente suas atividades em toda a jornada do usuário.
* As condições do público-alvo são respeitadas opcionalmente, para que os profissionais de marketing possam testar os critérios de direcionamento ou ignorá-los para garantir a qualidade da aparência das experiências sem precisar atender a essas condições.
* Os relatórios de controle de qualidade são capturados para que os profissionais de marketing possam confirmar que as métricas estão sendo incrementadas conforme esperado e os dados do relatório de controle de qualidade são mantidos separados dos relatórios de produção (para relatórios não-A4T).
* A capacidade de visualizar uma experiência de forma isolada ou com outras atividades ativas que satisfaçam os critérios de entrega (página/[!DNL Target] solicitação/público-alvo).
* A habilidade de garantir a qualidade de toda a jornada do usuário. Você pode acessar seu site uma vez com o link de controle de qualidade e, em seguida, navegar pelo site inteiro enquanto estiver no Controle de qualidade da atividade. Você permanece no Controle de qualidade da atividade até terminar a sessão ou até usar o [Bookmarklet de controle de qualidade do Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) para forçar você a sair do [!UICONTROL Activity QA]. Esse recurso é útil se você tiver uma atividade abrangendo várias páginas da Web.

  >[!NOTE]
  >
  >Essa funcionalidade é verdadeira para implementações da at.js com a versão 2.*x* ou posteriormente. Para at.js 1.*x* implementações, essa funcionalidade será verdadeira somente se o navegador do visitante não bloquear cookies de terceiros.

## Acesso e compartilhamento de um URL de controle de qualidade  {#section_1C59BAA247B247BDB125D1BE8EAD4547}

1. A partir de uma atividade de [!UICONTROL Overview] clique em **[!UICONTROL Activity QA]**.

   ![Link de controle de qualidade da atividade](assets/qa_link.png)

1. Configure as seguintes definições:

   ![Opções de configuração do Link de controle de qualidade](assets/qa_link_config.png)

   * **[!UICONTROL Match audience rules to see experiences]:** Às vezes, você deseja confirmar se a correspondência do público-alvo funciona. Outras vezes você deseja verificar a aparência da atividade. Se essa configuração for alternada para a posição &quot;ativada&quot;, os testadores deverão atender aos requisitos de direcionamento para se qualificarem para ver as experiências. Para as atividades do Direcionamento de experiência (XT), um único URL de atividade será fornecido. A experiência que você vê é determinada pela sua qualificação para uma das regras de direcionamento.

     Se essa configuração for colocada na posição &quot;off&quot;, você verá as experiências ao clicar nos links, independente do fato de você se qualificar ou não. Ao executar o controle de qualidade, você pode alternar entre exigir ou não exigir que o direcionamento do público-alvo seja respeitado.

   * **Mostrar conteúdo padrão para todas as outras atividades:** Se essa opção for alternada para a posição &quot;ativada&quot;, o conteúdo padrão será exibido para todas as outras atividades. Por exemplo, a visualização é exibida sem considerar todas as outras atividades ativas na mesma página/página[!DNL Target] solicitação.

     Se essa configuração for configurada como &quot;desativada&quot;, considere o seguinte:

      * Se houver colisões entre a atividade que você está testando e outras atividades ao vivo, [regras normais de prioridade](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) aplicável. Devido a colisões, é possível que você não consiga ver a atividade desejada para o controle de qualidade.
      * Aumento de métricas para as atividades visualizadas, mas apenas no ambiente de relatório de controle de qualidade.

1. Clique em **[!UICONTROL Done]** para salvar as alterações.
1. Compartilhe os URLs de link de atividade com os membros de sua organização para testes.

   Os links de atividades nunca expiram e você não precisa reenviar links se alguém alterar uma atividade ou experiência. No entanto, se você aplicar um público-alvo diferente do [!UICONTROL Audience Library], em vez de simplesmente editar a atividade, um novo link é gerado e deve ser compartilhado novamente.

   Cada URL de link de atividade (para a Experiência A, Experiência B e assim por diante) permite iniciar a jornada do usuário a partir da experiência correspondente. Clique no URL gerado para uma experiência e prossiga com a navegação normal do site para ver experiências em várias páginas (se houver várias páginas). Somente um URL é gerado por experiência, mesmo que a experiência abranja várias páginas (teste de modelo ou teste de várias páginas).

   Você pode navegar pelo site para ver as outras páginas porque o [!UICONTROL Activity QA] é aderente. Essa situação é verdadeira para implementações da at.js com a versão 2.*x* ou posteriormente. Para at.js 1.*x* implementações, essa situação só será verdadeira se o navegador do visitante não bloquear cookies de terceiros.

1. Para ver os relatórios gerados a partir dos URLs do link de atividade, clique no link **[!UICONTROL Reports]** clique no link **[!UICONTROL Settings]** ícone (  ![imagem icon_gear](assets/icon_gear.png) ) e selecione **[!UICONTROL QA Mode Traffic]** do **[!UICONTROL Environment]** lista suspensa.

## Liberando-se do modo de QA

[!UICONTROL Activity QA] é aderente. Depois de navegar em um site no [!UICONTROL Activity QA], seu [!DNL Target] a sessão deve expirar ou você deve ter [!DNL Target] liberar você do [!UICONTROL Activity QA] antes de exibir seu site como um visitante típico.

### at.js 2.*x* 

Se o site tiver a at.js 2.*x* implantado, use o [Bookmarklet de Controle de qualidade do Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879) para forçar você a sair do [!UICONTROL Activity QA]. O carregamento de uma página em seu site com um valor vazio, conforme descrito no próximo marcador, não *não* remova o cookie de controle de qualidade do navegador quando a at.js 2.*x* é implantado(a).

### at.js 1.*x*  

Se o site tiver a at.js 1.*x* implantado, além de usar o [Bookmarklet de Controle de qualidade do Target](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md#concept_A8A3551A4B5342079AFEED5ECF93E879), você também pode forçar a sua saída manualmente carregando uma página em seu site com o `at_preview_token` parâmetro com um valor vazio. Por exemplo,

`https://www.mysite.com/?at_preview_token=`

### [!DNL Adobe Experience Platform Web SDK]

Se o site tiver o [[!UICONTROL Platform Web SDK]](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank} implantado, você pode forçar a sua saída manualmente carregando uma página em seu site com o `at_qa_mode` parâmetro com um valor vazio. Por exemplo,

`https://www.mysite.com/?at_qa_mode=`

## Considerações {#section_B256EDD7BFEC4A6DA72A8A6ABD196D78}

* Como o Controle de qualidade da atividade agora está disponível para todos [!DNL Target] tipos de atividades, o recurso &quot;Visualizar atividades do Automated Personalization com URLs de visualização de experiência&quot; não é mais necessário.
* [!UICONTROL Activity QA] os links de visualização para atividades salvas podem não ser carregados se houver muitas atividades salvas em sua conta. Tentar novamente os links de visualização deve funcionar. Para evitar que essa situação continue ocorrendo, arquive as atividades salvas que não são mais usadas ativamente.
* [!UICONTROL Activity QA] Os URLs estão disponíveis com atividades com o [Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Ocorrências geradas ao executar o controle de qualidade usando [!UICONTROL Activity QA] fluxo para o mesmo conjunto de relatórios no qual os dados da atividade fluem mesmo após a atividade ser ativada.
* [!UICONTROL Activity QA] O não exibe o conteúdo de atividades arquivadas ou atividades que estão além das datas de término. Se você desativar uma atividade finalizada, deverá salvá-la novamente por [!UICONTROL Activity QA] para trabalhar.
* Atividades importadas para o [!DNL Target Standard/Premium] (de [!DNL Target Classic], por exemplo) não são compatíveis com URLs de controle de qualidade.
* Entrada [!UICONTROL Auto-Allocate] e [!UICONTROL Recommendations] atividades, o modelo não é afetado pelas visitas capturadas no [!UICONTROL Activity QA].
* Se você tiver especificado &quot;URL é&quot; ao criar a atividade [refinamentos no Criador baseado em formulário](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) ou [opções de entrega de página no Visual Experience Composer)](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81), o URL de controle de qualidade não funciona porque [!UICONTROL Activity QA] anexa parâmetros de URL. Para resolver esse problema, clique no URL do Controle de qualidade para acessar seu site, remover os parâmetros anexados do URL e, em seguida, carregar o novo URL.
* Se você tiver o at.js 1.*x*, [!UICONTROL Activity QA] O modo não é aderente se você usar o Safari ou outro navegador que bloqueie cookies de terceiros. Nesses casos, é necessário adicionar os parâmetros de visualização a cada URL para o qual você navega. O mesmo é verdadeiro se você tiver implementado o [CNAME](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/implement-cname-support-in-target.html){target=_blank}.
* Se uma atividade usar vários públicos-alvo de experiência (por exemplo, um site dos EUA e Reino Unido incluídos na mesma atividade), os links de controle de qualidade não serão gerados para as quatro combinações (Experiência A/Site dos EUA, Experiência A/Site do Reino Unido, Experiência B/Site dos EUA, Experiência B/Site do Reino Unido). Apenas dois links de Controle de qualidade (Experiência A e Experiência B) são criados e os usuários devem se qualificar para o público-alvo apropriado para ver a página. Uma pessoa do Controle de qualidade do Reino Unido não pode ver o site dos EUA.
* Todos os parâmetros `at_preview` e valores já estão codificados com URL. Na maioria das vezes, tudo funciona conforme o esperado. No entanto, alguns clientes devem carregar balanceadores ou servidores da Web que tentam codificar os parâmetros da cadeia de caracteres de consulta novamente.

  Devido a essa codificação dupla, quando [!DNL Target] O tenta decodificar o `at_preview_token`, [!DNL Target] O não pode extrair o valor do token correto, resultando em uma visualização que não funciona.

  [!DNL Adobe] incluir na lista de permissões A recomenda que você converse com sua equipe de TI para garantir que todos os parâmetros de visualização sejam classificados para que esses valores não sejam transformados de forma alguma.

  Incluir na lista de permissões A tabela a seguir lista os parâmetros que podem ser classificados em seu domínio:

  | Parâmetro | Tipo | Valor | Descrição |
  |--- |--- |--- |--- |
  | `at_preview_token` | Sequência de caracteres criptografada | Obrigatório; sem valor padrão | Uma entidade criptografada que contém a lista de IDs de campanha que podem ser executadas no modo de QA. |
  | `at_preview_index` | String | Empty | O formato do parâmetro é `<campaignIndex>` ou `<campaignIndex>_< experienceIndex>`<br>Ambos os índices começam com 1. |
  | `at_preview_listed_activities_only` | Booleano (true/false) | Valor padrão: false | Se &quot;true&quot;, todas as campanhas especificadas nos parâmetros `at_preview_index` serão processadas.<br>Se &quot;false&quot;, todas as campanhas da página serão processadas, mesmo que não tenham sido especificadas no token de visualização. |
  | `at_preview_evaluate_as_true_audience_ids` | String | Empty | Lista de segmentId-s separada por sublinhado (&quot;_&quot;) que deve sempre (no nível de direcionamento e relatórios) ser avaliada como &quot;true&quot; no escopo da [!DNL Target] solicitação. |
  | `_AT_Debug` | String | Janela ou console | Logon no console ou nova janela. |
  | `adobe_mc_ref` |  |  | Passa o URL de referência da página padrão para a nova página. Quando usado com a versão 2.1 (ou posterior) do `AppMeasurement.js`, o [!DNL Adobe Analytics] usa esse valor de parâmetro como o URL de referência na nova página. |
  | `adobe_mc_sdid` |  |  | Passa o [!DNL Supplemental Data Id] e a [!DNL Experience Cloud Org Id] da página padrão para a nova página. Transmitir essas IDs permite [!UICONTROL Analytics for Target] (A4T) para &quot;costurar&quot; o [!DNL Target] na página padrão com a variável [!DNL Analytics] na nova página. |

* A variável [!UICONTROL Target QA Mode] A interface do usuário mostra somente o primeiro URL de uma experiência em uma atividade de várias páginas. A suposição é que você esteja criando um teste de jornada e mova do URL 1 para URL 2. No entanto, se você quiser ir independentemente para o URL 2, copie todos os parâmetros de URL fornecidos em relação ao URL 1 e aplique-os ao URL 2 após colocar um &quot;?&quot; exatamente como você vê no URL 1.
* Os links de visualização de QA da atividade para atividades salvas podem não ser carregados se houver muitas atividades salvas em sua conta. Tente novamente os links de pré-visualização. Arquive atividades salvas que não são mais usadas ativamente para impedir que esse problema continue acontecendo.

## Biblioteca JavaScript do Target [!UICONTROL QA Mode] compatibilidade {#compatibility}

[!DNL Target] O é compatível com as seguintes bibliotecas JavaScript:

* [at.js 1.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [at.js 2.x](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html)
* [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR)

A tabela a seguir lista os vários tipos de atividades e indica se [!UICONTROL Activity QA] O modo é compatível com cada biblioteca:

| Tipo de atividade | at.js 1.x | at.js 2.x | SDK da Web da Platform |
| --- | --- | --- | --- |
| [!UICONTROL A/B Test] | Sim | Sim | Sim |
| [!UICONTROL Auto-Allocate] | Sim | Sim | Sim |
| [!UICONTROL Auto-Target] | Sim | Sim | Sim |
| [!UICONTROL Automated Personalization] (AP) | Sim | Sim | Sim |
| [!UICONTROL Experience Targeting] (XT) | Sim | Sim | Sim |
| [!UICONTROL Multivariate Test] (MVT) | Sim | Sim | Sim |
| [!UICONTROL Recommendations] | Sim | Sim | Sim |