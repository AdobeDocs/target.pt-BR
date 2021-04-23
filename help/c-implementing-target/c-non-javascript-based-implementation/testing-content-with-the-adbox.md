---
keywords: implementação; mbox.js não javascript; mbox; adbox
description: Use uma AdBox para fornecer imagens em uma implementação externa usando o Adobe Target. Uma AdBox é como uma mbox, mas é controlada por um URL em vez de JavaScript.
title: Como criar uma AdBox para uma imagem?
feature: Implementar Email
role: Developer
exl-id: c66cfbc2-633a-46f2-8d9f-dbd18f7e880e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 73%

---

# Criar uma AdBox para uma imagem

Use uma AdBox para fornecer imagens em uma implementação externa usando o Adobe Target.

Uma AdBox é como uma mbox, mas é controlada por um URL, em vez de um JavaScript. AdBoxes são criadas com um URL AdBox especial que carrega uma mbox de &quot;anúncio&quot; (ou AdBox) na conta da Adobe. Use a AdBox no lugar de uma mbox em suas atividades. Use o URL da AdBox em vez de uma referência direta da imagem em um email ou outras implementações não-JavaScript.

Para obter ajuda para selecionar a configuração correta, consulte  [Implementações não baseadas em JavaScript](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

1. Criar o URL AdBox:

   ```
   https://myClientCode.tt.omtrdc.net/m2/myClientCode/ubox/
   image?mbox=emailHeroImage123_320x200&
   mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif
   ```

   * Onde `myClientCode` é o código de cliente da sua empresa. O código de cliente de sua empresa tem todos os caracteres em minúsculas e sem caracteres especiais.

      O código de cliente está disponível na parte superior da página [!UICONTROL Administration > Implementation] da interface [!DNL Target].

   * Onde `image` é o tipo de chamada. Nesse caso, uma imagem.

   * Onde `emailHeroImage123_320x200` é o nome da AdBox.

   * Onde `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif` é o conteúdo padrão da mbox. Isso deve ser uma imagem.

      Isso deve ser codificado no URL e uma referência absoluta. Você pode usar a [Referência de codificação de URL HTML](https://www.w3schools.com/tags/ref_urlencode.asp) para codificar rapidamente seus URLs.

1. Crie [Ofertas de redirecionamento](/help/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) para cada imagem alternativa.

   >[!NOTE]
   >
   >As AdBoxes devem ser carregadas com uma Oferta de redirecionamento ou com a oferta de conteúdo padrão. Outros tipos de ofertas não funcionarão. Como a AdBox é um URL, ela só pode exibir os URLs que recebe, portanto, apenas a Oferta de redirecionamento funciona.

1. Crie a atividade.

   Consulte [Implementações não baseadas em JavaScript](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) para a configuração correta para atingir suas metas.
1. Faça o controle de qualidade da atividade.

   Como prática recomendada, crie uma página de teste e verifique se todas as experiências, o conteúdo padrão e os relatórios estão funcionando corretamente em todos os tipos de navegadores, para todos os seus ambientes.

1. Inicie a atividade.
