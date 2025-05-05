---
keywords: host;hosts;grupo de hosts;solução de problemas;práticas recomendadas;ubox;redireciona;redirecionar;lista de permissões;incluir na lista de permissões;lista negra;incluir na lista de bloqueios
description: Saiba como organizar seus sites e ambientes de pré-produção para facilitar o gerenciamento e os relatórios separados no Adobe Target.
title: O que são hosts e como usá-los?
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 17%

---

# Hosts

Organize seus sites e ambientes de pré-produção para facilitar o gerenciamento e gerar relatórios separados no [!DNL Adobe Target].

O objetivo principal do gerenciamento de hosts é assegurar que nenhum conteúdo inativo seja exibido acidentalmente nos sites. O gerenciamento de host também permite separar os dados do relatório por [ambiente](/help/main/administrating-target/environments.md).

Um host é qualquer domínio a partir do qual uma solicitação [!DNL Target] é feita. Em um site, geralmente é a propriedade `location.hostname` da URL que está fazendo a solicitação [!DNL Target].

Por padrão, o [!DNL Target] não limita um host que possa fazer [!DNL Target] solicitações e receber [!DNL Target] respostas. Quando novos hosts fazem solicitações, eles funcionam automaticamente. Esse processo também permite testar em domínios diferentes que você não conhece ou não pode antecipar. Se quiser substituir esse comportamento padrão, você pode configurar um incluir na lista de permissões incluo na lista de bloqueios de navegação ou para limitar quais hosts funcionam com o [!DNL Target].

{{permissions-update}}

Para gerenciar hosts, clique em **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.

## Reconhecimento de hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Para reconhecer um host e adicioná-lo à lista [!UICONTROL Hosts], as seguintes condições devem ser atendidas:

* Pelo menos uma solicitação [!DNL Target] deve existir no host
* Uma página no host deve ter o seguinte:

   * Uma referência at.js precisa
   * Uma solicitação [!DNL Target] ou uma solicitação [!DNL Target] global gerada automaticamente

* A página com a solicitação [!DNL Target] deve ser visualizada em um navegador

Após a visualização da página, o host é listado na lista [!UICONTROL Hosts], permitindo que você gerencie-o em um ambiente, e visualize e inicie atividades e testes.

>[!NOTE]
>
>Isso inclui quaisquer servidores de desenvolvimento pessoal.

Depois que um host for adicionado à lista [!UICONTROL Host], verifique se ele é reconhecido.

1. Clique em **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.
1. Se o seu host não estiver listado, atualize seu navegador.

   Por padrão, um host recém-reconhecido é colocado no ambiente [!UICONTROL Production]. O ambiente [!UICONTROL Production] é o mais seguro porque não permite que atividades inativas sejam visualizadas desses hosts.

1. (Condicional) Clique no ícone **[!UICONTROL Move]** ( ![ícone de movimentação](/help/main/administrating-target/assets/icon-move.png) ) para mover o host para o [!UICONTROL Development], [!UICONTROL Staging] ou outro ambiente.

>[!NOTE]
>
>O ambiente [!UICONTROL Production] não pode ser excluído, mesmo que você o renomeie. Pressupõe-se que esse ambiente seja onde você disponibiliza atividades finais, ativas e testes. O ambiente padrão não permite que campanhas inativas sejam visualizadas.

## Classificar ou pesquisar a lista de Hosts {#section_068B23C9D8224EB78BC3B7C8580251B0}

Para classificar a lista [!UICONTROL Hosts], clique em qualquer cabeçalho de coluna ([!UICONTROL Name], [!UICONTROL Environment] ou [!UICONTROL Last Requested]) para classificar a lista em ordem crescente ou decrescente.

Para pesquisar a lista [!UICONTROL Hosts], digite um termo de pesquisa na caixa [!UICONTROL Search Hosts].

## Incluir na lista de permissões Crie notificações que especificam hosts autorizados a enviar [!DNL Target] solicitações a [!DNL Target]. {#allowlist}

Você pode criar um incluo na lista de permissões que especifica hosts (domínios) autorizados a enviar [!DNL Target] solicitações para [!DNL Target]. Todos os outros hosts que geram solicitações recebem uma resposta comentada de erro de autorização. Por padrão, qualquer host que contenha uma solicitação [!DNL Target] é registrado com [!DNL Target] no ambiente [!UICONTROL Production] e tem acesso a todas as atividades ativas e aprovadas. Se essa abordagem não for a desejada, você poderá usar a inclui na lista de permissões para gravar hosts específicos que sejam elegíveis para fazer [!DNL Target] solicitações e receber conteúdo de [!DNL Target]. Todos os hosts continuam a ser exibidos na lista [!UICONTROL Hosts], e os ambientes ainda podem ser usados para agrupar esses hosts e atribuir diferentes níveis a cada um, como se o host pode ver atividades ativas e/ou inativas.

