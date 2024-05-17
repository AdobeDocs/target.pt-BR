---
keywords: Definição de metas; eec; visual experience composer; solucionar problemas do enhanced experience composer; solução de problemas
description: Saiba como solucionar problemas que às vezes ocorrem no Adobe [!DNL Target] O Enhanced Experience Composer (EEC) sob determinadas condições.
title: Como solucionar problemas relacionados ao Enhanced Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: 7562a1da201b570ee529db9763ef5f4b463f65a8
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 23%

---

# Solução de problemas relacionados ao [!UICONTROL Enhanced Experience Composer]

Problemas de exibição às vezes ocorrem no [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (CEE), sob certas condições.

## O EEC não carregará um URL interno de controle de qualidade que não esteja acessível no IP público. {#section_D29E96911D5C401889B5EACE267F13CF}

Isso pode ser resolvido incluindo na lista de permissões os seguintes endereços IP. Esses endereços IP são para o servidor Adobe usado para o proxy EEC. Eles são necessários somente para a atividade de edição. Incluir na lista de permissões Os visitantes do seu site não precisam desses endereços IP resolvidos.

Peça à sua equipe de TI para incluir na lista de permissões os seguintes endereços IP:

* 34 254 77 200
* 54.73.207.147
* 54 229 152 123
* 3 224 194 242
* 54.90.51.39
* 34 228 136 112
* 54.150.116.11
* 18.178.142.8
* 54 199 107 77
* 99 80 139 221
* 54.78.56.224
* 54 247 179 246
* 54.80.219.243
* 34.201.235.54
* 54 196 224 236
* 35.75.212.45
* 52 199 184 130
* 18.180.161.176

Você poderá ver a seguinte mensagem de erro no [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![Imagem de _erro EEC](assets/EEC_error.png)

Os motivos pelos quais você pode ver essa mensagem de erro e correções para corrigir a situação são:

* **Problema:** O domínio do site (ISP) está bloqueando o [!UICONTROL Enhanced Experience Composer].

  **Solução:** Inclua na lista de permissões os endereços IP listados acima.

* **Problema:** Incluir na lista de permissões Os endereços IP são resolvidos, mas o seu site não é compatível com a versão 1.2 do TLS. [!DNL Target] O atualmente usa a configuração padrão do 1.2. Antes da [!DNL Target] 18.4.1 (25 de abril de 2018), a configuração padrão era compatível com TLS 1.0. Para obter mais informações, consulte [Alterações na criptografia da Segurança da camada de transporte (TLS)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

  **Solução:** Consulte a seguinte pergunta (A [!UICONTROL Enhanced Visual Experience Composer] O não será carregado nas páginas seguras do meu site que usam TLS 1.2).

## O EEC não será carregado nas páginas seguras do meu site que usam TLS 1.0. (Somente EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

Você poderá ver a mensagem de erro descrita acima em &quot;A [!UICONTROL Enhanced Visual Experience Composer] O não será carregado nas páginas seguras do meu site.&quot; incluir na lista de permissões se os endereços IP acima forem resolvidos, mas o seu site não for compatível com a versão 1.2 do TLS. [!DNL Target] O atualmente usa a configuração padrão do 1.2. Antes da [!DNL Target] 18.4.1 (25 de abril de 2018), a configuração padrão era compatível com TLS 1.0. Para obter mais informações, consulte [Alterações na criptografia da Segurança da camada de transporte (TLS)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

Para verificar a versão do TLS no seu site usando o Firefox (outros navegadores têm etapas semelhantes):

1. Abra o site afetado no Firefox.
1. Clique em **[!UICONTROL Show Site Information]** ícone na barra de endereços do navegador.

   ![imagem firefox_more_info](assets/firefox_more_info.png)

1. Clique em **[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**.

   ![imagem firefox_more_info_2](assets/firefox_more_info_2.png)

1. Analise as informações de versão do TLS em Detalhes técnicos:

   ![imagem firefox_more_info_3](assets/firefox_more_info_3.png)

1. Se você descobrir que seu site está mostrando o TLS 1.0, consulte [Alterações na criptografia da Segurança da camada de transporte (TLS)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank} para obter informações sobre a política de suporte TLS do Target. Para solucionar a situação por enquanto (válida até 12 de setembro de 2018){target=_blank}, alcance para [Atendimento ao cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para configuração com sua versão TLS e o domínio.

## Vejo tempos limite ou erros de &quot;acesso negado&quot; ao carregar sites com proxy ativado. (Somente EEC) {#section_60CBB9022DC449F593606C0E6252302D}

Verifique se os IPs de proxy não estão bloqueados em seu ambiente.
