---
keywords: Definição de metas; eec; visual experience composer; solucionar problemas do enhanced experience composer; solução de problemas
description: Saiba como solucionar problemas que às vezes ocorrem no Enhanced Experience Composer (EEC) do Adobe [!DNL Target]  sob determinadas condições.
title: Como solucionar problemas relacionados ao Enhanced Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: 7dea7707-5d9f-49c4-9ccd-618eeb7b3568
source-git-commit: b14c39bd1de3f8d78aa720f7a064009759916802
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 23%

---

# Solução de problemas relacionados ao [!UICONTROL Enhanced Experience Composer]

Problemas de exibição às vezes ocorrem no [!DNL Adobe Target] [!UICONTROL Enhanced Experience Composer] (EEC) sob determinadas condições.

## O EEC não carregará um URL interno de controle de qualidade que não esteja acessível no IP público. {#section_D29E96911D5C401889B5EACE267F13CF}

Isso pode ser resolvido incluindo na lista de permissões os seguintes endereços IP. Esses endereços IP são para o servidor do Adobe usado para o proxy EEC. Eles são necessários somente para a atividade de edição. Incluir na lista de permissões Os visitantes do seu site não precisam desses endereços IP resolvidos.

Peça à sua equipe de TI para incluir na lista de permissões os seguintes endereços IP:

### Prod va7

40.70.154.136/29
52.254.106.240/28
52.254.106.160/28
52.254.107.16/28
20.186.185.181
20.22.83.112
20.186.185.227
52.254.106.192/28
52.254.106.0/28
52.254.107.128/28
52.254.107.80/28
52.254.106.176/28
52.254.107.32/28
52.254.105.192/28
52.254.107.64/28
52.254.106.208/28
52.254.107.0/28
52.254.106.224/28
20.14.241.153
20.186.185.239
4.152.211.251
52.254.107.144/28
52.254.106.144/28

### Prod nld2

51.138.17.16/28
51.138.17.48/28
51.138.16.128/28
51.138.17.32/28
51.138.16.240/28
51.138.17.112/28
51.138.16.160/28
51.138.16.208/28
51.138.17.80/28
51.138.17.0/28
51.138.17.96/28
51.138.16.144/28
20.31.145.248
20.126.189.248
51.138.16.224/28
51.138.16.192/28
51.138.12.94
51.138.12.11
51.138.16.176/28
51.138.12.100
51.138.17.64/28
51.138.12.160/28

### Prod aus5

20.43.104.160/28
20.227.35.177
20.40.188.227
20.43.104.112/28
20.43.104.128/28
20.43.104.144/28
20.40.188.166
20.53.206.128
20.43.104.80/28
20.43.104.16/28
20.43.105.48/28
20.43.104.96/28
20.43.104.48/28
20.40.188.194
20.43.104.32/28
20.40.191.224/28
20.43.105.16/28
20.40.191.96/28
20.43.104.176/28
20.40.191.240/28
20.43.104.64/28
20.43.105.32/28
20.43.104.192/28
20.43.105.0/28
20.43.104.0/28

### Endereços IP herdados

Incluir na lista de permissões Os endereços IP herdados a seguir devem continuar sendo migrados até notificação adicional.

34.254.77.200
54.73.207.147
54.229.152.123
3.224.194.242
54.90.51.39
34.228.136.112
54.150.116.11
18.178.142.8
54.199.107.77
99.80.139.221
54.78.56.224
54.247.179.246
54.80.219.243
34.201.235.54
54.196.224.236
35.75.212.45
52.199.184.130
18.180.161.176

Você poderá ver a seguinte mensagem de erro em [!DNL Target]:

`Error: Your website domain (ISP) is blocking the [!UICONTROL Enhanced Experience Composer]. You can allowlist the [!UICONTROL Enhanced Experience Composer]'s IP addresses or turn off [!UICONTROL Enhanced Experience Composer] in [!UICONTROL Configure] > [!UICONTROL Page Delivery] menu.`

![Imagem de erro EEC](assets/EEC_error.png)

Os motivos pelos quais você pode ver essa mensagem de erro e correções para corrigir a situação são:

* **Problema:** o domínio do site (ISP) está bloqueando o [!UICONTROL Enhanced Experience Composer].

  **Solução:** Inclua na lista de permissões os endereços IP listados acima.

* incluir na lista de permissões **Problema:** os endereços IP são resolvidos, mas o seu site não é compatível com a versão 1.2 do TLS. O [!DNL Target] atualmente usa a configuração padrão 1.2. Antes do [!DNL Target] 18.4.1 (25 de abril de 2018), a configuração padrão era compatível com o TLS 1.0. Para obter mais informações, consulte [Alterações na criptografia do TLS (Transport Layer Security)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

  **Solução:** veja a seguinte pergunta (O [!UICONTROL Enhanced Visual Experience Composer] não será carregado nas páginas seguras do meu site que usam TLS 1.2).

## O EEC não será carregado nas páginas seguras do meu site que usam TLS 1.0. (Somente EEC) {#section_C5B31E3D32A844F68E5A8153BD17551F}

Você poderá ver a mensagem de erro descrita acima em &quot;O [!UICONTROL Enhanced Visual Experience Composer] não será carregado nas páginas seguras do meu site&quot;. incluir na lista de permissões se os endereços IP acima forem resolvidos, mas o seu site não for compatível com a versão 1.2 do TLS. O [!DNL Target] atualmente usa a configuração padrão 1.2. Antes do [!DNL Target] 18.4.1 (25 de abril de 2018), a configuração padrão era compatível com TLS 1.0. Para obter mais informações, consulte [Alterações na criptografia do TLS (Transport Layer Security)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank}.

Para verificar a versão do TLS no seu site usando o Firefox (outros navegadores têm etapas semelhantes):

1. Abra o site afetado no Firefox.
1. Clique no ícone **[!UICONTROL Show Site Information]** na barra de endereços do navegador.

   ![imagem do firefox_more_info](assets/firefox_more_info.png)

1. Clique em **[!UICONTROL Show Connection Details]** > **[!UICONTROL More Information]**.

   ![imagem do firefox_more_info_2](assets/firefox_more_info_2.png)

1. Analise as informações de versão do TLS em Detalhes técnicos:

   ![imagem do firefox_more_info_3](assets/firefox_more_info_3.png)

1. Se você descobrir que seu site está mostrando o TLS 1.0, consulte [Alterações de Criptografia do TLS (Transport Layer Security)](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/tls-transport-layer-security-encryption.html){target=_blank} para obter informações sobre a política de suporte TLS do Target. Para solucionar a situação por enquanto (válida até 12 de setembro de 2018){target=_blank}, acesse o [Atendimento ao cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para obter a configuração com a versão TLS e o domínio.

## Vejo tempos limite ou erros de &quot;acesso negado&quot; ao carregar sites com proxy ativado. (Somente EEC) {#section_60CBB9022DC449F593606C0E6252302D}

Verifique se os IPs de proxy não estão bloqueados em seu ambiente.
