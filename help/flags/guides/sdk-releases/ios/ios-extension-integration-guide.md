---
title: Guia da extensão de implantação da experiência para integração com o iOS
description: Saiba como integrar a extensão de Implantação de experiência com o Adobe Experience Platform Mobile SDK no iOS.
hide: true
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '1116'
ht-degree: 6%

---

# Extensão de implantação da experiência para o iOS {#ios-extension-integration-guide}

Este guia descreve como integrar a extensão de Implantação de experiência com o Adobe Experience Platform Mobile SDK no iOS.

## Pré-requisitos {#prerequisites}

Antes de implementar a extensão de Implantação de experiência, verifique se você tem:

* Uma propriedade móvel configurada em [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)
* A extensão de Implantação da experiência instalada e configurada em sua propriedade móvel
* Uma ID de organização da Adobe Experience Cloud
* Destino mínimo de implantação: iOS 12.0
* Xcode 14.1 ou posterior

## Dependências de extensão {#extension-dependencies}

A extensão da Implantação de experiência exige as seguintes extensões do Adobe Experience Platform:

| Extensão | Descrição | Obrigatório |
|---|---|---|
| Núcleo móvel | Fornece funcionalidade principal incluindo configuração e processamento de eventos | Sim |
| Vida útil | Coleta dados do ciclo de vida e da sessão do aplicativo para o Mobile SDK | Sim |
| Edge Network | Permite a comunicação com o Adobe Experience Platform Edge Network | Sim |
| Identidade do Edge | Gerencia a identidade do usuário para o Edge Network | Sim |

Verifique se essas extensões estão instaladas na propriedade móvel da Coleção de dados e incluídas nas dependências do aplicativo.

## Configurar a extensão de Implantação de experiência na Coleção de dados {#configure}

### Instalar a extensão {#install-extension}

1. Faça logon em [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection).
1. Selecione a guia **Tags** e escolha sua propriedade móvel.
1. Navegue até **Extensões** > **Catálogo**.
1. Pesquise por **Extensão de implantação da experiência** e selecione **Instalar**.
1. Defina as configurações de extensão:

   | Configuração | Descrição |
   |---|---|
   | Sandbox | A sandbox do Adobe Experience Platform que contém a configuração de Implantação da experiência |
   | ID do aplicativo | Um identificador exclusivo para seu aplicativo na Implantação da experiência |
   | ID do conjunto de dados | A ID do conjunto de dados do Adobe Experience Platform para os dados de evento de análise |

1. Selecione **Salvar**.
1. Siga o [processo de publicação](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) para atualizar sua configuração.

### Obter a ID do arquivo de ambiente {#environment-file-id}

1. Na propriedade do seu dispositivo móvel, navegue até **Ambientes**.
1. Selecione o ícone de caixa sob a coluna **Instalar** para o seu ambiente.
1. Na caixa de diálogo **Instruções de Instalação do Mobile**, copie a **ID do Arquivo de Ambiente**.

>[!IMPORTANT]
>
>No ambiente de **preparo**, adicione o prefixo `staging/` à ID do arquivo de ambiente — isto é, use `staging/<environmentId>`. Em **produção**, use a ID do arquivo de ambiente diretamente.

## Adicionar a extensão de Implantação de experiência ao seu aplicativo {#add-to-app}

### Adicionar dependências {#add-dependencies}

Adicione as dependências do Mobile SDK ao seu projeto. A extensão de Implantação de experiência exige o Mobile Core e as extensões relacionadas ao Edge listadas abaixo.

#### Uso do gerenciador de pacotes Swift (recomendado) {#swift-package-manager}

1. No Xcode, navegue até **Arquivo** > **Adicionar dependências de pacote**.
1. Insira o URL do repositório do Adobe Experience Platform Mobile SDK:

   ```
   https://github.com/adobe/aepsdk-core-ios
   ```

1. Adicione os seguintes pacotes:

   | Pacote | Repositório |
   |---|---|
   | AEPCore, AEPLifecycle | `https://github.com/adobe/aepsdk-core-ios` |
   | AEPEdge | `https://github.com/adobe/aepsdk-edge-ios` |
   | AEPEdgeIdentity | `https://github.com/adobe/aepsdk-edgeidentity-ios` |
   | AEPRollout | `https://github.com/adobe/aepsdk-rollout-ios` |

