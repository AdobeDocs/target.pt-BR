---
keywords: host; hosts; grupo de hosts; solução de problemas; práticas recomendadas; ubox; redirecionamentos; redirecionamento; lista de permissões;  lista de permissões; lista negra;  lista de bloqueios
description: Saiba como organizar seus sites e ambientes de pré-produção para fácil gerenciamento e relatórios separados no Adobe Target.
title: O que são hosts e como os uso?
feature: Administração e configuração
role: Administrador
translation-type: tm+mt
source-git-commit: 86102ed5b49d102660ed38fe0a71612cefcd2caf
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 22%

---


# Hosts

Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados em [!DNL Adobe Target].

O objetivo principal do gerenciamento de hosts é assegurar que nenhum conteúdo inativo seja exibido acidentalmente nos sites. O gerenciamento de hosts também permite separar os dados do relatório por [environment](/help/administrating-target/environments.md).

Um host é qualquer domínio do qual uma solicitação [!DNL Target] é feita. Em um site, geralmente é a propriedade `location.hostname` do URL que faz a solicitação [!DNL Target].

Por padrão, [!DNL Target] não limita um host que pode fazer solicitações [!DNL Target] e receber respostas [!DNL Target]. Quando novos hosts fazem solicitações, elas funcionam automaticamente. Esse processo também permite testes em domínios diferentes que você não sabe ou não pode antecipar. Se quiser substituir esse comportamento padrão, você pode configurar uma  de lista de permissões ou lista de bloqueios para limitar quais hosts funcionam com [!DNL Target].

Para gerenciar hosts, clique em **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Reconhecimento de hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Para reconhecer um host e adicioná-lo à lista [!UICONTROL Hosts], as seguintes condições devem ser atendidas:

* Pelo menos uma solicitação [!DNL Target] deve existir no host
* Uma página no host deve ter  o seguinte:

   * Uma referência precisa à at.js
   * Uma solicitação [!DNL Target] ou uma solicitação [!DNL Target] global gerada automaticamente

* A página com a solicitação [!DNL Target] deve ser visualizada em um navegador

Após a visualização da página, o host é listado na lista [!UICONTROL Hosts], permitindo que você gerencie-o em um ambiente, e visualize e inicie atividades e testes.

>[!NOTE]
>
>Isso inclui quaisquer servidores de desenvolvimento pessoal.

Após adicionar um host na lista de [!UICONTROL Host], certifique-se de que o host seja reconhecido.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Hosts]**.
1. Se o seu host não estiver listado, atualize seu navegador. 


   Por padrão, um novo host reconhecido é colocado no ambiente [!UICONTROL Production]. O ambiente [!UICONTROL Production] é o ambiente mais seguro porque não permite que atividades inativas sejam visualizadas a partir desses hosts.

1. (Condicional) Clique no ícone **[!UICONTROL Move]** ( ![move icon](/help/administrating-target/assets/icon-move.png) ) para mover o host para o [!UICONTROL Development], [!UICONTROL Staging] ou outro ambiente.

>[!NOTE]
>
>O ambiente [!UICONTROL Produção] não pode ser excluído, mesmo que você o renomeie. Pressupõe-se que esse ambiente seja o local em que você disponibiliza atividades ativas e testes finais. O ambiente padrão não permite que campanhas inativas sejam visualizadas.

## Classifique ou pesquise a lista de Hosts {#section_068B23C9D8224EB78BC3B7C8580251B0}

Para classificar a lista [!UICONTROL Hosts], clique em qualquer cabeçalho de coluna ([!UICONTROL Nome], [!UICONTROL Ambiente] ou [!UICONTROL Último pedido]) para classificar a lista em ordem crescente ou decrescente.

Para pesquisar a lista [!UICONTROL Hosts], digite um termo de pesquisa na caixa [!UICONTROL Pesquisar Hosts].

## Crie listas de permissões que especifiquem hosts autorizados a enviar solicitações do Target para o Target. {#allowlist}

Você pode criar uma  de lista de permissões que especifica hosts (domínios) autorizados a enviar solicitações [!DNL Target] para [!DNL Target]. Todos os outros hosts que geram solicitações recebem uma resposta comentada do erro de autorização. Por padrão, qualquer host que contenha uma solicitação [!DNL Target] é registrado com [!DNL Target] no ambiente [!UICONTROL Produção] e tem acesso a todas as atividades ativas e aprovadas. Se essa abordagem não for desejada, você poderá usar a  de lista de permissões para gravar hosts específicos que sejam elegíveis para fazer solicitações [!DNL Target] e receber conteúdo [!DNL Target]. Todos os hosts continuam a ser exibidos na lista [!UICONTROL Hosts], e os ambientes ainda podem ser usados para agrupar esses hosts e atribuir níveis diferentes a cada um, como se o host pode ver atividades ativas e/ou inativas.

