---
keywords: adobe.target.trackEvent;trackEvent;trackevent;track event;at.js;functions;function;preventDefault;preventdefault;prevent default
description: Informações sobre a função adobe.target.trackEvent(options) da biblioteca at.js de JavaScript do Adobe Target.
title: adobe.target.trackEvent(options)
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: a5a84e96ea3498140f4e0c9af4f75ec674bbf4b8
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 78%

---


# adobe.target.trackEvent(options)

Essa função aciona uma solicitação para relatar ações do usuário, como cliques e conversões. Não entrega atividades na resposta.

Essa mbox de monitoramento de evento pode, então, ser usada para definir métricas em atividades. Para obter mais informações, consulte [Métricas de sucesso](../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) e [Conversões de rastreamento](../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053).

Veja os detalhes da API:

| Chave | Tipo | Obrigatório | Descrição |
|--- |--- |--- |--- |
| mbox | String | Sim | Mbox <br>**nameNote**: Se uma chamada trackEvent() for acionada com um nome de mbox que já tenha sido acionado na página, o SDID de trackEvent() será redefinido e será diferente das chamadas de Público alvo na página. Entretanto, disparar uma chamada trackEvent() com um nome de mbox diferente mantém a SDID da chamada trackEvent() consistente com as chamadas de Solicitação de carregamento de página/triggerView() na página. |
| selector | String    | Não | Seletores CSS usados para encontrar os elementos HTML. Os ouvintes do evento serão fixados aos elementos encontrados. |
| type | String | Não | Representa um tipo de evento registrado. Pode ser que ambos sejam elementos HTML conhecidos como: clique, mouse para baixo, etc., bem como eventos HTML. |
| preventDefault | Booleano | Não | Indica se usará `event.preventDefault()` no retorno do ouvinte do evento. O padrão é false.<br>**Observação:** somente `form[submit] and `a[click] são compatíveis. Outros cenários não são compatíveis devido à complexidade e à grande quantidade de cenários para suporte. |
| params | Objeto | Não | Parâmetros de mbox. Um objeto de pares de valores-chave que tem a seguinte estrutura:<br>`{ "param1": "value1", "param2": "value2"}` |
| timeout | Número | Não | Tempo limite em milissegundos.<br>Se não especificado, o valor padrão é utilizado:<br>`...timeoutInSeconds: 0.15...}` |
| success | Função | Não | Uma função de retorno de chamada usada para sinalizar que o evento foi relatado. |
| error | Função | Não | Uma função de retorno de chamada usada para sinalizar que não foi possível relatar o evento. |

## Exemplo

```
<a href="https://asite.com">click me!</a> 
```

Além do código JavaScript para atribuição de `trackEvent`:

```
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

Ou:

```
adobe.target.trackEvent({ 
    "mbox": "clicked-cta", 
    "params": { 
        "param1": "value1" 
    } 
});
```

>[!NOTE]
>
>Caso os campos obrigatórios não estejam definidos, nenhuma solicitação é executada e um erro é lançado.