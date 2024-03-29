---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; redirecionar; oferta de redirecionamento; adobe-mc-sdid; adobe_mc_ref
description: Encontre respostas para perguntas sobre como usar ofertas de redirecionamento ao usar o Analytics para [!DNL Target] (A4T). O A4T permite usar os relatórios do Analytics para [!DNL Target] atividades.
title: Onde posso encontrar perguntas frequentes sobre ofertas de redirecionamento com o A4T?
feature: Analytics for Target (A4T)
exl-id: 4706057f-bd8b-4562-94e0-be22b2e19297
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 47%

---

# Ofertas de redirecionamento - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre o uso de ofertas de redirecionamento [!DNL Adobe Analytics] como fonte de relatórios para [!DNL Adobe Target] (A4T).

## O Analytics for Adobe Target (A4T) é compatível com as ofertas de redirecionamento? {#section_46B8B03ED4D542C6AD875F5F61176298}

+++Responda Sim, se a implementação usar [!DNL at.js]. No entanto, sua implementação deve atender aos requisitos mínimos listados abaixo para usar [ofertas de redirecionamento](/help/main/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) em atividades que utilizam o Analytics como a fonte de relatórios.

+++

## Quais são os requisitos mínimos para usar as ofertas de redirecionamento com o A4T? {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

+++Responda Sua implementação deve atender aos seguintes requisitos mínimos:

* Serviço de ID de visitante da Experience Cloud: [!DNL visitorAPI.js] versão 2.3.0 ou superior.
* Adobe Analytics: [!DNL appMeasurement.js] versão 2.1.
* Adobe Target: [!DNL at.js] versão 1.6.2 ou posteriores.

As três bibliotecas devem ser incluídas na página com a oferta de redirecionamento e na página para a qual o visitante será redirecionado.

+++

## Por que algumas vezes existem discrepâncias de dados entre o A4T e o Analytics?

+++Resposta Algumas discrepâncias de dados são esperadas. Para obter mais informações, consulte [Variações de dados esperadas entre o Target e o Analytics ao usar ou não o A4T](/help/main/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md).

+++

## Como posso minimizar as discrepâncias na distribuição de tráfego ao usar ofertas de redirecionamento em atividades do A4T? {#discrepancies}

+++Resposta Um número limitado de clientes relatou graus mais altos de variação na distribuição do tráfego ao usar ofertas de redirecionamento em atividades configuradas com o [!UICONTROL Analytics for Target] (A4T).

Considere o seguinte:

* Ordem incorreta de [!DNL Target] e [!DNL Analytics] As chamadas de podem ser responsáveis por graus mais altos de variação.

   A variável [!DNL Target] a chamada deve preceder o [!DNL Analytics] chame na página de origem (onde o redirecionamento ocorre) e na página de destino (onde o redirecionamento termina).

* Certifique-se de usar ofertas de redirecionamento nas atividades de redirecionamento do A4T.
* Se houver vários [!DNL Target] solicitações de local na página de origem (onde ocorre o redirecionamento), [!DNL Adobe] A recomenda que você execute a atividade de redirecionamento na primeira [!DNL Target] solicitação de localização.

   Execução da atividade de redirecionamento no primeiro [!DNL Target] de localização reduz as chances de quaisquer qualificações de atividade ocorrerem em [!DNL Target] solicitações de local e como ser contado no relatório. Os visitantes redirecionados não precisam ser contados nos relatórios de outras atividades, pois não verão as experiências.

+++

## Por que as visualizações de página na página original e na página de redirecionamento são contadas às vezes? {#section_B8F6CC2190B84CF08D945E797C5AF07B}

