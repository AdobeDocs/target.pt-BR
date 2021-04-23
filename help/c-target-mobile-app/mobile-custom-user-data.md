---
keywords: aplicativo móvel, enviar dados aplicativo móvel, aplicativo móvel target, dados de usuários personalizados móveis, dados personalizados de aplicativo móvel
description: Saiba como enviar informações adicionais sobre a localização ou o usuário para o Adobe [!DNL Target] como pares de nome-valor para ajudá-lo a criar públicos-alvo personalizados.
title: Como envio dados de usuário personalizados em um aplicativo iOS?
feature: Implementar dispositivos móveis
role: Developer
exl-id: c64219ec-8d60-4d05-b2b8-103e8ffcaefc
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 89%

---

# iOS - Enviar dados do usuário personalizados

Você pode enviar informações adicionais sobre a localização ou o usuário para o Target como pares de nome-valor.

Essa informação pode ser usada para construir públicos-alvo personalizados (por exemplo, usuários com mais de 25.000 milhas) e em relatórios.

Existem dois tipos de parâmetros que você pode enviar com uma chamada do Target:

* parâmetros de mbox

   Parâmetros mbox não são persistentes entre sessões.
* Parâmetros do perfil

   Parâmetros de perfil são armazenados no perfil do visitante e são persistentes entre sessões. Parâmetros mbox não persistem. Enquanto algumas chaves são reservadas, tanto os parâmetros de perfil e de mbox podem ser pares de valores chave personalizados.

Embora algumas chaves são reservadas, tanto os parâmetros de perfil e de mbox podem conter pares de valores chave personalizados.

1. Crie um dicionário.

   Primeiro, crie um dicionário com os valores que você quer passar para o Target. Por conveniência, adicione isso dentro do método `welcomeMessageCampaign` para que você não tenha que se preocupar com o alcance.

   A seguir está uma amostra de dicionário. Você pode cipar e colar isto dentro de `(void)welcomeMessageCampaign`. Os valores para chaves como `userLevel` e `userMiles` são codificados neste exemplo. No geral, você passa nas variáveis correspondentes.

   ```
   NSDictionary *targetParams = [[NSDictionary alloc] initWithObjectsAndKeys: 
                                 @"platinum",@"userLevel", 
                                 @26500,@"userMiles", 
                                 @"1067007",@"entity.id", 
                                 @"dealsapp.qa", @"host", 
                                 @"fashion",@"entity.categoryId", 
                                 @"millenial", @"profile.persona", 
                                 @"cohort_5", @"profile.cohort", 
                                 nil];
   ```

   * Chaves com o prefixo profile (por exemplo, `profile.persona`) são armazenadas no perfil do usuário.

      Estes atributos e perfil podem ser usados entre diferentes atividades e canais.

   * Chaves que não possuem nenhum perfil (por exemplo, `userMiles`) são parâmetros mbox.

      Estes parâmetros só estão disponíveis durante a sessão.

   * Chaves com o prefixo entity (por exemplo, `entity.category.id`) são usadas para recomendações de produto.

1. Verifique os dados.
   1. Na aplicação `didFinishLaunchingWithOptions`, exclua o comentário ou adicione `[ADBMobile setDebugLogging:YES];`.

      Isso imprime relatórios detalhados de depuração.
   1. Compile o aplicativo.
   1. Verifique se os parâmetros foram passados na chamada de definição.

      Procure pelo seu nome de local de definição no seu console de depuração. Você verá uma chamada para `YOUR-CLIENT-CODE.tt.omtrdc.net` com todos parâmetros que você acabou de passar.

      ![](assets/mobile-debug.png)
   Você pode construir audiência e restringir ou definir a exibição de conteúdo usando estes parâmetros no Target Standard.
