---
title: Guia de integração do Flags extension for Android
description: Saiba como integrar a extensão Sinalizadores ao Adobe Experience Platform Mobile SDK no Android.
hide: true
exl-id: 683ef4d4-e637-4b7b-b694-689c7e65a99e
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 4%

---

# Extensão de sinalizadores para o Android {#android-extension-integration-guide}

Este guia descreve como integrar a extensão Flags ao Adobe Experience Platform Mobile SDK no Android.

## Pré-requisitos {#prerequisites}

Antes de implementar a extensão Sinalizadores, verifique se você tem:

* Uma propriedade móvel configurada em [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)
* A extensão Sinalizadores instalada e configurada em sua propriedade móvel
* Uma ID de organização da Adobe Experience Cloud
* SDK mínimo: API 21 (Android 5.0 Lollipop)

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

#### Usando Gradle com BOM (Recomendado) {#gradle-bom}

Adicione as seguintes dependências ao arquivo `build.gradle.kts` do seu aplicativo:

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation(platform("com.adobe.marketing.mobile:sdkbom:3.+"))

    // Required extensions
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")
}
```

#### Uso de Gradle (Groovy) {#gradle-groovy}

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM
    implementation platform('com.adobe.marketing.mobile:sdkbom:3.+')

    // Required extensions
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'
}
```

