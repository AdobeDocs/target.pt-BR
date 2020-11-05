---
keywords: partial data;partial-data;A4T;discrepancies;analytics for target;orphaned;virtual report suite;phantom;troubleshooting;unstitched;inflated;unspecified
description: Informações para ajudá-lo a minimizar os efeitos de contagens inflacionadas de Visitas e Visitantes ao usar o Analytics como origem de geração de relatórios.
title: Minimizar contagens inflacionadas de visitas e visitantes no A4T
feature: a4t troubleshooting
topic: Standard
uuid: 1d5f242a-634f-47f7-ad23-b62019359734
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 96%

---


# Minimizar contagens inflacionadas de visitas e visitantes no A4T{#minimizing-inflated-visit-and-visitor-counts-in-a-t}

Informações para ajudá-lo a minimizar os efeitos de contagens inflacionadas de Visitas e Visitantes ao usar o Analytics como origem de geração de relatórios.

>[!IMPORTANT]
>Em 14 de novembro de 2016, o Adobe Analytics mudou a forma como os dados são processados para clientes que usam a criação de relatórios do Analytics para Target (A4T). Essas alterações alinham melhor os dados do Adobe Target com o modelo de dados para Adobe Analytics. Essas alterações foram implementadas para todos os clientes utilizando A4T. Essas alterações são direcionadas especificamente a um problema em que alguns clientes notaram um contador de visitantes inflado quando há atividades do Target em execução.
>
>Observe que essa alteração não é retroativa. Se seus relatórios históricos mostrarem contagens aumentadas e você quiser excluí-las de seus relatórios, poderá criar um conjunto de relatórios virtuais, conforme explicado abaixo.
>
>Além disso, várias bibliotecas de JavaScript foram atualizadas para ajudar a minimizar as contagens infladas. Recomendamos que você faça upgrade das seguintes versões de biblioteca (ou mais recentes):
>
>* Serviço de ID de visitante da Experience Cloud: visitorAPI.js versão 2.3.0 ou superior.
>* Adobe Analytics: appMeasurement.js versão 2.1.
>* Adobe Target: at.js versão 0.9.6 ou posterior (exceto a versão 1.1.0, se estiver usando ofertas de redirecionamento com A4T).

>
>  
A biblioteca mbox.js não é compatível com as ofertas de redirecionamento com o A4T. Sua implementação deve usar at.js.

## O que mudou? {#section_9CCF45F5D66D48EBA88F3A178B27D986}

Quando o [!DNL Adobe Analytics] é usado para medir as atividades do [!DNL Target] (chamado A4T), o [!DNL Analytics] coleta dados adicionais que não estão disponíveis quando não há nenhuma atividade do [!DNL Target] na página. Isso ocorre porque a atividade do [!DNL Target] aciona uma chamada na parte superior da página, mas o [!DNL Analytics] geralmente aciona suas chamadas de coleta de dados na parte inferior da página. Na implementação do A4T até o momento, incluímos estes dados adicionais sempre que uma atividade do [!DNL Target] estava ativa. A partir de agora, incluiremos esses dados adicionais apenas quando as tags do [!DNL Target] e do [!DNL Analytics] forem acionadas.

## Por que a Adobe fez essa alteração? {#section_92380A4BD69E4B8886692DD27540C92A}

A Adobe orgulha-se de sua qualidade e precisão de dados. Quando a tag do [!DNL Target] é disparada, mas a tag do [!DNL Analytics] não, estamos registrando &quot;dados parciais&quot; (algumas vezes chamados de &quot;acessos não corrigidos&quot;), que não seriam capturados pelo [!DNL Analytics] se não houvesse atividade do [!DNL Target]. Embora a inclusão desses dados parciais nos relatórios do [!DNL Analytics] realmente forneça informações adicionais, ela também cria inconsistência com dados históricos de períodos em que não havia atividades do [!DNL Target] em execução. Isso pode causar problemas para os usuários do [!DNL Analytics] que estão analisando tendências ao longo do tempo. Com o intuito de assegurar a consistência dos dados no [!DNL Analytics], nós excluiremos todos os dados parciais.

