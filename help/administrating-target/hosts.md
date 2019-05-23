---
description: Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.
keywords: host;hosts;grupo de hosts;ambiente;solução de problemas;práticas recomendadas
seo-description: Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.
seo-title: Hosts
solution: Target
title: Hosts
topic: Padrão
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: d16f43524b18135b9173714a87a6d9f62173b900

---


# Hosts{#hosts}

Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.

## Hosts {#concept_516BB01EBFBD4449AB03940D31AEB66E}

Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.

Uma funcionalidade semelhante existia em [!DNL Target Classic]. Os grupos de host em [!DNL Target Classic] foram chamados de &quot;ambientes&quot; em [!DNL Target Standard/Premium].

O objetivo principal do gerenciamento de hosts é assegurar que nenhum conteúdo inativo seja exibido acidentalmente nos sites. O gerenciamento de host também permite que você separe os dados de relatório por ambiente.

Um host é qualquer servidor da Web (ou domínio da Web) de onde você serve conteúdo em qualquer fase do seu projeto. Todo host que serve um mbox é reconhecido.

Os hosts são agrupados em ambientes para facilitar o gerenciamento. Por exemplo, você pode ter dezenas de hosts agrupados em dois ou três ambientes. Os ambientes predefinidos incluem Produção, Armazenamento temporário e Desenvolvimento. Você pode adicionar novos ambientes e renomear seus ambientes, se desejado.

Um ambiente, o ambiente padrão, é pré-nomeado Produção. Esse ambiente padrão não pode ser removido, mesmo que você o renomeie. O [!DNL Target] parte do princípio que este é o local onde você disponibiliza atividades finais, aprovadas e testes.

Quando uma solicitação de mbox é recebida em um novos sites ou domínios, esses novos domínios sempre aparecem no ambiente Produção. O ambiente Produção não pode ter suas configurações alteradas de forma que, sites novos ou desconhecidos somente visualizarão o conteúdo pronto e ativo. O gerenciamento de hosts também permite garantir a qualidade de novas atividades e do conteúdo em seus ambientes de teste, armazenamento temporário e desenvolvimento, antes das atividades serem ativadas.

O Target não limita um host que pode enviar e receber mboxes. Dessa forma, quando novos servidores ou domínios entram em contato, funcionam automaticamente (a menos que tenha configurado uma lista de permissões ou lista negra). Isso também permite o teste de publicidade em domínios diferentes, desconhecidos ou não previstos.

Para gerenciar hosts e ambientes, clique em **[!UICONTROL Configuração]** &gt; **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Reconhecimento de hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

As informações sobre as condições a serem seguidas para que o [!DNL Target] reconheça um host e adicione-o à lista Hosts.

Para reconhecer um host, as condições a seguir devem ser cumpridas:

* Pelo menos uma mbox deve existir no host
* Uma página no host deve ter o seguinte:

   * Uma referência de [!DNL mbox.js] precisa
   * Uma mbox ou uma chamada de mbox global automaticamente gerada

* A página com a mbox deve ser visualizada em um navegador

Após a visualização de uma página, o host é adicionado na lista de [!UICONTROL Hosts], permitindo que você gerencie-o em uma ambiente, bem como, visualize e inicie atividades e testes.

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>Isso inclui quaisquer servidores de desenvolvimento pessoal.

Após adicionar um host na lista de [!UICONTROL Host], certifique-se de que o host seja reconhecido.

1. Clique em **[!UICONTROL Configuração]** &gt; **[!UICONTROL Hosts]**.
1. Se o seu host não estiver listado, atualize seu navegador.
Por padrão, um novo host reconhecido é colocado no ambiente de Produção. Esse é o ambiente mais seguro porque ele não permite que atividades inativas sejam visualizadas nesses hosts.
1. (Condicional) Mova o host para o ambiente de Desenvolvimento ou Ambiente de preparo.

>[!NOTE]
>
>O ambiente de produção não pode ser removido, mesmo que você o renomeie. Pressupõe-se que este seja o local em que você disponibiliza atividades ativas e testes finais e aprovados. O ambiente padrão não permite que campanhas inativas sejam visualizadas.

## Gerenciar hosts e ambientes {#concept_90573F5A52E04600A8C3C5897880C10F}

Informações para ajudá-lo a gerenciar hosts e ambientes (grupos de hosts) incluindo a configuração de host padrão para geração de relatório, criação de listas de permissão, alteração do nome do ambiente, transferência de um host para outro ambiente e exclusão de um host ou ambiente.