#### Uso de CocoaPods {#cocoapods}

Adicione os seguintes pods ao seu `Podfile`:

```ruby
pod 'AEPCore'
pod 'AEPLifecycle'
pod 'AEPEdge'
pod 'AEPEdgeIdentity'
pod 'AEPRollout'
```

Em seguida, execute:

```bash
pod install
```

>[!IMPORTANT]
>
>Para aplicativos de produção, a Adobe recomenda fixar em números de versão explícitos, em vez de usar `~>` ou intervalos abertos. Consulte o [Guia de versão do CocoaPods](https://guides.cocoapods.org/using/the-podfile.html) para obter mais informações.

### Inicializar o SDK {#initialize-sdk}

Inicialize o Mobile SDK no `AppDelegate` (ou `SceneDelegate`) antes de chamar qualquer API de extensão de Implantação de Experiência. Use a ID de arquivo de ambiente da sua propriedade móvel para que o aplicativo escolha as configurações de implantação publicadas na Coleção de dados.

**Swift**

```swift
import AEPCore
import AEPLifecycle
import AEPEdge
import AEPEdgeIdentity
import AEPRollout

@main
class AppDelegate: UIResponder, UIApplicationDelegate {

    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {

        MobileCore.setLogLevel(.error)

        MobileCore.registerExtensions(
            [Lifecycle.self, Edge.self, Identity.self, Rollout.self]
        ) {
            // Initialize with your Environment File ID from Data Collection
            MobileCore.configureWith(appId: "YOUR_ENVIRONMENT_FILE_ID")
        }

        return true
    }
}
```

**Objetive-C**

```objc
@import AEPCore;
@import AEPLifecycle;
@import AEPEdge;
@import AEPEdgeIdentity;
@import AEPRollout;

@implementation AppDelegate

- (BOOL)application:(UIApplication *)application
    didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

    [AEPMobileCore setLogLevel:AEPLogLevelError];

    NSArray *extensions = @[
        AEPMobileLifecycle.class,
        AEPMobileEdge.class,
        AEPMobileEdgeIdentity.class,
        AEPMobileRollout.class
    ];

    [AEPMobileCore registerExtensions:extensions completion:^{
        // Initialize with your Environment File ID from Data Collection
        [AEPMobileCore configureWithAppId:@"YOUR_ENVIRONMENT_FILE_ID"];
    }];

    return YES;
}

@end
```

>[!IMPORTANT]
>
>Para aplicativos de produção, use somente `LogLevel.error`. Não use `.debug` ou `.verbose` em compilações de versão.

## Contexto de avaliação {#evaluation-context}

`FeatureEvaluationContext` inclui atributos de direcionamento (usados para correspondência da regra de implantação) e identidade opcional (usada para análise).

| Método | Obrigatório | Descrição |
|---|---|---|
| `withIdentity(namespace:id:)` | Não | Primeiro argumento: namespace de identidade (consulte [namespaces de identidade da Adobe](https://experienceleague.adobe.com/pt-br/docs/experience-platform/identity/features/namespaces)). Segundo argumento: valor de identidade. Inclua isso quando quiser que o namespace e a ID sejam representados no Analytics para essa avaliação. Se não for fornecido, o Analytics usará a ECID por padrão. Isso não é usado para orientar decisões de ativação de recursos. |
| `withAttributes(_:)` | Não | `[String: [String]]`. Chave é o nome do atributo de contexto usado pelas suas regras de implantação (por exemplo `locale`, `platform`, `appVersion`, `deviceType`). Valor é a lista de valores de atributos candidatos para essa chave para o usuário/sessão atual (por exemplo, `["en_US"]` ou `["phone"]`). |

**Swift**

```swift
import AEPRollout

let attrs: [String: [String]] = [
    "locale": ["en_US"],
    "platform": ["IOS"],
    "appVersion": ["3.0.0"]
]

let ctx = FeatureEvaluationContext.builder()
    .withIdentity(namespace: "Email", id: "customer@example.com")
    .withAttributes(attrs)
    .build()
```

**Objetive-C**

```objc
@import AEPRollout;

NSDictionary<NSString *, NSArray<NSString *> *> *attrs = @{
    @"locale": @[@"en_US"],
    @"platform": @[@"IOS"],
    @"appVersion": @[@"3.0.0"]
};

AEPFeatureEvaluationContext *ctx = [[[AEPFeatureEvaluationContextBuilder builder]
    withIdentityNamespace:@"Email" id:@"customer@example.com"]
    withAttributes:attrs]
    .build;
```

### Amostra de atributos de direcionamento {#sample-attributes}

| Atributo | Descrição | Valores de exemplo |
|---|---|---|
| `locale` | Local/idioma do usuário | `["en_US"]`, `["fr_FR"]` |
| `platform` | Identificador da plataforma | `["IOS"]` |
| `appVersion` | Versão do aplicativo | `["3.0.0"]` |
| `deviceType` | Tipo de dispositivo | `["phone"]`, `["tablet"]` |

## Principais conceitos para a avaliação de recursos {#key-concepts}

Lembre-se do seguinte ao implementar portais de recursos no aplicativo:

* **Passar valores de atributo, não exibir rótulos.** Os valores do atributo de contexto são **sensíveis a maiúsculas e minúsculas**. Passe o valor bruto que seu aplicativo ou site envia (por exemplo, `"en_US"` ou `"IOS"`), não o rótulo mostrado no console.
* **Avaliar no nível de recurso (sinalizador).** Mesmo quando um sinalizador pertence a um grupo de recursos, sempre chame a API com a **chave de recurso** individual. Não há avaliação em nível de grupo. A resposta retorna a variante na qual o usuário se encaixou.
* **A identidade não precisa estar vinculada a um perfil.** A avaliação ocorre em tempo de execução. O evento de avaliação é enviado para o Customer Journey Analytics independentemente da identidade estar vinculada a um perfil conhecido.
* **Cada novo sinalizador requer uma alteração de código.** Adicione uma porta para cada chave de sinalizador no código. Use `isFeatureEnabled()` para verificar um estado booliano ligado/desligado ou `getFeature()` para recuperar a carga de recurso completa, incluindo a variante.

## Referência da API {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled` retorna se um recurso de Implantação de Experiência está ativado ou desativado para o contexto fornecido. Passe `featureKey`, um `FeatureEvaluationContext` (atributos de direcionamento opcionais e identidade opcional para análise) e um manipulador de conclusão. Consulte [Contexto de avaliação](#evaluation-context).

**Assinatura**

*Swift*

```swift
Rollout.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (Bool) -> Void
)
```

*Objetive-C*

```objc
[AEPMobileRollout isFeatureEnabled:(NSString *)featureKey
               evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
                      completion:(void (^)(BOOL))completion];
```

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | String | Chave de recurso para avaliar na implantação da experiência |
| `evaluationContext` | ContextoDeAvaliaçãoDoRecurso | Inclua atributos de direcionamento e identidade opcional para análise conforme necessário; use `FeatureEvaluationContext.builder().build()` para um contexto vazio. Consulte [Contexto de avaliação](#evaluation-context). |
| `completion` | `(Bool) -> Void` | Chamado com `true` se o recurso estiver habilitado, `false` caso contrário. |

**Exemplos**

*Swift*

```swift
import AEPRollout

Rollout.isFeatureEnabled(
    featureKey: "new-checkout-experience",
    evaluationContext: ctx
) { isEnabled in
    if isEnabled {
        showNewCheckout()
    } else {
        showDefaultCheckout()
    }
}
```

*Objetive-C*

```objc
@import AEPRollout;

[AEPMobileRollout isFeatureEnabled:@"new-checkout-experience"
               evaluationContext:ctx
                      completion:^(BOOL isEnabled) {
    if (isEnabled) {
        [self showNewCheckout];
    } else {
        [self showDefaultCheckout];
    }
}];
```

### getFeature {#get-feature}

`getFeature` retorna a carga do recurso avaliado para o contexto fornecido. Use essa API quando precisar de mais do que habilitado/desabilitado e quiser metadados ou valores de recursos.

**Assinatura**

*Swift*

```swift
Rollout.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    completion: @escaping (FeatureEvaluationResult?) -> Void
)
```

*Objetive-C*

```objc
[AEPMobileRollout getFeature:(NSString *)featureKey
         evaluationContext:(AEPFeatureEvaluationContext *)evaluationContext
                completion:(void (^)(AEPFeatureEvaluationResult * _Nullable))completion];
```

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | String | Chave de recurso para avaliar na implantação da experiência |
| `evaluationContext` | ContextoDeAvaliaçãoDoRecurso | Inclua atributos de direcionamento e identidade opcional para análise conforme necessário; use `FeatureEvaluationContext.builder().build()` para um contexto vazio. Consulte [Contexto de avaliação](#evaluation-context). |
| `completion` | `(FeatureEvaluationResult?) -> Void` | Chamado com a carga do recurso avaliado; pode ser `nil` quando o recurso não é encontrado. |

**Resposta**

*FeatureEvaluationResult*

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | Int | Identificador numérico do recurso |
| `key` | String | Chave do recurso |
| `releaseKey` | String? | Chave de versão para este recurso quando disponível |
| `meta` | String? | Metadados de recurso como uma sequência de caracteres JSON quando disponíveis |
| `analyticsParam` | AnalyticsParam? | Detalhes do Analytics para o recurso avaliado |

*AnalyticsParam*

| Campo | Tipo | Descrição |
|---|---|---|
| `releaseId` | Int | Identificador numérico da versão |
| `featureId` | Int | Identificador numérico do recurso |
| `variantId` | String? | Identificador da variante |

**Exemplos**

*Swift*

```swift
import AEPRollout

Rollout.getFeature(
    featureKey: "new-checkout-experience",
    evaluationContext: ctx
) { feature in
    if let meta = feature?.meta, !meta.isEmpty {
        applyMetaDrivenExperience(meta)
    } else {
        showFallbackExperience()
    }
}
```

*Objetive-C*

```objc
@import AEPRollout;

[AEPMobileRollout getFeature:@"new-checkout-experience"
         evaluationContext:ctx
                completion:^(AEPFeatureEvaluationResult * _Nullable feature) {
    NSString *meta = feature.meta;
    if (meta != nil && meta.length > 0) {
        [self applyMetaDrivenExperience:meta];
    } else {
        [self showFallbackExperience];
    }
}];
```

### refreshCache {#refresh-cache}

Por padrão, a extensão Implantação de experiência sincroniza regularmente as regras e os recursos de implantação mais recentes do servidor, de acordo com um agendamento que você pode configurar. Se você precisar de uma atualização antes da próxima sincronização agendada, chame `refreshCache` para forçar uma atualização. Os casos típicos incluem após o logon ou quando o estado do aplicativo é alterado de uma forma que deve afetar o direcionamento.

**Sintaxe**

*Swift*

```swift
Rollout.refreshCache()
```

*Objetive-C*

```objc
[AEPMobileRollout refreshCache];
```

### extensionVersion {#extension-version}

Retorna a cadeia de caracteres da versão da extensão de Implantação de experiência.

**Sintaxe**

```swift
Rollout.extensionVersion(): String
```

**Exemplo**

*Swift*

```swift
let version = Rollout.extensionVersion()
```

*Objetive-C*

```objc
NSString *version = [AEPMobileRollout extensionVersion];
```

## Resumo da API {#api-summary}

| administração | Devoluções |
|---|---|
| `isFeatureEnabled(featureKey:evaluationContext:completion:)`. `FeatureEvaluationContext` possui atributos de direcionamento para regras e identidade opcional para análise. Consulte [isFeatureEnabled](#is-feature-enabled). | Bool via manipulador de conclusão |
| `getFeature(featureKey:evaluationContext:completion:)`. Retorna a carga do recurso avaliado para o contexto especificado. Consulte [getFeature](#get-feature). | FeatureEvaluationResult? por meio do manipulador de conclusão |
| `refreshCache()` | Nulo |
| `extensionVersion()` | String |

## Consulte também {#see-also}

* [Aplicativos móveis](../../integrate/mobile-applications.md)
* [Etapas de integração](../../integrate/integration-steps.md)
* [SDKs](../../integrate/sdks.md)
* [guia de integração de extensão do Android](../android/android-extension-integration-guide.md)

<!-- -->
