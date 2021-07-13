---
keywords: dados parciais; dados parciais; A4T; discrepâncias; analytics para target; órfão; conjunto de relatórios virtual; fictício; solução de problemas; não corrigido; inflacionado; não especificado
description: Saiba como minimizar os efeitos de contagens inflacionadas de visitas e visitantes ao usar o Analytics para [!DNL Target] (A4t). Saiba o que é "dados parciais" e como reduzi-los.
title: Como minimizar as contagens aumentadas de visitas e visitantes no A4T?
feature: 'Analytics for Target (A4T) '
exl-id: 308711f7-e630-4f6b-8a6d-a1f36ed7902d
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 47%

---

# Minimizar contagens inflacionadas de visitas e visitantes no A4T

Informações para ajudá-lo a minimizar os efeitos de contagens inflacionadas de Visitas e Visitantes ao usar [!DNL Adobe Analytics] como fonte de relatórios para [!DNL Adobe Target] (A4T).

>[!IMPORTANT]
>Em 14 de novembro de 2016, o Adobe Analytics mudou a forma como os dados são processados para clientes que usam a criação de relatórios do Analytics para Target (A4T). Essas alterações alinham melhor os dados do Adobe Target com o modelo de dados para Adobe Analytics. Essas alterações foram implementadas para todos os clientes utilizando A4T. Essas alterações são direcionadas especificamente a um problema em que alguns clientes notaram um contador de visitantes inflado quando há atividades do Target em execução.
>
>Essa alteração não é retroativa. Se seus relatórios históricos mostrarem contagens aumentadas e você quiser excluí-las de seus relatórios, poderá criar um conjunto de relatórios virtuais, conforme explicado abaixo.
>
>Além disso, várias bibliotecas JavaScript foram atualizadas para ajudar a minimizar as contagens infladas. O Adobe recomenda atualizar para as seguintes versões de biblioteca (ou mais recentes):
>
>* Serviço de ID de visitante da Experience Cloud: visitorAPI.js versão 2.3.0 ou superior.
>* Adobe Analytics: appMeasurement.js versão 2.1.
>* Adobe Target: at.js versão 0.9.6 ou posterior (exceto a versão 1.1.0, se estiver usando ofertas de redirecionamento com A4T).


## O que mudou? {#section_9CCF45F5D66D48EBA88F3A178B27D986}

Quando [!DNL Adobe Analytics] é usado para medir [!DNL Target] atividades (chamadas de A4T), [!DNL Analytics] coleta dados extras que não estão disponíveis quando não há atividade [!DNL Target] na página. A atividade [!DNL Target] aciona uma chamada na parte superior da página, mas [!DNL Analytics] normalmente aciona suas chamadas de coleta de dados na parte inferior da página. Na implementação do A4T até o momento, o Adobe inclui esses dados adicionais sempre que uma atividade [!DNL Target] estava ativa. A partir de agora, o Adobe inclui esses dados adicionais apenas quando as tags [!DNL Target] e [!DNL Analytics] forem acionadas.

## Por que a Adobe fez essa alteração? {#section_92380A4BD69E4B8886692DD27540C92A}

A Adobe orgulha-se de sua qualidade e precisão de dados. Quando a tag [!DNL Target] é acionada, mas a tag [!DNL Analytics] não, o Analytics registra &quot;dados parciais&quot; (às vezes chamados de &quot;ocorrências não corrigidas&quot;). Essas ocorrências não corrigidas não seriam capturadas por [!DNL Analytics] se não houvesse atividade [!DNL Target]. Embora a inclusão desses dados parciais nos relatórios [!DNL Analytics] forneça informações adicionais, ela também cria inconsistência com dados históricos de períodos em que não havia atividades [!DNL Target] em execução. Essa situação pode causar problemas para os usuários [!DNL Analytics] que estão analisando tendências ao longo do tempo. Para garantir a consistência dos dados em [!DNL Analytics], o Adobe exclui todos os dados parciais.

## O que contribui para dados parciais? {#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

O Adobe encontrou alguns clientes com altas taxas de dados parciais em [!DNL Analytics]. Altas taxas de dados parciais podem resultar de uma implementação incorreta, mas também há causas legítimas.

As causas identificadas de dados parciais incluem:

* **IDs de conjunto de relatórios desalinhadas (Implementação):** O conjunto de relatórios especificado durante a configuração da atividade não corresponde ao conjunto de relatórios na página em que o teste foi fornecido. Os dados não podem ser reconciliados em servidores [!DNL Analytics], portanto, parecem dados parciais.
* **Páginas lentas: as chamadas do** [!DNL Target]  estão no topo da página e as  [!DNL Analytics] chamadas do geralmente estão no fim da página. Se a página carregar lentamente, aumenta a probabilidade de um visitante sair da página após a chamada [!DNL Target] ser acionada, mas antes da chamada [!DNL Analytics]. Páginas lentas podem ser especialmente problemáticas em sites móveis onde as conexões são geralmente mais lentas.
* **Erros de página:** se houver erros de JavaScript ou outros cenários em que cada um dos pontos de contato não é acionado (serviço de Experience Cloud ID, Target e Analytics), resultados de dados parciais.
* **Ofertas de redirecionamento na  [!DNL Target] atividade:** para ofertas de redirecionamento em atividades que usam o A4T, sua implementação deve atender certos requisitos mínimos. Além disso, há informações importantes que você precisa saber. Para obter mais informações, consulte [Perguntas frequentes das Ofertas de redirecionamento - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58).
* **Versões antigas das bibliotecas:** Ao longo do último ano, o Adobe fez várias melhorias nas bibliotecas do JavaScript (  [!DNL appMeasurement.js],  `at.js` e  `visitorAPI.js`) para garantir que os dados sejam enviados da maneira mais eficiente possível. Para saber mais sobre os requisitos de implementação, consulte [Antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543).

