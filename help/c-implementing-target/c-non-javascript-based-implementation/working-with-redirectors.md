---
keywords: implementação; mbox.js não javascript; redirecionador; custos por clique; receita por clique
description: 'Saiba como usar Redirecionadores em implementações de email, de forma semelhante à forma como você usa uma mbox em suas atividades do Adobe. [!DNL Target] '
title: Como Trabalho com Redirecionadores?
feature: Implementar Email
role: Developer
exl-id: 1e7b99e4-857b-4d0f-afbd-2c5ce6bf0557
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 66%

---

# Trabalhar com redirecionadores

Utilize o Redirecionador de forma similar a uma mbox em seus testes.

Redirecionadores são criados com um URL de Redirecionador especial, que carrega a mbox do Redirecionador na conta. Utilize o Redirecionador de forma similar a uma mbox em seus testes. Envie o URL de Redirecionador para sua Rede de publicidade como o link de destino do anúncio.

Use o Redirecionador para  faça o seguinte:

* Acompanhar cliques dos seus anúncios de exibição para o seu site
* Criar um relatório único e centralizado para rastrear os cliques para exibir anúncios em várias redes de anúncios
* Variar os destinos de anúncio de exibição

   Por exemplo, o mesmo banner pode acessar sua página inicial, de categoria e produto.

* Descobrir qual página de aterrissagem leva ao maior número de conversões

Para obter ajuda em decidir a configuração correta, consulte  [Implementações não baseadas em JavaScript](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

## Criar um redirecionador {#redirector}

Antes de utilizar um redirecionador, você deve criá-lo.

1. Determine as variações de destino do anúncio, incluindo o destino padrão.
1. Crie o redirecionador de URL.

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * Onde `yourclientcode` é o código de cliente da sua empresa. O código de cliente de sua empresa tem todos os caracteres em minúsculas e sem caracteres especiais.

      O código de cliente está disponível na parte superior da página [!UICONTROL Administration > Implementation] da interface [!DNL Target].

   * `redirectorlink_456` é o nome do Redirecionador mbox que aparece em sua conta para ser usado em campanhas e testes.

      Redirecionadores funcionam de forma diferente das outras mboxes, mas são exibidas como qualquer outra mbox em sua conta. Identifique o redirecionador de uma forma que seja fácil diferenciá-lo das mboxes de tipo padrão em sua conta.  Como prática recomendada, comece o nome da mbox com &quot;redirectorlink&quot;.

   * Onde `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` é o destino padrão.

      Isso deve ser codificado no URL e uma referência absoluta. Você pode usar a [Referência de codificação de URL HTML](https://www.w3schools.com/tags/ref_urlencode.asp) para codificar rapidamente seus URLs.

      >[!IMPORTANT]
      >
      >Observe que com o Redirecionador você pode ser exposto a um risco de Vulnerabilidade de Redirecionamento Aberto. Para evitar o uso não autorizado de links Redirecionadores por terceiros, recomendamos que você use &quot;hosts autorizados&quot; para lista de permissões os domínios padrão de URL de redirecionamento. O Target usa hosts para lista de permissões domínios aos quais você deseja permitir redirecionamentos. Para obter mais informações, consulte [Criar Lista de permissões que especificam hosts autorizados a enviar chamadas de mbox para o Target](/help/administrating-target/hosts.md#allowlist) em *Hosts*.

1. Valide o redirecionador.
   1. *Prática* recomendada de segurança: Certifique-se de que o domínio usado no Redirecionador é incluir na lista de permissões, conforme indicado acima. Se você usar um domínio que não é incluir na lista de permissões, o Adobe bloqueará qualquer chamada para esse domínio para impedir que atores mal-intencionados usem o Redirecionador para domínios potencialmente mal-intencionados.
   1. Insira o URL do redirecionador no navegador e atualize a página.
   1. Efetue logon em sua conta, atualize a lista de mbox e verifique se o novo redirecionador está indicado como uma mbox.
1. Se você vai testar destinos diferentes para um anúncio, crie [Ofertas de redirecionamento](/help/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA) para cada versão.
1. Crie uma campanha.

   Consulte [Implementações não baseadas em JavaScript](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) para a configuração correta para atingir seus objetivos.
1. Faça o controle de qualidade da campanha.

   Crie uma página de testes com um `<a href>` contendo o URL Redirecionador. Exemplo:

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. Verifique se todos as experiências, o conteúdo padrão e os relatórios estão funcionando corretamente em todos os tipos de navegadores, para todos os seus ambientes.

   >[!NOTE]
   >
   >* Redirecionadores não são suportados pela Visualização de oferta ou Procurar por mbox. Visualize as experiências diretamente em um navegador.
   >* `mboxDebug` não funciona com Redirecionadores.


1. Envie o URL completo do Redirecionador para sua rede de publicidade como destino do anúncio.

## Usar o redirecionador para enviar Custos por clique e Receita por clique {#concept_3078EF48E9C44B34992D62AAB9628853}

Informações sobre o uso de um redirecionador para transmitir os custos por clique e a receita por clique.

### Enviar custo por clique {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

Use o redirecionador para passar os custos por clique.

>[!NOTE]
>
>A prática recomendada é determinar o valor de custo usando a métrica de envolvimento **Pontuação por visita**.

Adicione `&mboxPageValue=-value` à URL. Observe o valor negativo.

Exemplo: Para um custo de 10 centavos por clique:

```
https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
&mboxPageValue=-0.1&mboxDefault=​https://www.yourcompany.com/usualdestination.htm
```

### Enviar receita por clique   {#section_3E48AC465E7D42DAAC51B4BFF83F64B1}

Use o redirecionador para passar a receita por clique.

>[!NOTE]
>
>A prática recomendada é determinar o valor da receita usando a métrica de envolvimento **Pontuação por visita**.

Adicione `&mboxPageValue=value` à URL.

Exemplo: Para uma receita de 10 centavos por clique.

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```
