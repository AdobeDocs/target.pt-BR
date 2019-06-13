---
description: Informações sobre alterações em como a Adobe e o Target usam a Segurança da camada de transporte (TLS) para manter os mais altos padrões de segurança e promover a segurança dos dados do cliente.
keywords: tls; tls 1.0; segurança de camada de transporte; criptografia
seo-description: Informações sobre alterações em como a Adobe e o Target usam a Segurança da camada de transporte (TLS) para manter os mais altos padrões de segurança e promover a segurança dos dados do cliente.
seo-title: Alterações na criptografia do TLS (Transport Layer Security)
solution: Target
title: Alterações na criptografia do TLS (Transport Layer Security)
topic: Padrão
uuid: d222b966-ee73-4254-87b7-68099583e0dd
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Alterações na criptografia do TLS (Transport Layer Security){#tls-transport-layer-security-encryption-changes}

Informações sobre alterações em como a Adobe e o Target usam a Segurança da camada de transporte (TLS) para manter os mais altos padrões de segurança e promover a segurança dos dados do cliente.

A Segurança da camada de transporte (TLS) é o protocolo de segurança mais amplamente implantado usado atualmente em navegadores Web e outros aplicativos que exigem dados trocados de maneira segura por meio de uma rede. A [!DNL Adobe] tem padrões de conformidade em segurança que exigem o fim da vida útil de protocolos mais antigos e o uso do TLS 1.2 para ter a versão mais atualizada e segura em vigor.

>[!NOTE]
>
>Em 20 de fevereiro de 2019, a infraestrutura do Adobe Target foi atualizada nas regiões EMEA, Japão e APAC para não coletar mais os dados de usuários finais com dispositivos antigos ou navegadores da Web que não sejam compatíveis com TLS 1.1 ou posteriores. A mesma atualização está planejada para a região da América do Norte em **1º de abril de 2019**. A migração para TLS 1.2 oferece segurança aprimorada. É importante que você verifique as especificidades e planeje as alterações com a equipe de TI para fazer uma transição sem complicações.

Não esperamos que isso afete significativamente os dados ou relatórios do cliente.

## Visual Experience Composer (VEC) com o Enhanced Experience Composer (EEC) habilitado {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

Até agora, o [Compositor de experiências avançadas](../../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) (EEC) do Adobe Target usava o TLS 1.0 por padrão. A partir da versão do Target 18.4.1 (25 de abril de 2018), o Target está mudando para o TLS 1.2 por padrão.

A Adobe estará movendo os clientes em fases para o TLS 1.2. Para aqueles cujos domínios já estão em conformidade com o TLS 1.2, nós os moveremos para o TLS 1.2 sem qualquer alteração necessária da sua parte. A maioria dos domínios dos clientes já é compatível com o TLS 1.2; no entanto, se o seu domínio não for compatível com o TLS 1.2, nós manteremos esses domínios no TLS 1.0 como atualmente (até fevereiro de 2019).

Você não deve enfrentar qualquer problema durante essa fase de migração. Se o VEC interrompeu o carregamento de um site que estava funcionando anteriormente, [abra um tíquete de Atendimento ao cliente](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) e cite esta migração como uma causa possível.

Se, no entanto, você for um dos clientes que usam o TLS 1.0 sem compatibilidade com o TLS 1.2, planeje a mudança dos seus domínios/infraestrutura para o TLS 1.2. Continuaremos a dar suporte ao protocolo TLS 1.0 até fevereiro de 2019. A partir de fevereiro de 2019, o Target não será mais compatível com o protocolo TLS 1.0 para ser usado no VEC com a função do Compositor de experiências avançadas.

Embora recomendemos fortemente a todos usar o TLS 1.2 de agora em diante, se você for um novo cliente, mas *NÃO* for compatível com o TLS 1.2, entre em contato com o Atendimento ao cliente e os informe de que você precisa usar o TLS 1.0 no Compositor de experiências avançadas. No entanto, planeje a mudança para o TLS 1.2 já que você também não terá mais suporte após fevereiro de 2019.

## Entrega da atividade {#section_46CA5943E4354B259014C2BF340AECD6}

A partir de fevereiro de 2019, os servidores do Target não serão mais compatíveis com o TLS 1.0. Com essa alteração, os servidores do Target não aceitarão mais solicitações de usuários finais com dispositivos ou navegadores Web mais antigos que não sejam compatíveis com o TLS 1.1 ou versão posterior. Como resultado, dispositivos e navegadores mais antigos que oferecem suporte apenas para o TLS 1.0 (ou suporte ao TLS 1.0, por padrão) não receberão conteúdo de atividade do Adobe Target. O conteúdo padrão do site será renderizado.

Alguns dos dispositivos e navegadores mais antigos que serão afetados incluem:

* Android 4.3 e versões anteriores
* Internet Explorer 8 a 10 no Windows 7 e versões anteriores
* Internet Explorer 10 no Windows Phone 8.0
* Safari 6.0.4/OS X10.8.4 e versões anteriores

Conforme você se planeja para esta mudança, considere o seguinte (observe que o prazo de fevereiro de 2019 afeta todos esses itens):

* Você deve assegurar que o seu site padrão esteja pronto de uma maneira que seja consumível por dispositivos e navegadores compatíveis.
* Esteja ciente de que o número de visitantes nos seus relatórios do Target pode sofrer potencialmente um declínio insignificante no número de visitantes.
* Você pode precisar alterar os públicos-alvo criados especificamente para direcionar aos dispositivos ou navegadores mais antigos que não sejam compatíveis com o TLS 1.0 - a entrega para esses dispositivos e navegadores não funcionará mais.

Para obter mais detalhes sobre os navegadores compatíveis e suas versões, consulte [Navegadores suportados](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100).

## APIs do Adobe Target {#section_88797FA5434049EC89F908853CC76903}

A partir de fevereiro de 2019, as APIs do Target não serão mais compatíveis com a criptografia do TLS 1.0. Clientes que acessam a API devem verificar se não serão afetados.

* Os clientes da API que usam o Java 7 com configurações padrão precisarão de modificações para serem compatíveis com TLS 1.2. Para obter mais informações, consulte &quot;[Mudança da versão padrão do protocolo TLS para pontos de extremidade do cliente: TLS 1.0 para TLS 1.2](https://www.java.com/en/configure_crypto.html)&quot; no site do Java.
* Os clientes de API que usam o Java 8 não deverão ser afetados, pois a configuração padrão é TLS 1.2.
* Os clientes da API que usam outras estruturas precisarão entrar em contato com seus fornecedores para obterem detalhes sobre o suporte a TLS 1.2.

## Acesso às interfaces das soluções da Experience Cloud {#section_748870ADE77B4CBEB18518DC784E64E5}

Como a interface do Target Standard/Premium já requer um [navegador moderno](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100), não prevemos problemas. Caso não seja possível se conectar ao Target, será necessário atualizar seu navegador para a versão mais recente.

## Como verificar qual versão do TLS o seu navegador usa {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

Para verificar a versão do TLS no seu site usando o Firefox (outros navegadores têm etapas semelhantes):

1. Abra o site afetado no Firefox.
1. Clique no ícone **[!UICONTROL Mostrar informações do site]na barra de endereços do navegador.**

   ![](assets/firefox_more_info.png)

1. Clique em **[!UICONTROL Mostrar detalhes da conexão]** &gt; **[!UICONTROL Mais informações]**.

   ![](assets/firefox_more_info_2.png)

1. Analise as informações de versão do TLS em Detalhes técnicos:

   ![](assets/firefox_more_info_3.png)

## Comportamento esperado com navegadores compatíveis com o TLS 1.0 somente. {#section_B5DA97A34EF248EB927610A5DA71EF2F}

Esta seção descreve o que esperar de navegadores que suportam o TLS 1.0 apenas quando usam uma implementação at.js ou mbox.js. Para fins de comparação, testa seção também descreve o que esperar com navegadores compatíveis com TLS 1.1 e 1.2.

### Endpoints centrais

| Implementação do JavaScript do Target | Detalhes |
|--- |--- |
| at.js | Com o TLS 1.0 habilitado:<ul><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li><li>O usuário vê a mensagem &quot;Não foi possível se conectar com segurança a essa página&quot;. A mensagem explica que isso pode ser causado porque o site usa configurações de segurança TLS desatualizadas ou inseguras.</li><li>Nenhum erro de console é exibido.</li></ul>Com o TLS 1.1 ou 1.2 habilitado:<ul><li>O arquivo at.js é baixado.</li></ul> |
| mbox.js | Com o TLS 1.0 habilitado:<ul><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li><li>O usuário vê a mensagem &quot;Não foi possível se conectar com segurança a essa página&quot;. A mensagem explica que isso pode ser causado porque o site usa configurações de segurança TLS desatualizadas ou inseguras.</li><li>Nenhum erro de console é exibido.</li></ul>Com o TLS 1.1 ou 1.2 habilitado:<ul><li>O arquivo mbox.js é baixado.</li></ul> |

### Endpoints de borda

| Implementação do JavaScript do Target | Detalhes |
|--- |--- |
| at.js | Com o TLS 1.0 habilitado:<ul><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li><li>O usuário vê a mensagem &quot;Não foi possível se conectar com segurança a essa página&quot;. A mensagem explica que isso pode ser causado porque o site usa configurações de segurança TLS desatualizadas ou inseguras.</li><li>Nenhum erro de console é exibido.</li><li>O conteúdo padrão é distribuído.</li></ul>Com o TLS 1.1 ou 1.2 habilitado:<ul><li>O conteúdo da oferta é distribuído.</li></ul> |
| mbox.js | Com o TLS 1.0 habilitado:<ul><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li><li>O usuário vê a mensagem &quot;Não foi possível se conectar com segurança a essa página&quot;. A mensagem explica que isso pode ser causado porque o site usa configurações de segurança TLS desatualizadas ou inseguras.</li><li>Nenhum erro de console é exibido.</li><li>O conteúdo padrão é distribuído.</li></ul>Com o TLS 1.1 ou 1.2 habilitado:<ul><li>O conteúdo da oferta é distribuído</li></ul> |

### Atividade direcionada com Audience de versão de navegador (Internet Explorer, Versões 6, 7 ou 8)

>[!NOTE]
>
>Os públicos-alvo param de funcionar.

| Implementação do JavaScript do Target | Detalhes |
|--- |--- |
| at.js | at.js não é compatível nas versões do Internet Explorer mais antigas que a versão 10. |
| mbox.js | Com o TLS 1.0 habilitado:<ul><li>O conteúdo padrão é distribuído.</li><li>Nenhuma solicitação do Target é acionada.</li><li>Nenhum erro de console é exibido.</li><li>Com as ferramentas dev do navegador, na guia Rede, você verá &quot;200 OK.&quot; Isso significa que a solicitação foi bem-sucedida.</li></ul>Com o TLS 1.1 ou 1.2 habilitado:<ul><li>O conteúdo da oferta é distribuído.</li></ul> |