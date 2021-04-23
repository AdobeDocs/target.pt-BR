---
keywords: kit de boas-vindas, kit de boas-vindas do target, introdução, introdução, introdução
description: Leia dicas do nosso painel de especialistas sobre como usar o Adobe [!DNL Target] como parte de seus esforços de teste e personalização.
title: Onde posso encontrar dicas e truques para usar o Target?
feature: Visão geral
exl-id: 86437ad1-83ea-4670-b503-6c3c1fff0c16
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2898'
ht-degree: 0%

---

# Capítulo 4: Dicas para usar o Target

Com base em nosso trabalho com muitos [!DNL Target] usuários, observamos maneiras de obter mais valor de sua [!DNL Target] solução. Resumimos essas dicas nas muitas dicas que incluímos neste capítulo. Embora talvez você não esteja pronto para usar todas essas ideias imediatamente, mantenha essa lista. Quanto mais experiência você tiver com a solução e quanto mais seu programa amadurecer, mais você verá como essas dicas podem ajudá-lo a fazer mais com [!DNL Target].

## Dica 1: Aumente a personalização ao aumentar o perfil do visitante com dados adicionais.

Você pode personalizar experiências com dados [!DNL Target] imediatamente. Mas personalize mais profundamente adicionando seus próprios dados na combinação. Você pode aumentar seu perfil com dados históricos de [!DNL Adobe Analytics] e dados em tempo real de [!DNL Adobe Audience Manager]. Você também pode usar Atributos do cliente, um recurso do serviço principal Pessoas em [!DNL Adobe Experience Cloud], para trazer facilmente dados do CRM, dados de parceiros secundários e dados adquiridos de terceiros para [!DNL Target].

Por exemplo, você pode associar dados de compra do seu sistema de ponto de venda a um perfil de visitante. Para fazer isso, basta criar um arquivo CSV com até 200 variáveis offline e carregá-lo diretamente em [!DNL Adobe Experience Cloud] por meio de um upload de arquivo ou usar o FTP para hospedar e agendar a atualização regular do arquivo. Depois que os atributos do cliente estiverem em [!DNL Adobe Experience Cloud], você poderá mapeá-los para [!DNL Experience Cloud] soluções como [!DNL Adobe Analytics] e [!DNL Target], onde estarão disponíveis para análise, teste e personalização.

Consulte [Atributos personalizados](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/working-with-customer-attributes.html) para obter instruções passo a passo.

**Bom saber**: Como  [!DNL Target] é uma plataforma aberta e agnóstica que funciona bem com diferentes tecnologias, você pode adicionar CRM ou dados adquiridos de várias maneiras diferentes. Isso significa que você pode escolher um método que funcione melhor para sua organização.

Consulte [Métodos para obter dados no Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md) para obter mais informações.

## Dica 2: Personalize mais profundamente ao mesclar públicos [!DNL Target] com outros públicos do Adobe Experience Cloud.

A combinação de públicos-alvo que vivem em diferentes soluções [!DNL Adobe Experience Cloud] pode fornecer uma compreensão mais ampla dos clientes, bem como a capacidade de personalizar mais profundamente. Por exemplo, embora [!DNL Target] forneça dados de público-alvo em tempo real, [!DNL Adobe Analytics] fornece dados históricos de público-alvo. Combinar os dois pode ajudar você a identificar quando o comportamento de um cliente é consistente e quando pode haver uma oportunidade de agir em um novo comportamento. Basta clicar no menu suspenso ao lado de &quot;Todos os visitantes&quot; ao criar uma atividade. Em seguida, marque as caixas de até vinte públicos, clique em &quot;Combinar vários públicos&quot; e em &quot;Salvar&quot;.

Consulte [Combinando vários públicos](/help/c-target/combining-multiple-audiences.md) para obter instruções passo a passo.

**Bom saber**:  [!DNL Adobe Audience Manager] Os públicos-alvo do estão disponíveis  [!DNL Target] automaticamente no . Mas [!DNL Adobe Analytics] o compartilhamento de público requer uma configuração manual. Basta marcar a caixa denominada &quot;Transformar em Experience Cloud audience&quot; durante o processo de criação do público em [!DNL Analytics]. Em seguida, de [!DNL Target], clique em &quot;Importar públicos-alvo do Experience Cloud&quot;.

## Dica 3: Exporte dados de [!DNL Target] para usar com ferramentas de terceiros.

