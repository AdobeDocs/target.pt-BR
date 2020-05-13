---
keywords: client care;cname;certificate program;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Informações sobre como trabalhar com o Adobe Client Care para implementar o suporte CNAME (Canonical Name) no Adobe Target.
title: CNAME e Adobe Target
topic: Standard
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 1bcfa02632a13cf1f20a618abb07cae41b49d5ec
workflow-type: tm+mt
source-wordcount: '1367'
ht-degree: 2%

---


# CNAME e Adobe Target {#cname-and-adobe-target}

Instructions for working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. Para melhor lidar com problemas de bloqueio de anúncios, ou políticas de cookies relacionadas ao ITP, um CNAME é usado, portanto, as chamadas são feitas para um domínio pertencente ao cliente em vez de um domínio pertencente à Adobe.

## Solicitar suporte CNAME

Execute as etapas a seguir para solicitar o suporte CNAME no [!DNL Target]:

1. A autoridade de certificação da Adobe (DigiCert) precisa verificar se a Adobe está autorizada a gerar certificados em seu domínio.

   A DigiCert chama esse processo de validação de controle de [domínio (DCV)](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/), e a Adobe não poderá gerar um certificado em seu domínio até que esse processo seja concluído para pelo menos um dos seguintes métodos DCV:

   * O método DCV mais rápido é o método DNS CNAME, no qual você adiciona um registro DNS CNAME (contendo um token) ao seu domínio que aponta para o nome do host DCV (`dcv.digicert.com`) da DigiCert. Este registro CNAME indica à DigiCert que a Adobe está autorizada a gerar o certificado. O Adobe Client Care enviará as instruções com os registros de DNS necessários. Um exemplo:

      ```
      3b0332e02daabf31651a5a0d81ba830a.target.example.com.  IN  CNAME  dcv.digicert.com.
      ```

      >[!NOTE]
      >
      >* Esses tokens DCV expiram depois de 30 dias, e o Adobe Client Care entrará em contato com você com os tokens atualizados. Por um tempo mais rápido para a resolução de sua solicitação CNAME, esteja preparado para fazer essas alterações de DNS em todos os domínios solicitados antes de enviar sua solicitação.
         >
         >
      * Se o domínio tiver registros [CAA](https://en.wikipedia.org/wiki/DNS_Certification_Authority_Authorization)DNS, você deverá adicionar `digicert.com` se ele ainda não tiver sido adicionado. Este registro DNS indica quais autoridades de certificados estão autorizadas a emitir certificados para o domínio. O registro DNS resultante seria semelhante a: `example.com. IN CAA 0 issue "digicert.com"`. Você pode usar [a G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CAA) para determinar se o domínio raiz tem um registro CAA existente. Você pode ler mais sobre como a DigiCert lida com registros CAA [aqui](https://docs.digicert.com/manage-certificates/dns-caa-resource-record-check).


   * A DigiCert também tenta o método de email, no qual envia mensagens de email para endereços encontrados nas informações do WHOIS do domínio e para endereços de email predeterminados (administrador, administrador, webmaster, host e postmaster `@[domain_name]`). Consulte a documentação [dos métodos](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) DCV para obter mais informações.

      Para acelerar o processo de email do DCV, a DigiCert fornece as seguintes recomendações:

      &quot;Verifique se o seu registrador/provedor WHOIS não mascarou ou removeu endereços [de email]relevantes. Se estiverem, descubra se eles fornecem uma maneira (por exemplo, endereço de email anônimo, formulário da Web) para permitir que as autoridades [de] certificados acessem os dados WHOIS de seu domínio.&quot;

1. Crie um registro CNAME no DNS do seu domínio apontando para seu nome de host comum `clientcode.tt.omtrdc.net`. Por exemplo, se o código do cliente for cnamecustomer e o nome do host proposto for `target.example.com`, seu registro CNAME de DNS deverá ser semelhante a:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. Abra um ticket do [Adobe Client Care solicitando suporte](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) CNAME para suas [!DNL Target] chamadas.

   A Adobe trabalhará com a DigiCert para comprar e implantar seu certificado nos servidores de produção da Adobe. A DigiCert iniciará o processo DCV e o Adobe Client Care notificará você quando sua implementação estiver pronta.

1. Depois de concluir o tarefa anterior e o Adobe Client Care ter notificado que a implementação está pronta, você deve atualizá-la `serverDomain` para o novo CNAME em at.js.

## Perguntas frequentes

As informações a seguir respondem a perguntas frequentes sobre como solicitar e implementar o suporte CNAME em [!DNL Target]:

### Posso fornecer meu próprio certificado (também conhecido como trazer seu próprio certificado ou BYOC)? Em caso afirmativo, qual é o processo?

Sim, você pode fornecer seu próprio certificado; no entanto, não é recomendado. O gerenciamento do ciclo de vida do certificado SSL é significativamente mais fácil para a Adobe e para você quando a Adobe compra e controla o certificado. Os certificados SSL devem ser renovados todos os anos, o que significa que o Adobe Client Care deve entrar em contato com você todos os anos para enviar um novo certificado à Adobe em tempo hábil. Alguns clientes podem ter dificuldade em produzir um certificado renovado em tempo hábil a cada ano, o que compromete sua [!DNL Target] implementação porque os navegadores recusarão as conexões quando o certificado expirar.

>[!IMPORTANT]
>
>Esteja ciente de que, se você solicitar uma implementação CNAME de [!DNL Target] trazer seu próprio certificado, é responsável por fornecer certificados renovados ao Atendimento ao cliente da Adobe todos os anos. Permitir que seu certificado CNAME expire antes que a Adobe possa implantar um certificado renovado resultará em uma interrupção para sua [!DNL Target] implementação específica.

1. Ignore a etapa 1 acima, mas conclua as etapas 2 e 3. Ao abrir um ticket do Adobe Client Care (etapa 3), informe-os de que você fornecerá seu próprio certificado.

   A Adobe gerará e enviará uma solicitação de assinatura de certificado (CSR).

1. Use o CSR para adquirir o certificado por meio da autoridade de certificação (CA) escolhida.

1. Envie o novo certificado público para a Adobe. Os representantes da Adobe implantarão o certificado público em seus servidores de produção.

1. Conclua a etapa 4 após o Adobe Client Care ter notificado que a implementação está pronta.

### Quanto tempo até que meu novo certificado SSL expire?

Os certificados emitidos antes de 1º de setembro de 2020 serão certificados de dois anos. Os certificados emitidos a partir de 1º de setembro de 2020 serão de um ano. Você pode ler mais sobre a mudança para certificados de um ano [aqui](https://www.digicert.com/position-on-1-year-certificates).

### Quais nomes de host devo escolher? Quantos nomes de host por domínio devo escolher?

[!DNL Target] As implementações CNAME exigem apenas um nome de host por domínio no certificado SSL e no DNS do cliente, portanto, é isso que recomendamos. Alguns clientes podem exigir nomes de host adicionais por domínio para seus próprios fins (teste em armazenamento temporário, por exemplo), o que é suportado.

A maioria dos clientes escolhe um nome de host como `target.example.com`, então é isso que recomendamos, mas a escolha é, em última análise, sua. Certifique-se de não solicitar um nome de host de um registro DNS existente, pois isso causaria um conflito e atrasaria o tempo para a resolução de sua solicitação de [!DNL Target] CNAME.

### Já tenho uma implementação CNAME para [!DNL Adobe Analytics], podemos usar o mesmo certificado ou nome do host?

Não, [!DNL Target] requer um nome de host e um certificado separados.

### Minha implementação atual do Público alvo é afetada pelo ITP 2.x?

Em um navegador Safari, navegue até seu site no qual você tem uma biblioteca JavaScript de Públicos alvos. If you see a Target cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.x.

Os problemas de ITP podem ser resolvidos para Público alvo com apenas um CNAME do Analytics. Você precisará de um Público alvo separado CNAME somente no caso de cenários de bloqueio de anúncios em que o Público alvo estiver bloqueado.

Para obter mais informações sobre o ITP, consulte [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### A Adobe/DigiCert pode enviar emails do DCV para outro endereço de email `<someone>@example.com`?

Não, a DigiCert (ou qualquer autoridade de certificação) não permitirá que apenas qualquer pessoa com um endereço de email sob um domínio autorize um certificado SSL sob esse mesmo domínio, a menos que esse endereço de email também esteja incluído nas informações WHOIS do domínio ou na lista predeterminada de endereços (veja acima). Isso garante que somente indivíduos autorizados possam aprovar o DCV para um domínio específico. Se isso não for viável para você, recomendamos o uso do método DNS CNAME DCV (consulte acima).

### Como posso validar se minha implementação CNAME está pronta para o tráfego?

Use o seguinte conjunto de comandos (no terminal de linha de comando do MacOs ou do Linux, usando bash e curl 7.49+):

1. Primeiro cole esta função bash no seu terminal:

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..32},34,35,37,38}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. Em seguida, cole este comando (substituindo `target.example.com` pelo nome do host):

   ```
   validateEdgeFpsslSni target.example.com
   ```

   Se a implementação estiver pronta, você deverá ver a saída como abaixo. A parte importante é que todas as linhas são exibidas `CN=target.example.com`, o que corresponde ao nome do host desejado. Se algum deles mostrar `CN=*.tt.omtrdc.net`, a implementação **não** está pronta.

   ```
   $ validateEdgeFpsslSni target.example.com
   mboxedge17.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge21.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge22.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge26.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge28.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge29.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge30.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge31.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge32.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge34.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge35.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge37.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   mboxedge38.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. Valide seu novo CNAME DNS com outra solicitação de curva, que também deve mostrar `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Se esse comando falhar, mas o `validateEdgeFpsslSni` comando acima for bem-sucedido, talvez seja necessário aguardar a propagação completa das atualizações de DNS. Os registros de DNS têm um [TTL associado (time-to-live)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) que determina o tempo de expiração do cache para as respostas de DNS desses registros, portanto talvez seja necessário aguardar pelo menos tanto tempo quanto seus TTLs. Você pode usar o `dig target.example.com` comando ou [a G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME) para procurar seus TTLs específicos.

## Limitações conhecidas

* O modo de QA não ficará fixo quando você tiver CNAME e at.js 1.x porque ele é baseado em um cookie de terceiros. A solução alternativa é adicionar os parâmetros de pré-visualização a cada URL para o qual você navega. O modo de QA é fixo quando você tem CNAME e at.js 2.x.
* Atualmente, a `overrideMboxEdgeServer` configuração não funciona corretamente com CNAME. Isso deve ser definido como `false` para evitar solicitações com falha.