+++Resposta Ao usar a at.js versão 1.6.3 ou posterior, contar as exibições de página em ambas as páginas não é um problema. Essa condição de corridas afeta apenas os clientes que usam as versões anteriores. A equipe do Target mantém duas versões do at.js, a versão atual e a segunda versão mais recente. Atualize o at.js conforme necessário para garantir que você esteja executando uma [versão compatível](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

Se você estiver usando uma versão anterior não compatível do at.js, existe a possibilidade de ocorrer uma condição de corrida que pode fazer com que a chamada do Analytics seja acionada antes que o redirecionamento seja executado na primeira página. Essa situação pode fazer com que as exibições de página na página original e na página de redirecionamento sejam contadas. Essa situação resulta em uma exibição de página extra na primeira página, quando o visitante nunca &quot;viu&quot; realmente essa primeira página.

É recomendável usar o compositor baseado em formulário para criar uma atividade de redirecionamento para aumentar a velocidade do redirecionamento de página devido ao local em que o código é executado na página. Além disso, é recomendável criar uma oferta de redirecionamento para cada experiência, até mesmo para a experiência padrão, na qual o redirecionamento retornaria a página original. Criar uma oferta de redirecionamento para cada experiência garante que, se ocorrer uma contagem incorreta, ela ocorra em todas as experiências. Os relatórios e as análises ainda são válidos para o teste.

Um motivo para usar ofertas de redirecionamento para todas as experiências na atividade, incluindo a experiência padrão (controle), é colocar as mesmas condições em todas as experiências. Por exemplo, se a experiência padrão não tiver uma oferta de redirecionamento, mas as outras experiências tiverem ofertas redirecionadas, a velocidade da experiência sem a oferta de redirecionamento terá uma vantagem inerente. O redirecionamento de ofertas é recomendado apenas para cenários temporários, como testes. O redirecionamento de ofertas não é recomendado para cenários permanentes, como personalização. Depois de determinar o &quot;vencedor&quot;, você deve remover o redirecionamento para melhorar o desempenho do carregamento da página.

+++

## O Visual Experience Composer (VEC) e o Experience Composer baseado em formulários são suportados? {#section_FDA26FE7909B48539DA770559E687677}

+++Responda Sim, ambos os compositores são compatíveis, desde que você use as ofertas de redirecionamento integradas.

Se você usa seu próprio código personalizado para o redirecionamento, deve garantir que preenche os dois novos parâmetros associados aos URLs de redirecionamento (`adobe_mc_sdid` e `adobe_mc_ref`, explicados abaixo).

+++

## Quais são os novos parâmetros de cadeia de caracteres de consulta adicionados aos URLs de redirecionamento? {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

+++Resposta Os seguintes parâmetros da sequência de consulta estão associados às ofertas de redirecionamento:

| Parâmetro | Descrição |
|--- |--- |
| `adobe_mc_sdid` | A variável `adobe_mc_sdid` O passa a Id de Dados complementares (SDID) e a Id de Experience Cloud da página padrão para a página nova. Essas IDs permitem que o A4T &quot;junte&quot; a solicitação do Target na página padrão com a solicitação do Analytics na nova página.<br>O formato esperado para transmitir a sdid no url (para aplicativos híbridos ou de um aplicativo para o site ou de um site para outro) é `ex. adobe_mc_sdid=SDID=123|MCORGID=123456789@AdobeOrg|TS=1498569322` |
| `adobe_mc_ref` | O parâmetro `adobe_mc_ref` passa o URL de referência da página padrão para a página nova. Quando usado com o AppMeasurement.js versão 2.1 (ou posterior), o Analytics usa esse valor de parâmetro como o URL de referência na nova página. |

Esses parâmetros são adicionados automaticamente aos URLs de redirecionamento ao usar as ofertas de redirecionamento integradas no VEC e no Experience Compose baseado em formulário quando o serviço de identificação do visitante está implementado na página. Se você estiver usando seu próprio código de redirecionamento personalizado no VEC ou no Compositor baseado em formulário, deve certificar-se de passar esses parâmetros com seu código personalizado.

+++

## Meus servidores da web estão removendo esses parâmetros de meus URLs. O que devo fazer?  {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

+++Answer Trabalhe com sua equipe de TI para obter esses parâmetros ( `adobe_mc_sdid` e `adobe_mc_ref`incluir na lista de permissões ).

+++

## E se eu não estiver usando o A4T com minha atividade de redirecionamento e não quiser que esses parâmetros extras sejam adicionados aos meus URLs? {#section_9E608D75FF9349FE96C65FEDD7539F45}

+++Resposta Use um redirecionamento codificado personalizado se:

* Você não está usando o A4T com sua atividade de redirecionamento
* Você implementou o serviço de ID de visitante
* Você não quer que esses parâmetros sejam adicionados automaticamente aos seus URLs

No entanto, como prática recomendada, convém manter o parâmetro `adobe_mc_ref` no URL para relatar as informações do referenciador ao [!DNL Analytics] corretamente.

+++

## Por que os parâmetros adobe_mc_ref e adobe_mc_sdid estão codificados com URL duplo na minha implementação? {#section_5EFE5F012B944C40865731EA18E7E79E}

+++Resposta Se você usa o A4T e ofertas de redirecionamento, o Target anexa a `adobe_mc_ref` e `adobe_mc_sdid` parâmetros para o URL. Esses valores já estão codificados por URL. Na maioria das vezes, tudo funciona conforme o esperado, no entanto, alguns clientes podem ter balanceadores de carga ou servidores WEB que tentam codificar os parâmetros de cadeia de caracteres de consulta mais uma vez.

Devido a essa codificação dupla, quando a API de visitante tenta decodificar o valor `adobe_mc_sdid`, ele não pode extrair o valor SDID e gera um novo SDID. Esse processo faz com que valores SDID incorretos sejam enviados para o Target e o Analytics, e você vê a divisão desigual para redirecionamentos nos relatórios do Analytics.

A Adobe recomenda que você converse com sua equipe de TI para garantir que `adobe_mc_ref` e `adobe_mc_sdid` incluir na lista de permissões são alterados para que esses valores não sejam transformados de forma alguma.

+++

## Por que o URL de referência deve ser passado para a nova página? {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

+++Resposta Suponha que um visitante clique em um link [!DNL `www.google.com`] para sua página inicial (`www.mysite.com/index.html`) em que uma atividade de redirecionamento está ao vivo e é redirecionada para uma nova página (`www.mysite.com/index2.html`).

Anteriormente, a solicitação do [!DNL Analytics] na nova página relataria um URL de referência do [!DNL `www.mysite.com/index.html`] em vez de [!DNL `www.google.com`]. Isso causava a geração de relatórios imprecisos no [!DNL Analytics] associados aos URLs de referência (relatórios de canal de marketing, por exemplo). Os relatórios perderam o fato de que você veio ao site de [!DNL `www.google.com`].

Com [!DNL at.js] versão 0.9.6 (ou posterior) e [!DNL AppMeasurement.js] 2.1 (ou posterior), a variável [!DNL Analytics] na nova página relata um URL de referência de [!DNL `www.google.com`].

+++

## Posso usar ofertas de redirecionamento personalizadas/HTML? {#section_E49F9A83A286488C8F1098A040203D7E}

+++Resposta Não, você deve usar uma oferta de redirecionamento integrada para atividades que usam [!DNL Analytics] como fonte de relatórios (A4T). Da perspectiva do [!DNL Target], as ofertas de HTML são opacas: o [!DNL Target] não pode saber que uma determinada parte do HTML contém JavaScript que instancia um redirecionamento.

+++

## ![Selo do Adobe Experience Platform Web SDK](/help/main/assets/platform.png) O faz [!DNL Adobe Experience Platform Web SDK] oferecer suporte às ofertas de redirecionamento para A4T? {#platform}

As perguntas frequentes a seguir fornecem mais informações sobre o uso do A4T e ofertas de redirecionamento com o [!DNL Platform Web SDK].

### O Analytics for Target (A4T) é compatível com as ofertas de redirecionamento?

+++Responda Sim, O A4T por meio do SDK da Web da plataforma é compatível [ofertas de redirecionamento](/help/main/c-experiences/c-manage-content/offer-redirect.md).

+++

### São as [!UICONTROL Visual Experience Composer] (VEC) e [!UICONTROL Experience Composer baseado em formulário] compatível?

+++Responda Sim, a variável [[!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) e o [[!UICONTROL Experience Composer baseado em formulário]](/help/main/c-experiences/form-experience-composer.md) são compatíveis se você usar ofertas de redirecionamento integradas.

+++

### Posso usar ofertas de redirecionamento personalizadas/HTML com o [!DNL Platform Web SDK]?

+++Resposta Não, você deve usar uma oferta de redirecionamento integrada para atividades que usam o A4T. No [!DNL Target] perspectiva, as ofertas de HTML são opacas. [!DNL Target] O não pode saber que uma determinada parte do HTML contém JavaScript que instancia um redirecionamento.

+++