Com os tokens de resposta, os administradores podem obter facilmente os dados do [!DNL Target] e em ferramentas de terceiros. Isso pode ser útil quando você quiser adicionar seus dados aos dados coletados em uma ferramenta de pesquisa. Por exemplo, se uma pesquisa mostrar uma amostra de uma população pontuou uma experiência como &quot;9&quot; e outra pontuou uma experiência como &quot;4&quot;, você poderá usar seus dados para ver quem viu a experiência A e quem viu a experiência B. Também é possível usar tokens de resposta para exportar [!DNL Target] dados para seu data warehouse interno. Basta clicar em &quot;Administração&quot; e depois alternar o switch ao lado do Token de resposta desejado para a posição ligada. Em seguida, crie uma atividade . Os dados estão prontos para serem transferidos para o fornecedor terceirizado. Você pode verificar se [!DNL Target] está exportando os dados usando as ferramentas de depuração.

Consulte [Tokens de resposta](/help/administrating-target/response-tokens.md) para obter instruções passo a passo.

**Dica** útil: Antes de um administrador poder ativar um token de resposta associado a terceiros, um desenvolvedor precisa configurar uma parceria com essa empresa de terceiros.

Consulte [Tokens de resposta](/help/administrating-target/response-tokens.md) para obter instruções passo a passo.

**Faça isso primeiro**: Verifique se você está usando a at.js versão 1.1 ou posterior. Se estiver usando uma versão anterior, você verá os tokens de resposta, mas a at.js não poderá usá-los.

## Dica 4: Crie públicos-alvo a partir dessas variáveis-chave para aumentar o valor de sua atividade.

Ao criar públicos-alvo para direcionar ou testar promoções e ofertas, considere primeiro essas variáveis:

* Comportamento. Padrões de visita e de compra do site
* Referenciador. Sites e campanhas de referência
* Temporal. Tempos do dia, dias da semana e fatores sazonais
* Offline. Padrões de visita e compra em lojas físicas
* Ambiente. País de origem, sistema operacional, tipo de navegador

## Dica 5: Dê aos usuários o nível de acesso que eles precisam para fazer seu trabalho.

Facilite o trabalho com os dados de sua organização, mantendo-os seguros. [!DNL Target Premium] O permite que os administradores controlem o nível de acesso dado a diferentes equipes internas e externas.

Consulte [Permissões de usuário empresarial](/help/administrating-target/c-user-management/property-channel/property-channel.md) para obter mais informações.

**Dica** útil: Ao adicionar usuários, se o nome de um membro da equipe não tiver sido adicionado anteriormente à sua organização, como pode ser o caso de um funcionário de agência de terceiros, inserir seu endereço de email e senha acionará um convite por email para ingressar na área de trabalho de uma equipe.

Usando o Target Standard? Você ainda pode [atribuir três níveis de acesso](/help/administrating-target/c-user-management/c-user-management/user-management.md) para seus usuários com funções somente leitura, editor e aprovador!

## Dica 6: Descubra como uma oferta é exibida em uma jornada do cliente, testando-a em cada página da jornada.

Veja como uma oferta, como frete grátis, é executada durante uma jornada do cliente que ocorre em várias páginas do seu site.

Consulte [Atividade multipáginas](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) para obter instruções passo a passo.

**Dica** útil: Alterar o URL após especificar um intervalo de páginas redefinirá a experiência. Isso significa que as variações especificadas não serão mais exibidas. Se precisar alterar o URL, lembre-se de redefinir a experiência.

## Dica 7: Teste uma oferta com públicos-alvo diferentes para descobrir se os públicos-alvo têm preferências diferentes.

Com as versões da experiência, você pode executar um teste com variações para quantos públicos desejar. Por exemplo, você pode criar um anúncio de banner oferecendo frete grátis — com variações de imagem e moeda para clientes nos EUA, Reino Unido e EUA — sem precisar executar testes para três públicos diferentes.