>[!IMPORTANT]
>
>Para aplicativos de produção, a Adobe recomenda usar números de versão explícitos em vez de versões dinâmicas. Consulte [Gerenciando dependências Gradle](https://docs.gradle.org/current/userguide/dependency_management.html) para obter mais informações.

### Adicionar a dependência Sinalizadores {#add-flags-dependency}

#### Uso do repositório Maven hospedado (recomendado) {#hosted-maven}

Adicionar o repositório Maven de Sinalizadores ao bloco `repositories` em `settings.gradle.kts`:

```kotlin
maven {
    url = uri("<HTTPS Flags Maven repository URL>")
}
```

Para um arquivo `settings.gradle` do Groovy:

```groovy
maven {
    url = uri('<HTTPS Flags Maven repository URL>')
}
```

Substitua `<HTTPS Flags Maven repository URL>` pela URL de repositório seguro fornecida para a extensão de Sinalizadores.

Em seguida, adicione a dependência Sinalizadores com versão ao `build.gradle.kts` do seu aplicativo:

```kotlin
implementation("com.adobe.marketing.mobile:flags:<version>")
```

Para um arquivo `build.gradle` do Groovy:

```groovy
implementation 'com.adobe.marketing.mobile:flags:<version>'
```

Substitua `<version>` pela versão exata da extensão de Sinalizadores fornecida para sua versão.

#### Uso do pacote de distribuição Flags {#distribution-package}

O pacote de distribuição da extensão Flags inclui:

* `flags-3.x.aar`
* `flags-3.x.module`
* `flags-3.x.pom`

Disponibilize a extensão para seu projeto do Android usando um dos seguintes métodos:

* Publique todos os arquivos do pacote de distribuição em um repositório Maven local ou privado e configure seu projeto para usar esse repositório.
* Adicione `flags-3.x.aar` diretamente ao seu projeto e declare as dependências transitivas especificadas em `flags-3.x.pom`.

### Adicionar permissões {#add-permissions}

Adicione as seguintes permissões ao arquivo `AndroidManifest.xml`:

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### Inicializar o SDK {#initialize-sdk}

Inicialize o Mobile SDK na classe `Application` antes de chamar APIs de extensão de Sinalizadores. Use a ID de Arquivo de Ambiente da sua propriedade móvel com o `MobileCore.initialize` para que o aplicativo escolha as configurações de Sinalizadores publicadas na Coleção de dados.

#### Uso do MobileCore.initialize {#mobile-core-initialize}

Disponível a partir do Android BOM versão 3.8.0, essa API inicializa o SDK com seu arquivo de ambiente de Coleção de dados.

>[!IMPORTANT]
>
>Para aplicativos de produção, use somente `LoggingMode.ERROR`; não use `DEBUG` ou `VERBOSE` em compilações de versão.

**Kotlin**

```kotlin
import android.app.Application
import com.adobe.marketing.mobile.LoggingMode
import com.adobe.marketing.mobile.MobileCore

class MainApplication : Application() {

    override fun onCreate() {
        super.onCreate()

        // Production: use LoggingMode.ERROR only. Do not use DEBUG or VERBOSE in release builds.
        MobileCore.setLogLevel(LoggingMode.ERROR)

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID")
    }
}
```

**Java**

```java
import android.app.Application;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        // Production: use LoggingMode.ERROR only. Do not use DEBUG or VERBOSE in release builds.
        MobileCore.setLogLevel(LoggingMode.ERROR);

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID", null);
    }
}
```

### Registrar a classe Application {#register-application}

Registre sua classe `Application` em `AndroidManifest.xml`:

```xml
<application
    android:name=".MainApplication"
    ... >
</application>
```

## Contexto de avaliação {#evaluation-context}

A classe `FeatureEvaluationContext` inclui atributos de direcionamento (usados para correspondência de regras de sinalizador).

| Método | Obrigatório | Descrição |
|---|---|---|
| `withAttributes(map)` | Não | `Map<String, List<String>>`. Chave é o nome do atributo de contexto usado pelas suas regras de sinalizador (por exemplo, `locale`, `platform`, `appVersion`, `deviceType`). Valor é a lista de valores de atributos candidatos para essa chave para o usuário/sessão atual (por exemplo, `["en_US"]` ou `["phone"]`). |

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext

val attrs = mapOf(
    "locale" to listOf("en_US"),
    "platform" to listOf("ANDROID")
)

val ctx = FeatureEvaluationContext.builder()
    .withAttributes(attrs)
    .build()
```

**Java**

```java
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

Map<String, List<String>> attrs = new HashMap<>();
attrs.put("locale", Arrays.asList("en_US"));
attrs.put("platform", Arrays.asList("ANDROID"));

FeatureEvaluationContext ctx = FeatureEvaluationContext.builder()
        .withAttributes(attrs)
        .build();
```

### Identidade personalizada {#custom-identity}

A extensão Sinalizadores usa a extensão Identidade do Edge Network para resolução de identidade. Um sinalizador de recurso pode ser coortado em uma identidade personalizada (por exemplo, uma ID de CRM ou uma ID de fidelidade) para que as divisões de variante e as análises sejam vinculadas à identidade que é importante para o aplicativo.

O namespace de identidade personalizado deve ser selecionado na interface do usuário de Sinalizadores quando o sinalizador de recurso é criado. Para avaliar um sinalizador em relação a essa identidade, a mesma identidade deve estar presente na Identidade Edge `identityMap` no dispositivo, usando o namespace correspondente. Forneça a ela, em tempo de execução, a Identidade da API `updateIdentities` do Edge Network.

#### Adicionar a identidade personalizada ao Mapa de identidade {#add-identity}

Adicione a identidade no mesmo namespace configurado no sinalizador de recurso.

**Kotlin**

```kotlin
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState
import com.adobe.marketing.mobile.edge.identity.Identity
import com.adobe.marketing.mobile.edge.identity.IdentityItem
import com.adobe.marketing.mobile.edge.identity.IdentityMap

val identityMap = IdentityMap()
identityMap.addItem(
    IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true),
    "userCRMId" // must match the namespace configured on the feature flag
)
Identity.updateIdentities(identityMap)
```

**Java**

```java
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState;
import com.adobe.marketing.mobile.edge.identity.Identity;
import com.adobe.marketing.mobile.edge.identity.IdentityItem;
import com.adobe.marketing.mobile.edge.identity.IdentityMap;

