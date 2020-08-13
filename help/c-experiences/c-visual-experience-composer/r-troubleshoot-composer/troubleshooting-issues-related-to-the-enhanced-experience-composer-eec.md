---
keywords: Targeting;eec;visual experience composer;troubleshoot enhanced experience composer;troubleshooting
description: Problemas de exibição às vezes ocorrem no Enhanced Experience Composer (EEC), sob certas condições.
title: Solução de problemas relacionados ao Enhanced Experience Composer
feature: vec
uuid: 2ea9a91f-08ca-4a06-ad5d-35ced140db14
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 71%

---


# Solução de problemas relacionados ao Enhanced Experience Composer{#troubleshooting-issues-related-to-the-enhanced-experience-composer}

Problemas de exibição às vezes ocorrem no Enhanced Experience Composer (EEC), sob certas condições.

## O EEC não carregará um URL interno de controle de qualidade que não esteja acessível no IP público. (Somente EEC) {#section_D29E96911D5C401889B5EACE267F13CF}

Isso pode ser resolvido incluir na lista de permissões os seguintes endereços IP. Esses endereços IP são para o servidor do Adobe usado para o proxy do Enhanced Experience Composer. Eles são necessários somente para a atividade de edição. Os visitantes do site não precisam desses endereços IP incluir na lista de permissões

Peça à sua equipe de TI para lista de permissões os seguintes endereços IP:

| Região | Endereço IP | Nomes de hosts |
|--- |--- |--- |
| Estados Unidos | 52.55.99.45 | `us1-proxy.adobemc.com` |
| Europa, Oriente Médio e África (EMEA) | 52.51.238.221 | `emea1-proxy.adobemc.com` |
| Pacífico Asiático (APAC) | 52.193.67.35 | `apac1-proxy.adobemc.com` |

Você poderá ver a seguinte mensagem de erro no Target:

`Error: Your website domain (ISP) is blocking the Enhanced Experience Composer. You can allowlist the Enhanced Experience Composer's IP addresses or turn off Enhanced Experience Composer in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

Os motivos pelos quais você pode ver essa mensagem de erro e correções para corrigir a situação são:

* **Problema:** o domínio (ISP) do site está bloqueando o Enhanced Experience Composer.

   **Solução:** lista de permissões os endereços IP listados acima.

* **Problema:** Os endereços IP são incluir na lista de permissões, mas seu site não suporta a versão 1.2 do TLS. Atualmente, o público alvo usa a configuração padrão 1.2. Antes do Público alvo 18.4.1 (25 de abril de 2018), a configuração padrão suportava TLS 1.0. Para obter mais informações, consulte Alterações [de criptografia de](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)TLS (Transport Layer Security).

   **Solução:** consulte a seguinte pergunta (O Enhanced Visual Experience Composer não será carregado nas páginas seguras do meu site que usam TLS 1.2).

## O EEC não será carregado nas páginas seguras do meu site que usam TLS 1.0. (Somente EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

Você poderá ver a mensagem de erro descrita acima em &quot;o Enhanced Visual Experience Composer não será carregado nas páginas seguras do meu site&quot;. if the above IP addresses are allowlisted but your website does not support TLS version 1.2. Target currently uses the default configuration of 1.2. Prior to the Target 18.4.1 (April 25, 2018), the default configuration supported TLS 1.0. For more information, see [TLS (Transport Layer Security) Encryption Changes](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

Para verificar a versão do TLS no seu site usando o Firefox (outros navegadores têm etapas semelhantes):

1. Abra o site afetado no Firefox.
1. Clique no ícone **[!UICONTROL Mostrar informações do site]** na barra de endereços do navegador.

   ![](assets/firefox_more_info.png)

1. Clique em **[!UICONTROL Mostrar detalhes da conexão]** > **[!UICONTROL Mais informações]**.

   ![](assets/firefox_more_info_2.png)

1. Analise as informações de versão do TLS em Detalhes técnicos:

   ![](assets/firefox_more_info_3.png)

1. Se você descobrir que o seu site está mostrando o TLS 1.0, consulte  [Alterações na criptografia da Segurança da camada de transporte (TLS)](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) para obter informações sobre a política de compatibilidade com o TLS do Target. Para solucionar a situação por enquanto (válida até 12 de setembro de 2018), acesse o [Atendimento ao cliente](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para obter a configuração com a versão TLS e o domínio.

## Vejo tempos limite ou erros de &quot;acesso negado&quot; ao carregar sites com proxy ativado. (Somente EEC) {#section_60CBB9022DC449F593606C0E6252302D}

Verifique se os IPs de proxy não estão bloqueados em seu ambiente.
