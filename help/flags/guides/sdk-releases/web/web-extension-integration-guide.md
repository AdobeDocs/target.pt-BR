---
title: Extensão de sinalizadores para o guia de integração com a Web
description: Saiba como integrar a extensão Sinalizadores ao Adobe Experience Platform Web SDK (Alloy) para aplicativos web.
hide: true
source-git-commit: 9c6f2b72f964b06da51e1f3655545147d7240a93
workflow-type: tm+mt
source-wordcount: '1180'
ht-degree: 7%

---

# Extensão de sinalizadores para a Web {#web-extension-integration-guide}

Este guia descreve como integrar a extensão Flags com o Adobe Experience Platform Web SDK (Alloy) para aplicações web. A extensão Flags permite o gerenciamento de sinalizadores de recursos e implantações controladas para experiências da Web.

## Pré-requisitos {#prerequisites}

Antes de implementar a extensão Sinalizadores, verifique se você tem:

* Uma propriedade da Web configurada em [Coleção de dados do Adobe Experience Platform](https://experience.adobe.com/#/data-collection)
* Extensão do Adobe Experience Platform Web SDK instalada
* Uma ID de organização da Adobe Experience Cloud
* Acesso aos sinalizadores em sua organização

### Permissões necessárias {#required-permissions}

Certifique-se de que você tenha os seguintes direitos de propriedade:

* Desenvolver
* Gerenciar extensões

## Dependências de extensão {#extension-dependencies}

A extensão Flags requer a seguinte extensão do Adobe Experience Platform:

| Extensão | Descrição | Obrigatório |
|---|---|---|
| Adobe Experience Platform Web SDK | Fornece funcionalidades essenciais, incluindo comunicação com a Edge Network e gerenciamento de identidade | Sim |

Verifique se essa extensão está instalada na propriedade da Web da Coleção de dados antes de instalar a extensão Sinalizadores.

## Configurar a extensão Sinalizadores na Coleção de dados {#configure}

### Instalar a extensão {#install-extension}

1. Faça logon em [experience.adobe.com](https://experience.adobe.com) usando suas credenciais da Adobe ID.
1. Navegue até **Coleção de dados** > **Marcas**.
1. Selecione a propriedade de tag desejada.
1. Navegue até **Extensões** > **Catálogo**.
1. Pesquise por **Sinalizadores** e selecione o cartão de extensão.
1. Selecione **Instalar**.

### Definir configurações de extensão {#configure-settings}

Ao instalar a extensão Flags, você é levado para a página de configuração. Configure as seguintes definições:

| Configuração | Descrição | Obrigatório |
|---|---|---|
| ID do cliente | Um identificador exclusivo para seu aplicativo em Sinalizadores. | Sim |

### Salvar e publicar {#save-publish}

1. Selecione **Salvar** para salvar a configuração da extensão.
1. Siga o fluxo de publicação para implantar as alterações:
   1. Adicione a extensão a uma biblioteca.
   1. Crie para o ambiente de desenvolvimento.
   1. Valide com o Adobe Experience Platform Debugger.
   1. Promover para preparo e produção.

## Adicionar o código incorporado de Tags ao seu site {#embed-code}

Depois de publicar a biblioteca de tags, é necessário adicionar o código incorporado ao site. O código incorporado é uma marca `<script>` que carrega a biblioteca de marcas e todas as extensões configuradas, incluindo a extensão Sinalizadores.

### Copiar o código incorporado {#copy-embed-code}

1. Em Coleção de dados, navegue até a propriedade da Web.
1. Selecione **Ambientes** na navegação à esquerda.
1. Na linha do ambiente de destino (Desenvolvimento, Preparo ou Produção), selecione o ícone de caixa sob a coluna **Instalar**.
1. Na caixa de diálogo **Instruções de Instalação da Web**, o padrão das Marcas é o código de inserção assíncrono.
1. Selecione o ícone **Copiar** para copiar o código incorporado para a área de transferência.
1. Selecione **Fechar** para fechar a modal.

>[!NOTE]
>
>Cada ambiente tem um URL de código integrado exclusivo. Consulte Ambientes para obter mais informações.

### Implementar o código incorporado {#implement-embed-code}

Adicione o código de inserção no elemento `<head>` das páginas do HTML. O código incorporado deve ser colocado antes de outros scripts que dependem da biblioteca de tags:

```html
<!DOCTYPE html>
<html>
<head>
  <title>My Website</title>

  <!-- Adobe Experience Platform Tags embed code -->
  <script src="https://assets.adobedtm.com/yourcompany/your-property/launchENxxxxxxxxxxx.min.js" async></script>
</head>
<body>
  <!-- Your page content -->
</body>
</html>
```

>[!NOTE]
>
>Substitua a URL `src` pelo código incorporado real da página Ambientes. A URL contém o identificador da empresa, o identificador de propriedade e o identificador de ambiente (por exemplo, `launch-EN123456789abcdef.min.js`).

### Avaliar sinalizadores com componentes de Tags {#tags-components}

A extensão Sinalizadores fornece superfícies de avaliação nativas de tags.

| Componente | Tipo | Descrição |
|---|---|---|
| O Recurso Está Habilitado | Condição | Retorna se um recurso está habilitado para o usuário/contexto atual |
| Sinalizador de recurso | Elemento de dados | Retorna um objeto booleano ou de recurso completo |

## Inicializar o SDK {#initialize-sdk}

A extensão Flags é inicializada automaticamente quando a biblioteca de Tags é carregada. A extensão expõe o cliente em:

```javascript
window._flagClient
```

### Aguardar prontidão do cliente {#client-readiness}

As tags são carregadas de forma assíncrona. Antes de chamar métodos SDK a partir do código personalizado, aguarde até que o cliente seja inicializado:

```javascript
window.flagClientReady
  .then(function () {
    const enabled = window._flagClient.isFeatureEnabled('my-feature', context);
    // Use enabled to select the feature or fallback behavior.
  })
  .catch(function (error) {
    console.error('Flags initialization failed:', error);
  });
```

## Contexto de avaliação {#evaluation-context}

`FeatureEvaluationContext` inclui identidade (necessária para avaliação, segmentação A/B e análise) e atributos de direcionamento opcionais (usados para correspondência de regras).

| Propriedade | Obrigatório | Descrição |
|---|---|---|
| `identityNamespace` | Sim | Namespace de identidade (consulte [Namespaces de identidade da Adobe](https://experienceleague.adobe.com/pt-br/docs/experience-platform/identity/features/namespaces)). Valores comuns: `ECID`, `Email`, `CRMId`. |
| `identityId` | Sim | Valor de identidade do usuário atual. |
| `attributes` | Não | `Record<string, string[]>`. Chave é o nome do atributo de contexto usado pelas suas regras de sinalizador (por exemplo, `locale`, `platform`). Valor é a lista de valores de atributos candidatos para essa chave. |

Nos componentes de Tags, defina os padrões de identidade na condição ou na interface do elemento de dados. O elemento de dados Sinalizador de Recurso também aceita atributos de tempo de execução via `getVar(name, attributes)` quando o segundo argumento é um mapa de atributo simples.

### Uso {#usage}

```javascript
const context = {
  identityNamespace: 'ECID',
  identityId: 'your-visitor-ecid',
  attributes: {
    locale: ['en-US'],
    platform: ['web']
  }
};
```

## Referência da API {#api-reference}

### isFeatureEnabled {#is-feature-enabled}

`isFeatureEnabled` retorna se um recurso Sinalizadores está ativado ou desativado para o contexto fornecido. Passar `featureKey` e um `FeatureEvaluationContext`. Consulte [Contexto de avaliação](#evaluation-context). Use a condição de Marcas **Recurso Habilitado** ou chame `window._flagClient.isFeatureEnabled(...)` do código personalizado após a inicialização.

**Assinatura**

```javascript
isFeatureEnabled(featureKey: string, context: FeatureEvaluationContext): boolean
```

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | string | Chave de recurso para avaliar em Sinalizadores |
| `context` | ContextoDeAvaliaçãoDoRecurso | Identidade (obrigatório) e atributos opcionais de direcionamento. Consulte [Contexto de avaliação](#evaluation-context). |

### Criar um elemento de dados Sinalizador de recurso {#create-data-element}

Use um elemento de dados quando precisar de um valor de sinalizador disponível como `%Data Element Name%` em regras ou código personalizado.

**Etapas**

1. Na propriedade, vá para **Elementos de Dados** e selecione **Adicionar Elemento de Dados**.
1. Na tela **Criar Elemento de Dados**, configure os campos de Marcas:

   | Campo | Valor |
   |---|---|
   | Nome | Um nome descritivo (por exemplo `checkout flag`) |
   | Extensão | Sinalizadores |
   | Tipo de elemento de dados | Sinalizador de recurso |

1. Configure os campos de extensão **Sinalizadores**:

   | Campo | Obrigatório | Descrição |
   |---|---|---|
   | Chave do recurso | Sim | Chave exclusiva de sinalizador (por exemplo `checkout_flag`) |
   | Tipo de retorno | Sim | **Booleano (true/false)** — habilitado/desabilitado ou **Objeto de Recurso (detalhes completos)** — carga completa, incluindo `meta` |

1. Selecione **Salvar**.

**Tipos de retorno**

| Tipo de retorno | Resolve para |
|---|---|
| Booleano (true/false) | `true` se habilitado, `false` caso contrário |
| Objeto do recurso (detalhes completos) | Carga do recurso avaliada completamente, ou `null` quando não satisfaz as regras |

### Usar o elemento de dados {#use-data-element}

Em uma regra — faça referência por nome, por exemplo `%Test Flag%`.

No código personalizado — use `_satellite.getVar`. Com atributos de tempo de execução, passe um mapa de atributo simples como o segundo argumento a ser avaliado:

```javascript
var isEnabled = _satellite.getVar('Test Flag', {
  locale: ['en-US'],
  platform: ['web']
});

if (isEnabled) {
  // your custom code
} else {
  // your default code
}
```

### getFeature {#get-feature}

`getFeature` retorna a carga do recurso avaliado quando você precisa de metadados além de habilitado/desabilitado.

Use um elemento de dados **Sinalizador de Recurso** com **Tipo de Retorno: Objeto de Recurso (detalhes completos)** — consulte [Criar um Elemento de Dados de Sinalizador de Recurso](#create-data-element) — ou chame `window._flagClient.getFeature(...)` do código personalizado após `flagClientReady` resolver.

**Assinatura**

```javascript
getFeature(featureKey: string, context: FeatureEvaluationContext): FeatureResult | null
```

**Parâmetros**

| Parâmetro | Tipo | Descrição |
|---|---|---|
| `featureKey` | string | Chave de recurso para avaliar em Sinalizadores |
| `context` | ContextoDeAvaliaçãoDoRecurso | Identidade (obrigatório) e atributos de direcionamento. Consulte [Contexto de avaliação](#evaluation-context). |

**Resposta**

*ResultadoDoRecurso*

| Campo | Tipo | Descrição |
|---|---|---|
| `id` | número | Identificador numérico do recurso. `-1` para sentinela de controle em nível de recurso. |
| `key` | string \| null | Chave do recurso. `null` para sentinela de controle em nível de recurso. |
| `featureGroupKey` | string \| null | Chave do grupo de recursos quando disponível |
| `meta` | string \| null | Metadados de recursos quando disponíveis |
| `analyticsParam` | AnalyticsParam \| nulo | Detalhes do Analytics para o recurso avaliado |

*AnalyticsParam*

| Campo | Tipo | Descrição |
|---|---|---|
| `featureGroupId` | número | Identificador do grupo de recursos numéricos |
| `featureId` | número | Identificador numérico do recurso |
| `variantId` | número \| nulo | Identificador de variante (`0` para controle) |

**Comportamento do grupo de controle**

| Cenário | isFeatureEnabled | getFeature | Evento do Analytics isFeatureEnabled | Recurso getFeature de evento do Analytics |
|---|---|---|---|---|
| Tratamento | `true` | Resultado normal | Sim | Sim |
| Controle no nível do recurso | `false` | Sentinela (`id: -1`, `key: null`) | Sim (`variantId: 0`) | Sim |
| Incompatibilidade de critérios / não encontrado | `false` | `null` | Não | Não |

**Exemplo**

```javascript
var feature = _flagClient.getFeature('new-testflag', {
  identityNamespace: 'ECID',
  identityId: visitorEcid,
  attributes: {
    locale: ['en-US']
  }
});

var meta = feature && feature.meta;
if (meta) {
  // your custom code
} else {
  // your default code
}
```

### extensionVersion {#extension-version}

Retorna a cadeia de caracteres da versão da extensão Sinalizadores.

**Assinatura**

```javascript
_flagClient.extensionVersion(): string
```

**Exemplo**

```javascript
const version = _flagClient.extensionVersion();
console.log(`Flags extension version: ${version}`);
```

## Resumo da API {#api-summary}

| administração | Devoluções |
|---|---|
| Sinalizador de recurso (elemento de dados Tags, booleano) | booleano |
| Sinalizador de recurso (elemento de dados das tags, objeto) | Objeto de recurso ou `null` |
| `window.flagClientReady` | Promessa — aguardar inicialização da extensão |
| `window._flagClient.isFeatureEnabled(featureKey, context)` | booleano |
| `window._flagClient.getFeature(featureKey, context)` | Objeto de recurso ou `null` |
| `window._flagClient.extensionVersion()` | String de versão da extensão |

## Tratamento de erros {#error-handling}

A extensão trata os erros normalmente:

| Cenário | Comportamento |
|---|---|
| Rede indisponível na inicialização | O SDK repete a busca inicial três vezes com retrocesso e a inicialização falha. `window.flagClientReady` e `_satellite.getVar(...)` são rejeitados com `Failed to initialize Flag`; `window._flagClient` permanece `undefined`. |
| Identidade ausente no contexto | A avaliação gera um erro; forneça `identityNamespace` e `identityId` |
| Recurso não encontrado | `getFeature` retorna `null`; `isFeatureEnabled` retorna `false` |

```javascript
try {
  const isEnabled = _flagClient.isFeatureEnabled('my-feature', context);
  // Use the result
} catch (error) {
  console.error('Evaluation failed:', error.message);
  // Use default value
}
```

## Práticas recomendadas {#best-practices}

### Fornecer identidade consistente {#consistent-identity}

Use o mesmo namespace e ID de identidade em todas as avaliações para uma segmentação consistente em implantações percentuais.

```javascript
const context = {
  identityNamespace: 'ECID',
  identityId: identity,
  attributes: {
    locale: ['en-US'],
    platform: ['web']
  }
};

const isEnabled = _flagClient.isFeatureEnabled('my-feature', context);
```

### Lidar com recursos ausentes normalmente {#handle-missing}

Sempre forneça comportamento de fallback quando um recurso não for encontrado ou a avaliação falhar.

```javascript
const feature = _flagClient.getFeature('new-testflag', context);

if (feature && feature.meta) {
  // your custom code
} else {
  // Feature not enabled - use default code
}
```

### Avaliar após o carregamento da página {#evaluate-after-load}

Verifique se a biblioteca de tags e a extensão de sinalizadores foram inicializadas antes de chamar as APIs. Use o evento **Biblioteca Carregada** nas regras, um elemento de dados **Sinalizador de Recurso** ou aguarde `flagClientReady`:

```javascript
window.flagClientReady.then(function () {
  var isEnabled = window._flagClient.isFeatureEnabled('my-feature', context);
  // Use the result
});
```

## Consulte também {#see-also}

* [Criar o primeiro sinalizador de recurso](../../feature-flags/create-your-first-feature-flag.md)
* [Público-alvo em sinalizadores e grupos de recursos](../../audience/audience-in-feature-flags-and-feature-groups.md)
* [Relatório](../../feature-flags/reporting.md)

<!-- -->
