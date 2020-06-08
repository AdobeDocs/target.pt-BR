---
keywords: host;hosts;host group;troubleshooting;best practices;ubox;redirects;redirect;whitelist;allowlist;blacklist;blocklist
description: Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.
title: Hosts
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: cf69c1d8472088d5f6a6b7250bedd1048cac5c10
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 57%

---


# Hosts{#hosts}

Organize seus sites e ambientes de pré-produção para fácil gerenciamento e geração de relatórios separados.

O objetivo principal do gerenciamento de hosts é assegurar que nenhum conteúdo inativo seja exibido acidentalmente nos sites. Host management also lets you separate report data by [environment](/help/administrating-target/environments.md).

Um host é qualquer servidor da Web (ou domínio da Web) de onde você serve conteúdo em qualquer fase do seu projeto. Todo host que serve um mbox é reconhecido.

Os hosts são agrupados em ambientes para facilitar o gerenciamento. Por exemplo, você pode ter dezenas de hosts agrupados em dois ou três ambientes. The preset environments include [!UICONTROL Production], [!UICONTROL Staging], and [!UICONTROL Development]. Você pode adicionar novos ambientes e renomear seus ambientes, se desejado.

One environment, the default environment, is pre-named [!UICONTROL Production]. Esse ambiente padrão não pode ser removido, mesmo que você o renomeie. O [!DNL Target] parte do princípio que este é o local onde você disponibiliza atividades finais, aprovadas e testes.

When an mbox request is received from new websites or domains, these new domains always appear in the [!UICONTROL Production] environment. The [!UICONTROL Production] environment cannot have its settings changed, so unknown or new sites are guaranteed to see only content that is active and ready. O gerenciamento de hosts também permite garantir a qualidade de novas atividades e do conteúdo em seus ambientes de teste, armazenamento temporário e desenvolvimento, antes das atividades serem ativadas.

[!DNL Target] não limita um host que pode enviar e receber mboxes, portanto, quando novos servidores ou domínios entram em contato, eles funcionam automaticamente (a menos que você tenha configurado uma lista de permissões ou uma lista de bloqueios). Isso também permite o teste de publicidade em domínios diferentes, desconhecidos ou não previstos.

Para gerenciar hosts, clique em **[!UICONTROL Administração]** > **[!UICONTROL Hosts]**.

![](assets/hosts_list.png)

## Recognizing hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Para reconhecer um host e adicioná-lo à lista [!UICONTROL Hosts] , as seguintes condições devem ser atendidas:

* Pelo menos uma mbox deve existir no host
* Uma página no host deve ter  o seguinte:

   * Uma referência precisa do at.js ou mbox.js
   * Uma mbox ou uma chamada de mbox global automaticamente gerada

* A página com a mbox deve ser visualizada em um navegador

Após a visualização de uma página, o host é adicionado na lista de [!UICONTROL Hosts], permitindo que você gerencie-o em uma ambiente, bem como, visualize e inicie atividades e testes.

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>Isso inclui quaisquer servidores de desenvolvimento pessoal.

Após adicionar um host na lista de [!UICONTROL Host], certifique-se de que o host seja reconhecido.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Hosts]**.
1. Se o seu host não estiver listado, atualize seu navegador. 


   By default, a newly recognized host is placed in the [!UICONTROL Production] environment. Esse é o ambiente mais seguro porque ele não permite que atividades inativas sejam visualizadas nesses hosts.

1. (Condicional) Clique no ícone Mover ( ícone ![](/help/administrating-target/assets/icon-move.png) Mover ) para mover o host para o [!UICONTROL Desenvolvimento], [!UICONTROL Armazenamento temporário]ou outro ambiente.

>[!NOTE]
>
>The [!UICONTROL Production] environment cannot be deleted, even if you rename it. Pressupõe-se que este seja o local em que você disponibiliza atividades ativas e testes finais e aprovados. O ambiente padrão não permite que campanhas inativas sejam visualizadas.

## Sort or search the Hosts list {#section_068B23C9D8224EB78BC3B7C8580251B0}

To sort the [!UICONTROL Hosts] list, click any column header ([!UICONTROL Name], [!UICONTROL Environment], or [!UICONTROL Last Requested]) to sort the list in ascending or descending order.

To search the [!UICONTROL Hosts] list, type a search term in the [!UICONTROL Search Hosts] box.

## Create allowlists that specify hosts that are authorized to send mbox calls to Target. {#whitelist}

