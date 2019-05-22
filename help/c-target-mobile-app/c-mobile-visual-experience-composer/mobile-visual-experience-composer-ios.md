---
description: O Adobe Target Mobile Experience Composer (VEC) permite que os desenvolvedores façam uma configuração única em seus aplicativos móveis iOS e permitem que os profissionais de marketing utilizem os recursos do VEC do aplicativo móvel.
keywords: VEC do aplicativo móvel; compositor de experiência visual móvel; opções do compositor de experiência móvel; configurando; ios; apple
seo-description: O Adobe Target Mobile Experience Composer (VEC) permite que os desenvolvedores façam uma configuração única em seus aplicativos móveis iOS e permitem que os profissionais de marketing utilizem os recursos do VEC do aplicativo móvel.
seo-title: iOS - Configuração do aplicativo móvel
solution: Target
title: iOS - Configuração do aplicativo móvel
topic: Padrão
uuid: 6db4f06a-d8f4-4192-af6f-917594e721e6
translation-type: tm+mt
source-git-commit: 5f58e6dc0e91a3341d73273edf953206a95d6450

---


# iOS - Configuração do aplicativo móvel{#ios-set-up-the-mobile-app}

O Adobe Target Mobile App Visual Experience Composer (VEC) permite que os desenvolvedores façam uma configuração única em seus aplicativos móveis iOS e permitem que os profissionais de marketing utilizem os recursos do VEC do aplicativo móvel.

Para obter mais informações sobre como habilitar a extensão do Adobe Target VEC, consulte [Adobe Target - Visual Experience Composer](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) nos sdks do *Adobe Experience Platform Mobile*.

## Incluir o SDK móvel e a biblioteca do Target {#sdk-library}

1. Adicione a biblioteca ao seu projeto por meio dos Cocoapods [!DNL Podfile] adicionando pods &quot;`ACPTargetVEC`.
1. Abra o projeto do aplicativo Objective-C no XCode.
1. Vá para as configurações de compilação do projeto e defina «Sempre incorporar bibliotecas padrão» como Yes se já não estiver configurado.
1. Nas configurações de criação do projeto, encontre “Outros sinalizadores de vinculador” e adicione `$(inherited)` se não estiver lá.
1. Somente para projetos do objective-C - Crie um arquivo swift para criar o cabeçalho de ligação. Configurarei seu ambiente de aplicativo para o Swift.
1. Adicione o manipulador de deeplink:

   1. Nas configurações do projeto do aplicativo, clique em **[!UICONTROL Informações]**.
   1. Em Tipos **[!UICONTROL de URL]**, clique no triângulo para abri-lo e clique no Sinal de adição para adicionar um novo campo.
   1. Adicione as seguintes informações:

      * Identificador: `com.adobe.sdktest`
      * Esquemas de URL: `vectester`
      * Função: Editor
   1. Clique nas configurações do projeto do aplicativo &gt; **[!UICONTROL Geral]**.
   1. Clique novamente nas configurações do projeto do aplicativo &gt; **[!UICONTROL Informações]para garantir que as configurações foram salvas.**

      Com o tipo de URL de exemplo, o esquema de URL do aplicativo será:

      ```
      vectester://com.adobe.sdktest
      ```


1. No XCode, abra o arquivo [!DNL AppDelegate].
1. Na parte superior do arquivo, adicione a seguinte linha no final das importações.

   `#import "ACPTargetVEC.h"`

   Se você estiver usando o Swift, adicione a seguinte linha:

   `import ACPTargetVEC`

