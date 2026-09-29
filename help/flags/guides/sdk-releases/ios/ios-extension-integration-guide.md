---
title: Guia de integração do Flags extension for iOS
description: Saiba como integrar a extensão Sinalizadores ao Adobe Experience Platform Mobile SDK no iOS.
badge: label="Beta" type="Informative"
hide: true
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '1046'
ht-degree: 6%
---
# Extensão de sinalizadores para o iOS {#ios-extension-integration-guide}

Este guia descreve como integrar a extensão Flags ao Adobe Experience Platform Mobile SDK no iOS.

## Pré-requisitos {#prerequisites}

Antes de implementar a extensão Sinalizadores, verifique se você tem:

* Uma propriedade móvel configurada em [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)
* A extensão Sinalizadores instalada e configurada em sua propriedade móvel
* Uma ID de organização da Adobe Experience Cloud
* Destino mínimo de implantação: iOS 12.0

## Dependências de extensão {#extension-dependencies}

A extensão Flags requer as seguintes extensões do Adobe Experience Platform:

| Extensão | Descrição | Obrigatório |
|---|---|---|
| Núcleo móvel | Fornece funcionalidade principal incluindo configuração e processamento de eventos | Sim |
| Vida útil | Coleta dados do ciclo de vida e da sessão do aplicativo para o Mobile SDK | Sim |
| Edge Network | Permite a comunicação com o Adobe Experience Platform Edge Network | Sim |
| Identidade do Edge | Habilita o gerenciamento de identidade de um aplicativo móvel ao usar a extensão Edge Network | Sim |

Verifique se essas extensões estão instaladas na propriedade móvel da Coleção de dados e incluídas nas dependências do aplicativo.

## Configurar a extensão Sinalizadores na Coleção de dados {#configure}

### Instalar a extensão {#install-extension}

1. Faça logon em [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection).
1. Selecione a guia **Tags** e escolha sua propriedade móvel.
1. Navegue até **Extensões** > **Catálogo**.
1. Pesquise por **Extensão de sinalizadores** e selecione **Instalar**.
1. Defina as configurações de extensão:

   | Configuração | Descrição |
   |---|---|
   | ID do aplicativo | Um identificador exclusivo para seu aplicativo em Sinalizadores |

1. Selecione **Salvar**.
1. Siga o [processo de publicação](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/publish/overview) para atualizar sua configuração.

### Obter a ID do arquivo de ambiente {#environment-file-id}

1. Na propriedade do seu dispositivo móvel, navegue até **Ambientes**.
1. Selecione o ícone de caixa sob a coluna **Instalar** para o seu ambiente.
1. Na caixa de diálogo **Instruções de Instalação do Mobile**, copie a **ID do Arquivo de Ambiente**.

## Adicionar a extensão Sinalizadores ao seu aplicativo {#add-to-app}

### Adicionar dependências {#add-dependencies}

Adicione as dependências do Mobile SDK ao seu projeto. A extensão Sinalizadores exige o Mobile Core e as extensões relacionadas ao Edge listadas abaixo.

#### Uso do gerenciador de pacotes Swift {#swift-package-manager}

No Xcode, selecione **Arquivo** > **Adicionar pacotes** e adicione as seguintes URLs de pacote do Adobe Experience Platform Mobile SDK:

| Pacote | URL |
|---|---|
| AEPCore | `https://github.com/adobe/aepsdk-core-ios.git` |
| AEPEdge | `https://github.com/adobe/aepsdk-edge-ios.git` |
| AEPEdgeIdentity | `https://github.com/adobe/aepsdk-edgeidentity-ios.git` |

Quando solicitado, selecione as seguintes bibliotecas para adicionar ao destino:

* `AEPCore`, `AEPLifecycle` (de `aepsdk-core-ios`)
* `AEPEdge` (de `aepsdk-edge-ios`)
* `AEPEdgeIdentity` (de `aepsdk-edgeidentity-ios`)

Use o AEPCore 5.8.0 ou posterior.

>[!NOTE]
>
>Ao adicionar um pacote no Xcode, escolha uma regra de dependência para cada pacote (por exemplo **Até a Próxima Versão Principal**), que seleciona automaticamente novas versões secundárias e de patch enquanto exclui a próxima versão principal. Para obter as versões mais recentes, verifique a página de versões de cada extensão no GitHub.

