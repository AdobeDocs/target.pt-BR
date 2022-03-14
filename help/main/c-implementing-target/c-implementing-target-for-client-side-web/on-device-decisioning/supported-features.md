---
keywords: implementação; biblioteca javascript; js; atjs; decisão no dispositivo; no device decisioning; recursos compatíveis
description: Saiba quais recursos são compatíveis com a tomada de decisão no dispositivo.
title: Quais recursos são compatíveis com o On-Device Decisioning
feature: at.js
role: Developer
exl-id: 3531ff55-c3db-44c1-8d0a-d7ec2ccb6505
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 13%

---

# Recursos compatíveis com a decisão no dispositivo

O [!DNL Adobe Target] O JS SDK oferece aos clientes a flexibilidade de escolher entre desempenho e atualização de dados para decisões. Em outras palavras, se o fornecimento do conteúdo personalizado mais relevante e envolvente por meio do aprendizado de máquina for mais importante para você, uma chamada de servidor ao vivo deverá ser feita. Mas quando o desempenho é mais importante, uma decisão no dispositivo e na memória deve ser tomada. Para que a decisão no dispositivo funcione, consulte as seguintes seções que listam os recursos compatíveis.

## Tipos de atividades suportadas

A tabela a seguir indica qual [tipos de atividades](/help/main/c-activities/target-activities-guide.md) criado pela [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) ou [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) são compatíveis ou não são compatíveis com decisões no dispositivo.

| Tipo de atividade | Suportado? |
| --- | --- |
| [Teste A/B](/help/main/c-activities/t-test-ab/test-ab.md) | Sim |
| [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Não |
| [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ![Premium](/help/main/assets/premium.png) | Não |
| [Teste multivariado](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Não |
| [Direcionamento de experiência](/help/main/c-activities/t-experience-target/experience-target.md) (XT) | Sim |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) ![Premium](/help/main/assets/premium.png) | Não |
| [Recommendations](/help/main/c-recommendations/recommendations.md) ![Premium](/help/main/assets/premium.png) | Não |
| [Atividades que usam o Analytics para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Sim |

## Direcionamento de público-alvo

A tabela a seguir indica quais regras de público-alvo são suportadas ou não para decisão no dispositivo.

| Regra de público-alvo | Suportado? |
| --- | --- |
| [Geografia](/help/main/c-target/c-audiences/c-target-rules/geo.md) | Sim |
| [Rede](/help/main/c-target/c-audiences/c-target-rules/network.md) | Não |
| [Móvel](/help/main/c-target/c-audiences/c-target-rules/mobile.md) | Não |
| [Parâmetros personalizados](/help/main/c-target/c-audiences/c-target-rules/custom-parameters.md) | Sim |
| [Sistema operacional](/help/main/c-target/c-audiences/c-target-rules/operating-system.md) | Sim |
| [Páginas do site](/help/main/c-target/c-audiences/c-target-rules/site-pages.md) | Sim |
| [Navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md) | Sim |
| [Perfil do visitante](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) | Não |
| [Fontes de Tráfego](/help/main/c-target/c-audiences/c-target-rules/traffic-sources.md) | Não |
| [Intervalo de tempo](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | Sim |
| Públicos-alvo da Adobe Experience Cloud<br>(Públicos-alvo de [!DNL Adobe Analytics], [!DNL Adobe Audience Manager]e [!DNL Adobe Experience Manager] | Não |

### Direcionamento geográfico para decisões no dispositivo

Para manter a latência mínima para atividades de decisão no dispositivo com públicos baseados em geografia, o Adobe recomenda que você forneça os valores geográficos na chamada para [getOffers](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md). Defina o objeto geográfico no contexto da solicitação. Isso significa, a partir do navegador, uma maneira de determinar a localização de cada visitante. Por exemplo, é possível executar uma pesquisa de IP para geografia usando um serviço configurado. Alguns provedores de hospedagem, como a Google Cloud, fornecem essa funcionalidade por meio de cabeçalhos personalizados em cada `HttpServletRequest`.

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				city: "SAN FRANCISCO", 
				countryCode: "US", 
				stateCode: "CA", 
				latitude: 37.75, 
				longitude: -122.4 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

No entanto, se você não conseguir realizar pesquisas IP-to-Geo em seu servidor, mas ainda quiser executar decisões no dispositivo para [getOffers](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) solicitações que contêm públicos-alvo com base na localização geográfica, isso também é suportado. O lado negativo dessa abordagem é que ela usa uma pesquisa remota de IP para geografia, o que adiciona latência a cada `getOffers` chame. Essa latência deve ser menor que uma `getOffers` com decisão do lado do servidor, pois ele atinge um CDN localizado próximo ao seu servidor. Forneça apenas o campo &quot;ipAddress&quot; no objeto Geográfico no Contexto de sua solicitação para que o SDK recupere a localização geográfica do endereço IP do visitante. Se qualquer outro campo além de &quot;ipAddress&quot; for fornecido, a variável [!DNL Target] O SDK não buscará os metadados de localização geográfica para resolução.

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				ipAddress: "127.0.0.1" 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

### Método de alocação

A tabela a seguir indica quais métodos de alocação são suportados ou não para decisões no dispositivo.

| Método de alocação | Suportado? |
| --- | --- |
| Manual | Sim |
| [Alocar automaticamente para a melhor experiência](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Não |
| [Direcionamento automático para experiências personalizadas](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Não |