Para criar uma inclui na lista de permissões:

1. Na lista [!UICONTROL Hosts], clique em **[!UICONTROL Authorize Hosts]**.
1. Habilite a alternância **[!UICONTROL Enable Authorized Hosts for content delivery]**.
1. Adicione os hosts desejados na caixa **[!UICONTROL Host contains]**, conforme desejado.

   Vários hosts podem ser listados, cada um na própria linha.

1. Adicione os hosts desejados na caixa **[!UICONTROL Host does not contains]**, conforme desejado.

   Vários hosts podem ser listados, cada um na própria linha.

1. Clique em **[!UICONTROL Save]**.

Se uma solicitação [!DNL Target] for feita em um host não autorizado, a chamada responderá com `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Práticas recomendadas de segurança**: se você usar a funcionalidade de ubox do [!DNL Target], essa incluída na lista de permissões também controlará a lista de domínios para os quais seus [redirecionadores](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html?lang=pt-BR){target=_blank} podem navegar. Adicione todos os domínios aos quais deseja redirecionar ao usar o ubox como parte da implementação. Se a inclui na lista de permissões for deixada não especificada, [!DNL Adobe] não poderá verificar as URLs de redirecionamento e proteger contra possíveis redirecionamentos mal-intencionados.
>
>A inclui na lista de permissões tem precedência sobre os ambientes. Limpe todos os hosts antes de usar o recurso de incluir na lista de permissões inclui na lista de permissões e, em seguida, somente os hosts permitidos pelo arquivo serão exibidos na lista de hosts. Em seguida, você poderá mover os hosts para o ambiente desejado.

Em algumas ocasiões, domínios de outros sites podem ser exibidos em seus ambientes. Um domínio é exibido na lista se chamar at.js. Por exemplo, se alguém copiar uma de suas página da Web para outro servidor, o domínio será exibido em seu ambiente. Você também poderá ver domínios de mecanismos spiders, sites de tradução ou unidades de disco locais.

Nos casos em que `mboxHost` é passada na chamada de API, a conversão é registrada para o ambiente que é transmitido. Se nenhum ambiente for passado, o host na chamada assumirá [!UICONTROL Production] como padrão.

Você também pode criar um incluo na lista de bloqueios que especifica os hosts (domínios) que não podem enviar [!DNL Target] solicitações para [!DNL Target] adicionando os hosts desejados na caixa [!UICONTROL Host Does Not Contain].

>[!NOTE]
>
>A lista [!UICONTROL Authorized Hosts] é usada para hosts [!DNL Target] e hosts de redirecionamento padrão. Adicione todos os domínios existentes aprovados para usar o [!DNL Adobe Target] JavaScript SDK (at.js) *E* todos os domínios usados nas URLs de redirecionamento padrão da ubox. Adicione quaisquer domínios semelhantes ao incluo na lista de permissões no futuro.

## Excluir um host {#section_F56355BA4BC54B078A1A8179BC954632}

Você pode excluir um host quando ele não é mais necessário.

1. Na lista [!UICONTROL Hosts], clique no ícone **[!UICONTROL Delete]**.
1. Clique em **[!UICONTROL Delete]** para confirmar a exclusão.

>[!NOTE]
>
>O host será listado novamente se alguém navegar para uma página que contenha uma solicitação [!DNL Target] no host.

## Solucionar problemas dos hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Tente as dicas de solução de problemas a seguir se tiver dificuldade com seus hosts:

**O host não aparece na lista da sua conta.**

* Atualize a página [!UICONTROL Hosts] no seu navegador.
* Confirme se a solicitação [!DNL Target] está correta, incluindo a referência à at.js.
* Tente navegar para uma das solicitações [!DNL Target] no host. É possível que nenhuma solicitação [!DNL Target] no host tenha sido renderizada em um navegador.

**Domínios aleatórios ou desconhecidos aparecem na lista [!UICONTROL Host].**

Um domínio é exibido nessa lista se uma solicitação para [!DNL Target] for feita no domínio. Frequentemente, é possível ver domínios de mecanismos spider, sites de tradutor de idiomas ou unidades de discos locais. Se o domínio listado não for um que sua equipe usa, você pode clicar em [!UICONTROL Delete] para removê-lo.

**Minha solicitação [!DNL Target] retorna /&#42; sem exibição - host mbox não autorizado &#42;/.**

Se uma solicitação [!DNL Target] for feita em um host não autorizado, ela responderá com /&#42; sem exibição - host mbox não autorizado &#42;/.
