---
keywords: kit de boas-vindas;kit de boas-vindas do target;introdução;introdução do
description: Leia dicas do nosso painel de especialistas sobre como usar o  [!DNL Target]  como parte de seus esforços de teste e personalização.
title: Onde posso encontrar dicas e truques para usar o Target?
feature: Visão geral
exl-id: 86437ad1-83ea-4670-b503-6c3c1fff0c16
source-git-commit: a30a81635d5556eb1822a67b637b37df26daeecd
workflow-type: ht
source-wordcount: '2898'
ht-degree: 100%

---

# Capítulo 4: dicas para usar o Target

Com base em nosso trabalho com muitos usuários dos [!DNL Target], observamos maneiras de obter mais valor da solução [!DNL Target]. Resumimos elas nas várias dicas incluídas neste capítulo. Embora talvez você não esteja pronto para usar todas essas ideias imediatamente, lembre-se dessa lista. Quanto mais experiência você tiver com a solução e quanto mais seu programa amadurecer, mais você verá como essas dicas podem ajudar a fazer mais com o [!DNL Target].

## Dica 1: aumente a personalização ao aumentar o perfil do visitante com dados adicionais.

Você pode personalizar experiências com dados do [!DNL Target] imediatamente. Mas personalize mais profundamente adicionando seus próprios dados na combinação. Você pode aumentar seu perfil com dados históricos do [!DNL Adobe Analytics] e dados em tempo real do [!DNL Adobe Audience Manager]. Você também pode usar Atributos do cliente, um recurso do serviço principal Pessoas na [!DNL Adobe Experience Cloud] a fim de trazer facilmente dados do CRM, dados de parceiros secundários e dados adquiridos de terceiros para [!DNL Target].

Por exemplo, você pode associar dados de compra do seu sistema de ponto de venda a um perfil do visitante. Para fazer isso, basta criar um arquivo CSV com até 200 variáveis offline e carregá-lo diretamente na [!DNL Adobe Experience Cloud] por meio de um upload de arquivo ou usar o FTP para hospedar e agendar a atualização regular do arquivo. Depois que os atributos do cliente estiverem na [!DNL Adobe Experience Cloud], você poderá mapeá-los para soluções da [!DNL Experience Cloud] como [!DNL Adobe Analytics] e [!DNL Target], onde estarão disponíveis para análise, teste e personalização.

Consulte [Atributos personalizados](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/working-with-customer-attributes.html?lang=pt-BR) para obter instruções passo a passo.

**Informações importantes**: como [!DNL Target] é uma plataforma aberta e agnóstica que funciona bem com diferentes tecnologias, você pode adicionar CRM ou dados adquiridos de várias maneiras diferentes. Isso significa que você pode escolher um método que funcione melhor para sua organização.

Consulte [Métodos para obter dados no Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md) para obter mais informações.

## Dica 2: personalize mais profundamente combinando públicos do [!DNL Target] com outros públicos da Adobe Experience Cloud.

A combinação de públicos-alvo que vivem em diferentes soluções [!DNL Adobe Experience Cloud] pode fornecer uma compreensão mais ampla dos clientes, bem como a capacidade de personalizar mais profundamente. Por exemplo, embora [!DNL Target] forneça dados de público-alvo em tempo real, o [!DNL Adobe Analytics] fornece dados históricos de público-alvo. A combinação dos dois pode ajudar você a identificar quando o comportamento de um cliente é consistente e quando pode haver uma oportunidade de agir diante de um novo comportamento. Clique no menu suspenso ao lado de &quot;Todos os visitantes&quot; ao criar uma atividade. Em seguida, marque as caixas de até vinte públicos, clique em &quot;Combinar vários públicos&quot; e, em seguida, clique em &quot;Salvar&quot;.

Consulte [Combinar vários públicos](/help/c-target/combining-multiple-audiences.md) para obter instruções passo a passo.

**Informações importantes**: os públicos-alvo do [!DNL Adobe Audience Manager] estão disponíveis no [!DNL Target] automaticamente. Mas o compartilhamento de público do [!DNL Adobe Analytics] requer uma configuração manual. Marque a caixa denominada &quot;Transformar em público-alvo da Experience Cloud&quot; durante o processo de criação do público no [!DNL Analytics]. Em seguida, no [!DNL Target], clique em &quot;Importar públicos-alvo da Experience Cloud&quot;.

