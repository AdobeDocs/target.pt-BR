---
keywords: faq;frequently asked questions;analytics for target;a4T;redirect;redirect offer;adobe-mc-sdid;adobe_mc_ref
description: Este tópico contém respostas para perguntas frequentes sobre o uso de ofertas de redirecionamento ao usar o Analytics como origem de geração de relatórios do Target (A4T).
title: Ofertas de redirecionamento - Perguntas frequentes sobre o A4T
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 94%

---


# Ofertas de redirecionamento - Perguntas frequentes sobre o A4T{#redirect-offers-a-t-faq}

Este tópico contém respostas para perguntas frequentes sobre o uso de ofertas de redirecionamento ao usar o Analytics como origem de geração de relatórios do Target (A4T).

## O Analytics for Target (A4T) é compatível com as ofertas de redirecionamento? {#section_46B8B03ED4D542C6AD875F5F61176298}

Sim, contanto que sua implementação use [!DNL at.js]. No entanto, sua implementação deve atender aos requisitos mínimos listados abaixo para usar [ofertas de redirecionamento](/help/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) em atividades que utilizam o Analytics como a fonte de relatórios.

>[!NOTE]
>
>Existe um problema conhecido que faz com que um número limitado de clientes que usam redirecionamentos com A4T vejam uma porcentagem maior de taxas de hit não unificadas. Consulte [Problemas conhecidos e problemas resolvidos](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## Quais são os requisitos mínimos necessários para usar as ofertas de redirecionamento com o A4T? {#section_FA9384C2AA9D41EDBCE263FFFD1D9B58}

Sua implementação deve atender os seguintes requisitos mínimos:

* Serviço de ID de visitante da Experience Cloud: [!DNL visitorAPI.js] versão 2.3.0 ou superior.
* Adobe Analytics: [!DNL appMeasurement.js] versão 2.1.
* Adobe Target: [!DNL at.js] versão 1.6.2 ou posteriores.

   A biblioteca [!DNL mbox.js] não é compatível com as ofertas de redirecionamento com o A4T. Sua implementação deve usar [!DNL at.js].

As três bibliotecas devem ser incluídas na página com a oferta de redirecionamento e na página para a qual o visitante será redirecionado.

## Por que algumas vezes existem discrepâncias de dados entre o A4T e o Analytics?

Algumas discrepâncias de dados são esperadas. Para obter mais informações, consulte [Variações de dados esperadas entre o Target e o Analytics ao usar ou não o A4T](/help/c-integrating-target-with-mac/a4t/understanding-expected-data-variances.md).

## Por que as visualizações de página na página original e na página de redirecionamento são contadas às vezes? {#section_B8F6CC2190B84CF08D945E797C5AF07B}

Ao usar o at.js versão 1.6.3 ou posterior, isso não é um problema. Essa condição de corridas afeta apenas os clientes que usam as versões anteriores. A equipe do Target mantém duas versões do at.js, a versão atual e a segunda versão mais recente. Atualize o at.js conforme necessário para garantir que você esteja executando uma [versão compatível](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

Se você estiver usando uma versão anterior não compatível do at.js, existe a possibilidade de ocorrer uma condição de corrida que pode fazer com que a chamada do Analytics seja acionada antes que o redirecionamento seja executado na primeira página. Isso pode fazer com que as visualizações de página na página original e na página de redirecionamento sejam todas contadas. Essa situação resulta em uma exibição de página extra na primeira página, quando o visitante nunca &quot;viu&quot; realmente essa primeira página.

Usar o compositor baseado em formulário para criar uma atividade de redirecionamento é recomendado para aumentar a velocidade do redirecionamento da página. Isto acontece devido ao local onde o código é executado na página. Além disso, é recomendável criar uma oferta de redirecionamento para cada experiência, até mesmo para a experiência padrão, na qual o redirecionamento retornaria a página original. Isso garante que, se ocorrer uma contagem incorreta, ela ocorrerá em todas as experiências, de forma que o relatório e a análise ainda sejam válidos para o teste.

Um motivo para usar ofertas de redirecionamento para todas as experiências na atividade, incluindo a experiência padrão (controle), é colocar as mesmas condições em todas as experiências. Por exemplo, se a experiência padrão não tiver uma oferta de redirecionamento, mas as outras experiências tiverem ofertas redirecionadas, a velocidade da experiência sem a oferta de redirecionamento terá uma vantagem inerente. O redirecionamento de ofertas é recomendado apenas para cenários temporários, como testes. O redirecionamento de ofertas não é recomendado para cenários permanentes, como personalização. Depois de determinar o “vencedor”, você deve remover o redirecionamento para melhorar o desempenho do carregamento da página.

Para obter mais informações sobre esse problema, consulte as informações das “Ofertas de redirecionamento” em [Problemas conhecidos](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

## Posso usar as ofertas de redirecionamento com o A4T se eu estiver usando a biblioteca JavaScript da mbox.js? {#section_D2A8B182B7254D61A8BB2BCBA0C0F64A}

A biblioteca [!DNL mbox.js] não é compatível com as ofertas de redirecionamento com o A4T. Sua implementação deve usar [!DNL at.js].

## O Visual Experience Composer (VEC) e o Experience Composer baseado em formulários são suportados? {#section_FDA26FE7909B48539DA770559E687677}

Sim, ambos os compositores são compatíveis, desde que você use as ofertas de redirecionamento integradas.

Se você usa seu próprio código personalizado para o redirecionamento, deve garantir que preenche os dois novos parâmetros associados aos URLs de redirecionamento (`adobe_mc_sdid` e `adobe_mc_ref`, explicados abaixo).

## Quais são os novos parâmetros de cadeia de caracteres de consulta adicionados aos URLs de redirecionamento? {#section_BA73E8B3CFCC4CBEB5BE3F76B2BC8682}

Os seguintes parâmetros de cadeia de caracteres de consulta estão associados a ofertas de redirecionamento:

| Parâmetro | Descrição |
|--- |--- |
| `adobe_mc_sdid` | O parâmetro `adobe_mc_sdid` passa a Id de Dados complementares (SDID) e a Id de Org da Experience Cloud da página padrão para a página nova para que o A4T &quot;identifique&quot; ao mesmo tempo a solicitação do Target na página padrão com a solicitação do Analytic na página nova. |
| `adobe_mc_ref` | O parâmetro `adobe_mc_ref` passa o URL de referência da página padrão para a página nova. Quando usado com o AppMeasurement.js versão 2.1 (ou superior), o Analytics usará o valor deste parâmetro como URL de referência na página nova. |

Esses parâmetros são adicionados automaticamente aos URLs de redirecionamento ao usar as ofertas de redirecionamento integradas no VEC e no Experience Compose baseado em formulário quando o serviço de identificação do visitante está implementado na página. Se você estiver usando seu próprio código de redirecionamento personalizado no VEC ou no Compositor baseado em formulário, deve certificar-se de passar esses parâmetros com seu código personalizado.

## Meus servidores da web estão removendo esses parâmetros de meus URLs. O que devo fazer?   {#section_0C2DDB72939F4875B6D0428B8DCB38E5}

Você precisará trabalhar com sua equipe de TI para que esses parâmetros ( `adobe_mc_sdid` e `adobe_mc_ref`) incluir na lista de permissões.

## E se eu não estiver usando o A4T com minha atividade de redirecionamento e não quiser que esses parâmetros extras sejam adicionados aos meus URLs? {#section_9E608D75FF9349FE96C65FEDD7539F45}

Se você não estiver usando o A4T com sua atividade de redirecionamento, tiver o serviço de identificação do visitante implementado e não quiser que esses parâmetros sejam adicionados automaticamente aos seus URLs, será necessário usar um redirecionamento codificado personalizado.

No entanto, como prática recomendada, convém manter o parâmetro `adobe_mc_ref` no URL para relatar as informações do referenciador ao [!DNL Analytics] corretamente.

## Por que os parâmetros adobe_mc_ref e adobe_mc_sdid estão codificados com URL duplo na minha implementação? {#section_5EFE5F012B944C40865731EA18E7E79E}

Se você usa o A4T e ofertas de redirecionamento, o Target anexa os parâmetros `adobe_mc_ref` e `adobe_mc_sdid` ao URL. Esses valores já estão codificados por URL. Na maioria das vezes, tudo funciona conforme o esperado, no entanto, alguns clientes podem ter balanceadores de carga ou servidores WEB que tentam codificar os parâmetros de cadeia de caracteres de consulta mais uma vez.

Devido a essa codificação dupla, quando a API de visitante tenta decodificar o valor `adobe_mc_sdid`, ele não pode extrair o valor SDID e gera um novo SDID. Isso faz com que valores SDID incorretos sejam enviados para o Target e para o Analytics. Você verá a divisão desigual para redirecionamentos nos relatórios do Analytics.

Recomendamos que você entre em contato com a equipe de TI para garantir que `adobe_mc_ref` e `adobe_mc_sdid` sejam incluir na lista de permissões para que esses valores não sejam transformados de nenhuma forma.

## Por que o URL de referência precisa ser passado para a nova página? {#section_91AB8B0891F6416CBF7E973DCAF54EB5}

Suponha que um visitante clique em um link em [!DNL `www.google.com`] para sua página inicial (`www.mysite.com/index.html`) no qual uma atividade de redirecionamento está ativa e é redirecionada para uma nova página (`www.mysite.com/index2.html`).

Anteriormente, a solicitação do [!DNL Analytics] na nova página relataria um URL de referência do [!DNL `www.mysite.com/index.html`] em vez de [!DNL `www.google.com`]. Isso causava a geração de relatórios imprecisos no [!DNL Analytics] associados aos URLs de referência (relatórios de canal de marketing, por exemplo). Os relatórios perderam o fato de que você veio ao site de [!DNL `www.google.com`].

Com a [!DNL at.js] versão 0.9.6 (ou posterior) e a [!DNL AppMeasurement.js] 2.1 (ou posterior), a solicitação do [!DNL Analytics] na nova página relatará um URL de referência do [!DNL `www.google.com`].

## Posso usar ofertas de redirecionamento personalizadas/HTML? {#section_E49F9A83A286488C8F1098A040203D7E}

Não, você deve usar as ofertas de redirecionamento incorporadas para atividades que usam o [!DNL Analytics] como fonte de geração de relatórios (A4T). Da perspectiva do [!DNL Target], as ofertas de HTML são opacas: o [!DNL Target] não pode saber que uma determinada parte do HTML contém JavaScript que instancia um redirecionamento.
