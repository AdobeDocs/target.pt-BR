---
keywords: Definição de metas; eec; visual experience composer; solucionar problemas do enhanced experience composer; solução de problemas
description: Saiba como solucionar problemas que às vezes ocorrem no Adobe [!DNL Target] Enhanced Experience Composer (EEC) sob determinadas condições.
title: Como soluciono problemas relacionados ao Enhanced Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: b623b7ac3793aa340f0d3072e7453bd988b733ac
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 55%

---

# Solução de problemas relacionados ao [!UICONTROL Enhanced Experience Composer]

Problemas de exibição às vezes ocorrem no [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEC) sob determinadas condições.

## O EEC não carregará um URL interno de controle de qualidade que não esteja acessível no IP público. {#section_D29E96911D5C401889B5EACE267F13CF}

Isso pode ser resolvido incluir na lista de permissões os seguintes endereços IP. Esses endereços IP são para o servidor Adobe usado para o proxy EEC. Eles são necessários somente para a atividade de edição. Os visitantes do seu site não precisam desses endereços IP incluídos na lista de permissões.

Peça à equipe de TI para lista de permissões os seguintes endereços IP:

* 34 253 100 20
* 34 248 100 23
* 52.49.228.246
* 54.205.42.123
* 107.22.177,39
* 52.201.5.105
* 52.193.211.177
* 18.180.24.249
* 52.194.154.154

Você poderá ver a seguinte mensagem de erro no [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![](assets/EEC_error.png)

Os motivos pelos quais você pode ver essa mensagem de erro e correções para corrigir a situação são:

* **Problema:**[!UICONTROL o domínio (ISP) do site está bloqueando o Enhanced Experience Composer].

   **Solução:** Lista de permissões os endereços IP listados acima.

* **Problema:** os endereços IP são incluir na lista de permissões, mas o seu site não é compatível com a versão 1.2 do TLS.  [!DNL Target] Atualmente usa a configuração padrão do 1.2. Antes da versão  [!DNL Target] 18.4.1 (25 de abril de 2018), a configuração padrão era compatível com o TLS 1.0. Para obter mais informações, consulte Alterações na criptografia do  [TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451).

   **Solução:**[!UICONTROL consulte a seguinte pergunta (O Enhanced Visual Experience Composer não será carregado nas páginas seguras do meu site que usam TLS 1.2).]

## O EEC não será carregado nas páginas seguras do meu site que usam TLS 1.0. (Somente EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

Você poderá ver a mensagem de erro descrita acima em &quot;O [!UICONTROL Enhanced Visual Experience Composer] não será carregado nas páginas seguras do meu site&quot;. se os endereços IP acima forem incluir na lista de permissões, mas o site não for compatível com a versão 1.2 do TLS. [!DNL Target] atualmente usa a configuração padrão do 1.2. Antes do [!DNL Target] 18.4.1 (25 de abril de 2018), a configuração padrão era compatível com o TLS 1.0. Para obter mais informações, consulte [Alterações de criptografia do TLS (Transport Layer Security)&lt;a/>.](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451)

Para verificar a versão do TLS no seu site usando o Firefox (outros navegadores têm etapas semelhantes):

1. Abra o site afetado no Firefox.
1. Clique no ícone **[!UICONTROL Mostrar informações do site]** na barra de endereços do navegador.

   ![](assets/firefox_more_info.png)

1. Clique em **[!UICONTROL Mostrar detalhes da conexão]** > **[!UICONTROL Mais informações]**.

   ![](assets/firefox_more_info_2.png)

1. Analise as informações de versão do TLS em Detalhes técnicos:

   ![](assets/firefox_more_info_3.png)

1. Se você descobrir que o seu site está mostrando o TLS 1.0, consulte  [Alterações na criptografia da Segurança da camada de transporte (TLS)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md#concept_CC1001E9D3AE4BABAF90B8311B0A6451) para obter informações sobre a política de compatibilidade com o TLS do Target. Para solucionar a situação por enquanto (válida até 12 de setembro de 2018), acesse o [Atendimento ao cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para obter a configuração com a versão TLS e o domínio.

## Vejo tempos limite ou erros de &quot;acesso negado&quot; ao carregar sites com proxy ativado. (Somente EEC) {#section_60CBB9022DC449F593606C0E6252302D}

Verifique se os IPs de proxy não estão bloqueados em seu ambiente.