## O que contribui para dados parciais? {#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

Nós observamos alguns clientes com taxas muito altas de dados parciais no [!DNL Analytics]. Isso pode ser causado por implementação inapropriada, mas também há causas legítimas.

As causas identificadas de dados parciais incluem:

* **IDs de conjunto de relatórios desalinhadas (Implementação):** O conjunto de relatórios especificado durante a configuração da atividade não corresponde ao conjunto de relatórios na página em que o teste foi fornecido. Isso se parece com dados parciais porque não foi possível reconciliar os dados nos servidores do [!DNL Analytics].
* **Páginas lentas:** Como as chamadas do [!DNL Target] estão no topo da página e as chamadas do [!DNL Analytics] geralmente estão na parte inferior, se a página carregar lentamente, aumenta a probabilidade de um visitante sair da página após o acionamento da chamada do [!DNL Target], mas antes da chamada do [!DNL Analytics]. Isso pode ser especialmente problemático em sites web para dispositivos móveis onde as conexões sejam geralmente mais lentas.
* **Erros de página:** Se houver erros de JavaScript ou outros cenários em que cada um dos pontos de contato não é acionado (Serviços de Experience Cloud ID, Target e Analytics), o resultado será dados parciais.
* **Ofertas de redirecionamento na [!DNL Target] atividade:** para ofertas de redirecionamento em atividades usando o A4T, sua implementação deve atender a certos requisitos mínimos. Além disso, há informações importantes que você precisa saber. Para obter mais informações, consulte [Ofertas de redirecionamento - Perguntas frequentes do A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58).
* **Versões antigas das bibliotecas:** No ano passado, a Adobe fez diversas melhorias nas bibliotecas do JavaScript ([!DNL appMeasurement.js], `at.js/mbox.js`e `visitorAPI.js`) para garantir que os dados sejam enviados da maneira mais eficiente possível. Para saber mais sobre os requisitos de implementação, consulte [Antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543).

## Quais são as práticas recomendadas para reduzir os dados parciais? {#section_065C38501527451C8058278054A1818D}

Analise as seguintes etapas, em ordem, para reduzir a coleta de dados parcial:

| Etapa | Tarefa |
| --- | --- |
| ![Etapa 1](assets/step1_icon.png) | Certifique-se de que o conjunto de relatórios selecionado no [!DNL Target] seja o mesmo que o conjunto na(s) página(s) onde a atividade será apresentada. |
| ![Etapa 2](assets/step2_icon.png) | Certifique-se de que as bibliotecas visitorAPI.js, appMeasurement.js, at.js / mbox.js estão em versões compatíveis com A4T. Para saber mais sobre os requisitos de implementação, consulte [Antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md). |
| ![Etapa 3](assets/step3_icon.png) | Certifique-se de que o SDID está sendo configurado em todas as chamadas do [!DNL Target] e do [!DNL Analytics] deixando a página e que elas são correspondentes.<br/>Faça isso usando um analisador de rede ou ferramenta de depuração para assegurar que o parâmetro `mboxMCSDID` na(s) chamada(s) do [!DNL Target] corresponde ao parâmetro SDID na chamada do [!DNL Analytics]. |
| ![Etapa 4](assets/step4_icon.png) | Confirme que as bibliotecas de implementação são carregadas na ordem correta nos seus sites. Para obter mais informações, consulte [Análise para implementação do Target](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## Como posso ver quantos dados parciais eu tenho? {#section_89B663E2824A4805AB934153508A0F4B}

Embora essas informações não sejam disponibilizadas diretamente no [!DNL Analytics], você pode entrar em contato com o atendimento ao cliente da Adobe para recuperar um relatório de dados parciais. Esse relatório é destinado a auxiliar na depuração.

## Como posso visualizar as tendências históricas sem dados parciais? {#section_4C9DED560FAD4428B362DDA2064897C3}

Como essa alteração de processamento afeta dados somente depois da data de lançamento (14 de novembro de 2016), se você desejar ajustar sua métrica histórica para correspondência, recomendamos que você crie um segmento para excluir dados parciais.

As informações a seguir relacionadas a essa alteração incluem instruções para ajudar você a definir o segmento e aplicá-lo a um conjunto de relatórios virtual para que este segmento sempre seja aplicado às suas visualizações do [!DNL Analytics].

Na maioria das situações, um acesso do [!DNL Target] é corrigido com um acesso do [!DNL Analytics] em cada página da Web. Essa correção acontece se houver uma SDID consistente nas chamadas do [!DNL Target] e do [!DNL Analytics] e um [!DNL Experience Cloud ID] (MCID) na chamada do [!DNL Analytics] na mesma página. O [!DNL Target] geralmente tem o MCID, mas se a chamada para o [!DNL Target] ocorrer antes que o ID de visitante retorne, o acesso ainda será corrigido por causa do SDID. Além disso, o usuário deve permanecer na página por tempo suficiente para disparar uma chamada do [!DNL Analytics] depois do disparo de uma chamada do [!DNL Target]. Este é o cenário ideal.

**Acessos a dados parciais:** Os usuários algumas vezes não permanecem em uma página tempo suficiente para enviar uma chamada do [!DNL Analytics], mas o [!DNL Target] tem um MCID apropriado. Isso resulta em acessos a dados parciais (acessos sem visualização de página do [!DNL Analytics]). Se esses usuários voltarem ao seu site e visualizarem uma página contendo código do [!DNL Analytics], serão contados apropriadamente como visitantes recorrentes. Esses são acessos que teriam sido perdidos se você só tivesse código do [!DNL Analytics] na página. Alguns clientes não querem dados desses acessos porque eles inflam certas métricas (visitas) e deflacionam outras métricas (visualizações de página por visita, tempo por visita e assim por diante). Você também verá visitas sem quaisquer visualizações de página. Entretanto, ainda há razões válidas para manter esses dados.

Para minimizar os acessos com dados parciais, você pode fazer sua página carregar mais rápido, atualizar para as versões mais recentes das bibliotecas, ou criar um [conjunto de relatórios virtuais](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) que excluem esses acessos. For step-by-step instructions, see [Create virtual report suites](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) in the *Analytics Components Guide*.

A ilustração a seguir mostra a definição de segmento para o conjunto de relatórios virtuais:

![](assets/ts_a4t.png)

Ao criar o conjunto de relatórios virtuais, especifique a configuração a seguir para definição de segmento (conforme mostrado na ilustração acima):

* **Exibir acesso:**
* Analytics for Target: existe
* E
* Visualizações de página: não existe
* E
* Instâncias de link personalizado: não existe
* E
* Instâncias de link de download: não existe
* E
* Instâncias de link de saída: não existe

**Ocorrências órfãs:** em poucas situações, os usuários não permanecem na página por tempo suficiente para obter uma chamada do Analytics e o Target não recebe uma MCID apropriada. Esses são os que definimos como acessos &quot;órfãos&quot;. Esses acessos representam clientes que raramente retornam e inflam contadores de visitas e visitantes de maneira imprópria.

Para minimizar esses acessos &quot;órfãos&quot;, você pode criar um [conjunto de relatórios virtuais](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) que exclua esses acessos conforme explicado acima.

## O que isso significa para meus [!DNL Target] relatórios? {#section_AAD354C722BE46D4875507F0FCBA5E36}

Quando essa alteração ocorrer, você poderá observar uma redução em novos visitantes e visitas para testes ao vivo, pois [!DNL Adobe] não processará os dados parciais de entrada. Conversões e acessos a outras [!DNL Analytics] métricas não serão alterados.
