---
description: Informações sobre o Target e o padrão de samesite IETF usado a partir do Google Chrome versão 76.
keywords: google; samesite
seo-description: Informações sobre o Adobe Target e o padrão samesite IETF introduzido com a versão 76 do Google Chrome.
seo-title: Políticas de cookie do Adobe Target e samesite
solution: Target
subtopic: Introdução
title: Políticas de cookie do Google Chrome para samesite
topic: Padrão
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Políticas de cookie do Google Chrome para samesite

O Google anunciou recentemente que a partir do Chrome 76 (slated para uma versão de July 0 de julho de 20 19), os desenvolvedores devem especificar explicitamente quais cookies podem funcionar entre sites e quais cookies podem acompanhar os usuários.

## Visão geral do samesite

Para fornecer proteções sobre quando os cookies podem ser enviados entre sites para que os usuários sejam protegidos, o Google adiciona suporte para um padrão IETF chamado "samesite" no Google Chrome 76 (e posterior). SameSite requires web developers to manage cookies with the SameSite attribute component in the `Set-Cookie` header.

Há três valores diferentes que podem ser passados para o atributo samesite: Estrito, Lax ou Nenhum.

| Valor | Descrição |
| --- | --- |
| Restrito | Os cookies com essa configuração podem ser acessados somente ao visitar o domínio em que foram inicialmente definidos. Em outras palavras, Rigorosamente bloqueia o cookie de ser usado entre sites. Essa opção é melhor para aplicativos que exigem alta segurança, como bancos. |
| Lax | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, such as `HTTP GET`. Therefore, this option should be used if the cookie can be used by third-parties, but with an added security benefit that protects users from being victimized by [CSRF](https://en.wikipedia.org/wiki/Cross-site_request_forgery) (Cross-Site Request Forgery) attacks. |
| Nenhum | Os cookies com essa configuração funcionam da mesma forma que os cookies funcionam hoje. |

Ao manter o acima em mente, o Chrome 76 (e posterior) introduz duas configurações: " Samesite por cookies padrão "e" Cookies sem samesite devem ser seguros ". Os usuários têm a capacidade de ativar a configuração ou ambas as configurações.

| Configuração | Descrição |
| --- | --- |
| Samesite por cookies padrão | When set, all cookies that don't specify the SameSite attribute are automatically forced with `SameSite = Lax`. |
| Os cookies sem samesite devem ser seguros | When set, cookies without the SameSite attribute or with `SameSite = None`, must be Secure. Proteger neste contexto significa que todas as solicitações do navegador devem seguir o protocolo HTTPS. Os cookies que não aderirem a esse requisito são rejeitados. |

![página de configurações do samesite](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

## O Target segue as práticas recomendadas de segurança do Google

Com o Target, queremos garantir que você tenha sempre suporte às práticas recomendadas mais recentes do setor para segurança. Temos o prazer de anunciar que o Target oferece suporte às novas configurações de segurança introduzidas no Google Chrome 76.

Quando os visitantes ativaram a configuração "samesite por cookies padrão", o Target continua a fornecer a personalização sem qualquer impacto e sem qualquer intervenção por você. Target uses first-party cookies and will continue to function properly as the flag `SameSite = Lax` is applied by Google Chrome.

Quando os visitantes ativarem os "Cookies sem samesite", e você não optar pelo recurso de rastreamento entre domínios do Target, os cookies originais do Target continuarão funcionando. However, when you opt-in to using cross-domain tracking to leverage Target across multiple domains, Google Chrome 76 (and later) requires `SameSite = None` and `Secure` flags to be used for third-party cookies. Isso significa que você deve garantir que seus sites usem o protocolo HTTPS. Target's client-side libraries automatically use the HTTPS protocol and, in addition to that, attach the `SameSite = None` and `Secure` flags to Target’s third-party cookie to ensure all activities continue to deliver.

## O que você precisa fazer?

Analise a tabela a seguir para entender o que precisa fazer para que o Target continue trabalhando para usuários do Google Chrome 76 +.

A tabela contém as seguintes colunas:

* **Biblioteca do cliente do Target**: Se você está usando mbox. js, at. js 1.*x* ou at. js 2.*x* em seus sites e como as configurações do Google Chrome afetam você
* **Samesite por cookies padrão = Ativado**: Se os visitantes tiverem "samesite por cookies padrão ativados" no Chrome 76 +, como isso afeta você e há algo que você precisa fazer para que o Target continue funcionando
* **Os cookies sem samesite devem ser seguros = Ativados**: Se os visitantes tiverem «Cookies sem samesite» ativados no Chrome 76 +, como ela afeta você e há algo que você precisa fazer para que o Target continue funcionando
* **Rastreamento de domínio cruzado do Adobe Target = Ativado**: Se os visitantes tiverem "o mesmo site por cookies padrão" ativado e "Cookies sem samesite deve ser seguro" ativado no Chrome 76 + e estiver usando o Target para rastreamento entre domínios, como isso afeta você e há algo que você precisa fazer para que o Target continue funcionando

| Biblioteca do cliente do Target | Samesite por cookies padrão = Ativado | Os cookies sem samesite devem ser protegidos = Ativado | Rastreamento de domínio cruzado do Adobe Target = Ativado |
| --- | --- | --- | --- |
| mbox.js | Nenhum impacto porque o mbox. js usa um cookie próprio | Nenhum impacto porque os clientes não estão usando o rastreamento entre domínios | Os clientes devem ativar o protocolo HTTPS para o seu site.<br>O Target usa um cookie de terceiros para rastrear os usuários e o Google requer que os cookies de terceiros tenham `SameSite = None` e para sites o protocolo HTTPS. |
| at.js 1.*x* | Sem impacto, pois at. js 1.*x* usa um cookie próprio | Nenhum impacto porque os clientes não estão usando o rastreamento entre domínios | Os clientes devem ativar o protocolo HTTPS para o seu site.<br>O Target usa um cookie de terceiros para rastrear os usuários e o Google requer que os cookies de terceiros tenham `SameSite = None` e para que sites usem o protocolo HTTPS |
| at.js 2.*x* | Sem impacto, pois at. js 2.*x* usa um cookie próprio | Nenhum impacto porque os clientes não estão usando o rastreamento entre domínios | O rastreamento entre domínios não é suportado no at. js 2.*x* e, portanto, não há impacto nos clientes |

## O que a Adobe precisa fazer?

| Biblioteca do cliente do Target | Samesite por cookies padrão = Ativado | Os cookies sem samesite devem ser protegidos = Ativado | Rastreamento de domínio cruzado do Adobe Target = Ativado |
| --- | --- | --- | --- |
| mbox.js | Nenhum impacto porque o mbox. js usa um cookie próprio | Nenhum impacto porque os clientes não estão usando o rastreamento entre domínios | Target adds `SameSite = None` and `Secure` flag to third-party cookie when the Target backend is called. |
| at.js 1.*x* | Sem impacto, pois at. js 1.*x* usa um cookie próprio | Nenhum impacto porque os clientes não estão usando o rastreamento entre domínios | Target adds `SameSite = None` and `Secure` flag to third-party cookie when the Target backend is called. |
| at.js 2.*x* | Sem impacto, pois at. js 2.*x* usa um cookie próprio | Nenhum impacto porque os clientes não estão usando o rastreamento entre domínios | O rastreamento entre domínios não é suportado no at. js 2.*x* |

## Conclusão

Conforme o setor faz strides para criar uma Web mais segura para os consumidores, o Target tem o absoluto compromisso de fornecer experiências personalizadas durante a reunião e exceder as expectativas de privacidade dos visitantes.
