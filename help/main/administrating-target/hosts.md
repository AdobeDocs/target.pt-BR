---
keywords: host;hosts;grupo de hosts;solução de problemas;práticas recomendadas;ubox;redireciona;redirecionar;lista de permissões;incluir na lista de permissões;lista negra;incluir na lista de bloqueios
description: Saiba como organizar seus sites e ambientes de pré-produção para facilitar o gerenciamento e os relatórios separados no Adobe Target.
title: O que são hosts e como usá-los?
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 22%

---

# Hosts

Organize seus sites e ambientes de pré-produção para facilitar o gerenciamento e gerar relatórios separados no [!DNL Adobe Target].

O objetivo principal do gerenciamento de hosts é assegurar que nenhum conteúdo inativo seja exibido acidentalmente nos sites. O gerenciamento de host também permite separar dados de relatório por [ambiente](/help/main/administrating-target/environments.md).

Um host é qualquer domínio do qual um [!DNL Target] for feita. Em um site, geralmente é o `location.hostname` propriedade do URL que faz a [!DNL Target] solicitação.

Por padrão, [!DNL Target] não limita um host que possa fazer [!DNL Target] solicitações e recebimento [!DNL Target] respostas. Quando novos hosts fazem solicitações, eles funcionam automaticamente. Esse processo também permite testar em domínios diferentes que você não conhece ou não pode antecipar. Se quiser substituir esse comportamento padrão, você pode configurar um incluir na lista de permissões lista de bloqueios de navegação ou para limitar com quais hosts funciona [!DNL Target].

Para gerenciar hosts, clique em **[!UICONTROL Administração]** > **[!UICONTROL Hosts]**.

![imagem hosts_list](assets/hosts_list.png)

## Reconhecimento de hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Para reconhecer e adicionar um host à [!UICONTROL Hosts] as seguintes condições devem ser atendidas:

* Pelo menos um [!DNL Target] a solicitação deve existir no host
* Uma página no host deve ter  o seguinte:

   * Uma referência at.js precisa
   * A [!DNL Target] solicitação ou um evento global gerado automaticamente [!DNL Target] solicitação

* A página com o [!DNL Target] deve ser visualizada em um navegador

Após a visualização da página, o host é listado no [!UICONTROL Hosts] , permitindo que você o gerencie em um ambiente, e visualize e inicie atividades e testes.

>[!NOTE]
>
>Isso inclui quaisquer servidores de desenvolvimento pessoal.

Após adicionar um host na lista de [!UICONTROL Host], certifique-se de que o host seja reconhecido.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Hosts]**.
1. Se o seu host não estiver listado, atualize seu navegador. 


   Por padrão, um host recém-reconhecido é colocado no [!UICONTROL Produção] ambiente. A variável [!UICONTROL Produção] O ambiente é o mais seguro porque não permite que atividades inativas sejam visualizadas desses hosts.

1. (Condicional) Clique no link **[!UICONTROL Mover]** ícone ( ![ícone mover](/help/main/administrating-target/assets/icon-move.png) ) para mover o host para a [!UICONTROL Desenvolvimento], [!UICONTROL Estágios]ou outro ambiente.

>[!NOTE]
>
>A variável [!UICONTROL Produção] O ambiente não pode ser excluído, mesmo que você o renomeie. Pressupõe-se que esse ambiente seja onde você disponibiliza atividades finais, ativas e testes. O ambiente padrão não permite que campanhas inativas sejam visualizadas.

## Classificar ou pesquisar a lista de Hosts {#section_068B23C9D8224EB78BC3B7C8580251B0}

Para classificar o [!UICONTROL Hosts] clique em qualquer cabeçalho de coluna ([!UICONTROL Nome], [!UICONTROL Ambiente]ou [!UICONTROL Última solicitação]) para classificar a lista em ordem crescente ou decrescente.

Para pesquisar o [!UICONTROL Hosts] digite um termo de pesquisa na caixa [!UICONTROL Pesquisar hosts] caixa.

## Lista de permissões Criar notificações que especificam hosts autorizados a enviar [!DNL Target] solicitações para [!DNL Target]. {#allowlist}

Você pode criar uma inclui na lista de permissões que especifica hosts (domínios) autorizados a enviar [!DNL Target] solicitações para [!DNL Target]. Todos os outros hosts que geram solicitações recebem uma resposta comentada de erro de autorização. Por padrão, qualquer host que contenha um [!DNL Target] registros de solicitação com [!DNL Target] no [!UICONTROL Produção] e tem acesso a todas as atividades ativas e aprovadas. Se essa abordagem não for a desejada, você poderá usar a inclui na lista de permissões para gravar hosts específicos que sejam elegíveis para fazer [!DNL Target] solicitações e recebimento [!DNL Target] conteúdo. Todos os hosts continuam a ser exibidos no [!UICONTROL Hosts] Os ambientes e ainda podem ser usados para agrupar esses hosts e atribuir diferentes níveis a cada um, como se o host pode ver atividades ativas e/ou inativas.