### Adicionar o pacote de Sinalizadores {#add-flags-package}

Use o pacote Swift ou o método de integração XCFramework para um destino de aplicativo, não ambos.

#### Para um projeto Xcode sem um arquivo Package.swift {#xcode-project}

1. No Xcode, selecione **Arquivo** > **Adicionar pacotes**.
1. Selecione **Adicionar Local**.
1. Selecione o diretório `Packages/AEPFlags` fornecido que contém `Package.swift`.
1. Adicione a biblioteca `AEPFlags` ao destino do seu aplicativo.

O Xcode armazena a referência de pacote local no projeto, portanto, seu aplicativo não precisa de seu próprio arquivo `Package.swift`.

#### Para um projeto com um arquivo Package.swift {#package-swift-project}

No manifesto existente, adicione `AEPFlags` às dependências de destino do aplicativo e adicione o destino binário usando a URL e a soma de verificação do manifesto fornecido:

```swift
targets: [
    .target(
        name: "YourApp",
        dependencies: [
            "AEPFlags"
        ]
    ),
    .binaryTarget(
        name: "AEPFlags",
        url: "<AEPFlags binary URL>",
        checksum: "<AEPFlags binary checksum>"
    )
]
```

O Gerenciador de pacotes Swift resolve o destino binário para builds locais de Xcode, CI e arquivamento.

#### Adicionar o XCFramework diretamente {#xcframework}

Como alternativa, arraste o `AEPFlags.xcframework` fornecido para o navegador do projeto Xcode e adicione-o ao destino do seu aplicativo. Em **Geral** > **Estruturas, Bibliotecas e Conteúdo Inserido**, defina a estrutura como **Incorporar e Assinar**.

### Inicializar o SDK {#initialize-sdk}

Registre as extensões do Mobile SDK em seu `AppDelegate` antes de chamar quaisquer APIs de Sinalizadores. Registre o `Flag` após a Identidade, o Edge e o Ciclo de Vida e configure a SDK usando a ID do Arquivo de Ambiente da sua propriedade móvel.

#### Registrar e configurar extensões {#register-configure}

>[!IMPORTANT]
>
>Para aplicativos de produção, use somente o nível de log `.error`; não use `.debug` ou `.trace` em compilações de versão.

**Swift**

```swift
// AppDelegate.swift
import AEPCore
import AEPLifecycle
import AEPEdge
import AEPEdgeIdentity
import AEPFlags
import UIKit

final class AppDelegate: NSObject, UIApplicationDelegate {

    func application(_: UIApplication,
                      didFinishLaunchingWithOptions _: [UIApplication.LaunchOptionsKey: Any]? = nil) -> Bool {
        // Production: use .error only. Do not use .debug or .trace in release builds.
        MobileCore.setLogLevel(.error)

        MobileCore.registerExtensions([
            Identity.self,
            Edge.self,
            Lifecycle.self,
            Flag.self
        ]) {
            MobileCore.configureWith(appId: "YOUR_ENVIRONMENT_FILE_ID")
            MobileCore.lifecycleStart(additionalContextData: nil)
        }

        return true
    }
}
```

**Objetive-C**

```objc
// AppDelegate.m
#import "AppDelegate.h"
@import AEPCore;
@import AEPLifecycle;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPFlags;

@implementation AppDelegate

- (BOOL)application:(UIApplication *)application
    didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

    // Production: use AEPLogLevelError only. Do not use Debug or Trace in release builds.
    [AEPMobileCore setLogLevel:AEPLogLevelError];

    [AEPMobileCore registerExtensions:@[
        AEPMobileEdgeIdentity.class,
        AEPMobileEdge.class,
        AEPMobileLifecycle.class,
        AEPMobileFlag.class
    ] completion:^{
        [AEPMobileCore configureWithAppId:@"YOUR_ENVIRONMENT_FILE_ID"];
        [AEPMobileCore lifecycleStart:nil];
    }];

    return YES;
}

@end
```

## Contexto de avaliação {#evaluation-context}

`FeatureEvaluationContext` inclui atributos de direcionamento (usados para correspondência de regras de sinalizador).

