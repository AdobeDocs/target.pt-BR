---
description: Utilize o Redirecionador de forma similar a uma mbox em seus testes.
keywords: implementação; mbox.js não javascript; redirecionador; custos por clique; receita por clique
seo-description: Utilize o Redirecionador de forma similar a uma mbox em seus testes.
seo-title: Trabalhar com redirecionadores
solution: Target
subtopic: Introdução
title: Trabalhar com redirecionadores
topic: Padrão
uuid: 79d7caf6-5693-4bb3-9131-8d1ae420fa5e
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Trabalhar com redirecionadores{#work-with-redirectors}

Utilize o Redirecionador de forma similar a uma mbox em seus testes.

Redirecionadores são criados com um URL de Redirecionador especial, que carrega a mbox do Redirecionador na conta. Utilize o Redirecionador de forma similar a uma mbox em seus testes. Envie o URL de Redirecionador para sua Rede de publicidade como o link de destino do anúncio.

Use o Redirecionador para faça o seguinte:

* Acompanhar cliques dos seus anúncios de exibição para o seu site
* Criar um relatório único e centralizado para rastrear os cliques para exibir anúncios em várias redes de anúncios
* Variar os destinos de anúncio de exibição

   Por exemplo, o mesmo banner pode acessar sua página inicial, de categoria e produto.

* Descobrir qual página de aterrissagem leva ao maior número de conversões

Para obter ajuda em decidir a configuração correta, consulte [Implementações não baseadas em JavaScript](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

## Criando um Redirecionador {#task_76608B0F73FC45C4A9F125B894DCF821}

Antes de utilizar um redirecionador, você deve criá-lo.

1. Determine as variações de destino do anúncio, incluindo o destino padrão.
1. Crie o redirecionador de URL.

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * Onde `yourclientcode` está o código de cliente da sua empresa. O código de cliente de sua empresa tem todos os caracteres em minúsculas e sem caracteres especiais.

      * **at.js**: Seu código de cliente está disponível no topo da página [!UICONTROL Configuração &gt; Implementação &gt; Editar configurações] da at.js da [!DNL Target] interface.

      * **mbox.js**: Seu código de cliente está disponível no topo da [!UICONTROL página Configurar &gt; Implementação &gt; Editar configurações mbox.js.]
   * `redirectorlink_456` é o nome do Redirecionador mbox que aparece em sua conta para ser usado em campanhas e testes.

      Redirecionadores funcionam de forma diferente das outras mboxes, mas são exibidas como qualquer outra mbox em sua conta. Identifique o redirecionador de uma forma que seja fácil diferenciá-lo das mboxes de tipo padrão em sua conta.  Como prática recomendada, comece o nome da mbox com &quot;redirectorlink&quot;.

   * Onde `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` é o destino padrão.

      Isso deve ser codificado no URL e uma referência absoluta. Você pode usar a Referência de codificação de URL [HTML](https://www.w3schools.com/tags/ref_urlencode.asp) para codificar rapidamente seus urls. |



1. Valide o redirecionador.
   1. Insira o URL do redirecionador no navegador e atualize a página.
   1. Efetue logon em sua conta, atualize a lista de mbox e verifique se o novo redirecionador está indicado como uma mbox.
1. Se você vai testar destinos diferentes para um anúncio, crie [Ofertas de redirecionamento](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA) para cada versão.
1. Crie uma campanha.

   Consulte [Implementações não baseadas em JavaScript](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) para a configuração correta para atingir seus objetivos.
1. Faça o controle de qualidade da campanha.

   Crie uma página de testes com um `<a href>` contendo o URL Redirecionador. Exemplo:

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. Verifique se todos as experiências, o conteúdo padrão e os relatórios estão funcionando corretamente em todos os tipos de navegadores, para todos os seus ambientes.

   >[!NOTE] {class=&quot;- topic/note &quot;}
   >
   >* Redirecionadores não são suportados pela Visualização de oferta ou Procurar por mbox. Visualize as experiências diretamente em um navegador.
   >* `mboxDebug` não funciona com Redirecionadores.


1. Envie o URL completo do Redirecionador para sua rede de publicidade como destino do anúncio.

## Usar o Redirecionador para enviar Custos por clique e Receita por clique {#concept_3078EF48E9C44B34992D62AAB9628853}

Informações sobre o uso de um redirecionador para transmitir os custos por clique e a receita por clique.

### Enviar custo por clique {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

Use o redirecionador para passar os custos por clique.

>[!NOTE]
>
>A prática recomendada é determinar o valor de custo usando a métrica de envolvimento **Pontuação por visita** , conforme descrito em [Envolvimento](https://marketing.adobe.com/resources/help/en_US/tnt/help/c_Capturing_Engagement.html).

Adicione `&mboxPageValue=-value` à URL. Observe o valor negativo.

Exemplo: Para um custo de 10 centavos por clique:

```
https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
&mboxPageValue=-0.1&mboxDefault=​https://www.yourcompany.com/usualdestination.htm
```

### Enviar receita por clique {#section_3E48AC465E7D42DAAC51B4BFF83F64B1}

Use o redirecionador para passar a receita por clique.

>[!NOTE]
>
>A prática recomendada é determinar o valor da receita usando a métrica de envolvimento **Pontuação por visita** , conforme descrito em [Envolvimento](https://marketing.adobe.com/resources/help/en_US/tnt/help/c_Capturing_Engagement.html).

Adicione `&mboxPageValue=value` à URL.

Exemplo: Para uma receita de 10 centavos por clique.

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```
