---
keywords: client care;cname;certificate programa;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Trabalhe com o Adobe Client Care para implementar o suporte CNAME (Nome Canônico) no Adobe Target para lidar com problemas de bloqueio de anúncios ou políticas de cookies relacionadas ao ITP.
title: Como uso o CNAME no Público alvo?
feature: Privacidade e segurança
role: Desenvolvedor
translation-type: tm+mt
source-git-commit: 69677b9d384d9817a39386fc1388a4aa42121713
workflow-type: tm+mt
source-wordcount: '1163'
ht-degree: 2%

---


# CNAME e Adobe Target

Instruções para trabalhar com [!DNL Adobe] o Client Care para implementar o suporte CNAME (Nome Canônico) em [!DNL Adobe Target]. Use o CNAME para lidar com problemas de bloqueio de anúncios ou políticas de cookies relacionadas ao ITP (Prevenção de rastreamento inteligente). Com CNAME, as chamadas são feitas para um domínio pertencente ao cliente, e não para um domínio pertencente a [!DNL Adobe].

## Solicitar suporte CNAME no Público alvo

1. Determine a lista de nomes de host necessários para seu certificado SSL (consulte as Perguntas frequentes abaixo).

1. Para cada nome de host, crie um registro CNAME em seu DNS apontando para seu nome de host regular [!DNL Target] `clientcode.tt.omtrdc.net`.

   Por exemplo, se seu código de cliente for &quot;cnamecustomer&quot; e seu nome de host proposto for `target.example.com`, seu registro CNAME de DNS será semelhante a:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >Certificado até que a DigiCert não emita uma etapa seja concluída. Portanto, [!DNL Adobe] não pode atender à solicitação de uma implementação CNAME até que essa etapa seja concluída.

