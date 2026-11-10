---
title: Guia de integração do Flags extension for iOS
description: Saiba como integrar a extensão Sinalizadores ao Adobe Experience Platform Mobile SDK no iOS.
badge: label="Beta" type="Informative"
hide: true
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: c1fafcfcd7d5d22781abdd10e6eb3c2b84136c2d
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 3%
---
# Extensão de sinalizadores para o iOS {#ios-extension-integration-guide}

Este guia descreve como integrar a extensão Flags ao Adobe Experience Platform Mobile SDK no iOS. O código-fonte está disponível no repositório [aepsdk-flags-ios](https://github.com/adobe/aepsdk-flags-ios).

## Pré-requisitos {#prerequisites}

Antes de começar, verifique se você tem:

* iOS 12.0 ou posterior e Swift 5.7 ou posterior
* Uma propriedade móvel na [Coleção de dados do Adobe Experience Platform](https://experience.adobe.com/#/data-collection)
* Essas extensões são instaladas e configuradas na propriedade móvel:

  | Extensão | Descrição | Versão mínima do SDK |
  |---|---|---|
  | [Núcleo do dispositivo móvel](https://developer.adobe.com/client-sdks/home/base/mobile-core/) | Configuração e processamento de eventos | AEPCore 5.8.0 |
  | [Vida útil](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/) | Dados do ciclo de vida do aplicativo | Igual ao AEPCore |
  | [Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/) | Comunicação com o Adobe Experience Platform Edge Network. Requer uma sequência de dados. | AEPEdge 5.0.2 |
  | [Identidade do Edge Network](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) | Gerenciamento de identidade para o Edge Network | AEPEdgeIdentity 5.0.0 |
  | [Sinalizadores](https://experienceleague.adobe.com/en/docs/target/flags/home) | Avaliação do sinalizador de recurso | Consulte [Instalação](#installation) |

## Configurar sinalizadores na coleção de dados {#configure}

### Instalar a extensão {#install-extension}

1. Faça logon em [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection).

1. Selecione o menu **[!UICONTROL Marcas]** e escolha sua propriedade móvel.

1. Navegue até **[!UICONTROL Extensões]** > **[!UICONTROL Catálogo]**.

1. Procure por **[!DNL Adobe Flags]** e selecione **[!UICONTROL Instalar]**.

   ![](../assets/extension-install.png)

1. Defina as configurações de extensão:

   * **[!UICONTROL Sandbox]**: a sandbox do Adobe Experience Platform que contém sua configuração de Sinalizadores.
   * **[!UICONTROL ID do Aplicativo]**: o identificador do seu aplicativo em Sinalizadores.

1. Selecione **[!UICONTROL Salvar]**.

1. Siga o [processo de publicação](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) para atualizar sua configuração.

### Obter a ID do arquivo de ambiente {#environment-file-id}

1. Na propriedade do seu dispositivo móvel, navegue até **[!UICONTROL Ambientes]**.

1. Selecione o ícone de caixa na coluna **[!UICONTROL Instalar]** do ambiente selecionado.

   ![](../assets/extension-install-2.png)

1. Na caixa de diálogo **[!UICONTROL Instruções de Instalação do Mobile]**, copie a **[!UICONTROL ID do Arquivo de Ambiente]**.

   ![](../assets/extension-install-3.png)

## Instalação {#installation}

Adicione a extensão com o Gerenciador de pacotes Swift ou um XCFramework. Use um método por destino de aplicativo.

### Gerenciador de pacotes Swift {#swift-package-manager}

No Xcode:

1. Selecione **Arquivo** > **Adicionar Dependências de Pacote**.

1. Digite a URL do pacote: `https://github.com/adobe/aepsdk-flags-ios.git`

1. Para a regra de versão, selecione **Versão Exata** e insira a versão mais recente na [página de versões](https://github.com/adobe/aepsdk-flags-ios/releases).

1. Adicione a biblioteca `AEPFlags` ao destino de aplicativo.

1. Adicione os pacotes do Adobe dos quais a extensão depende e adicione suas bibliotecas ao destino de aplicativo:

   * `https://github.com/adobe/aepsdk-core-ios.git`: `AEPCore`, `AEPLifecycle`, e `AEPServices`
   * `https://github.com/adobe/aepsdk-edge-ios.git`: `AEPEdge`
   * `https://github.com/adobe/aepsdk-edgeidentity-ios.git`: `AEPEdgeIdentity`

Se o projeto usar um arquivo `Package.swift`, adicione as dependências lá. Substitua `<latest-version>` pela versão mais recente na página de lançamentos.

```swift
dependencies: [
    .package(url: "https://github.com/adobe/aepsdk-flags-ios.git", exact: "<latest-version>"),
    .package(url: "https://github.com/adobe/aepsdk-core-ios.git", .upToNextMajor(from: "5.8.0")),
    .package(url: "https://github.com/adobe/aepsdk-edge-ios.git", .upToNextMajor(from: "5.0.2")),
    .package(url: "https://github.com/adobe/aepsdk-edgeidentity-ios.git", .upToNextMajor(from: "5.0.0"))
],
targets: [
    .target(
        name: "YourTarget",
        dependencies: [
            .product(name: "AEPFlags", package: "aepsdk-flags-ios"),
            .product(name: "AEPCore", package: "aepsdk-core-ios"),
            .product(name: "AEPLifecycle", package: "aepsdk-core-ios"),
            .product(name: "AEPServices", package: "aepsdk-core-ios"),
            .product(name: "AEPEdge", package: "aepsdk-edge-ios"),
            .product(name: "AEPEdgeIdentity", package: "aepsdk-edgeidentity-ios")
        ]
    )
]
```

### XCFramework {#xcframework}

1. Na [página de versões](https://github.com/adobe/aepsdk-flags-ios/releases), baixe `AEPFlags-<version>.xcframework.zip` e descompacte-o.

1. Baixe o XCFrameworks do qual a extensão depende a partir da página de versões de cada repositório:

   * [versões do aepsdk-core-ios](https://github.com/adobe/aepsdk-core-ios/releases): `AEPCore`, `AEPServices`, `AEPLifecycle` e `AEPRulesEngine`
   * [versões aepsdk-edge-ios](https://github.com/adobe/aepsdk-edge-ios/releases): `AEPEdge`
   * [versões aepsdk-edgeidentity-ios](https://github.com/adobe/aepsdk-edgeidentity-ios/releases): `AEPEdgeIdentity`

1. No Xcode, selecione o destino do seu aplicativo e abra **Geral** > **Estruturas, Bibliotecas e Conteúdo Inserido**.

1. Adicione `AEPFlags.xcframework` e todos os XCFrameworks dependentes.

1. Defina cada estrutura como **Incorporar e Assinar**.

## Inicializar o SDK {#initialize-sdk}

Registre a extensão Flags e inicialize o SDK com a ID de arquivo de ambiente da sua propriedade móvel. `MobileCore.initialize` não registra a extensão Sinalizadores para você, portanto, registre-a primeiro.

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPCore
import AEPFlags
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        MobileCore.registerExtensions([Flag.self])
        MobileCore.initialize(appId: "<your-environment-file-id>")
        return true
    }
}
```

>[!TAB Objetive-C]

```objc
@import AEPCore;
@import AEPFlags;

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [AEPMobileCore registerExtensions:@[AEPMobileFlag.class] completion:nil];
    [AEPMobileCore initializeWithAppId:@"<your-environment-file-id>" completion:nil];
    return YES;
}
```

>[!ENDTABS]

### Registrar extensões manualmente {#register-manually}

Se você mesmo registrar extensões, registre todas elas. Chame `MobileCore.lifecycleStart` quando o aplicativo entrar em primeiro plano e `MobileCore.lifecyclePause` quando ele entrar em segundo plano.

Se o aplicativo usa cenas, faça essas chamadas em `sceneWillEnterForeground(_:)` e `sceneDidEnterBackground(_:)`.

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPCore
import AEPEdge
import AEPEdgeIdentity
import AEPFlags
import AEPLifecycle
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        MobileCore.registerExtensions([
            Lifecycle.self,
            Edge.self,
            AEPEdgeIdentity.Identity.self,
            Flag.self
        ]) {
            MobileCore.configureWith(appId: "<your-environment-file-id>")
            DispatchQueue.main.async {
                if application.applicationState != .background {
                    MobileCore.lifecycleStart(additionalContextData: nil)
                }
            }
        }
        return true
    }

    func applicationWillEnterForeground(_ application: UIApplication) {
        MobileCore.lifecycleStart(additionalContextData: nil)
    }

    func applicationDidEnterBackground(_ application: UIApplication) {
        MobileCore.lifecyclePause()
    }
}
```

>[!TAB Objetive-C]

```objc
@import AEPCore;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPFlags;
@import AEPLifecycle;

- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    [AEPMobileCore registerExtensions:@[
        AEPMobileLifecycle.class,
        AEPMobileEdge.class,
        AEPMobileEdgeIdentity.class,
        AEPMobileFlag.class
    ] completion:^{
        [AEPMobileCore configureWithAppId:@"<your-environment-file-id>"];
        dispatch_async(dispatch_get_main_queue(), ^{
            if (application.applicationState != UIApplicationStateBackground) {
                [AEPMobileCore lifecycleStart:nil];
            }
        });
    }];
    return YES;
}

- (void)applicationWillEnterForeground:(UIApplication *)application {
    [AEPMobileCore lifecycleStart:nil];
}

- (void)applicationDidEnterBackground:(UIApplication *)application {
    [AEPMobileCore lifecyclePause];
}
```

>[!ENDTABS]

## Contexto de avaliação {#evaluation-context}

Cada chamada de avaliação leva um `FeatureEvaluationContext`. Ele contém os atributos que as regras de direcionamento dos seus sinalizadores usam.

| Parâmetro | Obrigatório | Descrição |
|---|---|---|
| `attributes` | Não | `[String: [String]]`. Cada chave é um nome de atributo usado pelas regras de direcionamento de sinalizador. Cada valor é a lista de valores do usuário atual. |

* Use nomes e valores de atributos que correspondam às regras de direcionamento definidas nos Sinalizadores.
* Chame `withAttributes` no máximo uma vez por construtor. Uma segunda chamada encerra o aplicativo.
* Para avaliar sem atributos, chame `build()` sem chamar `withAttributes`.

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPFlags

let context = FeatureEvaluationContext.builder()
    .withAttributes([
        "locale": ["en_US"],
        "appVersion": ["3.0.0"]
    ])
    .build()
```

>[!TAB Objetive-C]

```objc
@import AEPFlags;

AEPFeatureEvaluationContext *context = [[[AEPFeatureEvaluationContext builder]
    withAttributes:@{
        @"locale": @[@"en_US"],
        @"appVersion": @[@"3.0.0"]
    }]
    build];
```

>[!ENDTABS]

## Identidade personalizada {#custom-identity}

A extensão Sinalizadores usa a extensão Identidade do Edge Network para resolução de identidade. Um sinalizador de recurso pode ser coortado em uma identidade personalizada (por exemplo, uma ID de CRM ou uma ID de fidelidade) para que as divisões de variante e as análises sejam vinculadas à identidade que é importante para o aplicativo.

O namespace de identidade personalizado deve ser selecionado na interface do usuário de Sinalizadores quando o sinalizador de recurso é criado. Para avaliar um sinalizador em relação a essa identidade, a mesma identidade deve estar presente na Identidade Edge `identityMap` no dispositivo, usando o namespace correspondente. Forneça a ela, em tempo de execução, a Identidade da API `updateIdentities` do Edge Network.

### Adicionar a identidade personalizada ao Mapa de identidade {#add-identity}

Adicione a identidade no mesmo namespace configurado no sinalizador de recurso.

Observe o seguinte comportamento:

* O namespace deve corresponder exatamente ao configurado no sinalizador, incluindo letras maiúsculas e minúsculas.
* Se houver várias identidades no namespace, a marcada como primária será usada. Se nenhum estiver marcado como primário, o primeiro será usado.
* Se a identidade estiver ausente, a chamada não falhará. O usuário é atribuído a uma variante aleatoriamente somente para a sessão atual do aplicativo e pode ser atribuído a uma variante diferente após a reinicialização do aplicativo. Defina a identidade antes de avaliar os sinalizadores que a utilizam.

>[!BEGINTABS]

>[!TAB Swift]

```swift
import AEPEdgeIdentity

let identityMap = IdentityMap()
identityMap.add(
    item: IdentityItem(id: "1111", authenticatedState: .authenticated, primary: true),
    withNamespace: "userCRMId" // must match the namespace configured on the feature flag
)
Identity.updateIdentities(with: identityMap)
```

>[!TAB Objetive-C]

```objc
@import AEPEdgeIdentity;

AEPIdentityItem *item = [[AEPIdentityItem alloc] initWithId:@"1111"
                                         authenticatedState:AEPAuthenticatedStateAuthenticated
                                                    primary:YES];
AEPIdentityMap *identityMap = [[AEPIdentityMap alloc] init];
[identityMap addItem:item withNamespace:@"userCRMId"]; // must match the namespace configured on the feature flag
[AEPMobileEdgeIdentity updateIdentities:identityMap];
```

>[!ENDTABS]


## Referência da API {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

Verifique se um recurso está habilitado para o usuário atual. O resultado é `true` quando o recurso existe, o usuário corresponde às suas regras de direcionamento e o usuário não está em um grupo de controle. Caso contrário, o resultado será `false`.

>[!BEGINTABS]

>[!TAB Swift]

```swift
static func isFeatureEnabled(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void,
    errorCallback: ((AEPError) -> Void)?
)
```

>[!TAB Objetive-C]

```objc
+ (void)isFeatureEnabled:(NSString *)featureKey
       evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
              completion:(void (^)(BOOL))completion
           errorCallback:(void (^ _Nullable)(enum AEPError))errorCallback;
```

>[!ENDTABS]

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | String | Chave de recurso para avaliar em Sinalizadores |
| `evaluationContext` | ContextoDeAvaliaçãoDoRecurso | Inclua atributos de direcionamento conforme necessário; use `FeatureEvaluationContext.builder().build()` para um contexto vazio. Consulte [Contexto de avaliação](#evaluation-context). |
| `completion` | `(Bool) -> Void` | Chamado com `true` se o recurso estiver habilitado, `false` caso contrário. |
| `errorCallback` | `((AEPError) -> Void)?` | Opcional. Chamado apenas para falhas genuínas, como uma chave vazia, configuração ausente, uma avaliação com falha ou um tempo limite. |

**Exemplos**

>[!BEGINTABS]

>[!TAB Swift]

```swift
Flag.isFeatureEnabled("new-flag", evaluationContext: context) { isEnabled in
    DispatchQueue.main.async {
        if isEnabled {
            // Run the feature-specific behavior
        } else {
            // Run the default behavior
        }
    }
} errorCallback: { _ in
    DispatchQueue.main.async {
        // Run the default behavior
    }
}
```

>[!TAB Objetive-C]

```objc
[AEPMobileFlag isFeatureEnabled:@"new-flag"
              evaluationContext:context
                     completion:^(BOOL isEnabled) {
    dispatch_async(dispatch_get_main_queue(), ^{
        if (isEnabled) {
            // Run the feature-specific behavior
        } else {
            // Run the default behavior
        }
    });
} errorCallback:^(enum AEPError error) {
    dispatch_async(dispatch_get_main_queue(), ^{
        // Run the default behavior
    });
}];
```

>[!ENDTABS]

### getFeature {#get-feature}

>[!IMPORTANT]
>
>As versões anteriores chamavam o retorno de chamada de erro com `AEPError.unexpected` quando um recurso não era fornecido. Se o aplicativo tratou o erro como &quot;recurso ausente&quot;, manipule `nil` na conclusão.

Retorna os detalhes de um recurso para o usuário atual, incluindo seus metadados e a variante à qual o usuário está atribuído. Use-a quando precisar de mais do que habilitada ou desabilitada.

A conclusão é chamada com um resultado somente quando o recurso é disponibilizado ao usuário. Se o recurso não for atendido, a conclusão será chamada com `nil`. Esse é um resultado normal, não um erro, e a chamada de retorno de erro não é chamada. A conclusão é chamada com `nil` quando:

* Nenhum recurso tem essa chave.
* O usuário não corresponde às regras de direcionamento.
* O usuário está em um grupo de controle.

O retorno de chamada de erro é chamado com `AEPError.unexpected` (ou outro `AEPError`) apenas quando algo dá errado: a chave de recurso está vazia, um valor de configuração obrigatório está ausente, a avaliação falha, a resposta não pode ser lida ou o tempo limite da solicitação é excedido.

>[!BEGINTABS]

>[!TAB Swift]

```swift
static func getFeature(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void,
    errorCallback: ((AEPError) -> Void)?
)
```

>[!TAB Objetive-C]

```objc
+ (void)getFeature:(NSString *)featureKey
 evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
        completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion
     errorCallback:(void (^ _Nullable)(enum AEPError))errorCallback;
```

>[!ENDTABS]

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | String | Chave de recurso para avaliar em Sinalizadores |
| `evaluationContext` | ContextoDeAvaliaçãoDoRecurso | Inclua atributos de direcionamento conforme necessário; use `FeatureEvaluationContext.builder().build()` para um contexto vazio. Consulte [Contexto de avaliação](#evaluation-context). |
| `completion` | `(FeatureEvaluationResult?) -> Void` | Chamado com a carga do recurso avaliado. Chamado com `nil` quando o recurso não é fornecido ao usuário (chave desconhecida, direcionamento não correspondente ou grupo de controle). `nil` não é um erro. |
| `errorCallback` | `((AEPError) -> Void)?` | Opcional. Chamado apenas para falhas genuínas, como uma chave vazia, configuração ausente, uma avaliação com falha ou um tempo limite. Não chamado quando o recurso não é distribuído. |

**Resposta**

*FeatureEvaluationResult*

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | Int | A ID do recurso |
| `key` | String | A chave do recurso |
| `featureGroupKey` | String? | A chave do grupo de recursos que contém o recurso |
| `meta` | String? | Os metadados configurados para o recurso, como texto. Se os metadados forem JSON, decodifique-os no aplicativo. |
| `analyticsParam` | AnalyticsParam? | Identificadores do recurso e da variante do usuário |

**Exemplos**

>[!BEGINTABS]

>[!TAB Swift]

```swift
Flag.getFeature("new-flag", evaluationContext: context) { feature in
    DispatchQueue.main.async {
        guard let meta = feature?.meta, !meta.isEmpty else {
            // The feature is not served to this user (feature is nil), or it has no metadata.
            // Run the default behavior
            return
        }
        // Use the metadata to drive the feature behavior
    }
} errorCallback: { _ in
    DispatchQueue.main.async {
        // A genuine failure occurred. Run the default behavior
    }
}
```

>[!TAB Objetive-C]

```objc
[AEPMobileFlag getFeature:@"new-flag"
        evaluationContext:context
               completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    dispatch_async(dispatch_get_main_queue(), ^{
        if (feature.meta.length > 0) {
            // Use the metadata to drive the feature behavior
        } else {
            // Run the default behavior
        }
    });
} errorCallback:^(enum AEPError error) {
    dispatch_async(dispatch_get_main_queue(), ^{
        // Run the default behavior
    });
}];
```

>[!ENDTABS]

### extensionVersion {#extension-version}

Retorna a versão da extensão Sinalizadores.

*Swift*

```swift
let version = Flag.extensionVersion
```

*Objetive-C*

```objc
NSString *version = [AEPMobileFlag flagExtensionVersion];
```

## Resumo da API {#api-summary}

| administração | Devoluções |
|---|---|
| `isFeatureEnabled(_:evaluationContext:completion:errorCallback:)` | Boolear até a conclusão |
| `getFeature(_:evaluationContext:completion:errorCallback:)` | FeatureEvaluationResult? até a conclusão |
| `extensionVersion` | String |
