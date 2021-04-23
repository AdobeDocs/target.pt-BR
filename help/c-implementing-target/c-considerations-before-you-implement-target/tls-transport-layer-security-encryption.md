---
keywords: tls; tls 1.0; segurança da camada de transporte; criptografia; tls 1.1; tls 1.2
description: Saiba como [!DNL Target] usa o protocolo TLS (Transport Layer Security) para manter os mais altos padrões de segurança e promover a segurança dos dados do cliente.
title: Como o  [!DNL Target] usa o TLS para fornecer segurança?
feature: Privacidade e segurança
role: Developer
exl-id: 964a642a-830a-4556-a92a-d300670cd2fa
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 59%

---

# Alterações na criptografia do TLS (Transport Layer Security)

Informações sobre alterações em como [!DNL Adobe] e [!DNL Adobe Target] usam a Segurança da camada de transporte (TLS) para manter os mais altos padrões de segurança e promover a segurança dos dados do cliente.

A Segurança da camada de transporte (TLS) é o protocolo de segurança mais amplamente implantado usado atualmente em navegadores Web e outros aplicativos que exigem dados trocados de maneira segura por meio de uma rede. A Adobe tem padrões de conformidade em segurança que exigem o fim da vida útil de protocolos mais antigos e que estão demandando o uso do TLS 1.2 para que se tenha a versão mais atualizada e segura em uso.

>[!IMPORTANT]
>
>Depois de 1º de março de 2020, o Adobe Target não será mais compatível com a criptografia TLS 1.1 para o Visual Experience Composer (VEC), o Enhanced Experience Composer (EEC), a entrega de atividades, APIs etc. Atualize para o TLS 1.2 antes de 1º de março de 2020 para evitar problemas.

Não esperamos que isso afete significativamente os dados ou relatórios do cliente.

## Visual Experience Composer (VEC) com o Enhanced Experience Composer (EEC) habilitado {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

O TLS 1.2 é o padrão a partir de 1 de março de 2020 e o TLS 1.1 não será mais suportado.

A Adobe estará movendo os clientes em fases para o TLS 1.2. Para aqueles cujos domínios já estão em conformidade com o TLS 1.2, nós os moveremos para o TLS 1.2 sem qualquer alteração necessária da sua parte. A maioria dos domínios dos clientes já oferece suporte ao TLS 1.2; no entanto, se o seu domínio não for compatível com TLS 1.2, manteremos esses domínios no TLS 1.1 como hoje (até março de 2020).

Você não deve enfrentar qualquer problema durante essa fase de migração. Se o VEC interrompeu o carregamento de um site que estava funcionando anteriormente,  [abra um tíquete de Atendimento ao cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) e cite esta migração como uma causa possível.

No entanto, se você for um desses clientes que estão no TLS 1.1 sem suporte ao TLS 1.2, deverá planejar a mudança de seus domínios/infraestrutura para o TLS 1.2. Continuaremos a oferecer suporte ao protocolo TLS 1.1 até 1º de março de 2020. A partir de 1º de março de 2020, o Target não será compatível com o protocolo TLS 1.1 para ser usado no VEC por meio da capacidade do Enhanced Experience Composer.

Embora recomendemos fortemente a todos usar o TLS 1.2 de agora em diante, se você for um novo cliente, mas *NÃO* for compatível com o TLS 1.2, entre em contato com o Atendimento ao cliente e os informe de que você precisa usar o TLS 1.1 no Compositor de experiências avançadas. No entanto, planeje migrar para o TLS 1.2, já que você também não terá suporte após 1º de março de 2020.

## Delivery de atividade {#section_46CA5943E4354B259014C2BF340AECD6}

A partir de 1º de março de 2020, os servidores do Target não serão mais compatíveis com TLS 1.1. Com essa alteração, os servidores do Target não aceitarão mais solicitações de visitantes com dispositivos ou navegadores da Web antigos não compatíveis com TLS 1.2 (ou versão posterior). Como resultado, dispositivos e navegadores mais antigos que oferecem suporte apenas para o TLS 1.1 (ou suporte ao TLS 1.1, por padrão) não receberão conteúdo de atividade do Adobe Target. O conteúdo padrão do site será renderizado.

Alguns dos dispositivos e navegadores mais antigos que serão afetados incluem:

* Google Chrome (Chrome para Android) versões 29 e anteriores
* Opera Browser (Opera Mobile) versões 12.17 e anteriores
* Mozilla Firefox (Firefox para Mobile) versões 26 e anteriores
* Android 4.3 e versões anteriores
* Internet Explorer 8 a 10 no Windows 7 e versões anteriores
* Internet Explorer 10 no Windows Phone 8.0
* Safari 6.0.4/OS X10.8.4 e versões anteriores

Conforme você planeja essa alteração, considere o seguinte (observe que o prazo de 1º de março de 2020 afeta todos esses itens):

* Você deve assegurar que o seu site padrão esteja pronto de uma maneira que seja consumível por dispositivos e navegadores compatíveis.
* Esteja ciente de que o número de visitantes nos seus relatórios do Target pode sofrer potencialmente um declínio insignificante no número de visitantes.
* Talvez seja necessário alterar os públicos-alvo criados especificamente para direcionar dispositivos ou navegadores mais antigos que não sejam compatíveis com TLS 1.2. A entrega para esses dispositivos e navegadores não funcionará mais.

