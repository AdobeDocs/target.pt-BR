---
description: Problemas de exibição às vezes ocorrem no Enhanced Experience Composer (EEC), sob certas condições.
keywords: Definição de metas; eec; visual experience composer; solucionar problemas do enhanced experience composer; solução de problemas
seo-description: Problemas de exibição às vezes ocorrem no Enhanced Experience Composer (EEC), sob certas condições.
seo-title: Solução de problemas relacionados ao Enhanced Experience Composer
solution: Target
title: Solução de problemas relacionados ao Enhanced Experience Composer
uuid: 2ea9a91f-08ca-4a06-ad5d-35ced140db14
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Solução de problemas relacionados ao Enhanced Experience Composer{#troubleshooting-issues-related-to-the-enhanced-experience-composer}

Problemas de exibição às vezes ocorrem no Enhanced Experience Composer (EEC), sob certas condições.

## O EEC não carregará um URL interno de controle de qualidade que não esteja acessível no IP público. (Somente EEC) {#section_D29E96911D5C401889B5EACE267F13CF}

Isso pode ser resolvido adicionando os endereços IP a seguir à lista de permissões. Esses endereços IP são para o servidor do Adobe usado para o proxy do Enhanced Experience Composer. Eles são necessários somente para a atividade de edição. Os visitantes do seu site não precisam incluir esses endereços IP na lista de permissões

Peça que sua equipe de TI coloque os seguintes endereços IP na lista segura:

| Região | Endereço IP | Nomes de hosts |
|--- |--- |--- |
| Estados Unidos | 52.55.99.45 | `us1-proxy.adobemc.com` |
| Europa, Oriente Médio e África (EMEA) | 52.51.238.221 | `emea1-proxy.adobemc.com` |
| Pacífico Asiático (APAC) | 52.193.67.35 | `apac1-proxy.adobemc.com` |

Você poderá ver a seguinte mensagem de erro no Target:

`Error: Your website domain (ISP) is blocking the Enhanced Experience Composer. You can whitelist the Enhanced Experience Composer's IP addresses or turn off Enhanced Experience Composer in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

Os motivos pelos quais você pode ver essa mensagem de erro e correções para corrigir a situação são:

* **Problema:** o domínio (ISP) do site está bloqueando o Enhanced Experience Composer.

   **Solução:** adicione os endereços IP especificados acima à lista de permissões.

* **Problema:** os endereços IP estão na lista de permissões, mas o seu site não é compatível com a versão 1.2 do TLS. O Target atualmente usa a configuração padrão do 1.2. Antes do Target 18.4.1 (25 de abril de 2018), a configuração padrão era compatível com o TLS 1.0. Para obter mais informações, consulte [Alterações na criptografia da Segurança da camada de transporte (TLS)](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

   **Solução:** consulte a seguinte pergunta (O Enhanced Visual Experience Composer não será carregado nas páginas seguras do meu site que usam TLS 1.2).

## O EEC não será carregado nas páginas seguras do meu site que usam TLS 1.0. (Somente EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

Você poderá ver a mensagem de erro descrita acima em "o Enhanced Visual Experience Composer não será carregado nas páginas seguras do meu site". se os endereços IP acima estão na lista de permissões, mas o seu site não é compatível com a versão 1.2 do TLS. O Target atualmente usa a configuração padrão do 1.2. Antes do Target 18.4.1 (25 de abril de 2018), a configuração padrão era compatível com o TLS 1.0. Para obter mais informações, consulte [Alterações na criptografia da Segurança da camada de transporte (TLS)](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

Para verificar a versão do TLS no seu site usando o Firefox (outros navegadores têm etapas semelhantes):

1. Abra o site afetado no Firefox.
1. Clique no ícone **[!UICONTROL Mostrar informações do site]na barra de endereços do navegador.**

   ![](assets/firefox_more_info.png)

1. Clique em **[!UICONTROL Mostrar detalhes da conexão]** &gt; **[!UICONTROL Mais informações]**.

   ![](assets/firefox_more_info_2.png)

1. Analise as informações de versão do TLS em Detalhes técnicos:

   ![](assets/firefox_more_info_3.png)

1. Se você descobrir que o seu site está mostrando o TLS 1.0, consulte [Alterações na criptografia da Segurança da camada de transporte (TLS)](../../../c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) para obter informações sobre a política de compatibilidade com o TLS do Target. Para solucionar a situação por enquanto (válida até 12 de setembro de 2018), acesse o [Atendimento ao cliente](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para obter a configuração com a versão TLS e o domínio.

## Vejo tempos limite ou erros de "acesso negado" ao carregar sites com proxy ativado. (Somente EEC) {#section_60CBB9022DC449F593606C0E6252302D}

Verifique se os IPs de proxy não estão bloqueados em seu ambiente.