## Dica 3: exporte dados do [!DNL Target] para usar com ferramentas de terceiros.

Com os tokens de resposta, os administradores podem enviar dados do [!DNL Target] para ferramentas de terceiros. Isso pode ser útil quando você quiser adicionar seus dados aos coletados em uma ferramenta de pesquisa. Por exemplo, se uma pesquisa mostrar uma amostra de uma população que pontuou uma experiência como &quot;9&quot; e outra que pontuou uma experiência como &quot;4&quot;, você poderá usar seus dados para descobrir quem viu a experiência A e quem viu a experiência B. Também é possível usar tokens de resposta para exportar dados do [!DNL Target] para seu data warehouse interno. Basta clicar em &quot;Administração&quot; e depois alternar o switch ao lado do Token de resposta desejado para a posição ligada. Em seguida, crie uma atividade. Os dados estão prontos para serem transferidos para o fornecedor terceirizado. Você pode verificar se o [!DNL Target] está exportando os dados usando as ferramentas de depuração.

Consulte [Tokens de resposta](/help/administrating-target/response-tokens.md) para obter instruções passo a passo.

**Dica útil**: antes de um administrador poder ativar um token de resposta associado a terceiros, um desenvolvedor precisa configurar uma parceria com essa empresa de terceiros.

Consulte [Tokens de resposta](/help/administrating-target/response-tokens.md) para obter instruções passo a passo.

**Faça isso primeiro**: verifique se você está usando a at.js versão 1.1 ou posterior. Se estiver usando uma versão anterior, você verá os tokens de resposta, mas a at.js não poderá usá-los.

## Dica 4: crie públicos-alvo a partir dessas variáveis-chave para aumentar o valor de sua atividade.

Ao criar públicos-alvo para direcionar ou testar promoções e ofertas, considere primeiro essas variáveis:

* Comportamento. Padrões de visita e de compra do site
* Referenciador. Sites e campanhas de referência
* Temporal. Horas do dia, dias da semana e fatores sazonais
* Offline. Padrões de visita e compra em lojas físicas
* Ambiente. País de origem, sistema operacional, tipo de navegador

## Dica 5: dê aos usuários o nível de acesso que eles precisam para fazer seu trabalho.

Facilite o trabalho com os dados de sua organização, mantendo-os seguros. O [!DNL Target Premium] permite que os administradores controlem o nível de acesso dado a diferentes equipes internas e externas.

Consulte [Permissões de usuário empresarial](/help/administrating-target/c-user-management/property-channel/property-channel.md) para obter mais informações.

**Dica útil**: ao adicionar usuários, se o nome de um membro da equipe não tiver sido adicionado anteriormente à sua organização, como pode ser o caso de um funcionário de agência de terceiros, inserir seu endereço de email e senha acionará um convite por email para ingressar no espaço de trabalho de uma equipe.

Você está utilizando o Target Standard? Você ainda pode [atribuir três níveis de acesso](/help/administrating-target/c-user-management/c-user-management/user-management.md) aos usuários com funções somente leitura, editor e aprovador.

## Dica 6: descubra como uma oferta é exibida em uma jornada do cliente, testando-a em cada página da jornada.

Veja como uma oferta, como frete grátis, é executada durante uma jornada do cliente que ocorre em várias páginas do seu site.

Consulte [Atividade multipáginas](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) para obter instruções passo a passo.

**Dica útil**: alterar o URL após especificar um intervalo de páginas redefinirá a experiência. Isso significa que as variações especificadas não serão mais exibidas. Se precisar alterar o URL, lembre-se de redefinir a experiência.

## Dica 7: teste uma oferta com públicos-alvo diferentes para descobrir se os públicos-alvo têm preferências diferentes.

Com as versões da experiência, você pode executar um teste com variações para quantos públicos desejar. Por exemplo, você pode criar um anúncio de banner oferecendo frete grátis, com variações de imagem e moeda para clientes nos EUA, Reino Unido e EUA, sem precisar executar testes para três públicos diferentes.