Para obter mais detalhes sobre os navegadores compatíveis e suas versões, consulte  [Navegadores suportados](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100).

## APIs do Adobe [!DNL Target] {#section_88797FA5434049EC89F908853CC76903}

A partir de 1º de março de 2020, as APIs do Target não serão mais compatíveis com a criptografia TLS 1.1. Clientes que acessam a API devem verificar se não serão afetados.

* Os clientes da API que usam o Java 7 com configurações padrão precisarão de modificações para serem compatíveis com TLS 1.2. Para obter mais informações, consulte &quot;[Mudança da versão padrão do protocolo TLS para pontos de extremidade do cliente: TLS 1.0 para TLS 1.2](https://www.java.com/en/configure_crypto.html)&quot; no site do Java.
* Os clientes de API que usam o Java 8 não deverão ser afetados, pois a configuração padrão é TLS 1.2.
* Os clientes da API que usam outras estruturas precisarão entrar em contato com seus fornecedores para obterem detalhes sobre o suporte a TLS 1.2.

## Acesso às interfaces das soluções do Experience Cloud {#section_748870ADE77B4CBEB18518DC784E64E5}

Como a interface do Target Standard/Premium já requer um [navegador moderno](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100), não prevemos problemas. Caso não seja possível se conectar ao Target, será necessário atualizar seu navegador para a versão mais recente.

## Como verificar qual versão do TLS seu navegador usa {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

Para verificar a versão do TLS em seu site usando o Google Chrome:

1. Abra o site afetado no Chrome.
1. No menu do Chrome (os três elipses verticais), clique em Mais ferramentas > Ferramentas do desenvolvedor.

   ![Ferramentas de desenvolvedor do Google Chrome](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. Abra a guia Segurança e examine as informações da versão do TLS em Conexão:

   ![Detalhes da versão do TLS](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>Essas instruções estão atualizadas a partir da publicação e estão sujeitas a alterações. Uma busca rápida pela Internet deve ajudar caso essas instruções mudem.  Outros navegadores têm etapas semelhantes.

## Comportamento esperado com navegadores compatíveis com versões TLS abaixo de 1.2 {#section_B5DA97A34EF248EB927610A5DA71EF2F}

Esta seção descreve o que esperar de navegadores que suportam versões TLS abaixo de 1.2 apenas ao usar uma implementação at.js ou mbox.js. Para fins de comparação, esta seção também descreve o que esperar de navegadores compatíveis com TLS 1.2.

### Pontos de extremidade centrais

| Implementação do JavaScript do Target | Detalhes |
|--- |--- |
| at.js | Com TLS 1.0 ou TLS 1.1 habilitado:<ul><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li><li>O usuário vê a mensagem &quot;Não foi possível se conectar com segurança a essa página&quot;. A mensagem explica que isso pode ser causado porque o site usa configurações de segurança TLS desatualizadas ou inseguras.</li><li>Nenhum erro de console é exibido.</li></ul>Com o TLS 1.2 habilitado:<ul><li>O arquivo at.js é baixado.</li></ul> |
| mbox.js | Com TLS 1.0 ou TLS 1.1 habilitado:<ul><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li><li>O usuário vê a mensagem &quot;Não foi possível se conectar com segurança a essa página&quot;. A mensagem explica que isso pode ser causado porque o site usa configurações de segurança TLS desatualizadas ou inseguras.</li><li>Nenhum erro de console é exibido.</li></ul>Com o TLS 1.2 habilitado:<ul><li>O arquivo mbox.js é baixado.</li></ul> |

### Pontos de extremidade da borda

| Implementação do JavaScript do Target | Detalhes |
|--- |--- |
| at.js | Com TLS 1.0 ou TLS 1.1 habilitado:<ul><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li><li>O usuário vê a mensagem &quot;Não foi possível se conectar com segurança a essa página&quot;. A mensagem explica que isso pode ser causado porque o site usa configurações de segurança TLS desatualizadas ou inseguras.</li><li>Nenhum erro de console é exibido.</li><li>O conteúdo padrão é distribuído.</li></ul>Com o TLS 1.2 habilitado:<ul><li>O conteúdo da oferta é distribuído.</li></ul> |
| mbox.js | Com TLS 1.0 ou TLS 1.1 habilitado:<ul><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li><li>O usuário vê a mensagem &quot;Não foi possível se conectar com segurança a essa página&quot;. A mensagem explica que isso pode ser causado porque o site usa configurações de segurança TLS desatualizadas ou inseguras.</li><li>Nenhum erro de console é exibido.</li><li>O conteúdo padrão é distribuído.</li></ul>Com o TLS 1.2 habilitado:<ul><li>O conteúdo da oferta é distribuído</li></ul> |

### Atividade direcionada com o público-alvo de versão do navegador (Internet Explorer, Versões 6, 7 ou 8)

>[!NOTE]
>
>Os públicos-alvo param de funcionar.

| Implementação do JavaScript do Target | Detalhes |
|--- |--- |
| at.js | at.js não é compatível nas versões do Internet Explorer mais antigas que a versão 10. |
| mbox.js | Com TLS 1.0 ou TLS 1.1 habilitado:<ul><li>O conteúdo padrão é distribuído.</li><li>Nenhuma solicitação do Target é acionada.</li><li>Nenhum erro de console é exibido.</li><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li></ul>Com o TLS 1.2 habilitado:<ul><li>O conteúdo da oferta é distribuído.</li></ul> |