Para criar uma  lista de permissões:

1. Na lista [!UICONTROL Hosts], clique em **[!UICONTROL Autorizar Hosts]**.
1. Ative a opção **[!UICONTROL Ativar hosts autorizados para entrega de conteúdo]**.
1. Adicione os hosts desejados na caixa **[!UICONTROL Host contém]**, conforme desejado.

   Vários hosts podem ser listados, cada um na própria linha.

1. Adicione os hosts desejados na caixa **[!UICONTROL Host não contém]**, conforme desejado.

   Vários hosts podem ser listados, cada um na própria linha.

1. Clique em **[!UICONTROL Salvar]**.

Se uma solicitação [!DNL Target] for feita em um host não autorizado, a chamada responderá com `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Práticas recomendadas** de segurança: Se você usar a funcionalidade de ubox do  [!DNL Target], essa lista de permissões também controlará a lista de domínios para os quais os  [](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) redirecionadores navegarão. Certifique-se de adicionar quaisquer domínios aos quais deseja redirecionar quando usar a ubox como parte da implementação. Se a  lista de permissões for deixada não especificada, [!DNL Adobe] não será capaz de verificar os URLs de redirecionamento e proteger de possíveis redirecionamentos mal-intencionados.
>
>A  de lista de permissões tem precedência sobre os ambientes. Limpe todos os hosts antes de usar o recurso de  de lista de permissões e, em seguida, somente os hosts permitidos pela lista de permissões serão exibidos na lista de hosts. Em seguida, você poderá mover os hosts para o ambiente desejado.

Em algumas ocasiões, domínios de outros sites podem ser exibidos em seus ambientes. Um domínio é exibido na lista se ele chamar at.js. Por exemplo, se alguém copiar uma de suas página da Web para outro servidor, o domínio será exibido em seu ambiente. Você também poderá ver domínios de mecanismos spiders, sites de tradução ou unidades de disco locais.

Nos casos em que `mboxHost` é passada na chamada de API, a conversão é registrada para o ambiente que é transmitido. Se nenhum ambiente for transmitido, o host na chamada volta ao padrão [!UICONTROL Production].

Você também pode criar uma  de lista de bloqueios que especifica hosts (domínios) que não podem enviar solicitações [!DNL Target] para [!DNL Target] ao adicionar os hosts desejados na caixa [!UICONTROL Host não contém].

>[!NOTE]
>
>A lista [!UICONTROL Hosts Autorizados] é usada tanto para hosts [!DNL Target] quanto para hosts de redirecionamento padrão. Adicione todos os domínios existentes aprovados para usar o [!DNL Adobe Target] SDK do JavaScript (at.js) *AND* todos os domínios usados nos URLs de redirecionamento padrão da ubox. Adicione novos domínios semelhantes à lista de permissões no futuro.

## Excluir um host {#section_F56355BA4BC54B078A1A8179BC954632}

Você pode excluir um host quando ele não é mais necessário.

1. Na lista [!UICONTROL Hosts], clique no ícone **[!UICONTROL Excluir]**.
1. Clique em **[!UICONTROL Excluir]** para confirmar a exclusão.

>[!NOTE]
>
>O host é listado novamente se alguém navegar para uma página que contém uma solicitação [!DNL Target] no host.

## Solucionar problemas dos hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Tente as dicas de solução de problemas a seguir se tiver dificuldade com seus hosts:

**O host não é exibido na lista de sua conta.**

* Atualize a página [!UICONTROL Hosts] no seu navegador.
* Confirme se a solicitação [!DNL Target] está correta, incluindo a referência a at.js.
* Tente navegar para uma das solicitações [!DNL Target] no host. É possível que nenhuma solicitação [!DNL Target] no host tenha sido renderizada em um navegador.

**Domínios aleatórios ou desconhecidos são exibidos nas listas de grupo de [!UICONTROL Hosts].**

Um domínio é exibido nessa lista se uma solicitação para [!DNL Target] for feita a partir do domínio. Frequentemente, é possível ver domínios de mecanismos spider, sites de tradutor de idiomas ou unidades de discos locais. Se o domínio listado não for o domínio utilizado pela sua equipe, clique em [!UICONTROL Excluir] para removê-lo.

**Minha  [!DNL Target] solicitação retorna /* sem exibição - host do mbox não autorizado */.**

Se uma solicitação [!DNL Target] for feita em um host não autorizado, a solicitação responderá com /* sem exibição - host mbox não autorizado */.