Consulte para [Vários públicos-alvo de experiência em um Teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md) e [Versões de experiência no Adobe Target](https://helpx.adobe.com/target/how-to/experience-versions.html?playlist=/ccx/v1/collection/product/target/seg-%20ment/business-practitioners/explevel/beginner-adls/applaunch/how-to-2/collection.ccx.js?ref=helpx.adobe.com) para obter instruções passo a passo.

## Dica 8: Economize tempo replicando as experiências da atividade em páginas semelhantes.

Crie uma variação em uma página da Web, como uma nova cor de botão, e a aplique automaticamente a todas as páginas que compartilham o mesmo modelo. Você pode especificar páginas ou aplicar as variações a todas as páginas semelhantes em seu site.

Consulte [Incluir a mesma experiência em páginas semelhantes](/help/c-experiences/c-visual-experience-composer/temtest.md) para obter instruções passo a passo.

## Dica 9: Reduza a confusão na Biblioteca de público-alvo criando públicos-alvo únicos.

Se você estiver direcionando um segmento que você sabe que não será direcionado novamente, por exemplo, clientes afetados por um evento climático inesperado, criar um público-alvo de uso único pode ajudá-lo a realizar o trabalho sem desorganizar a Biblioteca de público-alvo. Isso facilita encontrar públicos-alvo que você usa repetidamente.

Consulte [Criar um público-alvo somente de atividade](/help/c-target/creating-activity-only-audience.md) para obter instruções passo a passo.

**Recurso** altamente solicitado: Nossos clientes nos pediram para tornar possível impedir que públicos-alvo de uso único sejam salvos automaticamente na Biblioteca de público-alvo. Agora, eles não precisam mais excluir públicos manualmente para manter suas bibliotecas organizadas.

## Dica 10: Execute testes simples mais rapidamente, sem colocá-los no processo padrão de controle de qualidade.

Não há nada pior do que ter uma atividade pronta para ir e depois esperar semanas para que ela conclua o processo de QA padrão. Você pode fazer o controle de qualidade da maioria das atividades, basta passar alguns links de controle de qualidade para colegas para experimentá-los em vários navegadores. Você provavelmente desejará fazer mais testes de controle de qualidade para esforços que mudam drasticamente a função do site, mas na realidade, você deve ter menos atividades e muito mais atividades mais básicas. Adicionar melhores controles de direitos para que menos pessoas possam jogar as coisas ao vivo também adiciona limites significativos e permite que você realize o que precisa sem sacrificar a velocidade e a eficiência. Outra opção é ter um recurso de TI designado para fornecer a supervisão oportuna do processo de QA.

Consulte [Controle de qualidade da atividade](/help/c-activities/c-activity-qa/activity-qa.md) para obter instruções passo a passo.

## Dica 11: Execute testes em páginas de alto tráfego para atingirem a significância estatística mais rapidamente.

Muitos profissionais de marketing lançam programas de otimização para segmentação e direcionamento de público-alvo sem verificar se os níveis de tráfego e os públicos-alvo representados fornecerão resultados significativos dentro do período de teste para suas metas de otimização e conversão. Para evitar esse erro comum, responda antecipadamente a essas perguntas:

* Quantos visitantes únicos diários a página tem?
* Qual é a taxa de conversão da página?
* Por quanto tempo você antecipa a necessidade de executar o teste antes de poder chamá-lo de concluído com confiança?

**Dica** útil: Use a  [calculadora de tamanho da ](https://docs.adobe.com/content/target-microsite/testcalculator.html) amostra do Target para ajudar a determinar o tamanho da amostra necessário para um teste bem-sucedido.

## Dica 12: Projete testes mais simples para garantir que você possa criá-los e implementá-los.

Depois de considerar todos os aspectos de como projetar um teste, um plano pode se tornar muito complexo. Com base em onde sua empresa está com testes e na capacidade do seu grupo de projetar, codificar, executar e analisar os resultados, determine se o teste parece muito ambicioso. Em caso afirmativo, estar preparado para reduzir o seu âmbito e a sua complexidade. Antes iniciar que seja pequeno do que não executar o teste. Você não pode fornecer aumento impactante se nunca iniciar o teste. É importante equilibrar as aspirações da equipe com as realidades dos seus recursos e capacidades.

## Dica 13: Divida testes complexos em atividades de teste menores para torná-las viáveis.

Em vez de desenvolver um grande teste com múltiplas variáveis e desenvolvimento complexo, desenvolva uma série menos complexa de testes menores com variáveis mínimas. Isso permite uma compreensão mais profunda do desempenho de teste com base em variáveis específicas. Também reduz possíveis questões técnicas que surgem com o desenvolvimento de projetos maiores.

![Ilustração de testes complexos de quebra](/help/c-intro/assets/break-complex-tasks.png)

## Dica 14: Maximize o impacto do teste, testando mais perto do final do funil de conversão.

Testar o mais próximo da página em que os visitantes clicam em Concluir compra, Enviar aplicativo ou, de outra forma, concluir uma conversão tende a fornecer os resultados mais impactantes. Os visitantes que atingem o final do funil são mais qualificados, investiram mais tempo e estão prontos para comprar, portanto, testar insights sobre suas preferências e ações pode ajudar você a fazer alterações lucrativas. Como as páginas no caminho de compra são essenciais para as taxas de conversão, os testes realizados nessas páginas devem ser socializados para os principais participantes antes de serem lançados.

![Ilustração de funil de conversão](/help/c-intro/assets/conversion-funnel.png)

## Dica 15: Atualize constantemente seus testes para fazer melhorias iterativas.

Se a hipótese não for verdadeira, pense em maneiras de melhorar o teste. Lembre-se de que, mesmo que nenhuma das experiências testadas tenha um desempenho melhor, seu experimento não foi uma perda de tempo. Um teste bem-sucedido nem sempre significa um aumento na receita ou conversões. Se o teste realmente suportou sua hipótese, então você está a caminho de desenvolver uma teoria geral. Mas mesmo quando você tiver um resultado vencedor claro, não pare por aí. Com demasiada frequência, os profissionais de marketing cometem o erro de testar uma vez e depois de basear-se nesses resultados sem realmente compreender o que levou ao sucesso. Em vez disso, planeje iterar nesses resultados para descobrir por que o candidato estava à frente. Isso o levará a insights mais profundos que você poderá usar em campanhas futuras.

## Dica 16: Compare testes e atividades de personalização de ideias para melhorar o direcionamento.

Comparar o desempenho de conversão de diferentes públicos-alvo em diferentes testes em locais diferentes pode ajudar a focalizar e refinar a estratégia de otimização de uma empresa. Use comparações de teste para identificar quais públicos-alvo são mais valiosos para testar, quais devem receber experiências direcionadas e quais tipos de experiências têm maior probabilidade de obter uma resposta.

Por exemplo, um cliente de serviços financeiros realizou uma campanha promocional para um cartão de crédito que envolveu incentivos para eventos desportivos profissionais. Por meio de testes multivariados fatoriais parciais de suas landing pages, o cliente foi capaz de equilibrar de maneira ideal as mensagens sobre benefícios de cartões de crédito com incentivos esportivos para direcionar públicos distintos de sua base de clientes. Essa abordagem permitia que a empresa aproveitasse e maximizasse a conversão durante uma janela sensível ao tempo em torno de um evento esportivo importante.

## Dica 17: Tome os testes úteis apenas inicializando-os se você souber que pode agir com os dados.

Um teste é inútil se você não estiver claro sobre como você atuará nos dados. Isso inclui conhecer sua principal métrica de sucesso, o que precisa acontecer para impulsionar um vencedor, como você seguirá os resultados dos testes e o que fará com as informações do público-alvo. Para um teste rápido e bem-sucedido, é vital que todos os grupos envolvidos no teste (desenvolvedores, criadores, especialistas em testes e outros) estejam cientes de seu papel antes do lançamento do teste.

## Dica 18: Antes de iniciar um teste, verifique se a empresa suporta a promoção do vencedor.

As organizações de otimização bem-sucedidas acreditam no conceito de teste e entendem que suas opiniões profissionais sobre o que a experiência ganhará no teste nem sempre são verdadeiras. Eles determinam o vencedor com base em uma sólida base de dados, e estão ansiosos e dispostos a impulsionar a experiência vencedora ao vivo depois que os resultados estiverem no , mesmo que não esteja em conformidade com suas expectativas ou pareça contraintuitiva.

Por exemplo, um cliente de serviços de assistência médica Adobe demonstrou recentemente o valor do teste, mostrando como um banner de herói que a equipe havia considerado um pedaço de slam afetou negativamente a conversão. Se sua organização ainda não tiver adotado totalmente os testes, é melhor realizar testes de escopo mais simples e menores, para que as alterações nos resultados dos testes possam ser feitas de forma incremental.

## Dica 19: Informe a todos que você iniciou um teste para evitar preocupações quando o site mudar.

Um dos benefícios de configurar suas atividades para usar parâmetros de controle de qualidade é que você pode compartilhar esses links com todos em sua equipe. Você sensibiliza mais pessoas para a atividade e garante que elas não considerem que o site não está funcionando corretamente quando elas atingem uma variante de teste.

Depois de concluir seus testes, comunicar inicializações de campanha, resultados de testes e especialmente as lições aprendidas ajuda a conscientizar e interessar-se pelos resultados do teste. Compartilhar os resultados com todos na organização também evita o reteste de uma hipótese, instrui todos sobre o que funciona e os ajuda a desafiar fundamentalmente suas próprias ideias do que funciona com base no que você encontrou. É uma boa ideia preparar um modelo que você usa cada vez para compartilhar suas descobertas e aprendizados-chave.
Em seguida, considere criar um livro compartilhável ou um convés do Microsoft PowerPoint que capture cumulativamente esses aprendizados.

## Dica 20: Toque na funcionalidade móvel para criar atividades móveis mais inovadoras.

As experiências do usuário do tablet e do smartphone precisam se concentrar em controles orientados por toque como a principal interação do visitante, em vez de cliques do mouse e controles do teclado. Aproveite os controles de exibição para dispositivos móveis, incluindo deslizar o dedo, tocar, arrastar, apertar e aplicar zoom. Use botões simples e grandes para designar interações e navegação, como um grande carrinho de compras ou um botão de reprodução de vídeo. Se estiver projetando para varejo móvel, incorpore uma visualização de produto avançada otimizada para o tipo de dispositivo. Sempre procure oportunidades para mudar o foco da experiência do usuário para visualizadores grandes incorporados ou de tela inteira, zoom e panorâmica interativos, rotação de 360 graus e funcionalidade de vídeo aprimorada.

## Dica 21: Ajude os visitantes móveis a encontrar o que desejam otimizando a pesquisa móvel.

Usuários móveis têm alta intenção. A maioria deles usa pesquisa antes de fazer qualquer coisa em sites de comércio eletrônico, tornando a otimização de pesquisa de site móvel crucial. Para melhorar a otimização do mecanismo de pesquisa (SEO) para dispositivos móveis, use dicas de navegação explícitas para facilitar a navegação. Além disso, implemente a sugestão automática e a correção automática nas caixas de entrada de pesquisa para solucionar a dificuldade de digitação móvel. Forneça resultados de pesquisa relevantes e atraentes, otimizados para o tamanho e o local da tela.

## Dica 22: Alcance melhor os públicos-alvo móveis usando a definição de metas de hora do dia para campanhas SEM móveis.

Entenda como e quando alcançar seu público-alvo e como gerenciar melhor seu investimento diário em publicidade, dividindo suas campanhas móveis em diferentes segmentos ao longo do dia.

Muitos profissionais de marketing cometem o erro de não alocar orçamento suficiente para capturar essa parte de voz nas horas em que o uso de dispositivos específicos é mais pesado, deixando assim muita receita e leads sobre a mesa.

Por exemplo, o uso de tablets normalmente apresenta picos no horário noturno e muitos usuários navegam enquanto assistem televisão. Por outro lado, os usuários de smartphone normalmente acessam o conteúdo em qualquer lugar. Os tempos de conversão máximos também variam de acordo com o setor, portanto, é importante entender quando seus clientes únicos têm maior probabilidade de agir.

## Lembre-se

Considere as seguintes ideias antes de passarmos para o próximo capítulo: &quot;Inspiração para atividades de teste e personalização.&quot;

### Quando você criar seus testes, não decorar, seja intencional.

* Controle o fluxo com caminhos de olhos intencionais focados em pontos de conversão.
* Certifique-se de usar seu Real Estate em sua vantagem.
* Aproveite o foco da imagem para garantir que as imagens não sejam decorações, mas estejam funcionando para você.
* Reduza a desordem, o atrito e o desfoque com a cópia simplificada.
* Certifique-se de ter Chamadas efetivas para ações quando precisar que o usuário tome uma ação.
* Sempre que possível, adicione credibilidade por meio do Conteúdo gerado pelo usuário.

### Simplifique seu site.

* Não &quot;faça&quot; com que os clientes leiam. Eles não vão.
* Facilite a digitalização.
* Use blocos de cópia com marcadores.
* Certifique-se de que a cópia siga um processo de reflexão sequencial e limpo.

### Usar uma chamada efetiva para ações (CTAs)

* Coloque-se no lugar do cliente.
* Use uma linguagem orientada a ações.
* Considere a motivação para a conversão.
* Resolver o resultado da conversão.
* Certifique-se de que os CTAs sejam vistos!