1. No arquivo [!DNL AppDelegate], adicione a seguinte linha em `AppDelegate::application:didFinishLaunchingWithOptions:`. Se a função delegada não estiver definida, crie-a e adicione a seguinte linha no aplicativo Objective-C ou Swift, respectivamente:

   ```
   // CONFIGURATION LINE FOR OBJECTIVE C ONLY (Skip any framework which is not applicable for you): 
   [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
   [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
   [ACPLifecycle registerExtension]; 
   [ACPIdentity registerExtension]; 
   [ACPUserProfile registerExtension]; 
   [ACPTarget registerExtension];
   
   [ACPTargetVEC registerExtension];
   [ACPCore start:^{
        [ACPCore lifecycleStart:nil];
   }];
   
   // CONFIGURATION LINE FOR SWIFT ONLY: 
   ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
   ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
   ACPLifecycle.registerExtension() 
   ACPIdentity.registerExtension() 
   ACPUserProfile.registerExtension() 
   ACPTarget.registerExtension() 
   
   ACPTargetVEC.registerExtension() 
   
   ACPCore.start {
     ACPCore.lifecycleStart(nil)
   }
   ```

   Por exemplo, o método deve ser semelhante ao seguinte:

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY: 
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions { 
        // Override point for customization after application launch. 
       [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
       [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
       [ACPLifecycle registerExtension]; 
       [ACPIdentity registerExtension]; 
       [ACPUserProfile registerExtension]; 
       [ACPTarget registerExtension]; 
   
       [ACPTargetVEC registerExtension]; 
   
       [ACPCore start:nil]; 
       [ACPCore lifecycleStart:nil]; 
   
      return YES; 
   } 
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY: 
   func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey : Any]? = nil) 
   { 
       ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
       ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
       ACPLifecycle.registerExtension() 
       ACPIdentity.registerExtension() 
       ACPUserProfile.registerExtension() 
       ACPTarget.registerExtension() 
   
       ACPTargetVEC.registerExtension() 
   
       ACPCore.start(nil) 
       ACPCore.lifecycleStart(nil)
   
       return true 
   
   }
   ```

1. Adicione a seguinte linha no início de `AppDelegate:application:openURL`. Se a função delegada não estiver definida, crie-a e adicione a seguinte linha.

   ```
   // URL HANDLER LINE FOR OBJECTIVE C ONLY: 
   [ACPTargetVEC handleDeepLink:url];
   
   // URL HANDLER LINE FOR SWIFT ONLY: 
   ACPTargetVEC.handleDeepLink(url)
   ```

   Por exemplo, o método deve ser semelhante ao seguinte:

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY:
   -  (BOOL)application:(UIApplication *)application openURL:(NSURL *)url options:(NSDictionary<NSString *, id> *)options {
    [ACPTargetVEC handleDeepLink:url];
    return YES;
   }
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY:
   func application(_ app: UIApplication, open url: URL, options: [UIApplication.OpenURLOptionsKey : Any] = [:]) -> Bool {
      ACPTargetVEC.handleDeepLink(url)
      return true;
   }
   ```

1. Crie e execute seu aplicativo e use-o para testar os recursos do aplicativo móvel do aplicativo.

## Configurar exibições do Target em seu aplicativo móvel {#views}

O SDK para dispositivos móveis da Adobe expõe um novo método que os desenvolvedores acionam sempre que uma nova Exibição é renderizada. Leia as diretrizes gerais sobre como inserir corretamente as chamadas da API de exibição do Target para um aplicativo iOS. No iOS, todas as exibições do Target são definidas de acordo com o `UIViewController` no qual são exibidas. Então, ao contrário do Android, a inserção de `TargetViews` está limitada às seguintes chamadas.

A extensão automática do aplicativo Adobe Mobile App Extension gera nomes `UIViewControllers` para interagir na estrutura VEC do aplicativo móvel, com base no nome da classe da subclassificação `UIViewController`. Se desejar substituir esses nomes, você pode chamar o método a seguir na `viewWillAppear` seção `ViewController`.

```
// TARGET VIEW LINE FOR OBJECTIVE C ONLY 
[ACPTargetVEC setTargetView:@"exampleViewController"]; 
   
// TARGET VIEW LINE FOR SWIFT ONLY 
ACPTargetVEC.setTargetView("exampleViewController")
```

O SDK do Adobe Mobile também expõe um método alternativo para os desenvolvedores segmentarem as exibições personalizadas durante o tempo de execução. Como desenvolvedor, certifique-se de que as exibições sejam nomeadas de forma exclusiva. Chame o método a seguir antes de adicionar a exibição ao `superview`:

