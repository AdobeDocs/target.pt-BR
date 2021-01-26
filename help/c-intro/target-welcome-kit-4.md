---
keywords: welcome kit;target welcome kit;intro;introduction;getting started
description: Kit de boas-vindas da Adobe Target - Capítulo 4 - Dicas para usar o Público alvo
title: Kit de boas-vindas da Adobe Target - Capítulo 4 - Dicas para usar o Público alvo
feature: Overview
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '2880'
ht-degree: 0%

---


# Capítulo 4: Dicas para usar o Público alvo

Com base em nosso trabalho com muitos [!DNL Target] usuários, observamos maneiras de obter mais valor da solução [!DNL Target]. Resumimos essas dicas nas várias dicas que incluímos neste capítulo. Embora você possa não estar pronto para usar todas essas ideias imediatamente, segure essa lista. Quanto mais experiência você tiver com a solução e mais seu programa amadurecer, mais você verá como essas dicas podem ajudá-lo a realizar mais com [!DNL Target].

## Dica 1: Aumente a personalização aumentando o perfil do visitante com dados adicionais.

Você pode personalizar experiências com [!DNL Target] dados imediatamente. Mas personalize mais profundamente adicionando seus próprios dados na combinação. Você pode aumentar seu perfil com dados históricos de [!DNL Adobe Analytics] e dados em tempo real de [!DNL Adobe Audience Manager]. Você também pode usar os Atributos do cliente, um recurso dentro do serviço principal de Pessoas em [!DNL Adobe Experience Cloud], para trazer facilmente dados do CRM, dados de parceiros de terceiros e dados adquiridos de terceiros para [!DNL Target].

Por exemplo, você pode associar dados de compra do seu sistema de ponto de venda a um perfil de visitante. Para fazer isso, basta criar um arquivo CSV com até 200 variáveis offline e carregá-lo diretamente em [!DNL Adobe Experience Cloud] por meio de um upload de arquivo, ou usar o FTP para hospedar e agendar a atualização regular do arquivo. Assim que seus Atributos do cliente estiverem em [!DNL Adobe Experience Cloud], você poderá mapeá-los para [!DNL Experience Cloud] soluções como [!DNL Adobe Analytics] e [!DNL Target], onde eles estarão disponíveis para análise, teste e personalização.

Consulte [Atributos personalizados](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/working-with-customer-attributes.html) para obter instruções passo a passo.

**Bom saber**: Como  [!DNL Target] é uma plataforma aberta e agnóstica que funciona bem com diferentes tecnologias, você pode adicionar CRM ou dados adquiridos de várias maneiras diferentes. Isso significa que você pode escolher um método que funcione melhor para sua organização.

Consulte [Métodos para obter dados no Público alvo](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md) para obter mais informações.

## Dica 2: Personalize mais profundamente ao combinar audiências de Públicos alvos com outras audiências Adobe Experience Cloud.

Combinar audiências que vivem em diferentes [!DNL Adobe Experience Cloud] soluções pode fornecer uma compreensão muito mais ampla dos clientes, bem como a capacidade de personalizar mais profundamente. Por exemplo, embora [!DNL Target] forneça dados de audiência em tempo real, [!DNL Adobe Analytics] fornece dados históricos de audiência. Combinar os dois pode ajudá-lo a identificar quando o comportamento de um cliente é consistente e quando pode haver uma oportunidade de agir sobre um novo comportamento. Basta clicar no menu suspenso ao lado de &quot;Todos os Visitantes&quot; ao criar uma atividade. Em seguida, marque as caixas de até vinte audiências, clique em &quot;Combinar várias Audiências&quot; e clique em &quot;Salvar&quot;.

Consulte [Combinando várias audiências](/help/c-target/combining-multiple-audiences.md) para obter instruções passo a passo.

**Bom saber**:  [!DNL Adobe Audience Manager] As audiências estão disponíveis  [!DNL Target] automaticamente. Mas [!DNL Adobe Analytics] o compartilhamento de audiências requer uma configuração manual. Basta marcar a caixa &quot;Torne isso uma audiência&quot; durante o processo de criação da audiência em [!DNL Analytics]. Em seguida, de [!DNL Target], clique em &quot;Importar audiências do Experience Cloud&quot;.

## Dica 3: Exporte dados do Público alvo para uso com ferramentas de terceiros.