Para criar uma inclui na lista de permissões:

1. No [!UICONTROL Hosts] clique em **[!UICONTROL Autorizar hosts]**.
1. Ativar o **[!UICONTROL Ativar hosts autorizados para entrega de conteúdo]** alternar.
1. Adicione os hosts desejados no **[!UICONTROL O host contém]** conforme desejado.

   Vários hosts podem ser listados, cada um na própria linha.

1. Adicione os hosts desejados no **[!UICONTROL O host não contém]** conforme desejado.

   Vários hosts podem ser listados, cada um na própria linha.

1. Clique em **[!UICONTROL Salvar]**.

Se um [!DNL Target] for feita em um host não autorizado, a chamada responderá com `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Práticas recomendadas de segurança**: Se você usar a funcionalidade de ubox do [!DNL Target], essa inclui na lista de permissões também controla a lista de domínios para os quais o [redirecionadores](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html){target=_blank} é possível navegar. Adicione todos os domínios aos quais deseja redirecionar ao usar o ubox como parte da implementação. Se a inclui na lista de permissões mudar não for especificada, [!DNL Adobe] O não consegue verificar os URLs de redirecionamento e proteger contra possíveis redirecionamentos mal-intencionados.
>
>A inclui na lista de permissões tem precedência sobre os ambientes. Limpe todos os hosts antes de usar o recurso de incluir na lista de permissões lista de permissões e, em seguida, somente os hosts permitidos pelo arquivo serão exibidos na lista de hosts. Em seguida, você poderá mover os hosts para o ambiente desejado.

Em algumas ocasiões, domínios de outros sites podem ser exibidos em seus ambientes. Um domínio é exibido na lista se chamar at.js. Por exemplo, se alguém copiar uma de suas página da Web para outro servidor, o domínio será exibido em seu ambiente. Você também poderá ver domínios de mecanismos spiders, sites de tradução ou unidades de disco locais.

Nos casos em que `mboxHost` é passada na chamada de API, a conversão é registrada para o ambiente que é transmitido. Se nenhum ambiente for transmitido, o host na chamada assumirá como padrão [!UICONTROL Produção].

Você também pode criar uma inclui na lista de bloqueios que especifique hosts (domínios) que não podem enviar [!DNL Target] solicitações para [!DNL Target] adicionando os hosts desejados no [!UICONTROL O host não contém] caixa.

>[!NOTE]
>
>A variável [!UICONTROL Hosts autorizados] a lista é usada para ambos [!DNL Target] hosts e hosts de redirecionamento padrão. Adicionar todos os domínios existentes aprovados para usar o [!DNL Adobe Target] SDK do JavaScript (at.js) *E* todos os domínios usados nos URLs de redirecionamento padrão da ubox. Adicione quaisquer domínios semelhantes ao incluo na lista de permissões no futuro.

## Excluir um host {#section_F56355BA4BC54B078A1A8179BC954632}

Você pode excluir um host quando ele não é mais necessário.

1. No [!UICONTROL Hosts] clique na guia **[!UICONTROL Excluir]** ícone.
1. Clique em **[!UICONTROL Excluir]** para confirmar a exclusão.

>[!NOTE]
>
>O host será listado novamente se alguém navegar até uma página que contenha uma [!DNL Target] no host.

## Solucionar problemas dos hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Tente as dicas de solução de problemas a seguir se tiver dificuldade com seus hosts:

**O host não aparece na lista da sua conta.**

* Atualize a página [!UICONTROL Hosts] no seu navegador.
* Confirme se o [!DNL Target] está correta, incluindo a referência à at.js.
* Tente navegar para uma das [!DNL Target] no host. É possível que nenhum [!DNL Target] solicitação no host nunca foi renderizada em um navegador.

**Domínios aleatórios ou desconhecidos são exibidos nas listas de grupo de [!UICONTROL Hosts].**

Um domínio é exibido nessa lista se uma solicitação para [!DNL Target] é feito do domínio. Frequentemente, é possível ver domínios de mecanismos spider, sites de tradutor de idiomas ou unidades de discos locais. Se o domínio listado não for o domínio utilizado pela sua equipe, clique em [!UICONTROL Excluir] para removê-lo.

**Meus [!DNL Target] retornos de solicitação /&#42; sem exibição - host de mbox não autorizado &#42;/.**

Se um [!DNL Target] for feita em um host não autorizado, a solicitação responderá com /&#42; sem exibição - host de mbox não autorizado &#42;/.