```
// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN OBJECTIVE C 
CustomPopupView *popupView = [[CustomPopupView alloc] initWithFrame:CGRectMake(0, 0, 300, 200)]; 
[ACPTargetVEC setTargetView:@"myCustomPopupView" forView:popupView];

// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN SWIFT 
let popupView = CustomPopupView.init(frame: CGRect(x: 0, y: 0, width: 300, height: 200)) 
ACPTargetVEC.setTargetView("myCustomPopupView", for: popupView)
```

## Configuração de parâmetros de perfil e outros parâmetros globais {#parameters}

Agora oferecemos suporte à definição de parâmetros globais passados em cada chamada de API, além de passar parâmetros de mbox/exibição para visualizações correspondentes.

Os parâmetros incluem:

* Parâmetros mbox/view
* parâmetros do perfil de in-mbox e script
* Parâmetros do produto
* Parâmetros de pedido

**Os parâmetros globais são compatíveis com:**

```
//For Objective-c 
NSDictionary *mboxParams = @{@"mboxparam1":@"mboxvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekey1":@"profilevalue1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : ACPTargetProduct = ACPTargetProduct.init(id: "1234", categoryId: "furniture") 
var order : ACPTargetOrder = ACPTargetOrder.init(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : ACPTargetParameters = ACPTargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setGlobalRequest(targetParams)
```

**Os parâmetros de envio para o próximo acionador de exibição:**

Fornecemos algumas exibições automáticas criadas por padrão, como &quot;`AUTO_<viewControllerName>`para cada controlador de visualização presente no aplicativo. Se você quiser enviar esses parâmetros, poderá chamar a seguinte API:

```
//For Objective-c 
NSDictionary *mboxParams = @{@"viewparam1":@"viewvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekeyforview1":@"profilevalueforview1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : ACPTargetProduct = ACPTargetProduct.init(id: "1234", categoryId: "furniture") 
var order : ACPTargetOrder = ACPTargetOrder.init(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : ACPTargetParameters = ACPTargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setRequest(targetParams)
```

**Envio de parâmetros para especificar a exibição:**

Vimos a API acionar as Exibições via `TargetVEC.targetView("view_name")`. Você também pode passar parâmetros específicos para a exibição em particular, como mostrado abaixo:

```
//For Objective-c 
[ACPTargetVEC setTargetView:@"VIEW_NAME" withParameters:TARGET_PARAMS];

//FOR SWIFT 
ACPTargetVEC.setTargetView("VIEW_NAME", with: TARGET_PARAMS)
```

## Chamar explicitamente a API pré-busca {#section_373DB4527FC649C58FBA3DF0C18C9836}

Pode haver determinados cenários em que você queira chamar a API de pré-busca novamente para atualizar as ofertas armazenadas no cache. As seguintes APIs são expostas, descritas como:

**Buscar ofertas previamente:**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the main thread blocking the UI. 
 */ 
+ (void) prefetchOffers;
```

**Buscar ofertas previamente em segundo plano:**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the background thread so doesn't block UI. 
 */ 
+ (void) prefetchOffersBackground;
```

## Tutoriais: Implementação da Experience Cloud em aplicativos Ios-C e Swift do iOS {#tutorial}

* [Implementar a Experience Cloud em aplicativos Objetive-C para Ios](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-mobile-ios-objective-c-apps-with-launch/index.html)
* [Implementar a Experience Cloud em aplicativos Mobile iOS móveis](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-mobile-ios-swift-apps-with-launch/index.html)

Após concluir esses tutoriais, você poderá:

* Criar uma propriedade Mobile Launch
* Instalar uma propriedade Launch em um aplicativo Objetive-C ou Swift
* Implemente as seguintes soluções da Adobe Experience Cloud:
   * Serviço da Experience Cloud ID
   * Adobe Target
   * Adobe Analytics
   * Adobe Audience Manager

* Publicar alterações no Launch por meio de ambientes de desenvolvimento, armazenamento temporário e produção