Para acessar a lista [!UICONTROL Hosts], clique em **[!UICONTROL Configuração]** &gt; **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Filtrar, Classificar ou Pesquisar a lista de hosts {#section_068B23C9D8224EB78BC3B7C8580251B0}

Para filtrar a lista de [!UICONTROL Hosts] por ambiente, clique na lista suspensa **[!UICONTROL Tudo], em seguida, selecione o ambiente desejado (Produção, Armazenamento temporário, Desenvolvimento ou um ambiente personalizado que você criou).**

Para classificar a lista de [!UICONTROL Hosts], clique em qualquer cabeçalho e coluna (Nome, Ambiente ou Última solicitação) para classificar a lista em ordem ascendente ou descendente.

Para pesquisar a lista de [!UICONTROL Hosts], digite um termo de pesquisa na caixa Pesquisar.

## Selecionar vários hosts {#section_EF3B458475184B7EA997C3559714397C}

Para selecionar vários hosts, marque as caixas de seleção perto da coluna [!UICONTROL Nome] dos hosts desejados. Em seguida, você pode mover ou excluir todos os hosts selecionados.

## Criar um ambiente {#section_32097D0993724DF3A202D164D3F18674}

1. Na lista de [!UICONTROL Hosts], clique na guia **[!UICONTROL Ambientes].**
1. Clique em **[!UICONTROL Criar ambiente]**.
1. Especifique um nome descritivo para o ambiente.
1. Especifique o modo ativo desejado para o ambiente: [!UICONTROL Atividades ativas] ou [!UICONTROL Atividades ativas e inativas].
1. Clique em **[!UICONTROL Salvar]**.

## Definir o host padrão para relatórios {#section_4F8539B07C0C45E886E8525C344D5FB0}

Você pode selecionar o ambiente que deseja usar como padrão em todos os relatórios de atividade.

Se você usa a Produção como seu padrão, todos os hosts desconhecidos são automaticamente adicionados aqui os dados de relatórios deles são incluídos na exibição de relatório padrão. Em vez disso, criar um ambiente &quot;limpo&quot; garante somente a inclusão dos seus sites/domínios principais.

Para definir o ambiente padrão para relatório:

1. Na lista de [!UICONTROL Hosts], clique na guia **[!UICONTROL Configurações].**
1. Selecione o host padrão na lista suspensa **[!UICONTROL Configurações do ambiente].**
1. Clique em **[!UICONTROL Salvar]**.

>[!NOTE]
>
>[!DNL Recommendations]Os usuários do devem recriar sua base de dados comportamental e a base de dados de produtos se os hosts alternarem os grupos de host.

## Criar listas de permissões que especifica hosts autorizados a enviar chamadas de mbox para o Target. {#section_0AF7F56C386A42C381AF704DEF08D5CC}

Você pode criar uma lista de permissões que especifica hosts (domínios) autorizados a enviar chamadas de mbox para o [!DNL Target]. Todos os outros hosts que estiverem gerando chamadas receberão uma resposta comentada do erro de autorização. Por padrão, qualquer host que contenha uma chamada de mbox é registrado no [!DNL Target], dentro do ambiente Produção, e tem acesso a todas as atividades ativas e aprovadas. Se esta não for a abordagem desejada, você pode usar a lista de permissões para gravar hosts específicos que sejam elegíveis para fazer chamadas de mbox e receber conteúdo de atividade do [!DNL Target]. Todos os hosts continuarão a ser exibidos na lista de [!UICONTROL Hosts], e os ambientes ainda poderão ser usados para agrupar estes hosts e designar níveis diferentes a cada um, como decidir se o host pode ver campanhas ativas e/ou inativas.

Para criar uma lista de permissões:

1. Na lista de [!UICONTROL Hosts], clique na guia **[!UICONTROL Configurações].**
1. Marque a caixa de seleção **[!UICONTROL Ativar hosts autorizados para entrega de conteúdo].**
1. Adicione os hosts desejados na caixa **[!UICONTROL Host contém], conforme desejado.**

   Vários hosts podem ser listados, cada um na própria linha.

1. Clique em **[!UICONTROL Salvar]**.

Se uma chamada de mbox for feita em um host não autorizado, a chamada responderá com `/* no display - unauthorized mbox host */`.

A lista de permissões tem precedência em relação a outros ambientes. Você deve limpar todos os hosts antes de usar o recurso de lista de permissões; assim, apenas os hosts autorizados pela lista de permissões aparecerão na lista de hosts. Em seguida, você poderá mover os hosts para o ambiente desejado.

Em algumas ocasiões, domínios de outros sites podem ser exibidos em seus ambientes. Um domínio é exibido na lista se este fizer uma chamada para mbox.js. Por exemplo, se alguém copiar uma de suas página da Web para outro servidor, o domínio será exibido em seu ambiente. Você também poderá ver domínios de mecanismos spiders, sites de tradução ou unidades de disco locais.

Nos casos em que `mboxHost` é passada na chamada de API, a conversão é registrada para o ambiente que é transmitido. Se nenhum ambiente for transmitido, o host na chamada volta ao padrão Produção.

Você também pode criar uma lista negra que especifica os hosts (domínios) que não podem enviar chamadas da mbox para o [!DNL Target] ao adicionar os hosts desejados na caixa [!UICONTROL Host não contêm].

## Alterar o nome de um ambiente {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. Na lista de [!UICONTROL Hosts], clique na guia **[!UICONTROL Ambientes].**
1. Passe o cursor do mouse sobre o ambiente desejado, em seguida clique no ícone de **[!UICONTROL Editar.]**
1. Altere o nome do ambiente.
1. Clique em **[!UICONTROL Salvar]**.

## Mover um host para um ambiente diferente {#section_9F52549958BD485EB74FE78C32773D2A}

1. Na lista de [!UICONTROL Hosts], passe o cursor do mouse sobre o host que deseja mover.
1. Clique no ícone de **[!UICONTROL Mover.]**
1. Selecione o ambiente desejado na lista suspensa, em seguida, clique no ícone de marca de verificação.

## Excluir um host {#section_F56355BA4BC54B078A1A8179BC954632}

Você pode excluir um host quando ele não é mais necessário.

1. Na lista de [!UICONTROL Hosts], passe o cursor do mouse sobre o host que deseja excluir.
1. Clique no ícone de **[!UICONTROL Excluir.]**
1. Clique em **[!UICONTROL Excluir]para confirmar a exclusão.**

>[!NOTE]
>
>O host será listado novamente se alguém navegar até uma página com mbox no host.

## Excluir um ambiente {#section_737F8869612047868D03FC755B1223D3}

Você pode excluir um ambiente quando ele não é mais necessário.

1. Na lista de [!UICONTROL Hosts], clique na guia **[!UICONTROL Ambientes].**
1. Passe o cursor do mouse sobre o ambiente que deseja excluir.
1. Clique no ícone de **[!UICONTROL Excluir.]**
1. Clique em **[!UICONTROL Excluir]para confirmar a exclusão.**

>[!NOTE]
>
>Não é possível excluir o ambiente de Produção, mas você pode renomeá-lo.

## Solução de problemas de hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Práticas recomendadas para gerenciamento e solução de problemas de host no [!DNL Adobe Target].

Tente as dicas de solução de problemas a seguir se tiver dificuldade com seus hosts:

**O host não é exibido na lista de mbox da sua conta.**

* Atualize a página [!UICONTROL Hosts] no seu navegador.
* Confirme se o código da mbox está correto, incluindo a referência a [!DNL mbox.js].
* Tente navegar para uma das mboxes no host. É possível que nenhuma mbox no host tenha sido renderizada em um navegador.

**Domínios aleatórios ou desconhecidos são exibidos nas listas de grupo de[!UICONTROL Hosts].**

Um domínio é exibido nessa lista se uma chamada para o [!DNL Target] for feita no domínio. Frequentemente, é possível ver domínios de mecanismos spider, sites de tradutor de idiomas ou unidades de discos locais. Se o domínio listado não for o domínio utilizado pela sua equipe, clique em [!UICONTROL Excluir] para removê-lo.

**Minha chamada da mbox retorna /* sem exibição - host do mbox não autorizado */.**

Se uma chamada de mbox for feita em um host autorizado, a chamada responderá com /* sem exibição - host mbox não autorizado */.

## Recommendations: coleções e exclusões de filtros por ambiente (grupo de hosts)

![Selo premium](/help/assets/premium.png)

Você pode visualizar o conteúdo das coleções e exclusões do Recommendations de um ambiente selecionado (grupo de hosts).

>[!NOTE]
>As atividades do Recommendations estão disponíveis como parte da solução Target Premium. Elas não estão disponíveis no Target Standard sem uma licença do Target Premium.

O grupo de hosts pode ser usado para separar os itens disponíveis no catálogo para usos diferentes. Por exemplo, você pode usar grupos de hosts para os ambientes de Desenvolvimento e Produção, para diferentes marcas ou diferentes regiões. Por padrão, os resultados de visualização na Pesquisa no catálogo, nas Coleções e nas Exclusões estão baseados no grupo de hosts padrão. (Também é possível selecionar um grupo de hosts diferente para visualizar os resultados, usando o filtro Ambiente.) Por padrão, os itens recém adicionados ficam disponíveis em todos os grupos de hosts, a menos que uma ID de ambiente seja especificada ao criar ou atualizar o item. As recomendações entregues dependem do grupo de hosts especificado na solicitação.

Se você não visualiza seus produtos, certifique-se de que você esteja usando o grupo correto de hosts. Por exemplo, se você configurar sua recomendação para usar um ambiente de preparo e você definir o grupo de hosts para Armazenamento temporário, você pode necessitar recriar suas coleções no ambiente de preparo para serem mostradas pelos produtos. Para ver quais produtos estão disponíveis em cada ambiente, use a Pesquisa de catálogo com cada ambiente. Você também pode visualizar o conteúdo das coleções e exclusões do Recommendations para um ambiente selecionado (grupo de hosts).

>[!NOTE]
>Depois de alterar o ambiente selecionado, clique em Pesquisar para atualizar os resultados retornados.

O filtro Ambiente está disponível nos seguintes locais da interface do usuário do Target:

* Pesquisa do catálogo ([!UICONTROL Recommendations&gt; Pesquisa do catálogo])
* Caixa de diálogo Criar coleção ([!UICONTROL Recommendations&gt; Coleções &gt; Criar nova])
* Caixa de diálogo Atualizar coleção ([!UICONTROL Recommendations&gt; Coleções &gt; Editar])
* Caixa de diálogo Criar exclusão ([!UICONTROL Recommendations &gt; Exclusões &gt; Criar nova])
* Caixa de diálogo Atualizar exclusão ([!UICONTROL Recommendations &gt; Exclusões &gt; Editar])
