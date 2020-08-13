---
keywords: host;hosts;host group;troubleshooting;best practices;ubox;redirects;redirect;whitelist;allowlist;blacklist;blocklist
description: Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.
title: Hosts
feature: hosts and environments
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 27%

---


# Hosts{#hosts}

Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.

O objetivo principal do gerenciamento de hosts é assegurar que nenhum conteúdo inativo seja exibido acidentalmente nos sites. Host management also lets you separate report data by [environment](/help/administrating-target/environments.md).

Um host é qualquer domínio do qual uma [!DNL Target] solicitação é feita. Em um site, geralmente é a `location.hostname` propriedade do URL que faz a [!DNL Target] solicitação.

Por padrão, [!DNL Target] não limita um host que pode fazer [!DNL Target] solicitações e receber [!DNL Target] respostas. Quando novos hosts fazem solicitações, elas funcionam automaticamente. Isso também permite o teste em domínios diferentes que você não conhece ou que não pode antecipar. Se desejar substituir esse comportamento padrão, você pode configurar uma  lista de permissões ou lista de bloqueios para limitar com quais hosts trabalharão [!DNL Target].

Para gerenciar hosts, clique em **[!UICONTROL Administração]** > **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Recognizing hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Para reconhecer um host e adicioná-lo à lista [!UICONTROL Hosts] , as seguintes condições devem ser atendidas:

* At least one [!DNL Target] request must exist on the host
* Uma página no host deve ter  o seguinte:

   * Uma referência precisa do at.js ou mbox.js
   * Uma [!DNL Target] solicitação ou uma [!DNL Target] solicitação global gerada automaticamente

* The page with the [!DNL Target] request must be viewed in a browser

After the page is viewed, the host is listed in the [!UICONTROL Hosts] list, allowing you to manage it in an environment, as well as preview and launch activities and tests.

>[!NOTE]
>
>Isso inclui quaisquer servidores de desenvolvimento pessoal.

Após adicionar um host na lista de [!UICONTROL Host], certifique-se de que o host seja reconhecido.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Hosts]**.
1. Se o seu host não estiver listado, atualize seu navegador. 


   By default, a newly recognized host is placed in the [!UICONTROL Production] environment. Esse é o ambiente mais seguro porque ele não permite que atividades inativas sejam visualizadas nesses hosts.

1. (Condicional) Clique no ícone **[!UICONTROL Mover]** ( ícone ![mover](/help/administrating-target/assets/icon-move.png) ) para mover o host para [!UICONTROL Desenvolvimento], [!UICONTROL Armazenamento temporário]ou outro ambiente.

>[!NOTE]
>
>The [!UICONTROL Production] environment cannot be deleted, even if you rename it. Pressupõe-se que este seja o local em que você disponibiliza atividades ativas e testes finais e aprovados. O ambiente padrão não permite que campanhas inativas sejam visualizadas.

## Sort or search the Hosts list {#section_068B23C9D8224EB78BC3B7C8580251B0}

To sort the [!UICONTROL Hosts] list, click any column header ([!UICONTROL Name], [!UICONTROL Environment], or [!UICONTROL Last Requested]) to sort the list in ascending or descending order.

To search the [!UICONTROL Hosts] list, type a search term in the [!UICONTROL Search Hosts] box.

## Create allowlists that specify hosts that are authorized to send Target requests to Target. {#allowlist}

You can create an allowlist that specifies hosts (domains) that are authorized to send [!DNL Target] requests to [!DNL Target]. Todos os outros hosts que geram solicitações obterão uma resposta de erro de autorização comentada. By default, any host that contains a [!DNL Target] request registers with [!DNL Target] in the [!UICONTROL Production] environment and has access to all active and approved activities. If this is not the desired approach, you can instead use the allowlist to record specific hosts that are eligible to make [!DNL Target] requests and receive [!DNL Target] content. All hosts will continue to display in the [!UICONTROL Hosts] list, and environments can still be used to group these hosts and assign different levels to each, such as whether the host can see active and/or inactive activities.

Para criar uma  lista de permissões:

