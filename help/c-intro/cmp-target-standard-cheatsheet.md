---
keywords: Target Standard;faq;frequently asked questions;cheat sheet;cheatsheet
description: Uma lista das perguntas mais frequentes sobre o uso dos recursos do Adobe Target, juntamente com informações e links para obter mais informações.
title: Perguntas frequentes sobre otimização e personalização do Target
feature: intro
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '2901'
ht-degree: 98%

---


# Perguntas frequentes sobre otimização e personalização do Target{#target-optimization-and-personalization-faq}

Uma lista das perguntas mais frequentes sobre o uso dos recursos do Adobe Target, juntamente com informações e links para obter mais informações.

## Informações gerais {#section_CE5713B5AAC341C9A75586C107797FA3}

**Como posso observar como outros clientes usaram o Adobe Target para obter melhores resultados?**

Veja algumas das nossas [histórias de sucesso de clientes](https://www.adobe.com/in/marketing-cloud/target/resources.html#x). Veja como clientes como você utilizaram o Target para melhorar a otimização e personalização com o intuito de alcançar metas empresariais.

Observe que alguns desses estudos de caso utilizaram capacidades do Adobe Target Premium.

**Onde posso obter mais informações sobre os recursos mais recentes do Target?**

Consulte as [Notas de versão](/help/r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A) para verificar os detalhes da versão mais recente. As informações sobre todas as [versões anteriores](/help/r-release-notes/release-notes-for-previous-releases.md) também estão disponíveis online.

**A Adobe tem uma Comunidade/Fórum onde eu possa encontrar respostas e mais informações sobre o Target?**

Visite o [ Target Community Forum](/help/cmp-resources-and-contact-information.md#concept_9C203A8AED054DFFA9A504811DB6BA42), onde ajudamos nossos clientes, mas, principalmente, gostaríamos que praticantes do Adobe Target como você ajudem uns aos outros. Afinal, o sucesso de uma comunidade e de um fórum depende da participação ativa de seus membros. Torne-se parte de uma comunidade e contribua e procure respostas para suas perguntas.

**Quais navegadores são compatíveis com o Target?**

Leia a matriz de [Navegadores suportados](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100) para obter mais detalhes. Observe que há dois aspectos: o suporte à interface do Target Standard/Premium Experience Cloud e o suporte a navegadores para usuário final em desktops/dispositivos.

## Bibliotecas de JavaScript do Target (at.js e mbox.js)   {#section_C2AC78DFDAD84981A8C84DF20893E340}

**Qual arquivo JavaScript de implementação devo usar, at.js ou mbox.js?**

at.js é a nossa maior e mais recente biblioteca de JavaScript. mbox.js é a nossa versão mais antiga. Consulte [Vantagens da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) para compreender as diferenças entre as duas bibliotecas. Todos os novos clientes devem usar at.js.

Todos os clientes mbox.js existentes devem migrar pra at.js. Saiba mais sobre as etapas envolvidas na  [Migração de mbox.js para at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA) antes de fazer a transmissão.

## Atividades {#section_CB95B3BF9934445DB98E8A7E22FC2CF6}

**Posso realizar atividades estatisticamente rigorosas para encontrar uma experiência vencedora e uma perdedora ao usar uma experiência de controle?**

Use o [Teste A/B](/help/c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977) (opção Direcionamento manual) juntamente com a [Calculadora de tamanho da amostra](/help/c-activities/t-test-ab/sample-size-determination.md#section_286EB6E671184239BB1552F0387DAEB5) para obter melhores resultados.

**Como saberei quando interromper uma atividade?**

Interromper atividades prematuramente pode resultar em conclusões incorretas. Esteja ciente das [armadilhas comuns e garanta práticas para evitá-las](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md#section_DF01A97275E44CA5859D825E0DE2F49F). Consulte também [Por quanto tempo você deve executar um teste A/B](/help/c-activities/t-test-ab/sample-size-determination.md)?

**Como faço para realizar uma atividade se a janela de tempo for pequena?**

**Posso otimizar minha meta enquanto testo?**

Use os [relatórios para determinar a experiência vencedora](/help/c-activities/automated-traffic-allocation/determine-winner.md#concept_5741A89ED7224E1285A3BC34B2CCD0F9).

**Posso realizar uma atividade com um nível de personalização como parte integrante da atividade?**

Verifique a opção [Público alvo automático](/help/c-activities/auto-target/auto-target-to-optimize.md).

**Como posso saber qual tipo de atividade é atende melhor às minhas necessidades?**

Leia o [Guia de atividades do Target](/help/c-activities/target-activities-guide.md#concept_D974B0918EB74B3B8CB07ACD32BF37A1) para entender os cenários em que cada uma das opções fornecidas pelo Adobe Target faz sentido.

Considere também as [atividades do Recommendations](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

**Como faço para descobrir quais combinações de elementos na minha página contribuem para seu sucesso e até que ponto cada elemento ajuda?**

Confira as atividades [Multivariadas fatoriais completas (MVT)](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) com a análise de contribuição do Elemento para ver se atende às suas necessidades.

Observe que o requisito de tráfego aumenta com atividades MVT.

**Posso executar uma atividade abrangendo múltiplas páginas com estruturas diferentes?**

**Posso aplicar ofertas a locais diferentes (por exemplo, o funil de check-out)?**

Experimente o recurso de [Atividade multipáginas](/help/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) que permite usar várias páginas nas experiências.

**Como posso assegurar que uma meta (Primária ou secundária) tenha sido atingida, que um usuário nunca entre na atividade novamente e, ao invés disso, veja uma atividade diferente ao prosseguir?**

Isso é fácil de conseguir usando a opção [Configurações avançadas](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_E2FE441AFB324E498793ABB025ED9974) disponível com cada meta. Você tem opções para decidir o que deve acontecer depois que o usuário atingir a meta e como você deseja que a contagem seja incrementada.

Então, neste caso, você pode escolher &quot;Incrementar contagem, liberar usuário e impedir reentrada&quot; juntamente com &quot;Conteúdo de outra atividade/atividade padrão&quot; para atingir o objetivo. Verifique também outras opções.

**Eu criei várias metas na minha atividade. Posso criar uma cadeia de metas como um funil para fins de análise e criação de relatórios?**

**Por exemplo, eu desejo considerar a Meta B quando o usuário tiver atingido a Meta A, para que eu possa monitorar os números para um funil específico.**

O Target tem uma maneira robusta de atingir isso com nosso recurso de dependência de métrica. Simplesmente [adicione dependências em outra métrica de sucesso](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B). Você tem opções como &quot;Atingido&quot; e &quot;Não atingido,&quot; juntamente com a capacidade de combinar métricas de várias formas para criar qualquer combinação que você desejar.

**Como posso ter certeza sobre como configurar uma atividade para atingir meus objetivos?**

As [metas são inseridas aqui](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC).

Você deve começar por saber o que você deseja otimizar. Isso é receita, conversão ou envolvimento? Cada uma dessas opções está disponível na seção de metas. E, para cada uma delas, você pode definir que ação um usuário tomaria no seu site para qualificar que a meta foi atingida.

Isso é possibilitado pela configuração de meta primária na etapa 3 do fluxo de trabalho orientado de três partes. Você também pode adicionar metas, que podem ajudar você a criar relatórios melhores

**Posso programar uma atividade para iniciar e encerrar em um horário fixado?**

Use o recurso [Agendamento na etapa Metas e configurações](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC) do fluxo de trabalho da atividade de três partes especificando as datas inicial e final.

Lembre-se de ativar a atividade. Apenas atividades ativas aderem à programação especificada. Depois de atingida a data de encerramento, a atividade vai para o estado Encerrada.

**Posso fazer uma alteração apenas na etapa de direcionamento e não percorrer todo o fluxo de trabalho orientado de três etapas para edição?**

Você pode fazer isso com facilidade [ao inserir diretamente a etapa desejada de sua escolha na página Visão geral da atividade](/help/c-activities/edit-activity.md#concept_BB064C0D4A194BD1A1AE7CCA1E6BB8F0) e, em seguida, sair dessa etapa usando a opção Salvar e fechar.

**Posso ficar em uma etapa específica, continuar modificando a atividade (texto da oferta ou código personalizado, por exemplo) e realizar o QA em outra guia?**

Isso também é possível. Basta [usar a opção Salvar para fazer alterações adicionais sem sair da etapa](/help/c-activities/edit-activity.md#concept_BB064C0D4A194BD1A1AE7CCA1E6BB8F0).

**Como posso visualizar e fazer QA de uma atividade que acabei de criar?**

Use nosso [poderoso recurso de Modo de QA](/help/c-activities/c-activity-qa/activity-qa.md) para executar o QA. Você pode compartilhar links com sua equipe de QA e também testar a atividade de ponta a ponta, incluindo a criação de relatórios, para assegurar que, depois que a atividade estiver sendo realizada, ela funcione como pretendido e testado.

**Como posso usar o poder de decisão do Target para receber uma experiência/oferta que possa ser usada em aplicativos de página única (SPAs) ou integrações no lado do servidor?**

Use o poder das [atividades baseadas em formulário](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) com [ofertas JSON](/help/c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D) para atender à sua meta.

**Eu configurei duas atividades. Como sei qual delas um visitante acabará visualizando?**

**Posso definir a ordem de prioridade para algumas atividades?**

Use a configuração de prioridade disponível na etapa 3 do fluxo de trabalho orientado do Target (Página Metas e configurações) para [definir a prioridade das atividades](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC).

Existem duas opções:

* Padrão, com três níveis (Baixo/Médio/Alto)
* Personalizada, com um intervalo entre 0 e 999. Para Personalizado, ative o recurso Prioridades granuladas ( Administração > Visual Experience Composer).

## Públicos-alvo {#section_FA6314777ABC46D8B198D6F388051460}

**Posso criar um segmento de públicos-alvo em uma atividade que seja específico a ela? Eu não acredito que um público-alvo como esse deva ser criado na Biblioteca de público-alvo, pois não há fator de reutilização.**

Comece usando o [recurso Audience somente para atividades](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) a fim de definir audiences locais para a atividade.

**Como posso definir usuários como alvo com base em sua localização?**

Experimente [Geo audiences](/help/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670). Leia sobre os níveis de precisão deste recurso.

**Posso definir usuários como alvo com base em alguns dos atributos na página na sessão?**

A melhor maneira seria usar mboxes e [audiences personalizados](/help/c-target/c-audiences/c-target-rules/custom-parameters.md#concept_C4C6E00D7C5A4BE9B72D471DB2E3027B) para proporcionar a experiência correta.

**Posso oferecer experiências com base nos atributos do visitante em várias visitas?**

**Posso dividir aleatoriamente o tráfego em dois compartimentos?**

Experimente o [recurso Scripts de perfil](/help/c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2). É uma maneira poderosa de personalizar experiências, embora exija que você digite o código.

**Posso iniciar uma atividade com um número menor de visitantes?**

Use os controles de alocação de porcentagem disponíveis na [Etapa 2 do fluxo de trabalho guiado em três partes do Target (página de Direcionamento)](/help/c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087) para decidir como você deseja proceder em relação à configuração da atividade.

**Eu também tenho o Adobe Analytics e desejo utilizá-lo com o Target. Quais capacidades principais eu obterei integrando as duas soluções?**

Veja os seguintes aspectos do produto:

* [Analytics for Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)
* [Atributos do cliente](/help/c-target/c-visitor-profile/working-with-customer-attributes.md#concept_16C5C434D32D4EB1AD44A71821F3DEE8)
* [Públicos-alvo](/help/c-integrating-target-with-mac/mmp.md)

## Experiências {#section_5959536B8D6A4BEA8FAA1273338F3451}

**Posso executar uma atividade em múltiplas páginas com estrutura comum?**

Confira as [Regras de modelo](/help/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781) para incluir várias páginas estruturadas semelhantes à atividade, enquanto ainda cria a experiência no único URL fornecido.

**Estou cansado de ver a mensagem &quot;Deixe seu carregador carregar os scripts&quot; quando tento carregar minha página no Visual Experience Composer (VEC). Como posso evitar isso?**

Isso ocorre porque seu site tem conteúdo misto. É um site que obtém recursos HTTP e HTTPS. Solicite que sua equipe mude totalmente para HTTPS.

Até que isso aconteça, siga as instruções em  [Ativar conteúdo misto no navegador](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/mixed-content.md#concept_46D022D50280468C9EF6D5DF6EFC911C) para permitir que seu navegador carregue conteúdo misto. Este é um recurso de segurança da maioria dos navegadores modernos.

**Posso experimentar o Visual Experience Composer (VEC) no meu site mesmo que a biblioteca at.js do Target ainda não tenha sido implementada?**

Experimente carregar a página com o [Enhanced Experience Composer](/help/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D).

**Por que o meu site não está carregando dentro do Visual Experience Composer (VEC)?**

Experimente as [informações de solução de problemas](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4) descritas em nossa página de ajuda. Entre em contato com o [Suporte da Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) se nenhuma dessas abordagens funcionar.

Também temos a [abordagem baseada em formulários](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) que pode desbloquear você.

Leia também quando e por que o [Enhanced Experience Composer](/help/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) pode ser útil. Você pode precisar entrar em contato com seu departamento de TI para   [lista de permissões Adobe. ](/help/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#concept_E284B3F704C04406B174D9050A2528A6) Servidores proxy

**Eu tenho um site responsivo. Ao criar uma atividade, como posso ter certeza de que estou levando em consideração dispositivos importantes?**

Experimente o recurso [Mobile Viewports](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5). Observe que ele funciona quando o Enhanced Experience Composer está ativado.

**Eu tenho múltiplos domínios. Um dos domínios precisa que o Enhanced Experience Composer seja ativado, enquanto outros precisam que ele seja desativado. Como posso fazer isso?**

Você sempre pode usar a opção [Enhanced Experience Composer no nível de atividade](/help/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) para substituir a configuração padrão ( Administração > Visual Experience Composer).

**Por que eu não vejo uma opção de troca de imagens?**

Entre em contato com a Adobe para [garantir que sua conta esteja configurada para o Scene7](/help/administrating-target/scene7-settings.md#task_37AD0768EFBA4E588955FE3D5DD670A5). Depois de aprovisionado, você será capaz de trocar uma imagem por outra com facilidade.

**Eu desejo testar entre duas experiências diferentes, por exemplo, desconto com valor fixo ou desconto em porcentagem, mas quero direcionar as experiências apropriadamente (mostrar texto local diferente ou moeda diferente para pessoas de países diferentes). Como posso fazer isso?**

Você pode fazer isso facilmente com o recurso [Multiple Experience Versions](/help/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md#task_0138112E283A4A5B9F8AB9AAF2FBC2FF). Observe as nuances relacionadas à entrega nesses testes

**Como posso ver quais modificações eu fiz no Visual Experience Composer (VEC)?**

Sempre mostramos as alterações no [Editor de código](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5). A guia Modificações mostra o Seletor de CSS ou mbox que você aplicou à sua oferta.

Observe que o Seletor de CSS é um seletor do Sizzle. Você pode usar esta seção para fazer pequenas modificações ou excluir certas ofertas rapidamente.

**Eu desejo proporcionar o JavaScript como parte da experiência/atividade para fazer modificações em operação para alguns elementos dinâmicos ou simplesmente enviar uma chamada para uma solução de terceiros. Como posso fazer isso?**

Uma das maneiras é usar o [Editor de código personalizado](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5). Siga em frente e coloque seu JavaScript na seção e ele será fornecido. Você tem a opção de oferecê-lo no cabeçalho ou na parte superior do corpo, dependendo das suas necessidades.

**Por que eu não posso ir além da página de login dentro do Visual Experience Composer (VEC) ou para uma página entranhada nas profundezas para a qual eu não tenha um URL específico?**

Use os recursos Escrever e Navegar para navegar até a página se sua escolha e começar a criar sua experiência.

![](assets/vec2.png)

**Como eu posso ir até a experiência escolhida por mim na etapa 2 do fluxo de trabalho orientado do Target (página de direcionamento)?**

Clique na miniatura na frente do nome da experiência na etapa 2 e você será encaminhado para a experiência de sua escolha.

![](assets/thumbnail_experiences.png)

**Eu sou um antigo usuário do Target Classic. Posso utilizar minhas mboxes para certos casos de uso?**

Use [a abordagem baseada em formulário](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) para criar atividades.

**Posso garantir que a mesma experiência seja oferecida de maneira consistente em todos os dispositivos que um usuário pode ter?**

Veja nosso [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/home.html), que permite que você vincule múltiplos dispositivos de um usuário deterministicamente e probabilisticamente através do poder da cooperação.

Se você estiver em um Co-op, uma sinalização simples na página de Metas e Configurações ativa o recurso. A criação de relatórios também muda para refletir pessoas ao invés de visitantes. Fale com o seu contato na Adobe para saber mais sobre este recurso, pois ele não estará disponível em todas as regiões.

**Por que eu não estou vendo a oferta/experiência desejada e estou vendo outra atividade ao invés disso?**

Use nosso [depurador](/help/c-activities/c-troubleshooting-activities/content-trouble.md#concept_D2548B486C984B1E97ED7A72075B8EEA) e verifique se [há conflito de atividade](/help/c-experiences/c-visual-experience-composer/activity-collisions.md#concept_0BC6B929592744DFA7DA01FF4F91052E).

## Ofertas {#section_A547B1EAD0B34FD38D3B87AAF62E3963}

**Eu não quero experimentar mudanças menores. Ao invés disso, quero testar uma página nova e completamente diferente.**

**Eu desejo direcionar usuários para uma página de chegada, por exemplo, um novo lançamento.**

**Como posso fazer isso?**

Temos [o recurso de URL de redirecionamento](/help/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) que permite redirecionar os usuários para a página de escolha (com ou sem os parâmetros de consulta atuais).

**Por que a entrega do conteúdo não está acontecendo no meu processo de QA?**

É possível que seu site possa ter IDs dinâmicos, IDs duplicados ou classes dinâmicas em elementos. Você pode precisar avaliar as opções de preferência do site no nível da conta (ou no nível da atividade se o problema for específico a um domínio ou página). Consulte [Seletores de CSS](/help/administrating-target/visual-experience-composer-set-up.md#css).

**Por que eu não estou vendo a oferta/experiência desejada e estou vendo outra atividade ao invés disso?**

Use nosso [depurador](/help/c-activities/c-troubleshooting-activities/content-trouble.md#concept_D2548B486C984B1E97ED7A72075B8EEA) e verifique se [há conflito de atividade](/help/c-experiences/c-visual-experience-composer/activity-collisions.md#concept_0BC6B929592744DFA7DA01FF4F91052E).

**Posso usar o poder de decisão do Target para receber uma experiência/oferta que possa ser usada em aplicativos de página única (SPAs) ou integrações no lado do servidor?**

Use o poder das [atividades baseadas em formulário](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) com [ofertas JSON](/help/c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D) para atender à sua meta.

## Relatórios (Incluído Analytics for Target - A4T) {#section_8AECC69BEEB7422E894E7EC44A50BA0A}

**Eu também tenho o Adobe Analytics e desejo utilizá-lo com o Target. Quais capacidades principais eu obterei integrando as duas soluções?**

Veja os seguintes aspectos do produto:

* [Analytics for Público alvo (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)

* [Atributos do cliente](/help/c-target/c-visitor-profile/working-with-customer-attributes.md#concept_16C5C434D32D4EB1AD44A71821F3DEE8)

* [Públicos-alvo](/help/c-integrating-target-with-mac/mmp.md)


**Posso destrinchar a criação de relatórios sobre múltiplos segmentos de usuários?**

É aqui que entra o recurso [Públicos-alvo para relatórios](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_13119392051044FBA6387D9B3B1C43CF), disponível na página Metas e configurações da etapa 3 do fluxo de trabalho orientado.

Você tem a opção de adicionar 50 desses segmentos e também o ponto de aplicação (Entrada de atividade ou uma métrica específica) para ter uma forma poderosa de destrinchar os dados.

Observe que o Target coleta os dados relacionados a isso a partir do momento que você adiciona esses públicos-alvo, então se você deixar de adicionar segmentos antes de executar o teste, você está sem sorte.

**Eu não consigo definir audiências antes de executar a atividade. Eu acho que este aspecto de públicos-alvo em atividades do Target é restringente.**

**O que posso fazer para tornar este processo mais fácil?**

É aqui que o [Analytics for Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) é útil. Se você tem o Adobe Analytics, simplesmente escolha a fonte como Analytics, que elimina essa restrição. Agora você pode realizar análise em qualquer público-alvo e você não precisa definir os públicos-alvo de criação de relatórios antecipadamente.

**Posso realizar cálculos de criação de relatórios off-line?**

Use as [opções Exporte relatórios para CSV e Detalhes de Pedido de Download para CSV](/help/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) na página Relatórios para baixar os dados de criação de relatórios desejados.

**Posso mudar a experiência de controle para avaliação de relatórios ou mudar a metodologia de contagem de Visitantes para Visitas?**

Faça essas alterações usando a  [engrenagem de Configurações na página de relatórios](/help/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA). Leia mais sobre essas configurações para compreender como os cálculos variam.

**Como eu devo interpretar os relatórios?**

Nós tentamos tornar os relatórios os mais intuitivos possível com recursos como  [Barras de intervalo de confiança, limites de incentivo, significância/confiança e múltiplas seleções métricas, visualizações em tabela e gráfico, médias de execução e mais](/help/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) para possibilitar análise de relatórios poderosa, mas facilitada. Obviamente, você pode pesquisar Analytics se você estiver usando  [Atividades do Analytics for Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) para mais análise sobre públicos-alvo.

## Tokens de resposta {#section_C2A7118B4B62482A9D630C2212112A3D}

**Eu posso realizar uma integração com um sistema de terceiros, como Google Analytics ou ClickTale, para transmitir as informações de atividade entregues a um usuário final para análise?**

Temos uma solução para isso também com nosso [recurso de Tokens de resposta](/help/administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4).

## Solução de problemas {#section_6B8B4DC62AE34066A8C55915E9EC6C19}

**Como eu posso saber o status de disponibilidade do Adobe Target?**

Use a página [Status do sistema da Adobe](/help/r-release-notes/system-status-updates.md#concept_5CBDF506BEFA40E483CC7DE0DA915EAD) para visualizar o status dos produtos da Adobe e das soluções da Experience Cloud, incluindo o Target. Esta página ajuda a determinar se os problemas encontrados foram causados por atualizações do sistema ou pela manutenção de rotina.

**Você tem um guia de solução de problemas?**

Lamentamos saber que você está tendo problemas. Veja [Solução de problemas do Target](/help/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) para obter links para vários tópicos de solução de problemas.

## Aplicativos móveis do Target {#section_07BA89F2C38747158ECD5B153274AEAF}

**Nós temos um SKU móvel. Posso criar atividades móveis?**

Para otimização e personalização em dispositivos móveis, você precisa usar as [atividades baseadas em formulários](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) junto com o [Adobe SDK](/help/c-target-mobile-app/mobile-enable-target-in-sdk.md#task_FCA99AD0785A44E995468776AE76FE91). Confira mais detalhes sobre o [Target para aplicativos móveis](/help/c-target-mobile-app/target-mobile-app.md#concept_80126FF457724DE788CE37264A047559).

## APIs do Target {#section_714E85EFF6E3400389EF2E40D538E1DA}

**Onde eu posso aprender mais sobre as APIs do Target?**

Temos uma documentação completa sobre APIs. Consulte a documentação de [Delivery APIs, NodeJS SDK e Recommendations APIs](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md).