Com tokens de resposta, os administradores podem obter facilmente dados de [!DNL Target] e em ferramentas de terceiros. Isso pode ser útil quando você deseja adicionar seus dados aos dados coletados em uma ferramenta de pesquisa. Por exemplo, se uma pesquisa mostrar uma amostra de uma população marcou uma experiência como &quot;9&quot; e outra marcou uma experiência como &quot;4&quot;, você pode usar seus dados para ver quem viu a experiência A e quem viu a experiência B. Você também pode usar tokens de resposta para exportar [!DNL Target] dados para seu data warehouse interno. Basta clicar em &quot;Administração&quot; e depois alternar o switch ao lado do token de resposta desejado para a posição ligada. Em seguida, crie uma atividade. Os dados estão prontos para serem transferidos para o fornecedor terceirizado. Você pode verificar se [!DNL Target] está exportando os dados usando as ferramentas de depuração.

Consulte [Tokens de resposta](/help/administrating-target/response-tokens.md) para obter instruções passo a passo.

**Dica** útil: Antes que um administrador possa ativar um token de resposta associado a terceiros, um desenvolvedor precisa configurar uma parceria com essa empresa de terceiros.

Consulte [Tokens de resposta](/help/administrating-target/response-tokens.md) para obter instruções passo a passo.

**Faça isso primeiro**: Verifique se você está usando a versão 1.1 ou posterior do at.js. Se estiver usando uma versão anterior, você verá os tokens de resposta, mas o at.js não poderá usá-los.

## Dica 4: Crie audiências dessas variáveis principais para aumentar o valor de sua atividade.

Ao criar audiências para segmentação ou teste de promoções e ofertas, considere primeiro estas variáveis:

* Comportamento. Padrões de visita ao site e padrões de compra
* Referenciador. Sites de referência e campanhas
* Temporal. Tempos do dia, dias da semana e fatores sazonais
* Offline. Visita e padrões de compra em lojas físicas
* Ambiente. País da origem, sistema operacional, tipo de navegador

## Dica 5: Dê aos usuários o nível de acesso que eles precisam para fazer seu trabalho.

Facilite o trabalho com os dados de sua organização, mantendo-os seguros. [!DNL Target Premium] permite que os administradores controlem o nível de acesso dado a equipes internas e externas diferentes.

Consulte [Permissões de usuário do Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md) para obter mais informações.

**Dica** útil: Ao adicionar usuários, se o nome de um membro da equipe não tiver sido adicionado anteriormente à sua organização, como pode ser o caso de um funcionário da agência de terceiros, inserir seu endereço de email e senha acionará um convite por email para entrar na área de trabalho de uma equipe.

Usando o Target Standard? Você ainda pode [atribuir três níveis de acesso](/help/administrating-target/c-user-management/c-user-management/user-management.md) para seus usuários com funções somente leitura, editor e aprovador!

## Dica 6: Descubra como uma oferta funciona em uma jornada do cliente, testando-a em cada página da jornada.

Veja como uma oferta, como frete gratuito, funciona durante uma jornada do cliente que ocorre em várias páginas do seu site.

Consulte [atividade de várias páginas](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) para obter instruções passo a passo.

**Dica** útil: Alterar o URL após especificar um intervalo de páginas redefinirá a experiência. Isso significa que as variações especificadas não serão mais exibidas. Se precisar alterar o URL, lembre-se de redefinir a experiência.

## Dica 7: Teste uma oferta com audiências diferentes para descobrir se o audiência tem preferências diferentes.

Com as Versões de experiência, você pode executar um teste com variações para quantas audiências desejar. Por exemplo, você pode criar um anúncio de banner oferecendo frete gratuito — com variações de imagem e moeda para clientes nos Estados Unidos, Reino Unido e Estados Unidos — sem precisar executar testes para três audiências diferentes.