## Quais são as práticas recomendadas para reduzir os dados parciais? {#section_065C38501527451C8058278054A1818D}

Revise as seguintes etapas para reduzir a coleta de dados parcial:

| Etapa | Tarefa |
| --- | --- |
| ![Etapa 1](assets/step1_icon.png) | Certifique-se de que o conjunto de relatórios selecionado em [!DNL Target] seja o mesmo que o conjunto nas páginas em que a atividade é apresentada. |
| ![Etapa 2](assets/step2_icon.png) | Certifique-se de que as bibliotecas visitorAPI.js, appMeasurement.js e at.js estão em versões compatíveis com A4T. Para saber mais sobre os requisitos de implementação, consulte [Antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md). |
| ![Etapa 3](assets/step3_icon.png) | Certifique-se de que a SDID está sendo definida em todas as chamadas [!DNL Target] e [!DNL Analytics] deixando a página e que elas são correspondentes.<br/>Use um analisador de rede ou ferramenta de depuração para garantir que o  `mboxMCSDID` parâmetro em  [!DNL Target] chamadas corresponda ao parâmetro SDID na  [!DNL Analytics] chamada. |
| ![Etapa 4](assets/step4_icon.png) | Confirme que as bibliotecas de implementação são carregadas na ordem correta nos seus sites. Para obter mais informações, consulte [Análise para implementação do Target](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## Como posso ver quantos dados parciais eu tenho? {#section_89B663E2824A4805AB934153508A0F4B}

Embora essas informações não sejam disponibilizadas diretamente no [!DNL Analytics], você pode entrar em contato com o atendimento ao cliente da Adobe para recuperar um relatório de dados parciais. Esse relatório é destinado a auxiliar na depuração.

## Como posso visualizar as tendências históricas sem dados parciais? {#section_4C9DED560FAD4428B362DDA2064897C3}

Essa alteração de processamento afeta dados somente após a data de lançamento (14 de novembro de 2016). Se você quiser ajustar as métricas históricas para correspondência, o Adobe recomenda criar um segmento para excluir dados parciais.

As informações a seguir relacionadas a essa alteração incluem instruções para ajudar você a definir o segmento e aplicá-lo a um conjunto de relatórios virtual para que este segmento sempre seja aplicado às suas visualizações do [!DNL Analytics].

Na maioria das situações, um acesso do [!DNL Target] é corrigido com um acesso do [!DNL Analytics] em cada página da Web. Essa correção acontece se houver uma SDID consistente nas chamadas do [!DNL Target] e do [!DNL Analytics] e um [!DNL Experience Cloud ID] (MCID) na chamada do [!DNL Analytics] na mesma página. [!DNL Target] O geralmente tem o MCID, mas se a chamada para o  [!DNL Target] ocorrer antes que o ID de visitante retorne, o acesso ainda será corrigido por causa do SDID. Além disso, o usuário deve permanecer na página por tempo suficiente para disparar uma chamada do [!DNL Analytics] depois do disparo de uma chamada do [!DNL Target]. Esse cenário é ideal.

**Acessos a dados parciais:** Os usuários algumas vezes não permanecem em uma página tempo suficiente para enviar uma chamada do [!DNL Analytics], mas o [!DNL Target] tem um MCID apropriado. Esse cenário resulta em hits de dados parciais (hits sem [!DNL Analytics] visualização de página). Se esses usuários voltarem ao seu site e visualizarem uma página contendo código [!DNL Analytics], serão contados apropriadamente como visitantes recorrentes. Essas ocorrências teriam sido perdidas se você tivesse somente o código [!DNL Analytics] na página. Alguns clientes não querem dados desses acessos porque eles inflam certas métricas (visitas) e deflacionam outras métricas (visualizações de página por visita, tempo por visita e assim por diante). Você também vê visitas sem visualizações de página. Entretanto, ainda há razões válidas para manter esses dados.

Para minimizar os acessos com dados parciais, você pode fazer sua página carregar mais rápido, atualizar para as versões mais recentes das bibliotecas, ou criar um [conjunto de relatórios virtuais](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) que excluem esses acessos. Para obter instruções passo a passo, consulte [Criar conjuntos de relatórios virtuais](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) no *Guia de componentes do Analytics*.

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

**Ocorrências órfãs:** em poucas situações, os usuários não permanecem na página por tempo suficiente para obter uma chamada do Analytics e o Target não recebe uma MCID apropriada. Essas ocorrências são o que o Adobe define como ocorrências &quot;órfãs&quot;. Esses acessos representam clientes que raramente retornam e inflam contadores de visitas e visitantes de maneira imprópria.

Para minimizar esses acessos &quot;órfãos&quot;, você pode criar um [conjunto de relatórios virtuais](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) que exclua esses acessos conforme explicado acima.

## O que isso significa para meus [!DNL Target] relatórios? {#section_AAD354C722BE46D4875507F0FCBA5E36}

Quando essa alteração ocorrer, você poderá observar uma diminuição em novos visitantes e visitas para testes ao vivo, pois [!DNL Adobe] não processa dados parciais recebidos. Conversões e acessos a outras [!DNL Analytics] métricas não serão alterados.
