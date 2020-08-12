---
keywords: tls;tls 1.0;transport layer security;encryption;tls 1.1;tls 1.2
description: Informações sobre alterações em como a Adobe e o Target usam a Segurança da camada de transporte (TLS) para manter os mais altos padrões de segurança e promover a segurança dos dados do cliente.
title: Alterações na criptografia do TLS (Transport Layer Security)
feature: null
topic: Standard
uuid: d222b966-ee73-4254-87b7-68099583e0dd
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 62%

---


# Alterações na criptografia do TLS (Transport Layer Security){#tls-transport-layer-security-encryption-changes}

Informações sobre alterações em como o Adobe e a Adobe Target usam o TLS (Transport Layer Security) para manter os mais altos padrões de segurança e promover a segurança dos dados do cliente.

A Segurança da camada de transporte (TLS) é o protocolo de segurança mais amplamente implantado usado atualmente em navegadores Web e outros aplicativos que exigem dados trocados de maneira segura por meio de uma rede. A Adobe tem padrões de conformidade em segurança que exigem o fim da vida útil de protocolos mais antigos e que estão demandando o uso do TLS 1.2 para que se tenha a versão mais atualizada e segura em uso.

>[!IMPORTANT]
>
>Após 1º de março de 2020, a Adobe Target não oferecerá suporte à criptografia TLS 1.1 para o Visual Experience Composer (VEC), Enhanced Experience Composer (EEC), delivery, APIs etc. Atualize para TLS 1.2 antes de 1º de março de 2020 para evitar problemas.

Não esperamos que isso afete significativamente os dados ou relatórios do cliente.

## Visual Experience Composer (VEC) com o Enhanced Experience Composer (EEC) habilitado {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

O TLS 1.2 é o padrão a partir de 1º de março de 2020 e o TLS 1.1 não será mais suportado.

A Adobe estará movendo os clientes em fases para o TLS 1.2. Para aqueles cujos domínios já estão em conformidade com o TLS 1.2, nós os moveremos para o TLS 1.2 sem qualquer alteração necessária da sua parte. A maioria dos domínios do cliente já suporta TLS 1.2; no entanto, se o seu domínio não suportar TLS 1.2, manteremos esses domínios no TLS 1.1 como hoje (até março de 2020).

Você não deve enfrentar qualquer problema durante essa fase de migração. Se o VEC interrompeu o carregamento de um site que estava funcionando anteriormente,  [abra um tíquete de Atendimento ao cliente](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) e cite esta migração como uma causa possível.

No entanto, se você for um desses clientes que estão no TSL 1.1 sem suporte ao TLS 1.2, deverá planejar a movimentação dos domínios/infraestrutura para o TLS 1.2. Continuaremos a apoiar o protocolo TLS 1.1 até 1º de março de 2020. A partir de 1º de março de 2020, o Público alvo não oferecerá suporte ao protocolo TLS 1.1 a ser usado para o VEC por meio do recurso Enhanced Experience Composer.

Embora recomendemos fortemente a todos usar o TLS 1.2 de agora em diante, se você for um novo cliente, mas *NÃO* for compatível com o TLS 1.2, entre em contato com o Atendimento ao cliente e os informe de que você precisa usar o TLS 1.1 no Compositor de experiências avançadas. Entretanto, planeje mudar para o TLS 1.2, pois você também não será suportado depois de 1º de março de 2020.

## Activity delivery {#section_46CA5943E4354B259014C2BF340AECD6}

A partir de 1º de março de 2020, os servidores de Públicos alvos não oferecerão mais suporte ao TLS 1.1. Com essa alteração, os servidores de Públicos alvos não aceitarão mais solicitações de visitantes com dispositivos mais antigos ou navegadores da Web que não suportam TLS 1.2 (ou posterior). Como resultado, dispositivos e navegadores mais antigos que oferecem suporte apenas para o TLS 1.1 (ou suporte ao TLS 1.1, por padrão) não receberão conteúdo de atividade do Adobe Target. O conteúdo padrão do site será renderizado.

Alguns dos dispositivos e navegadores mais antigos que serão afetados incluem:

* Google Chrome (Chrome para Android) versões 29 e anteriores
* Opera Browser (Opera Mobile) versões 12.17 e anteriores
* Mozilla Firefox (Firefox para dispositivos móveis) versões 26 e anteriores
* Android 4.3 e versões anteriores
* Internet Explorer 8 a 10 no Windows 7 e versões anteriores
* Internet Explorer 10 no Windows Phone 8.0
* Safari 6.0.4/OS X10.8.4 e versões anteriores

Conforme você planeja essa alteração, considere o seguinte (observe que o prazo de 1º de março de 2020 afeta todos esses itens):

* Você deve assegurar que o seu site padrão esteja pronto de uma maneira que seja consumível por dispositivos e navegadores compatíveis.
* Esteja ciente de que o número de visitantes nos seus relatórios do Target pode sofrer potencialmente um declínio insignificante no número de visitantes.
* Talvez seja necessário alterar as audiências criadas especificamente para dispositivos mais antigos do público alvo ou navegadores que não suportam TLS 1.2. O delivery para esses dispositivos e navegadores não funcionará mais.

Para obter mais detalhes sobre os navegadores compatíveis e suas versões, consulte  [Navegadores suportados](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100).