final IdentityItem item = new IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true);
final IdentityMap identityMap = new IdentityMap();
identityMap.addItem(item, "userCRMId"); // must match the namespace configured on the feature flag
Identity.updateIdentities(identityMap);
```

## Referência da API {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled` retorna se um recurso Sinalizadores está ativado ou desativado para o contexto fornecido. Passe `featureKey`, um `FeatureEvaluationContext` (atributos de direcionamento opcionais) e um retorno de chamada. Consulte [Contexto de avaliação](#evaluation-context).

**Assinatura**

*Kotlin*

```kotlin
Flag.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

*Java*

```java
Flag.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | String | Chave de recurso para avaliar em Sinalizadores |
| `evaluationContext` | ContextoDeAvaliaçãoDoRecurso | Inclua atributos de direcionamento conforme necessário; use `FeatureEvaluationContext.builder().build()` para um contexto vazio. Consulte [Contexto de avaliação](#evaluation-context). |
| `callback` | AdobeCallback&lt;Booleano> | Invocado com `true` se o recurso estiver habilitado; caso contrário, `false`. Você também pode passar `AdobeCallbackWithError<Boolean>` para manipular `fail(...)`. |

**Exemplos**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.flags.Flag

Flag.isFeatureEnabled(
    "new-flag",
    ctx,
    object : AdobeCallback<Boolean> {
        override fun call(isEnabled: Boolean?) {
            if (isEnabled == true) {
                // run the feature-specific behavior
            } else {
                // fall back to the default behavior
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.flags.Flag;

Flag.isFeatureEnabled(
    "new-flag",
    ctx,
    new AdobeCallback<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            if (Boolean.TRUE.equals(isEnabled)) {
                // run the feature-specific behavior
            } else {
                // fall back to the default behavior
            }
        }
    }
);
```

### getFeature {#get-feature}

`getFeature` retorna a carga do recurso avaliado para o contexto fornecido. Use essa API quando precisar de mais do que habilitado/desabilitado e quiser metadados ou valores de recursos.

**Assinatura**

*Kotlin*

```kotlin
Flag.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

*Java*

```java
Flag.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | String | Chave de recurso para avaliar em Sinalizadores |
| `evaluationContext` | ContextoDeAvaliaçãoDoRecurso | Inclua atributos de direcionamento conforme necessário; use `FeatureEvaluationContext.builder().build()` para um contexto vazio. Consulte [Contexto de avaliação](#evaluation-context). |
| `callback` | AdobeCallback&lt;ResultadoDaAvaliaçãoDoRecurso> | Invocado com a carga do recurso avaliado; pode ser `null` quando o recurso não é encontrado. Você também pode passar `AdobeCallbackWithError<FeatureEvaluationResult>` para manipular `fail(...)`. |

**Resposta**

*FeatureEvaluationResult*

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | Int | Identificador numérico do recurso |
| `key` | String | Chave do recurso |
| `featureGroupKey` | String? | Chave do grupo de recursos quando disponível |
| `meta` | String? | Metadados de recurso como uma sequência de caracteres JSON quando disponíveis |
| `analyticsParam` | AnalyticsParam? | Detalhes do Analytics para o recurso avaliado |

*AnalyticsParam*

| Campo | Tipo | Descrição |
|---|---|---|
| `featureGroupId` | Int | Identificador do grupo de recursos numéricos |
| `featureId` | Int | Identificador numérico do recurso |
| `variantId` | String? | Identificador da variante |

**Exemplos**

*Kotlin*

```kotlin
import com.adobe.marketing.mobile.AdobeCallback
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult
import com.adobe.marketing.mobile.flags.Flag

Flag.getFeature(
    "new-flag",
    ctx,
    object : AdobeCallback<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            if (!meta.isNullOrEmpty()) {
                // Feature metadata is available: use it to drive the feature behavior
            } else {
                // No metadata available: fall back to the default behavior
            }
        }
    }
)
```

*Java*

```java
import com.adobe.marketing.mobile.AdobeCallback;
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult;
import com.adobe.marketing.mobile.flags.Flag;

Flag.getFeature(
    "new-flag",
    ctx,
    new AdobeCallback<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            String meta = feature != null ? feature.getMeta() : null;
            if (meta != null && !meta.isEmpty()) {
                // Feature metadata is available: use it to drive the feature behavior
            } else {
                // No metadata available: fall back to the default behavior
            }
        }
    }
);
```

### extensionVersion {#extension-version}

Retorna a cadeia de caracteres da versão da extensão Sinalizadores.

**Sintaxe**

```kotlin
Flag.extensionVersion(): String
```

**Exemplo**

*Kotlin*

```kotlin
val version = Flag.extensionVersion()
```

*Java*

```java
String version = Flag.extensionVersion();
```

## Resumo da API {#api-summary}

| administração | Devoluções |
|---|---|
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. `FeatureEvaluationContext` carrega atributos de direcionamento para regras. Consulte [Avaliação de recursos](#is-feature-enabled). | Booleano via retorno de chamada |
| `getFeature(featureKey, evaluationContext, callback)`. Retorna a carga do recurso avaliado para o contexto especificado. Consulte [getFeature](#get-feature). | FeatureEvaluationResult via retorno de chamada |
| `extensionVersion()` | String |

## Consulte também {#see-also}

* [Aplicativos móveis](../../integrate/mobile-applications.md)
* [SDKs](../../integrate/sdks.md)

<!-- -->