Consulte [Várias audiências de experiência em um Teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md) e [Versões de experiência no Adobe Target](https://helpx.adobe.com/target/how-to/experience-versions.html?playlist=/ccx/v1/collection/product/target/seg-%20ment/business-practitioners/explevel/beginner-adls/applaunch/how-to-2/collection.ccx.js?ref=helpx.adobe.com) para obter instruções passo a passo.

## Dica 8: Economize tempo replicando experiências de atividade em páginas semelhantes.

Crie uma variação em uma página da Web, como uma nova cor de botão, e aplique-a automaticamente a todas as páginas que compartilham o mesmo modelo. Você pode especificar páginas ou aplicar as variações a todas as páginas semelhantes em seu site.

Consulte [Inclua a mesma experiência em páginas semelhantes](/help/c-experiences/c-visual-experience-composer/temtest.md) para obter instruções passo a passo.

## Dica 9: Reduza a desordem na Biblioteca de Audiências criando audiências únicas.

Se você estiver direcionando um segmento que você sabe que não será público alvo novamente — por exemplo, clientes afetados por um evento meteorológico inesperado — criar uma audiência de uso único pode ajudá-lo a realizar o trabalho sem adicionar desordem na Biblioteca de Audiências. Isso facilita encontrar audiências que você usa várias vezes.

Consulte [Criar uma audiência somente atividade](/help/c-target/creating-activity-only-audience.md) para obter instruções passo a passo.

**Recurso** altamente solicitado: Nossos clientes nos pediram para tornar possível impedir que audiências de uso único sejam salvas automaticamente na Biblioteca de Audiências. Agora, eles não precisam mais excluir manualmente as audiências para manter suas bibliotecas organizadas.

## Dica 10: Execute testes simples mais rapidamente, sem colocá-los no processo padrão de controle de qualidade.

Não há nada pior do que ter uma atividade pronta para ir e depois esperar semanas para que ela conclua o processo padrão de QA. Você pode fazer o controle de qualidade de muitas atividades simplesmente passando alguns links de controle de qualidade para colegas para experimentá-los em vários navegadores. Provavelmente você desejará fazer mais testes de QA para esforços que mudam drasticamente a função do site, mas na realidade, você deve ter menos atividades e muito mais atividades mais básicas. Adicionar melhores controles de direitos para que menos pessoas possam empurrar as coisas completamente ao vivo também adiciona limites significativos e permite que você realize o que precisa sem sacrificar a velocidade e a eficiência. Outra opção é ter um recurso de TI designado para fornecer a supervisão atempada do processo de garantia de qualidade.

Consulte [Atividade QA](/help/c-activities/c-activity-qa/activity-qa.md) para obter instruções passo a passo.

## Dica 11: Execute testes em páginas de alto tráfego para que atinjam significância estatística mais rapidamente.

Muitos comerciantes lançam programas de otimização para segmentação e direcionamento de audiências sem verificar se os níveis de tráfego e as audiências representadas fornecerão resultados significativos dentro do período de tempo de teste para suas metas de otimização e conversão. Para evitar esse erro comum, responda antecipadamente a essas perguntas:

* Quantos visitantes únicos diários a página tem?
* Qual é a taxa de conversão da página?
* Quanto tempo você antecipa a necessidade de executar o teste antes de poder chamá-lo de concluído com confiança?

**Dica útil**: Use o  [ ](https://docs.adobe.com/content/target-microsite/testcalculator.html) calculador de tamanho de amostra do Público alvo para ajudar a determinar o tamanho de amostra necessário para um teste bem-sucedido.

## Dica 12: Projete testes mais simples para garantir que você possa criá-los e implementá-los.

Depois de considerar todos os aspectos de como projetar um teste, um plano pode ficar muito complexo. Com base em onde sua empresa está com os testes e na capacidade do seu grupo de projetar, codificar, executar e analisar os resultados, determine se o teste parece muito ambicioso. Em caso afirmativo, estar preparado para reduzir o seu âmbito e complexidade. É melhor start pequeno do que não executar o teste. Você não pode fornecer incentivo com impacto se nunca iniciar o teste. É importante equilibrar as aspirações da equipe com as realidades de seus recursos e habilidades.

## Dica 13: Dividir testes complexos em atividades de teste menores para torná-los viáveis.

Em vez de desenvolver um teste grande com várias variáveis e desenvolvimento complexo, desenvolva uma série menos complexa de testes menores com variáveis mínimas. Isso permite uma compreensão mais profunda do desempenho do teste com base em variáveis específicas. Também reduz possíveis questões técnicas que vêm com o desenvolvimento de projetos maiores.

![Ilustração de testes complexos de quebra](/help/c-intro/assets/break-complex-tasks.png)

## Dica 14: Maximize o impacto do teste testando mais perto do final do funil de conversão.

Testar tão próximo da página onde os visitantes clicam em Concluir compra, Enviar aplicativo ou, de outra forma, concluir uma conversão tende a fornecer os resultados mais impactantes. Os visitantes que chegam ao final do funil são mais qualificados, investem mais tempo e estão prontos para comprar, portanto, testar insights sobre suas preferências e ações pode ajudá-lo a fazer mudanças lucrativas. Como as páginas no caminho de compra são essenciais para as taxas de conversão, os testes realizados nessas páginas devem ser socializados para as principais partes interessadas antes da implantação.

![Ilustração do funil de conversão](/help/c-intro/assets/conversion-funnel.png)

## Dica 15: Atualize seus testes constantemente para fazer melhorias iterativas.

Se sua hipótese não se mostrou verdadeira, pense em maneiras de melhorar seu teste. Lembre-se de que, mesmo que nenhuma das experiências testadas tenha tido um desempenho melhor, seu experimento não foi uma perda de tempo. Um teste bem-sucedido nem sempre significa um aumento na receita ou nas conversões. Se o teste realmente suportou sua hipótese, então você está a caminho de desenvolver uma teoria geral. Mas mesmo quando você tiver um resultado claro, não pare por aí. Muitas vezes, os comerciantes cometem o erro de testar de vez em quando, baseando-se nesses resultados, sem realmente entenderem o que levou ao sucesso. Em vez disso, planeje interagir com esses resultados para descobrir por que o corredor principal estava à frente. Isso o levará a insights mais profundos que podem ser usados em campanhas futuras.

## Dica 16: Compare testes e atividades de personalização de ideias para melhorar a definição de metas.

A comparação do desempenho de conversão de diferentes audiências em diferentes testes em diferentes locais pode ajudar a focalizar e refinar a estratégia de otimização de uma empresa. Use comparações de testes para identificar quais audiências são mais valiosas para testar, quais devem receber experiências direcionadas e quais tipos de experiências têm maior probabilidade de obter uma resposta.

Por exemplo, um cliente de serviços financeiros executou uma campanha promocional para um cartão de crédito que envolveu incentivos profissionais ao evento esportivo. Através de testes multivariados parciais em seus aspectos, o cliente foi capaz de equilibrar as mensagens sobre os benefícios do cartão de crédito com incentivos esportivos para público alvo de audiências distintas de sua base de clientes. Essa abordagem permitia que a empresa capitalizasse e maximizasse a conversão durante uma janela sensível ao tempo em torno de um grande evento esportivo.

## Dica 17: Torne os testes úteis apenas iniciando-os se você sabe que pode agir com os dados.

Um teste é inútil se você não estiver claro sobre como você vai agir com base nos dados. Isso inclui conhecer sua principal métrica de sucesso, o que precisa acontecer para impulsionar um vencedor, como você acompanhará os resultados do teste e o que fará com as informações da audiência. Para um teste rápido e bem-sucedido, é vital que todos os grupos envolvidos no teste (desenvolvedores, criativos, especialistas em testes e outros) estejam cientes de seu papel antes do lançamento do teste.

## Dica 18: Antes de iniciar um teste, certifique-se de que a empresa oferece suporte para impulsionar o vencedor.

As organizações de otimização bem-sucedidas acreditam no conceito de teste e entendem que suas opiniões profissionais sobre qual experiência ganhará o teste nem sempre são verdadeiras. Eles determinam o vencedor com base em uma sólida base de dados, e estão ansiosos e dispostos a impulsionar a experiência vencedora ao vivo depois que os resultados estiverem disponíveis, mesmo que ela não esteja em conformidade com suas expectativas ou pareça contraintuitiva.

Por exemplo, um cliente de serviços de assistência médica Adobe recentemente demonstrou o valor dos testes mostrando como um banner principal que a equipe considerava um pedaço de barra afetou negativamente a conversão. Se a sua organização ainda não adotou totalmente os testes, é melhor realizar testes de escopo mais simples e menores para que as alterações nos resultados dos testes possam ser feitas de forma incremental.

## Dica 19: Avise a todos que você iniciou um teste para evitar preocupações quando o site mudar.

Um dos benefícios da configuração de suas atividades para usar parâmetros de QA é que você pode compartilhar esses links com todos em sua equipe. Você torna mais pessoas conscientes da atividade e garante que elas não presumam que o site não está funcionando corretamente quando atingem uma variante de teste.

Depois que você terminar seus testes, comunicar inicializações de campanhas, resultados de testes e, principalmente, as lições aprendidas ajudam a aumentar a conscientização e o interesse nos resultados dos testes. Compartilhar os resultados com todos na organização também evita retestar uma hipótese, educa todos sobre o que funciona e os ajuda a desafiar fundamentalmente suas próprias ideias do que funciona com base no que você encontrou. É uma boa ideia preparar um modelo que você usa cada vez para compartilhar suas descobertas e principais aprendizados.
Em seguida, considere a criação de um livro compartilhável ou uma plataforma do Microsoft PowerPoint que capture cumulativamente esses aprendizados.

## Dica 20: Aproveite a funcionalidade móvel para criar atividades móveis mais inovadoras.

As experiências do usuário do tablet e do smartphone precisam se concentrar nos controles acionados ao toque como a interação principal do visitante, em vez de cliques do mouse e controles do teclado. Tire proveito dos controles de exibição móveis, incluindo deslize com o dedo, toque, arraste, segure e aumente o zoom. Use botões simples e grandes para designar interações e navegação, como um grande carrinho de compras ou um botão de reprodução de vídeo. Se estiver criando para varejo móvel, incorpore uma visualização avançada de produto otimizada para o tipo de dispositivo. Procure sempre oportunidades para mudar o foco da experiência do usuário para visualizadores incorporados, grandes ou panorama e zoom interativos de tela inteira, rotação de 360 graus e funcionalidade de vídeo aprimorada.

## Dica 21: Ajude os visitantes móveis a encontrar o que desejam, otimizando a pesquisa móvel.

Usuários móveis têm alta intenção. A maioria deles usa pesquisa antes de fazer qualquer outra coisa em sites de comércio eletrônico, tornando a otimização da pesquisa de sites móveis crucial. Para melhorar a otimização do mecanismo de pesquisa (SEO) para dispositivos móveis, use dicas de navegação explícitas para facilitar a navegação. Além disso, implemente a sugestão automática e a correção automática em caixas de entrada de pesquisa para resolver a dificuldade de digitação móvel. Fornecer resultados de pesquisa relevantes e atraentes, otimizados para o tamanho e o local da tela.

## Dica 22: Alcance melhor audiências móveis usando a definição de metas de tempo do dia para campanhas SEM móveis.

Entenda como e quando atingir sua audiência e como gerenciar melhor seus gastos diários em publicidade, dividindo suas campanhas móveis em diferentes segmentos ao longo do dia.

Muitos profissionais de marketing cometem o erro de não alocar orçamento suficiente para capturar esse compartilhamento de voz nas horas em que o uso de dispositivos específicos é mais pesado, deixando assim muita receita e lideranças na mesa.

Por exemplo, o uso de tablets geralmente pica na hora da noite e muitos usuários navegam enquanto assistem televisão. Por outro lado, os usuários de smartphone normalmente acessam conteúdo em qualquer lugar. Os tempos de conversão máximos também variam de acordo com o setor, portanto, é importante entender quando seus clientes únicos têm maior probabilidade de agir.

## Lembre-se

Considere as seguintes ideias antes de passarmos para o próximo capítulo: &quot;Inspiração para atividades de teste e personalização.&quot;

### Quando você criar seus testes, não decore, seja intencional.

* Controle o fluxo com Caminhos de olhos intencionais focados em pontos de conversão.
* Use seu imóvel em seu proveito.
* Utilize o foco da imagem para garantir que as imagens não sejam decoração, mas estejam funcionando para você.
* Reduza a desordem, o atrito e o desfoque com a cópia simplificada.
* Certifique-se de ter Chamadas Efetivas para Ações quando precisar que o usuário execute uma ação.
* Adicione credibilidade por meio do Conteúdo gerado pelo usuário, sempre que possível.

### Simplifique seu site.

* Não &quot;faça&quot; os clientes lerem. Eles não vão.
* Facilite a digitalização.
* Use blocos de cópia com marcadores.
* Certifique-se de que sua cópia siga um processo de pensamento claro e sequencial.

### Usar Chamada efetiva para ações (CTAs)

* Coloque-se no lugar do cliente.
* Use linguagem orientada a ações.
* Considere a motivação para a conversão.
* Atender ao resultado da conversão.
* Verifique se os CTAs estão visíveis!