## APIs do Adobe Target {#section_88797FA5434049EC89F908853CC76903}

A partir de 1º de março de 2020, as APIs de Público alvo não oferecerão mais suporte à criptografia TLS 1.1. Clientes que acessam a API devem verificar se não serão afetados.

* Os clientes da API que usam o Java 7 com configurações padrão precisarão de modificações para serem compatíveis com TLS 1.2. Para obter mais informações, consulte &quot;[Mudança da versão padrão do protocolo TLS para pontos de extremidade do cliente: TLS 1.0 para TLS 1.2](https://www.java.com/en/configure_crypto.html)&quot; no site do Java.
* Os clientes de API que usam o Java 8 não deverão ser afetados, pois a configuração padrão é TLS 1.2.
* Os clientes da API que usam outras estruturas precisarão entrar em contato com seus fornecedores para obterem detalhes sobre o suporte a TLS 1.2.

## Access to Experience Cloud Solutions interfaces {#section_748870ADE77B4CBEB18518DC784E64E5}

Como a interface do Target Standard/Premium já requer um [navegador moderno](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100), não prevemos problemas. Caso não seja possível se conectar ao Target, será necessário atualizar seu navegador para a versão mais recente.

## How to check which TLS version your browser uses {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

Para verificar a versão TLS em seu site usando o Google Chrome:

1. Abra o site afetado no Chrome.
1. No menu Chrome (as três elipses verticais), clique em Mais ferramentas > Ferramentas do desenvolvedor.

   ![Ferramentas de desenvolvedor do Google Chrome](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. Abra a guia Segurança e, em seguida, examine as informações da versão TLS em Conexão:

   ![Detalhes da versão TLS](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>Essas instruções estão atualizadas a partir da publicação e estão sujeitas a alterações. Uma busca rápida na internet deve ajudar caso essas instruções mudem.  Outros navegadores têm etapas semelhantes.

## Comportamento esperado com navegadores que suportam versões TLS abaixo de 1.2 {#section_B5DA97A34EF248EB927610A5DA71EF2F}

Esta seção descreve o que esperar com navegadores que suportam versões TLS abaixo de 1.2 somente ao usar uma implementação do at.js ou mbox.js. Para fins de comparação, esta seção também descreve o que esperar com navegadores compatíveis com TLS 1.2.

### Pontos finais centrais

| Implementação do JavaScript do Target | Detalhes |
|--- |--- |
| at.js | Com TLS 1.0 ou TLS 1.1 ativado:<ul><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li><li>O usuário vê a mensagem &quot;Não foi possível se conectar com segurança a essa página&quot;. A mensagem explica que isso pode ser causado porque o site usa configurações de segurança TLS desatualizadas ou inseguras.</li><li>Nenhum erro de console é exibido.</li></ul>Com o TLS 1.2 habilitado:<ul><li>O arquivo at.js é baixado.</li></ul> |
| mbox.js | Com TLS 1.0 ou TLS 1.1 ativado:<ul><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li><li>O usuário vê a mensagem &quot;Não foi possível se conectar com segurança a essa página&quot;. A mensagem explica que isso pode ser causado porque o site usa configurações de segurança TLS desatualizadas ou inseguras.</li><li>Nenhum erro de console é exibido.</li></ul>Com o TLS 1.2 habilitado:<ul><li>O arquivo mbox.js é baixado.</li></ul> |

### Pontos finais da borda

| Implementação do JavaScript do Target | Detalhes |
|--- |--- |
| at.js | Com TLS 1.0 ou TLS 1.1 ativado:<ul><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li><li>O usuário vê a mensagem &quot;Não foi possível se conectar com segurança a essa página&quot;. A mensagem explica que isso pode ser causado porque o site usa configurações de segurança TLS desatualizadas ou inseguras.</li><li>Nenhum erro de console é exibido.</li><li>O conteúdo padrão é distribuído.</li></ul>Com o TLS 1.2 habilitado:<ul><li>O conteúdo da oferta é distribuído.</li></ul> |
| mbox.js | Com TLS 1.0 ou TLS 1.1 ativado:<ul><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li><li>O usuário vê a mensagem &quot;Não foi possível se conectar com segurança a essa página&quot;. A mensagem explica que isso pode ser causado porque o site usa configurações de segurança TLS desatualizadas ou inseguras.</li><li>Nenhum erro de console é exibido.</li><li>O conteúdo padrão é distribuído.</li></ul>Com o TLS 1.2 habilitado:<ul><li>O conteúdo da oferta é distribuído</li></ul> |

### Atividade direcionada à audiência da versão do navegador (Internet Explorer, versões 6, 7 ou 8)

>[!NOTE]
>
>Os públicos-alvo param de funcionar.

| Implementação do JavaScript do Target | Detalhes |
|--- |--- |
| at.js | at.js não é compatível nas versões do Internet Explorer mais antigas que a versão 10. |
| mbox.js | Com TLS 1.0 ou TLS 1.1 ativado:<ul><li>O conteúdo padrão é distribuído.</li><li>Nenhuma solicitação do Target é acionada.</li><li>Nenhum erro de console é exibido.</li><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li></ul>Com o TLS 1.2 habilitado:<ul><li>O conteúdo da oferta é distribuído.</li></ul> |