| Parâmetro | Obrigatório | Descrição |
|---|---|---|
| `attributes` | Não | `[String: [String]]`. Chave é o nome do atributo de contexto usado pelas suas regras de sinalizador (por exemplo, `locale`, `platform`, `appVersion`, `deviceType`). Valor é a lista de valores de atributos candidatos para essa chave para o usuário/sessão atual (por exemplo, `["en_US"]` ou `["phone"]`). |

**Swift**

```swift
import AEPFlags

let attrs: [String: [String]] = [
    "locale": ["en_US"],
    "platform": ["IOS"],
    "appVersion": ["3.0.0"]
]

let ctx = FeatureEvaluationContext.builder()
    .withAttributes(attrs)
    .build()
```

**Objetive-C**

```objc
@import AEPFlags;

NSDictionary<NSString *, NSArray<NSString *> *> *attrs = @{
    @"locale": @[@"en_US"],
    @"platform": @[@"IOS"],
    @"appVersion": @[@"3.0.0"]
};

AEPFeatureEvaluationContextBuilder *builder = [AEPFeatureEvaluationContext builder];
AEPFeatureEvaluationContext *ctx = [[builder withAttributes:attrs] build];
```

### Amostra de atributos de direcionamento {#sample-attributes}

| Atributo | Descrição | Valores de exemplo |
|---|---|---|
| `locale` | Local/idioma do usuário | `["en_US"]`, `["fr_FR"]` |
| `platform` | Identificador da plataforma | `["IOS"]` |
| `appVersion` | Versão do aplicativo | `["3.0.0"]` |
| `deviceType` | Tipo de dispositivo | `["phone"]`, `["tablet"]` |

### Identidade personalizada {#custom-identity}

A extensão Sinalizadores usa a extensão Identidade do Edge Network para resolução de identidade. Um sinalizador de recurso pode ser coortado em uma identidade personalizada (por exemplo, uma ID de CRM ou uma ID de fidelidade) para que as divisões de variante e as análises sejam vinculadas à identidade que é importante para o aplicativo.

O namespace de identidade personalizado deve ser selecionado na interface do usuário de Sinalizadores quando o sinalizador de recurso é criado. Para avaliar um sinalizador em relação a essa identidade, a mesma identidade deve estar presente na Identidade Edge `identityMap` no dispositivo, usando o namespace correspondente. Forneça a ela, em tempo de execução, a Identidade da API `updateIdentities` do Edge Network.

#### Adicionar a identidade personalizada ao Mapa de identidade {#add-identity}

Adicione a identidade no mesmo namespace configurado no sinalizador de recurso.

**Swift**

```swift
import AEPEdgeIdentity

let identityMap = IdentityMap()
identityMap.add(item: IdentityItem(id: "1111", authenticatedState: .authenticated, primary: true),
                 withNamespace: "userCRMId") // must match the namespace configured on the feature flag
Identity.updateIdentities(with: identityMap)
```

**Objetive-C**

```objc
@import AEPEdgeIdentity;

AEPIdentityItem *item = [[AEPIdentityItem alloc]
    initWithId:@"1111"
    authenticatedState:AEPAuthenticatedStateAuthenticated
    primary:YES];
AEPIdentityMap *identityMap = [[AEPIdentityMap alloc] init];
[identityMap addItem:item withNamespace:@"userCRMId"]; // must match the namespace configured on the feature flag
[AEPMobileEdgeIdentity updateIdentities:identityMap];
```

## Referência da API {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled` retorna se um recurso Sinalizadores está ativado ou desativado para o contexto fornecido. Passe `featureKey`, um `FeatureEvaluationContext` (atributos de direcionamento opcionais) e um fechamento de conclusão. Consulte [Contexto de avaliação](#evaluation-context).

**Assinatura**

*Swift*

```swift
static func isFeatureEnabled(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void
)
```

*Objetive-C*

