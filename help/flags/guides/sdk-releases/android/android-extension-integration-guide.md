---
title: Guia de integração do Flags extension for Android
description: Saiba como integrar a extensão Sinalizadores ao Adobe Experience Platform Mobile SDK no Android.
badge: label="Beta" type="Informative"
hide: true
exl-id: 683ef4d4-e637-4b7b-b694-689c7e65a99e
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: c1fafcfcd7d5d22781abdd10e6eb3c2b84136c2d
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 4%
---
# Extensão de sinalizadores para o Android {#android-extension-integration-guide}

Este guia descreve como integrar a extensão Flags ao Adobe Experience Platform Mobile SDK no Android.

## Pré-requisitos {#prerequisites}

Antes de implementar a extensão Sinalizadores, verifique se você tem:

* Uma propriedade móvel configurada em [Adobe Experience Platform Data Collection](https://experience.adobe.com/#/data-collection)
* A extensão Adobe Flags instalada e configurada em sua propriedade móvel
* Uma ID de organização da Adobe Experience Cloud
* Uma sequência de dados do Edge Network configurada em sua propriedade móvel para receber análises de exposição
* Android API 21 (Android 5.0 Lollipop) ou posterior
* Mobile Core 3.6.0 ou posterior (incluído em `sdk-bom` 3.17.0 e posterior)

## Dependências de extensão {#extension-dependencies}

A extensão Flags requer as seguintes extensões do Adobe Experience Platform:

| Extensão | Descrição | Obrigatório |
|---|---|---|
| [Núcleo do dispositivo móvel](https://developer.adobe.com/client-sdks/home/base/mobile-core/) | Fornece configuração, processamento de eventos e inicialização do SDK | Sim |
| [Vida útil](https://developer.adobe.com/client-sdks/home/base/mobile-core/lifecycle/) | Relata quando o aplicativo é movido para o primeiro ou segundo plano | Sim |
| [Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/) | Envia análises de exposição para o Adobe Experience Platform | Sim |
| [Identidade do Edge Network](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) | Fornece as identidades usadas para atribuir usuários a variantes | Sim |

Verifique se essas extensões estão instaladas na propriedade móvel da Coleção de dados e incluídas nas dependências do aplicativo.

## Configurar a extensão Sinalizadores na Coleção de dados {#configure}

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

## Adicionar a extensão Sinalizadores ao seu aplicativo {#add-to-app}

### Adicionar dependências {#add-dependencies}

>[!IMPORTANT]
>
>A extensão Sinalizadores não faz parte da BOM do Mobile SDK. Substitua `<latest-version>` pela versão mais recente da Maven Central. Sem uma versão, Gradle não pode resolver a dependência.
>
></br>
>&gt;Para aplicativos de produção, a Adobe recomenda usar números de versão explícitos em vez de versões dinâmicas, como "3.+". Consulte [Gerenciamento de dependências Gradle](https://docs.gradle.org/current/userguide/dependency_management.html) para obter mais informações.

Adicione as seguintes dependências ao arquivo `build.gradle.kts` (Kotlin) ou `build.gradle` (Groovy) do seu aplicativo:

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
dependencies {
    // Adobe Experience Platform Mobile SDK BOM (3.17.0 or later)
    implementation(platform("com.adobe.marketing.mobile:sdk-bom:3.+"))

    // Required extensions (versions managed by the BOM)
    implementation("com.adobe.marketing.mobile:core")
    implementation("com.adobe.marketing.mobile:lifecycle")
    implementation("com.adobe.marketing.mobile:edge")
    implementation("com.adobe.marketing.mobile:edgeidentity")

    // Flags extension (not managed by the BOM; specify the version)
    implementation("com.adobe.marketing.mobile:flags:<latest-version>")
}
```

>[!TAB Groovy]

```groovy
dependencies {
    // Adobe Experience Platform Mobile SDK BOM (3.17.0 or later)
    implementation platform('com.adobe.marketing.mobile:sdk-bom:3.+')

    // Required extensions (versions managed by the BOM)
    implementation 'com.adobe.marketing.mobile:core'
    implementation 'com.adobe.marketing.mobile:lifecycle'
    implementation 'com.adobe.marketing.mobile:edge'
    implementation 'com.adobe.marketing.mobile:edgeidentity'

    // Flags extension (not managed by the BOM; specify the version)
    implementation 'com.adobe.marketing.mobile:flags:<latest-version>'
}
```

>[!ENDTABS]

### Inicializar o SDK {#initialize-sdk}

>[!IMPORTANT]
>
>Para aplicativos de produção, use somente `LoggingMode.ERROR`. Não use `DEBUG` ou `VERBOSE` em compilações de versão.

Inicialize o Mobile SDK na classe `Application` antes de chamar APIs de extensão de Sinalizadores. Use a ID de arquivo de ambiente da sua propriedade móvel para que o aplicativo escolha as configurações de Sinalizadores publicadas na Coleção de dados.

`MobileCore.initialize` registra cada extensão do Adobe incluída em suas dependências de Gradle, incluindo a extensão Sinalizadores.

Observe que, quando você usar `MobileCore.initialize`, não ligue também para `MobileCore.registerExtensions`, `MobileCore.lifecycleStart` ou `MobileCore.lifecyclePause`. Estas são para você.

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import android.app.Application
import com.adobe.marketing.mobile.LoggingMode
import com.adobe.marketing.mobile.MobileCore

class MainApplication : Application() {

    override fun onCreate() {
        super.onCreate()

        MobileCore.setLogLevel(LoggingMode.ERROR)

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID")
    }
}
```

>[!TAB Java]

```java
import android.app.Application;
import com.adobe.marketing.mobile.LoggingMode;
import com.adobe.marketing.mobile.MobileCore;

public class MainApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();

        MobileCore.setLogLevel(LoggingMode.ERROR);

        // Initialize with your Environment File ID from Data Collection
        MobileCore.initialize(this, "YOUR_ENVIRONMENT_FILE_ID");
    }
}
```

>[!ENDTABS]

### Registrar a classe Application {#register-application}

Registre sua classe `Application` em `AndroidManifest.xml`:

```xml
<application
    android:name=".MainApplication"
    ... >
</application>
```

### Se você registrar extensões manualmente {#register-manually}

Se o aplicativo não puder usar o `MobileCore.initialize` e registrar extensões com `MobileCore.registerExtensions`, adicione `Flag.EXTENSION` à lista. Use a Identidade para a classe Edge Network, `com.adobe.marketing.mobile.edge.identity.Identity`, não o `com.adobe.marketing.mobile.Identity` herdado.

```kotlin
import com.adobe.marketing.mobile.Edge
import com.adobe.marketing.mobile.Lifecycle
import com.adobe.marketing.mobile.MobileCore
import com.adobe.marketing.mobile.edge.identity.Identity
import com.adobe.marketing.mobile.flags.Flag

MobileCore.setApplication(this)
MobileCore.configureWithAppID("YOUR_ENVIRONMENT_FILE_ID")
MobileCore.registerExtensions(
    listOf(Lifecycle.EXTENSION, Identity.EXTENSION, Edge.EXTENSION, Flag.EXTENSION)
) { }
```

Nesta configuração, o ciclo de vida não é rastreado automaticamente. Chame `MobileCore.lifecycleStart(null)` em cada atividade de `onResume` e `MobileCore.lifecyclePause()` em seu `onPause`. Sem essas chamadas, a extensão mantém os sinalizadores de atualização enquanto o aplicativo está em segundo plano e a análise de exposição é enviada posteriormente.

## Contexto de avaliação {#evaluation-context}

`FeatureEvaluationContext` contém os atributos de direcionamento que suas regras de sinalizador usam. Você não passa uma identidade: a extensão a lê da Identidade do Edge Network em cada avaliação. Consulte [Identidade personalizada](#custom-identity).

| Método | Obrigatório | Descrição |
|---|---|---|
| `withAttributes(map)` | Não | `Map<String, List<String>>`. Cada chave é um nome de atributo usado pelas suas regras de sinalizador (por exemplo, `locale` ou `appVersion`). Cada valor é a lista de valores do usuário atual (por exemplo, `["en_US"]`). |

* Um contexto é necessário para cada avaliação. Se você não tiver atributos, passe `FeatureEvaluationContext.builder().build()`.
* Chame `withAttributes` no máximo uma vez por construtor.
* Um contexto criado não pode ser alterado, portanto, você pode reutilizá-lo nas avaliações.

### Uso {#evaluation-context-usage}

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.flags.FeatureEvaluationContext

val ctx = FeatureEvaluationContext.builder()
    .withAttributes(
        mapOf(
            "locale" to listOf("en_US"),
            "platform" to listOf("ANDROID")
        )
    )
    .build()
```

>[!TAB Java]

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

>[!ENDTABS]

### Amostra de atributos de direcionamento {#sample-attributes}

| Atributo | Descrição | Valores de exemplo |
|---|---|---|
| `locale` | Local do usuário | `["en_US"]`, `["fr_FR"]` |
| `platform` | Plataforma | `["ANDROID"]` |
| `appVersion` | Versão do aplicativo | `["3.0.0"]` |
| `deviceType` | Tipo de dispositivo | `["phone"]`, `["tablet"]` |

Os nomes e valores de atributos devem corresponder aos usados nas regras de sinalizador.

## Identidade personalizada {#custom-identity}

A extensão Sinalizadores usa a Identidade para [extensão do Edge Network](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/) para resolução de identidade. Um sinalizador de recurso pode ser coortado em uma identidade personalizada, por exemplo, uma ID de CRM ou uma ID de fidelidade, para que as divisões de variante e as análises sejam vinculadas à identidade que é importante para o aplicativo.

O namespace de identidade personalizado deve ser selecionado na interface do usuário de Sinalizadores quando o sinalizador de recurso é criado. Para avaliar um sinalizador em relação a essa identidade, a mesma identidade deve estar presente na Identidade Edge `identityMap` no dispositivo, usando o namespace correspondente. Forneça a ela, em tempo de execução, a Identidade da API `updateIdentities` do Edge Network.

### Adicionar a identidade personalizada ao mapa de identidade {#add-identity}

Adicione a identidade no mesmo namespace configurado no sinalizador de recurso, antes de avaliar o sinalizador.

Observe o seguinte ao adicionar a identidade:

* O namespace deve corresponder exatamente, incluindo letras maiúsculas e minúsculas.
* Se o namespace tiver mais de uma identidade, será usada a marcada como primária. Caso contrário, o primeiro será usado.
* Se a identidade estiver ausente quando o sinalizador for avaliado, o usuário será atribuído por uma ID temporária que muda sempre que o aplicativo for iniciado. A variante do usuário pode ser alterada entre inicializações do aplicativo. Sempre defina a identidade antes de avaliar os sinalizadores que a usam.

>[!BEGINTABS]

>[!TAB Kotlin]

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

>[!TAB Java]

```java
import com.adobe.marketing.mobile.edge.identity.AuthenticatedState;
import com.adobe.marketing.mobile.edge.identity.Identity;
import com.adobe.marketing.mobile.edge.identity.IdentityItem;
import com.adobe.marketing.mobile.edge.identity.IdentityMap;

IdentityMap identityMap = new IdentityMap();
identityMap.addItem(
        new IdentityItem("1111", AuthenticatedState.AUTHENTICATED, true),
        "userCRMId"); // must match the namespace configured on the feature flag
Identity.updateIdentities(identityMap);
```

>[!ENDTABS]

## Referência da API {#api-reference}

### Retornos de chamada e tratamento de erros {#callbacks-errors}

Estas regras se aplicam a `isFeatureEnabled` e `getFeature`:

* Sempre forneça uma experiência padrão. Passar um `AdobeCallbackWithError` e mostrar sua experiência padrão em `fail`. Com um `AdobeCallback` simples, nada é chamado quando ocorre um erro.

* A extensão pré-carrega definições de sinalizador quando o aplicativo é iniciado. Depois disso, os sinalizadores são avaliados no dispositivo.

* Outros erros: `fail` é chamado com `AdobeError.UNEXPECTED_ERROR` quando:

  * a chave do recurso está vazia,
  * as configurações de Sinalizadores ou a ID da organização da Experience Cloud estão ausentes na configuração publicada, ou
  * não foi possível baixar as definições de sinalizador quando o aplicativo foi iniciado (por exemplo, o dispositivo estava offline). A extensão tenta novamente na próxima atualização de configuração, geralmente na próxima inicialização do aplicativo.

### isFeatureEnabled {#is-feature-enabled}

Retorna se um recurso está habilitado para o usuário atual.

**Assinatura**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
Flag.isFeatureEnabled(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<Boolean>
)
```

>[!TAB Java]

```java
Flag.isFeatureEnabled(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<Boolean> callback);
```

>[!ENDTABS]

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | String | Chave do recurso a ser avaliado |
| `evaluationContext` | ContextoDeAvaliaçãoDoRecurso | Direcionamento de atributos. Use `FeatureEvaluationContext.builder().build()` se não tiver nenhum. Consulte [Contexto de avaliação](#evaluation-context). |
| `callback` | AdobeCallback&lt;Booleano> | Chamado com `true` se o recurso estiver habilitado para o usuário. Chamado com `false` se o recurso não for encontrado, as regras de direcionamento não corresponderem ou o usuário estiver no grupo de controle. Envie um `AdobeCallbackWithError<Boolean>` para também receber erros. |

**Exemplos**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.AdobeCallbackWithError
import com.adobe.marketing.mobile.AdobeError
import com.adobe.marketing.mobile.flags.Flag

Flag.isFeatureEnabled(
    "new-checkout",
    ctx,
    object : AdobeCallbackWithError<Boolean> {
        override fun call(isEnabled: Boolean?) {
            runOnUiThread {
                if (isEnabled == true) showNewCheckout() else showDefaultCheckout()
            }
        }

        override fun fail(error: AdobeError?) {
            runOnUiThread { showDefaultCheckout() }
        }
    }
)
```

>[!TAB Java]

```java
import com.adobe.marketing.mobile.AdobeCallbackWithError;
import com.adobe.marketing.mobile.AdobeError;
import com.adobe.marketing.mobile.flags.Flag;

Flag.isFeatureEnabled(
    "new-checkout",
    ctx,
    new AdobeCallbackWithError<Boolean>() {
        @Override
        public void call(Boolean isEnabled) {
            runOnUiThread(() -> {
                if (Boolean.TRUE.equals(isEnabled)) {
                    showNewCheckout();
                } else {
                    showDefaultCheckout();
                }
            });
        }

        @Override
        public void fail(AdobeError error) {
            runOnUiThread(() -> showDefaultCheckout());
        }
    }
);
```

>[!ENDTABS]

### getFeature {#get-feature}

Retorna o recurso avaliado para o usuário atual, incluindo seus metadados. Use essa API quando precisar de mais do que habilitado ou desabilitado.

**Assinatura**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
Flag.getFeature(
    featureKey: String,
    evaluationContext: FeatureEvaluationContext,
    callback: AdobeCallback<FeatureEvaluationResult>
)
```

>[!TAB Java]

```java
Flag.getFeature(
    String featureKey,
    FeatureEvaluationContext evaluationContext,
    AdobeCallback<FeatureEvaluationResult> callback);
```

>[!ENDTABS]

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | String | Chave do recurso a ser avaliado |
| `evaluationContext` | ContextoDeAvaliaçãoDoRecurso | Direcionamento de atributos. Use `FeatureEvaluationContext.builder().build()` se não tiver nenhum. Consulte [Contexto de avaliação](#evaluation-context). |
| `callback` | AdobeCallback&lt;ResultadoDaAvaliaçãoDoRecurso> | Chamado com o recurso avaliado, ou com `null` quando o recurso não é fornecido ao usuário: a chave é desconhecida, os critérios de direcionamento não são atendidos ou o usuário está em um coorte de controle. `null` é um resultado normal, não um erro. As exposições de coorte de controle ainda são relatadas para o Analytics. Envie um `AdobeCallbackWithError<FeatureEvaluationResult>` para receber `fail(...)` por falhas genuínas, como tempos limite. |

Trate um resultado de `null` como &quot;recurso desativado&quot; e mostre sua experiência padrão. Também mostra a experiência padrão quando `fail` é chamado, o que só acontece em falhas genuínas, como tempos limite.

**Resposta**

*FeatureEvaluationResult*

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | Int | ID do recurso |
| `key` | String | Chave do recurso |
| `featureGroupKey` | String? | Chave do grupo de recursos, se o recurso pertencer a um grupo |
| `meta` | String? | Metadados configurados para o recurso, como texto sem formatação, ou `null` se nenhum estiver definido. Se você armazenou o JSON, analise a cadeia de caracteres no aplicativo. |
| `analyticsParam` | AnalyticsParam? | Detalhes do Analytics para a avaliação |

*AnalyticsParam*

| Campo | Tipo | Descrição |
|---|---|---|
| `featureGroupId` | Int | ID do grupo de recursos |
| `featureId` | Int | ID do recurso |
| `variantId` | String? | ID da variante à qual o usuário foi atribuído |

**Exemplos**

>[!BEGINTABS]

>[!TAB Kotlin]

```kotlin
import com.adobe.marketing.mobile.AdobeCallbackWithError
import com.adobe.marketing.mobile.AdobeError
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult
import com.adobe.marketing.mobile.flags.Flag

Flag.getFeature(
    "new-checkout",
    ctx,
    object : AdobeCallbackWithError<FeatureEvaluationResult> {
        override fun call(feature: FeatureEvaluationResult?) {
            val meta = feature?.meta
            runOnUiThread {
                if (!meta.isNullOrEmpty()) applyExperience(meta) else showDefaultExperience()
            }
        }

        override fun fail(error: AdobeError?) {
            runOnUiThread { showDefaultExperience() }
        }
    }
)
```

>[!TAB Java]

```java
import com.adobe.marketing.mobile.AdobeCallbackWithError;
import com.adobe.marketing.mobile.AdobeError;
import com.adobe.marketing.mobile.flags.FeatureEvaluationResult;
import com.adobe.marketing.mobile.flags.Flag;

Flag.getFeature(
    "new-checkout",
    ctx,
    new AdobeCallbackWithError<FeatureEvaluationResult>() {
        @Override
        public void call(FeatureEvaluationResult feature) {
            final String meta = feature != null ? feature.getMeta() : null;
            runOnUiThread(() -> {
                if (meta != null && !meta.isEmpty()) {
                    applyExperience(meta);
                } else {
                    showDefaultExperience();
                }
            });
        }

        @Override
        public void fail(AdobeError error) {
            runOnUiThread(() -> showDefaultExperience());
        }
    }
);
```

>[!ENDTABS]

### extensionVersion {#extension-version}

Retorna a versão da extensão Sinalizadores.

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
| `isFeatureEnabled(featureKey, evaluationContext, callback)`. Consulte [isFeatureEnabled](#is-feature-enabled). | Booleano via retorno de chamada |
| `getFeature(featureKey, evaluationContext, callback)`. Consulte [getFeature](#get-feature). | FeatureEvaluationResult via retorno de chamada |
| `extensionVersion()` | String |

## Depuração {#debugging}

Para depurar, defina `MobileCore.setLogLevel(LoggingMode.DEBUG)` em uma compilação de depuração e filtre Logcat por `Flags`. Você deve ver uma mensagem `Discovered extension` do MobileCore para `com.adobe.marketing.mobile.flags.FlagExtension`.