1. Na lista [!UICONTROL Hosts] , clique em **[!UICONTROL Autorizar hosts]**.
1. Ative a opção **[!UICONTROL Ativar hosts autorizados para alternar delivery]** de conteúdo.
1. Add the desired hosts in the **[!UICONTROL Host contains]** box, as desired.

   Vários hosts podem ser listados, cada um na própria linha.

1. Add the desired hosts in the **[!UICONTROL Host does not contains]** box, as desired.

   Vários hosts podem ser listados, cada um na própria linha.

1. Clique em **[!UICONTROL Salvar]**.

If a [!DNL Target] request is made on an unauthorized host, the call will respond with `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Práticas** recomendadas de segurança: Se você usar a funcionalidade de ubox [!DNL Target], observe que essa lista de permissões também controlará a lista de domínios para os quais seus [redirecionadores](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) podem navegar. Certifique-se de adicionar quaisquer domínios aos quais você deseja redirecionar ao usar o ubox como parte da implementação. Se a  de lista de permissões não for especificada, não será possível verificar os URLs de redirecionamento e proteger contra possíveis redirecionamentos mal-intencionados. [!DNL Adobe]
>
>A lista de permissões tem precedência sobre os ambientes. Você deve apagar todos os hosts antes de usar o recurso de  de lista de permissões e, em seguida, apenas os hosts permitidos pela lista de permissões serão exibidos na lista dos hosts. Em seguida, você poderá mover os hosts para o ambiente desejado.

Em algumas ocasiões, domínios de outros sites podem ser exibidos em seus ambientes. Um domínio é exibido na lista se o domínio fizer uma chamada para seu at.js ou mbox.js. Por exemplo, se alguém copiar uma de suas página da Web para outro servidor, o domínio será exibido em seu ambiente. Você também poderá ver domínios de mecanismos spiders, sites de tradução ou unidades de disco locais.

Nos casos em que `mboxHost` é passada na chamada de API, a conversão é registrada para o ambiente que é transmitido. If no environment is passed, the host in the call defaults to [!UICONTROL Production].

You can also create a denylist that specifies hosts (domains) than cannot send [!DNL Target] requests to [!DNL Target] by adding the desired hosts in the [!UICONTROL Host Does Not Contain] box.

>[!NOTE]
>
>Como a lista Hosts Autorizados é usada para hosts [!DNL Target] e hosts de redirecionamento padrão, você deve adicionar todos os domínios existentes aprovados para usar o [!DNL Adobe Target] Javascript SDK (at.js) ** E todos os domínios usados em URLs de redirecionamento padrão da ubox. Você também deve adicionar novos domínios semelhantes à lista de permissões no futuro.

## Delete a host {#section_F56355BA4BC54B078A1A8179BC954632}

Você pode excluir um host quando ele não é mais necessário.

1. From the [!UICONTROL Hosts] list, click the **[!UICONTROL Delete]** icon.
1. Clique em **[!UICONTROL Excluir]** para confirmar a exclusão.

>[!NOTE]
>
>O host será listado novamente se alguém navegar até uma página que contém uma [!DNL Target] solicitação no host.

## Solucionar problemas dos hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Tente as dicas de solução de problemas a seguir se tiver dificuldade com seus hosts:

**O host não aparece na lista da sua conta.**

* Atualize a página [!UICONTROL Hosts] no seu navegador.
* Confirme se a [!DNL Target] solicitação está correta, incluindo a referência a at.js ou mbox.js.
* Try browsing to one of the [!DNL Target] requests on the host. It&#39;s possible that no [!DNL Target] request on the host was ever rendered in a browser.

**Domínios aleatórios ou desconhecidos são exibidos nas listas de grupo de[!UICONTROL Hosts].**

A domain appears in this list if a request to [!DNL Target] is made from the domain. Frequentemente, é possível ver domínios de mecanismos spider, sites de tradutor de idiomas ou unidades de discos locais. Se o domínio listado não for o domínio utilizado pela sua equipe, clique em [!UICONTROL Excluir] para removê-lo.

**Minha[!DNL Target]solicitação retorna /* sem exibição - host mbox não autorizado */.**

If a [!DNL Target] request is made on an unauthorized host, the request will respond with /* no display - unauthorized mbox host */.
