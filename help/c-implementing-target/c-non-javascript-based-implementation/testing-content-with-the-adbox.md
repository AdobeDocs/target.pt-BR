---
description: Use uma AdBox para usar imagens em uma implementação externa.
keywords: implementação; mbox.js não javascript; mbox; adbox
seo-description: Use uma AdBox para usar imagens em uma implementação externa.
seo-title: Criar uma AdBox para uma imagem
solution: Target
subtopic: Introdução
title: Criar uma AdBox para uma imagem
topic: Padrão
uuid: 6b1763f7-08de-4bde-9e20-e79b92b02f20
translation-type: tm+mt
source-git-commit: ece87434c94501eeed1d6af9cb2a92f8585775b7

---


# Criar uma AdBox para uma imagem{#create-an-adbox-for-an-image}

Use uma AdBox para usar imagens em uma implementação externa.

Uma AdBox é como uma mbox, mas é controlada por um URL, em vez de um JavaScript. AdBoxes são criadas com um URL adbox especial que carrega uma mbox de &quot;anúncio&quot; (ou adbox) na conta da Adobe. Use a AdBox no lugar de uma mbox em suas atividades. Use o URL da AdBox em vez de uma referência direta da imagem em um email ou outras implementações não-JavaScript.

Para obter ajuda para selecionar a configuração correta, consulte [Implementações não baseadas em JavaScript](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

1. Criar o URL AdBox:

   ```
   https://myClientCode.tt.omtrdc.net/m2/myClientCode/ubox/
   image?mbox=emailHeroImage123_320x200
   mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif
   ```

   * Onde `myClientCode` está o código de cliente da sua empresa. O código de cliente de sua empresa tem todos os caracteres em minúsculas e sem caracteres especiais.

      * **at.js**: Seu código de cliente está disponível no topo da página [!UICONTROL Configuração &gt; Implementação &gt; Editar configurações] da at.js da [!DNL Target] interface.

      * **mbox.js**: Seu código de cliente está disponível no topo da [!UICONTROL página Configurar &gt; Implementação &gt; Editar configurações mbox.js.]
   * Onde `image` é o tipo de chamada. Nesse caso, uma imagem.

   * Onde `emailHeroImage123_320x200` está o nome da adbox.

   * Onde `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif` é o conteúdo padrão da mbox. Isso deve ser uma imagem.

      Isso deve ser codificado no URL e uma referência absoluta. Você pode usar a Referência de codificação de URL [HTML](https://www.w3schools.com/tags/ref_urlencode.asp) para codificar rapidamente seus urls.


1. Crie [Ofertas de redirecionamento](../../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) para cada imagem alternativa.

   >[!NOTE] {class=&quot;- topic/note &quot;}
   >
   >As adboxes devem ser carregadas com uma Oferta de redirecionamento ou com a oferta de conteúdo padrão. Outros tipos de ofertas não funcionarão. Como a AdBox é um URL, ela só pode exibir os URLs que recebe, portanto, apenas a Oferta de redirecionamento funciona.

1. Crie a atividade.

   Consulte [Implementações não baseadas em JavaScript](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) para a configuração correta para atingir suas metas.
1. Faça o controle de qualidade da atividade.

   Como prática recomendada, crie uma página de teste e verifique se todas as experiências, o conteúdo padrão e os relatórios estão funcionando corretamente em todos os tipos de navegadores, para todos os seus ambientes. 1. Inicie a atividade.