Consulte [Vários públicos-alvo de experiência em um Teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md) e [Versões de experiência no Adobe Target](https://helpx.adobe.com/br/target/how-to/experience-versions.html?playlist=/ccx/v1/collection/product/target/seg-%20ment/business-practitioners/explevel/beginner-adls/applaunch/how-to-2/collection.ccx.js?ref=helpx.adobe.com) para obter instruções passo a passo.

## Dica 8: economize tempo replicando as experiências da atividade em páginas semelhantes.

Crie uma variação em uma página da Web, como uma nova cor de botão, e a aplique automaticamente a todas as páginas que compartilham o mesmo modelo. Você pode especificar páginas ou aplicar as variações a todas as páginas semelhantes em seu site.

Consulte [Incluir a mesma experiência em páginas semelhantes](/help/c-experiences/c-visual-experience-composer/temtest.md) para obter instruções passo a passo.

## Dica 9: reduza a confusão na Biblioteca de público-alvo criando públicos-alvo únicos.

Se estiver direcionando um segmento que você sabe que não será direcionado novamente, por exemplo, clientes afetados por um evento climático inesperado, criar um público-alvo de uso único pode ajudar a realizar o trabalho sem desorganizar a Biblioteca de público-alvo. Isso facilita encontrar públicos-alvo que você utiliza repetidamente.

Consulte [Criar um público-alvo somente de atividade](/help/c-target/creating-activity-only-audience.md) para obter instruções passo a passo.

**Recurso altamente solicitado**: nossos clientes nos pediram para tornar possível impedir que públicos-alvo de uso único sejam salvos automaticamente na Biblioteca de público-alvo. Agora, eles não precisam mais excluir públicos manualmente para manter as bibliotecas organizadas.

## Dica 10: execute testes simples mais rapidamente, sem colocá-los no processo padrão de controle de qualidade.

Não há nada pior do que ter uma atividade prontae depois esperar semanas para que ela conclua o processo de controle de qualidade padrão. Você pode fazer o controle de qualidade da maioria das atividades ao passar alguns links de controle de qualidade para colegas para experimentá-los em vários navegadores. Você provavelmente vai desejar fazer mais testes de controle de qualidade para esforços que mudam drasticamente a função do site, mas na realidade, você deve ter menos atividades e muito mais atividades mais básicas. Adicionar controles de direitos melhores para que menos pessoas possam ativar itens comletamente também adiciona limites significativos e permite que você faça o que precisa sem sacrificar a velocidade e a eficiência. Outra opção é ter um recurso de TI designado para fornecer a supervisão oportuna do processo de controle de qualidade.

Consulte [Controle de qualidade da atividade](/help/c-activities/c-activity-qa/activity-qa.md) para obter instruções passo a passo.

## Dica 11: execute testes em páginas de alto tráfego para atingirem a significância estatística mais rapidamente.

Muitos profissionais de marketing lançam programas de otimização para segmentação e direcionamento de público sem verificar se os níveis de tráfego e os públicos-alvo representados fornecerão resultados significativos no período de teste para suas metas de otimização e conversão. Para evitar esse erro comum, responda antecipadamente a essas perguntas:

* Quantos visitantes únicos diários a página tem?
* Qual é a taxa de conversão da página?
* Por quanto tempo você antecipa a necessidade de executar o teste antes de poder considerá-lo como concluído com confiança?

**Dica útil**: use a [calculadora de tamanho da amostra](https://experienceleague.adobe.com/tools/calculator/testcalculator.html?lang=pt-BR) do Target para ajudar a determinar o tamanho da amostra necessário para um teste bem-sucedido.

## Dica 12: projete testes mais simples para garantir que você possa criá-los e implementá-los.

Depois de considerar todos os aspectos de como projetar um teste, um plano pode se tornar muito complexo. Com base no andamento dos testes da sua empresa e na capacidade do seu grupo de projetar, codificar, executar e analisar os resultados, determine se o teste parece muito ambicioso. Em caso afirmativo, prepare-se para reduzir o seu âmbito e a sua complexidade. É melhor começar pequeno do que não executar o teste. Você não pode fornecer um aumento impactante se nunca iniciar o teste. É importante equilibrar as aspirações da equipe com as realidades dos seus recursos e capacidades.

## Dica 13: divida testes complexos em atividades de teste menores para torná-las viáveis.

Em vez de desenvolver um grande teste com múltiplas variáveis e desenvolvimento complexo, desenvolva uma série menos complexa de testes menores com variáveis mínimas. Isso permite uma compreensão mais profunda do desempenho de teste com base em variáveis específicas. Também reduz possíveis questões técnicas que surgem com o desenvolvimento de projetos maiores.

![Ilustração de testes complexos de quebra](/help/c-intro/assets/break-complex-tasks.png)

## Dica 14: maximize o impacto do teste, testando mais perto do final do funil de conversão.

Testar o mais próximo da página em que os visitantes clicam em Concluir compra, Enviar solicitação ou, de outra forma, concluir uma conversão tende a fornecer os resultados mais impactantes. Os visitantes que atingem o final do funil são mais qualificados, investiram mais tempo e estão prontos para comprar, portanto, testar insights sobre suas preferências e ações pode ajudar você a fazer alterações lucrativas. Como as páginas no caminho de compra são essenciais para as taxas de conversão, os testes realizados nessas páginas devem ser socializados para os principais participantes antes de serem lançados.

![Ilustração de funil de conversão](/help/c-intro/assets/conversion-funnel.png)

## Dica 15: atualize constantemente seus testes para fazer melhorias iterativas.

Se a hipótese não for verdadeira, pense em maneiras de melhorar o teste. Lembre-se de que, mesmo que nenhuma das experiências testadas tenha um desempenho melhor, seu experimento não foi uma perda de tempo. Um teste bem-sucedido nem sempre significa um aumento na receita ou conversões. Se o teste realmente suportou sua hipótese, então você está a caminho de desenvolver uma teoria geral. Mas mesmo quando você tiver um resultado vencedor claro, não pare por aí. Frequentemente, os profissionais de marketing cometem o erro de testar uma vez e depois de basear-se nesses resultados sem realmente compreender o que resultou no sucesso. Em vez disso, planeje iterar nesses resultados para descobrir por que o primeiro estava à frente. Isso resultará em insights mais profundos que você poderá usar em campanhas futuras.

## Dica 16: compare testes e atividades de personalização de ideias para melhorar o direcionamento.

Comparar o desempenho de conversão de diferentes públicos-alvo em diferentes testes em locais diferentes pode ajudar a focalizar e refinar a estratégia de otimização de uma empresa. Use comparações de teste para identificar quais públicos-alvo são mais valiosos para testar, quais devem receber experiências direcionadas e quais tipos de experiências têm maior probabilidade de obter uma resposta.

Por exemplo, um cliente de serviços financeiros realizou uma campanha promocional para um cartão de crédito que envolveu incentivos para eventos esportivos profissionais. Por meio de multivariate testing fatorial parcial de suas páginas de aterrissagem, o cliente foi capaz de equilibrar de maneira ideal as mensagens sobre benefícios de cartões de crédito com incentivos esportivos para direcionar públicos distintos de sua base de clientes. Essa abordagem permitia que a empresa aproveitasse e maximizasse a conversão durante uma janela com detecção de hora relacionada a um evento esportivo importante.

## Dica 17: torne os testes úteis iniciando-os apenas se você souber que pode aproveitar os dados.

Um teste é inútil se você não souber como aproveitar os dados. Isso inclui conhecer sua principal métrica de sucesso, o que precisa acontecer para impulsionar um vencedor, como você seguirá os resultados dos testes e o que fará com as informações do público-alvo. Para um teste rápido e bem-sucedido, é vital que todos os grupos envolvidos no teste (desenvolvedores, criadores, especialistas em testes e outros) estejam cientes de seu papel antes do lançamento dele.

## Dica 18: antes de iniciar um teste, verifique se a empresa comportar o impulsionamento do vencedor.

As organizações de otimização bem-sucedidas acreditam no conceito de teste e entendem que suas opiniões profissionais sobre qual experiência ganhará o teste nem sempre são verdadeiras. Elas determinam o vencedor com base em uma sólida base de dados, e estão ansiosas e dispostas a impulsionar a experiência vencedora em tempo real depois que os resultados estiverem forem divulgados, mesmo que não esteja em conformidade com suas expectativas ou pareça contraintuitivo.

Por exemplo, um cliente de serviços da área de saúde da Adobe demonstrou recentemente o valor do teste, mostrando como um banner de imagem que a equipe havia considerado como perfeito afetou negativamente a conversão. Caso sua organização ainda não tenha adotado totalmente os testes, é melhor realizar testes de escopo mais simples e menores para que as alterações nos resultados dos testes possam ser feitas de forma incremental.

## Dica 19: informe a todos que você iniciou um teste para evitar preocupações quando o site mudar.

Um dos benefícios de configurar suas atividades para usar parâmetros de controle de qualidade é que você pode compartilhar esses links com todos em sua equipe. Você torna mais pessoas cientes da atividade e garante que elas não considerem que o site não está funcionando corretamente ao encontrar uma variante de teste.

Depois de concluir os testes, informar sobre inicializações de campanha, resultados de testes e especialmente as lições aprendidas ajuda a gerar conscientização e interesse pelos resultados do teste. Compartilhar os resultados com todos na organização também evita o reteste de uma hipótese, instrui todos sobre o que funciona e os ajuda a desafiar fundamentalmente suas próprias ideias sobre o que funciona com base no que foi descoberto. É uma boa ideia preparar um modelo que você usa sempre para compartilhar suas descobertas e aprendizados-chave.
Em seguida, considere criar um livro compartilhável ou uma apresentação do Microsoft PowerPoint que capture cumulativamente esses aprendizados.

## Dica 20: aproveite a funcionalidade móvel para criar atividades móveis mais inovadoras.

As experiências do usuário do tablet e do smartphone precisam se concentrar em controles orientados por toque como a principal interação do visitante em vez de cliques do mouse e controles do teclado. Aproveite os controles de exibição para dispositivos móveis, incluindo deslizar o dedo, tocar, arrastar, apertar e aplicar zoom. Use botões simples e grandes para designar interações e navegação, como um grande carrinho de compras ou um botão de reprodução de vídeo. Se estiver projetando para varejo móvel, incorpore uma visualização de produto avançada otimizada para o tipo de dispositivo. Sempre procure oportunidades para mudar o foco da experiência do usuário para visualizadores grandes incorporados ou de tela inteira, zoom e panorâmica interativos, rotação de 360 graus e funcionalidade de vídeo aprimorada.

## Dica 21: ajude os visitantes móveis a encontrar o que desejam ao otimizar a pesquisa móvel.

Usuários móveis têm alta intenção. A maioria deles usa a pesquisa antes de qualquer ação em sites de comércio eletrônico, tornando a otimização de pesquisa de site móvel essencial. Para melhorar a SEO (otimização de mecanismo de pesquisa) para dispositivos móveis, use dicas de navegação explícitas para facilitar a navegação. Além disso, implemente a sugestão automática e a correção automática nas caixas de entrada de pesquisa para solucionar a dificuldade de digitação móvel. Forneça resultados de pesquisa relevantes e atraentes, otimizados para o tamanho e o local da tela.

## Dica 22: alcance melhor os públicos-alvo móveis usando a definição de metas de hora do dia para campanhas SEM para dispositivos móveis.

Entenda como e quando alcançar seu público-alvo e como gerenciar melhor seu investimento diário em publicidade, dividindo suas campanhas móveis em diferentes segmentos ao longo do dia.

Muitos profissionais de marketing cometem o erro de não alocar orçamento suficiente para capturar essa parte de voz nas horas em que o uso de dispositivos específicos é mais pesado, deixando assim muita receita e leads livres.

Por exemplo, o uso de tablets normalmente apresenta picos no horário noturno e muitos usuários navegam enquanto assistem televisão. Por outro lado, os usuários de smartphone normalmente acessam o conteúdo em qualquer lugar. Os tempos de conversão máximos também variam de acordo com o setor, portanto, é importante entender quando seus clientes únicos têm maior probabilidade de agir.

## Lembre-se

Considere as seguintes ideias antes de passarmos para o próximo capítulo: &quot;Inspiração para atividades de teste e personalização.&quot;

### Ao criar seus testes, não exagere, seja intencional.

* Controle o fluxo com caminhos intencionais com foco em pontos de conversão.
* Certifique-se de usar seu espaço em sua vantagem.
* Aproveite o foco da imagem para garantir que as imagens não sejam decorações, mas funcionem para você.
* Reduza a desordem, o atrito e o desfoque com a cópia simplificada.
* Certifique-se de ter Chamadas para ação efetivas quando precisar que o usuário tome uma ação.
* Sempre que possível, adicione credibilidade por meio do Conteúdo gerado pelo usuário.

### Simplifique o site.

* Não &quot;faça&quot; os clientes lerem. Eles não vão.
* Facilite a digitalização.
* Use blocos de cópia com marcadores.
* Certifique-se de que a cópia siga um processo de reflexão sequencial e claro.

### Usar uma CTA (chamada efetiva para ação)

* Coloque-se no lugar do cliente.
* Use uma linguagem orientada a ações.
* Considere a motivação para a conversão.
* Aborde o resultado da conversão.
* Garanta que as CTAs sejam vistas!
