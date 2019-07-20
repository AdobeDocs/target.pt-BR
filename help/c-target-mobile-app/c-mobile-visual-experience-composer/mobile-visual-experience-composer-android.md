---
description: A nova Biblioteca SDK do Target permite que os desenvolvedores façam uma configuração única nos aplicativos móveis com Android e que os profissionais de marketing usem os recursos do Mobile Visual Experience Composer (VEC).
keywords: mobile vec, mobile visual experience composer, opções do mobile experience composer, configuração, android
seo-description: A nova Biblioteca SDK do Target permite que os desenvolvedores façam uma configuração única nos aplicativos móveis com Android e que os profissionais de marketing usem os recursos do Mobile Visual Experience Composer (VEC).
seo-title: Android - Configuração do aplicativo móvel
solution: Target
title: Android - Configuração do aplicativo móvel
topic: Padrão
uuid: 39938ec2-b12e-44cf-9218-69195fba0ff7
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Android - Configuração do aplicativo móvel{#android-set-up-the-mobile-app}

O Visual Experience Composer (VEC) para aplicativos móveis do Adobe Target permite que os desenvolvedores façam uma configuração única nos aplicativos móveis com Android e que os profissionais de marketing utilizem os recursos do VEC para aplicativos móveis.

Para obter mais informações sobre a ativação da extensão VEC do Adobe Target, consulte [Adobe Target - Visual Experience Composer](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) nos *SDKs da Adobe Experience Platform para dispositivos móveis*.

## Incluir o SDK para dispositivos móveis e a biblioteca do Target {#sdk-library}

1. Para obter informações sobre a inicialização do SDK V5, consulte [Inicializar o SDK e configurar o rastreamento](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk).
1. Adicione a linha a seguir à seção de dependências:

   ```
   implementation 'com.adobe.marketing.mobile:target-vec:1.+'
   ```

1. O VEC para aplicativos móveis exige que os seguintes artefatos sejam incluídos como uma dependência no `build.gradle`.

   ```
    implementation 'com.google.code.gson:gson:2.8.2'
    implementation 'android.arch.lifecycle:extensions:1.1.1'
    implementation('io.github.sac:SocketclusterClientJava:1.7.5')
    implementation 'com.android.support:support-annotations:28.0.0'
    implementation 'com.android.support:support-compat:28.0.0'
    implementation 'com.android.support:design:28.0.0'
   ```

1. Adicione um filtro de intenção ao arquivo do `AndroidManifest.XML`, escolhendo um esquema único de deep link para criação no VEC para aplicativos móveis (por exemplo, `[sdkbetabus://com.adobe.sdkbetabus](sdkbetabus://com.adobe.sdkbetabus)`):

   ```
   <activity 
       android:name=".listing.MoviesListingActivity" 
       android:launchMode="singleTask"> 
       <intent-filter> 
           <action android:name="android.intent.action.VIEW" /> 
   
           <category android:name="android.intent.category.DEFAULT" /> 
           <category android:name="android.intent.category.BROWSABLE" /> 
   
           <data 
               android:host="com.adobe.sdkbetabus" 
               android:scheme="sdkbetabus" /> 
       </intent-filter> 
   </activity>
   ```

1. Vá para o projeto para dispositivos móveis e insira as seguintes linhas ao final de `Application::onCreate override`:

   ```
   public class SDKTest extends MultiDexApplication { 
   
       @Override 
       public void onCreate() { 
           /* Put Your App's implementation */ 
           MobileCore.setApplication(this); 
           MobileCore.setLogLevel(LoggingMode.DEBUG); 
           MobileCore.configureWithAppID("YOUR_ADOBE_LAUNCH_APP_ID"); 
   
           ... 
           try { 
               TargetVEC.registerExtension(); //Single line code to initialize TargetVEC
               Target.registerExtension();
               Identity.registerExtension();
               Lifecycle.registerExtension();
               Signal.registerExtension();
               MobileCore.start(new AdobeCallback () {
                  @Override
                  public void call(Object o) {
                     MobileCore.configureWithAppID("launch-EN4e833d644d1949e39e985ddad4f52bd4-development");
                  }
               });
           } catch (InvalidInitException e) { 
             .. 
           }
       }
   
   /* Rest of Application test goes here ... */
   ```

1. Se a sua configuração não estiver funcionando, analise os projetos de exemplo fornecidos abaixo que devem funcionar por padrão e analise as alterações nas localizações a seguir:

   1. `Application::OnCreate override`
   1. `AndroidManifest.XML`
   1. `build.gradle` do aplicativo Android

## Configurar exibições do Target no aplicativo móvel{#views}

O SDK para dispositivos móveis da Adobe expõe um novo método que os desenvolvedores acionam sempre que uma nova Exibição é renderizada. Como desenvolvedor, você deve assegurar que as exibições sejam nomeadas de maneira adequada e a chamada a `targetView` esteja no código principal da interface do usuário. Nesta seção, será demostrado primeiro como inserir essas chamadas com dois aplicativos de demonstração diferentes, além de discutir as diretrizes gerais sobre como inserir corretamente as chamadas de API da Exibição do Target em qualquer aplicativo Android.

>[!NOTE]
>
>Se não o `targetView function` for acionado, a extensão VEC tenta identificar a Exibição na atividade do Android. Para aplicativos sem exibições dinâmicas, isso pode ser uma etapa opcional.

Uma Exibição do Target pode ser acionada com uma chamada de função. Todos os parâmetros de direcionamento podem ser fornecidos opcionalmente com a exibição.

```
public class TargetVEC { 
   
   /** 
    * Marks a view hierarchy for editing in Mobile App VEC.  Call must insert when the view hierarchy 
    * is memory and committed to being shown, but not yet shown on the screen. 
    * 
    * @param viewName the unique Target View Name 
    */ 
   public static void targetView(String viewName); 
  
  /** 
   * Trigger Target view 
   * Triggering a Target view may cause Target offers to be applied on the current container component. 
   * Note that Target offers are applied from local Target cache, so flicker should be negligible. 
   * 
   * @param viewName Mandatory Target View name, which must be unique at app level 
   * @param parameters Parameters to be included in the next Target call 
   */ 
  
    public static void targetView(String viewName, TargetParameters parameters); 
}
```

Nosso primeiro projeto de exemplo é um modelo de um aplicativo simples de horários de ônibus. Para configurar este aplicativo para ser usado no VEC para aplicativos móveis:

1. No Android Studio, abra o projeto com o arquivo `build.gradle` no subdiretório do pacote `BusBooking`.
1. No método `DemoApplication::OnCreate`, adicione `TargetVEC.registerExtension()` para registrar a extensão VEC do Target com outras extensões.
1. Compile e execute o aplicativo.
1. Para entrar no modo de criação do VEC para aplicativos móveis, use o [!DNL sdkbetabus://com.adobe.sdkbetabus] como seu esquema de URL e abra o deep link gerado no dispositivo (consulte as instruções abaixo).

Deste aplicativo simples de horários de ônibus, usamos todas as Exibições do Target geradas automaticamente associadas ao ciclo de vida da atividade. Além disso, demonstramos a flexibilidade da API ao chamar a API de Exibição do Target em um elemento de exibição personalizado dinamicamente adicionado, quando um botão oculto é clicado (a imagem da oferta na tela). Esta nova Exibição do Target é implementada ao se inserir uma chamada à API no código em `OfferDetailsActivity.java:40`. Quando o botão oculto é clicado, um novo evento da Exibição do Target chamado "SURPRISE_VIEW" é acionado, o que permite ao profissional de marketing direcionar com mais precisão as alterações na experiência com o aplicativo.

Inserção da exibição dinâmica direcionada:

```
package com.adobe.target.examples.bus; 
   
import android.app.DialogFragment; 
import android.os.Bundle; 
import android.os.Handler; 
import android.support.v7.app.AppCompatActivity; 
import android.support.v7.widget.Toolbar; 
import android.view.View; 
import android.view.ViewGroup; 
import android.widget.LinearLayout; 
import android.widget.Toast; 
   
import com.adobe.target.mobile.TargetVEC; 
   
/** 
 * This activity class is responsible to show offer details 
 */ 
public class OfferDetailsActivity extends AppCompatActivity { 
    @Override 
    protected void onCreate(Bundle savedInstanceState) { 
        super.onCreate(savedInstanceState); 
        setContentView(R.layout.activity_offer_details); 
        setUpToolBar(); 
        final Handler mainHandler = new Handler(getApplicationContext().getMainLooper()); 
   
        final View surpriseView = getLayoutInflater().inflate(R.layout.suprise_layout, 
                (ViewGroup) findViewById(android.R.id.content), false); 
   
        final View imagePresentView = this.findViewById(R.id.image_present); 
        final LinearLayout currentLayout = this.findViewById(R.id.offer_layout); 
   
        imagePresentView.setOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                Toast.makeText(getApplicationContext(),"Surprise!", Toast.LENGTH_SHORT).show(); 
                mainHandler.post(new Runnable() { 
                    @Override 
                    public void run() { 
                        currentLayout.addView(surpriseView); 
                        TargetVEC.targetView("SURPRISE_VIEW"); 
                        currentLayout.invalidate(); 
                    } 
                }); 
                // One-shot.  Remove clicker afterwards. 
                imagePresentView.setOnClickListener(null); 
            } 
        }); 
    } 
   
    private void setUpToolBar() { 
        Toolbar toolbar = findViewById(R.id.toolbar); 
        toolbar.setNavigationIcon(R.drawable.abc_ic_ab_back_material); 
        toolbar.setTitle("Buy 1 Get 1"); 
        toolbar.setNavigationOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                onBackPressed(); 
            } 
        }); 
    } 
   
    @Override 
    protected void onPause() { 
        super.onPause();
        MobileCore.lifecyclePause();
    } 
   
    @Override 
    protected void onResume() { 
        super.onResume();
        MobileCore.lifecycleStart(null);
    } 
}
```

## Configuração dos parâmetros de perfil e outros parâmetros globais {#parameters}

Agora, há suporte para a configuração de parâmetros globais que serão passados em cada chamada de API, assim como a passagem de parâmetros mbox/view para as exibições correspondentes.

Os parâmetros incluem:

* Parâmetros mbox/view
* parâmetros do perfil de in-mbox e script
* Parâmetros do produto
* Parâmetros de pedido

**Os parâmetros globais são compatíveis com:**

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("mboxparam1", "mboxvalue1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekey1", "profilevalue1"); 
  
TargetVEC.setGlobalRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**Os parâmetros de envio para o próximo acionador de exibição:**

Fornecemos algumas exibições automáticas criadas por padrão, como "`AUTO_<activity|fragment name>`" para cada atividade e fragmento presentes no seu aplicativo. Se você quiser enviar esses parâmetros, poderá chamar a seguinte API:

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("viewKey1", "viewparam1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekeyforview1", "profilevalueforview1"); 
  
TargetVEC.setRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**Passagem de parâmetros para uma exibição específica:**

Vimos a API acionar Exibições via `TargetVEC.targetView("view_name")`. Você também pode passar parâmetros específicos para a exibição em particular, como mostrado abaixo:

```
Map<String, String> profileParams = new HashMap<>(); 
profileParams.put("surprisekey1", "surprisevalue1");  //ProfileParams 
TargetVEC.targetView("SURPRISE_VIEW", 
        new TargetParameters.Builder() 
                .profileParameters(profileParams) 
                .product(new TargetProduct("3354", "kitchen")) 
                .build());
```

## Chamada explícita à API de pré-busca {#section_2D02B74558474D3BA9F25E4D25E7C7E3}

Pode haver determinados cenários em que você queira chamar a API de pré-busca novamente para atualizar as ofertas armazenadas no cache. As seguintes APIs são expostas, descritas como:

* **prefetchOffers**

   ```
   /** 
    * Prefetch Target offers. 
    * Note that calling this will pre-hide the current layout, until Target offers are prefetched 
    * and applied to currently visible Target views, possibly causing flicker, thus it's recommended 
    * to call this method inside the containing component's onCreate() lifecycle method 
    */ 
   public static void prefetchOffers();
   ```

* **prefetchOffersBackground**

   ```
   /** 
    * Prefetch Target offers in the background. 
    * Note, that in contrast to prefetchOffers(), calling this method will NOT pre-hide 
    * the current layout, instead prefetched Target offers will be only be cached and will subsequently 
    * be applied as Target Views are being triggered. 
    */ 
   public static void prefetchOffersBackground();
   ```

## Tutorial: Implement the Experience Cloud in Mobile Android Applications {#tutorial}

* [Implementar a Experience Cloud em aplicativos móveis Android](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-mobile-android-apps-with-launch/index.html)

Após concluir este tutorial, você poderá:

* Criar uma propriedade Mobile Launch
* Instalar uma propriedade Launch em um aplicativo Android
* Implemente as seguintes soluções da Adobe Experience Cloud:
   * Serviço da Experience Cloud ID
   * Adobe Target
   * Adobe Analytics
   * Adobe Audience Manager

* Publicar alterações no Launch por meio de ambientes de desenvolvimento, armazenamento temporário e produção