1. [Preencha este ](https://experienceleague.adobe.com/docs/core-services/assets/FPC_Request_Form.xlsx?lang=en) formulário e inclua-o ao  [abrir um ticket do Atendimento ao cliente do Adobe solicitando suporte](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) CNAME:

   * Adobe [!DNL Target] código do cliente:
   * Nomes de host de certificado SSL (por exemplo: `target.example.com target.example.org`):
   * Comprador de certificados SSL (o Adobe é altamente recomendado, consulte as Perguntas frequentes): Adobe/cliente
   * Se o cliente estiver comprando o certificado, também conhecido como &quot;Traga seu próprio certificado&quot; (BYOC), preencha estes detalhes adicionais:
      * Organização do certificado (por exemplo: Exemplo de Empresa Inc):
      * Unidade organizacional do certificado (opcional, por exemplo: Comercialização):
      * País do certificado (por exemplo: EUA):
      * Estado/região do certificado (exemplo: Califórnia):
      * Cidade do certificado (por exemplo: San Jose):

1. Se [!DNL Adobe] estiver comprando o certificado, [!DNL Adobe] funcionará com a DigiCert para implantar seu certificado nos servidores de produção do Adobe.

   Se o cliente estiver comprando o certificado (BYOC), o [!DNL Adobe] Client Care enviará a solicitação de assinatura de certificado (CSR). Use o CSR ao adquirir o certificado por meio da autoridade de certificação escolhida. Depois que o certificado for emitido, envie uma cópia do certificado e de quaisquer certificados intermediários para o [!DNL Adobe] Client Care para implantação.

   [!DNL Adobe] O Client Care notifica quando sua implementação está pronta.

1. Atualize `serverDomain` para o novo CNAME em at.js.

## Perguntas frequentes

As informações a seguir respondem a perguntas frequentes sobre como solicitar e implementar o suporte CNAME em [!DNL Target]:

### Posso fornecer meu próprio certificado (Trazer seu próprio certificado ou BYOC)?

Você pode fornecer seu próprio certificado. Entretanto, [!DNL Adobe] não recomenda essa prática. O gerenciamento do ciclo de vida do certificado SSL é mais fácil tanto para [!DNL Adobe] quanto para você se [!DNL Adobe] comprar e controlar o certificado. Os certificados SSL devem ser renovados todos os anos. Portanto, o [!DNL Adobe] Client Care deve entrar em contato com você todos os anos para obter um novo certificado em tempo hábil. Alguns clientes podem ter dificuldade em produzir um certificado renovado em tempo hábil. Sua implementação [!DNL Target] fica comprometida quando o certificado expira porque os navegadores recusam as conexões.

>[!IMPORTANT]
>
>Se você solicitar uma implementação CNAME [!DNL Target] do seu próprio certificado, você será responsável por fornecer certificados renovados ao [!DNL Adobe] Client Care todos os anos. Permitir que seu certificado CNAME expire antes de [!DNL Adobe] poder implantar um certificado renovado resulta em uma interrupção para sua implementação específica de [!DNL Target].

### Quanto tempo até que meu novo certificado SSL expire?

Os certificados emitidos antes de 1º de setembro de 2020 são certificados de dois anos. Os certificados emitidos a partir de 1º de setembro de 2020 são certificados de um ano. Você pode ler mais sobre a mudança para certificados de um ano [aqui](https://www.digicert.com/position-on-1-year-certificates).

### Quais nomes de host devo escolher? Quantos nomes de host por domínio devo escolher?

[!DNL Target] As implementações CNAME exigem apenas um nome de host por domínio no certificado SSL e no DNS do cliente. Adobe recomenda um nome de host. Alguns clientes exigem mais nomes de host por domínio para seus próprios fins (teste em armazenamento temporário, por exemplo), o que é suportado.

A maioria dos clientes escolhe um nome de host como `target.example.com`. A Adobe recomenda seguir essa prática, mas a escolha é sua. Não solicite um nome de host de um registro DNS existente. Isso causa um conflito e atrasa o tempo para a resolução da solicitação [!DNL Target] CNAME.

### Já tenho uma implementação CNAME para [!DNL Adobe Analytics], podemos usar o mesmo certificado ou nome do host?

Não, [!DNL Target] requer um nome de host e um certificado separados.

### Minha implementação atual do Público alvo é afetada pelo ITP 2.x?

Em um navegador do Safari, navegue até o site em que você tem uma biblioteca JavaScript [!DNL Target]. Se você vir um cookie [!DNL Target] definido no contexto de um CNAME, como `analytics.company.com`, você não será afetado pelo ITP 2.x.

Os problemas de ITP podem ser resolvidos para [!DNL Target] com apenas um [!DNL Analytics] CNAME. Você precisa de um [!DNL Target] CNAME separado somente em cenários de bloqueio de anúncios nos quais [!DNL Target] esteja bloqueado.

Para obter mais informações sobre o ITP, consulte [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### Que tipo de interrupções de serviço posso esperar quando minha implementação CNAME é implantada?

Não há interrupção de serviço quando o certificado é implantado (incluindo renovações de certificados).

No entanto, depois de alterar o nome do host em seu código de implementação [!DNL Target] (`serverDomain` em at.js) para o novo nome do host CNAME (`target.example.com`), os navegadores da Web tratam os visitantes recorrentes como novos visitantes. Os dados dos perfis de retorno dos visitantes são perdidos porque o cookie anterior está inacessível sob o nome do host antigo (`clientcode.tt.omtrdc.net`). O cookie anterior está inacessível devido a modelos de segurança do navegador. Essa interrupção ocorre somente no corte inicial para o novo CNAME. As renovações de certificados não têm o mesmo efeito porque o nome do host não é alterado.

### Que tipo de chave e algoritmo de assinatura de certificado são usados para minha implementação CNAME?

Todos os certificados são RSA SHA-256 e as chaves são RSA 2048-bit, por padrão. Os tamanhos de chave maiores que 2048 bits não são suportados no momento.

### Como posso validar se minha implementação CNAME está pronta para o tráfego?

Use o seguinte conjunto de comandos (no terminal de linha de comando macOS ou Linux, usando bash e curl 7.49+):

1. Cole esta função bash no seu terminal:

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. Cole este comando (substituindo `target.example.com` pelo seu nome de host):

   ```
   validateEdgeFpsslSni target.example.com
   ```

   Se a implementação estiver pronta, você verá a saída como abaixo. A parte importante é que todas as linhas incluem `CN=target.example.com`, que corresponde ao nome do host desejado. Se alguma linha incluir `CN=*.tt.omtrdc.net`, a implementação está **não** pronta.

   ```
   $ validateEdgeFpsslSni target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge36.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge37.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge38.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. Valide seu novo CNAME DNS com outra solicitação de curva, que também deve mostrar `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Se esse comando falhar, mas o comando `validateEdgeFpsslSni` acima for bem-sucedido, aguarde que suas atualizações de DNS se propaguem completamente. Os registros DNS têm um [TTL (time-to-live)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) associado que determina o tempo de expiração do cache para as respostas DNS desses registros. Como resultado, talvez você precise esperar pelo menos tanto tempo quanto seus TTLs. Você pode usar o comando `dig target.example.com` ou [a G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME) para procurar seus TTLs específicos.

## Limitações conhecidas

* O modo de QA não é aderente quando você tem CNAME e at.js 1.x porque é baseado em um cookie de terceiros. A solução alternativa é adicionar os parâmetros de pré-visualização a cada URL para o qual você navega. O modo de QA é fixo quando você tem CNAME e at.js 2.x.
* Atualmente, a configuração `overrideMboxEdgeServer` não funciona corretamente com CNAME ao usar versões do at.js anteriores ao at.js 1.8.2 e ao at.js 2.3.1. Se você estiver usando uma versão mais antiga do at.js, essa configuração deve ser definida como `false` para evitar solicitações com falha. Como alternativa, você deve considerar [atualizar o at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) para uma versão mais recente e compatível.
* Ao usar CNAME, é mais provável que o tamanho do cabeçalho do cookie para chamadas [!DNL Target] aumente. [!DNL Adobe] recomenda manter o tamanho do cookie abaixo de 8 KB.