You can create an allowlist that specifies hosts (domains) that are authorized to send mbox calls to [!DNL Target]. Todos os outros hosts que estiverem gerando chamadas receberão uma resposta comentada do erro de autorização. Por padrão, qualquer host que contenha uma chamada de mbox é registrado no [!DNL Target], dentro do ambiente Produção, e tem acesso a todas as atividades ativas e aprovadas. If this is not the desired approach, you can instead use the allowlist to record specific hosts that are eligible to make mbox calls and receive [!DNL Target] content. Todos os hosts continuarão a ser exibidos na lista de [!UICONTROL Hosts], e os ambientes ainda poderão ser usados para agrupar estes hosts e designar níveis diferentes a cada um, como decidir se o host pode ver campanhas ativas e/ou inativas.

Para criar uma lista permitida:

1. Na lista [!UICONTROL Hosts] , clique em **[!UICONTROL Autorizar hosts]**.
1. Ative a opção **[!UICONTROL Ativar hosts autorizados para alternar delivery]** de conteúdo.
1. Add the desired hosts in the **[!UICONTROL Host contains]** box, as desired.

   Vários hosts podem ser listados, cada um na própria linha.

1. Add the desired hosts in the **[!UICONTROL Host does not contains]** box, as desired.

   Vários hosts podem ser listados, cada um na própria linha.

1. Clique em **[!UICONTROL Salvar]**.

Se uma chamada de mbox for feita em um host não autorizado, a chamada responderá com `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Práticas** recomendadas de segurança: Se você usar a funcionalidade de ubox [!DNL Target], observe que essa lista de permissões também controlará a lista de domínios para os quais seus [redirecionadores](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) podem navegar. Certifique-se de adicionar quaisquer domínios aos quais você deseja redirecionar ao usar o ubox como parte da implementação. Se a lista de permissão não for especificada, a Adobe não poderá verificar os URLs de redirecionamento e proteger contra possíveis redirecionamentos mal-intencionados.
>
>A lista de permissão tem precedência sobre os ambientes. Você deve limpar todos os hosts antes de usar o recurso de lista permitida, e então apenas os hosts permitidos pela lista permitida aparecem na lista dos hosts. Em seguida, você poderá mover os hosts para o ambiente desejado.

Em algumas ocasiões, domínios de outros sites podem ser exibidos em seus ambientes. Um domínio é exibido na lista se o domínio fizer uma chamada para seu at.js ou mbox.js. Por exemplo, se alguém copiar uma de suas página da Web para outro servidor, o domínio será exibido em seu ambiente. Você também poderá ver domínios de mecanismos spiders, sites de tradução ou unidades de disco locais.

Nos casos em que `mboxHost` é passada na chamada de API, a conversão é registrada para o ambiente que é transmitido. If no environment is passed, the host in the call defaults to [!UICONTROL Production].

Você também pode criar uma lista negra que especifica os hosts (domínios) que não podem enviar chamadas da mbox para o [!DNL Target] ao adicionar os hosts desejados na caixa [!UICONTROL Host não contêm].

>[!NOTE]
>
>Como a lista Hosts Autorizados é usada para hosts mbox e hosts de redirecionamento padrão, você deve adicionar todos os domínios existentes aprovados para usar o SDK do Javascript do Público alvo da Adobe (at.js) ** E todos os domínios usados em urls de redirecionamento padrão da ubox. Você também deve adicionar novos domínios semelhantes à lista de permissões no futuro.

## Delete a host {#section_F56355BA4BC54B078A1A8179BC954632}

Você pode excluir um host quando ele não é mais necessário.

1. From the [!UICONTROL Hosts] list, click the **[!UICONTROL Delete]** icon.
1. Clique em **[!UICONTROL Excluir]** para confirmar a exclusão.

>[!NOTE]
>
>O host será listado novamente se alguém navegar até uma página com mbox no host.

## Solucionar problemas dos hosts {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Práticas recomendadas para gerenciamento e solução de problemas de host no [!DNL Adobe Target].

Tente as dicas de solução de problemas a seguir se tiver dificuldade com seus hosts:

**O host não é exibido na lista de mbox da sua conta.**

* Atualize a página [!UICONTROL Hosts] no seu navegador.
* Confirme se o código da mbox está correto, incluindo a referência a at.js ou mbox.js.
* Tente navegar para uma das mboxes no host. É possível que nenhuma mbox no host tenha sido renderizada em um navegador.

**Domínios aleatórios ou desconhecidos são exibidos nas listas de grupo de[!UICONTROL Hosts].**

Um domínio é exibido nessa lista se uma chamada para o [!DNL Target] for feita no domínio. Frequentemente, é possível ver domínios de mecanismos spider, sites de tradutor de idiomas ou unidades de discos locais. Se o domínio listado não for o domínio utilizado pela sua equipe, clique em [!UICONTROL Excluir] para removê-lo.

**Minha chamada da mbox retorna /* sem exibição - host do mbox não autorizado */.**

Se uma chamada de mbox for feita em um host autorizado, a chamada responderá com /* sem exibição - host mbox não autorizado */.