```objc
+ (void)isFeatureEnabled:(NSString *)featureKey
       evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
               completion:(void (^)(BOOL))completion;
```

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | String | Chave de recurso para avaliar em Sinalizadores |
| `evaluationContext` | ContextoDeAvaliaçãoDoRecurso | Inclua atributos de direcionamento conforme necessário; use `FeatureEvaluationContext.builder().build()` para um contexto vazio. Consulte [Contexto de avaliação](#evaluation-context). |
| `completion` | `(Bool) -> Void` | Chamado com `true` se o recurso estiver habilitado, `false` caso contrário. |

**Exemplos**

*Swift*

```swift
import AEPFlags

Flag.isFeatureEnabled(
    "new-flag",
    evaluationContext: ctx
) { isEnabled in
    if isEnabled {
        // Feature is enabled: run the feature-specific behavior
    } else {
        // Feature is disabled: fall back to the default behavior
    }
}
```

*Objetive-C*

```objc
@import AEPFlags;

[AEPMobileFlag isFeatureEnabled:@"new-flag"
              evaluationContext:ctx
                      completion:^(BOOL isEnabled) {
    if (isEnabled) {
        // Feature is enabled: run the feature-specific behavior
    } else {
        // Feature is disabled: fall back to the default behavior
    }
}];
```

### getFeature {#get-feature}

`getFeature` retorna a carga do recurso avaliado para o contexto fornecido. Use essa API quando precisar de mais do que habilitado/desabilitado e quiser metadados ou valores de recursos.

**Assinatura**

*Swift*

```swift
static func getFeature(
    _ featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void
)
```

*Objetive-C*

```objc
+ (void)getFeature:(NSString *)featureKey
 evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
        completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion;
```

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | String | Chave de recurso para avaliar em Sinalizadores |
| `evaluationContext` | ContextoDeAvaliaçãoDoRecurso | Inclua atributos de direcionamento conforme necessário; use `FeatureEvaluationContext.builder().build()` para um contexto vazio. Consulte [Contexto de avaliação](#evaluation-context). |
| `completion` | `(FeatureEvaluationResult?) -> Void` | Chamado com a carga do recurso avaliado; `nil` quando o recurso não é encontrado. |

**Resposta**

*FeatureEvaluationResult*

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | Int | Identificador numérico do recurso |
| `key` | String | Chave do recurso |
| `featureGroupKey` | String? | Chave do grupo de recursos quando disponível |
| `meta` | String? | Metadados de recursos opacos quando disponíveis |
| `analyticsParam` | AnalyticsParam? | Detalhes do Analytics para o recurso avaliado |

*AnalyticsParam*

| Campo | Tipo | Descrição |
|---|---|---|
| `featureGroupId` | Int | Identificador do grupo de recursos numéricos |
| `featureId` | Int | Identificador numérico do recurso |
| `variantId` | String? | Identificador da variante |

**Exemplos**

*Swift*

```swift
import AEPFlags

Flag.getFeature(
    "new-flag",
    evaluationContext: ctx
) { feature in
    guard let meta = feature?.meta, !meta.isEmpty else {
        // No metadata available: fall back to the default behavior
        return
    }
    // Feature metadata is available: use it to drive the feature behavior
}
```

*Objetive-C*

```objc
@import AEPFlags;

[AEPMobileFlag getFeature:@"new-flag"
        evaluationContext:ctx
                completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    NSString *meta = feature.meta;
    if (meta.length > 0) {
        // Feature metadata is available: use it to drive the feature behavior
    } else {
        // No metadata available: fall back to the default behavior
    }
}];
```

### extensionVersion {#extension-version}

Retorna a cadeia de caracteres da versão da extensão Sinalizadores.

**Sintaxe**

*Swift*

```swift
static var extensionVersion: String
```

*Objetive-C*

```objc
+ (nonnull NSString *)flagExtensionVersion;
```

**Exemplo**

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
| `isFeatureEnabled(_:evaluationContext:completion:)`. `FeatureEvaluationContext` carrega atributos de direcionamento para regras. Consulte [isFeatureEnabled](#is-feature-enabled). | Bool via fechamento de Término |
| `getFeature(_:evaluationContext:completion:)`. Retorna a carga do recurso avaliado para o contexto especificado. Consulte [getFeature](#get-feature). | FeatureEvaluationResult? via fechamento |
| `extensionVersion` | String |

## Consulte também {#see-also}

* [Aplicativos móveis](../../integrate/mobile-applications.md)
* [SDKs](../../integrate/sdks.md)
* [guia de integração de extensão do Android](../android/android-extension-integration-guide.md)

<!-- -->
