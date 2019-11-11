---
keywords: client care;cname;programa de certificado;nome canônico;cookies;certificado;amc;adobe managed certificate;digicert;domínio control validation;dcv
description: Informações sobre como trabalhar com o Adobe Client Care para implementar o suporte CNAME (Canonical Name) no Adobe Target.
title: CNAME e Adobe Target
topic: Padrão
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: 117e4c8712d49a284331552268cec42bb34cf013

---


# CNAME e Adobe Target {#cname-and-adobe-target}

Instructions about working with Adobe Client Care to implement CNAME (Canonical Name) support in [!DNL Adobe Target]. Para melhor lidar com problemas de bloqueio de anúncios, ou políticas de cookies relacionadas ao ITP, um CNAME é usado, portanto, as chamadas são feitas para um domínio pertencente ao cliente em vez de um domínio pertencente à Adobe.

## Solicitar suporte CNAME

Execute as etapas a seguir para solicitar o suporte CNAME no [!DNL Target]:

1. A autoridade de certificação da Adobe (DigiCert) precisa verificar se a Adobe está autorizada a gerar certificados em seu domínio.

   A DigiCert chama esse processo de validação [de controle de](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) domínio (DCV), e a Adobe não poderá gerar um certificado em seu domínio até que esse processo seja concluído.

   O DCV usa alguns métodos e há algumas coisas que você pode fazer antes de abrir um ticket do Adobe Client Care (etapa 3) para ajudar a acelerar o processo do DCV:

   * A DigiCert tentará primeiro o método de email, no qual eles enviarão emails para endereços encontrados nas informações do WHOIS do domínio, bem como endereços de email pré-determinados (administrador, administrador, webmaster, host e postmaster `@[domain_name]`). Consulte a documentação [dos métodos](https://docs.digicert.com/manage-certificates/dv-certificate-enrollment/domain-control-validation-dcv-methods/) DCV para obter mais informações.

      Para acelerar o processo de email do DCV, a DigiCert fornece as seguintes recomendações:

      "Verifique se o seu registrador/provedor WHOIS não mascarou ou removeu endereços [de email]relevantes. Se estiverem, descubra se eles fornecem uma maneira (por exemplo, endereço de email anônimo, formulário da Web) para permitir que as autoridades [de] certificados acessem os dados WHOIS de seu domínio."

   * Se o método de email DCV não for uma opção para você, o próximo método será o DNS TXT, no qual você adicionará um registro DNS TXT ao seu domínio com um valor de hash. Este registro TXT indica à DigiCert que a Adobe está autorizada a gerar o certificado. Se precisar usar esse método, informe ao Adobe Client Care quando abrir um ticket (etapa 3). Isso ajudará a acelerar o processo de DCV.

1. Crie um registro CNAME no DNS do seu domínio apontando para seu nome de host comum `clientcode.tt.omtrdc.net`. Por exemplo, se o código do cliente for cnamecustomer e o nome do host proposto for `target.example.com`, seu registro CNAME de DNS deverá ser semelhante a:

   ```
   target.example.com  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

1. Abra um ticket do [Adobe Client Care solicitando suporte](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html#reference_ACA3391A00EF467B87930A450050077C) CNAME para suas [!DNL Target] chamadas.

   A Adobe trabalhará com a DigiCert para comprar e implantar seu certificado nos servidores de produção da Adobe. A DigiCert iniciará o processo DCV e o Adobe Client Care notificará você quando sua implementação estiver pronta.

1. Após concluir as tarefas anteriores e o Adobe Client Care tiver notificado que a implementação está pronta, você deve atualizar o CNAME `serverDomain` para o novo CNAME em at.js.

## Perguntas frequentes

As informações a seguir respondem a perguntas frequentes sobre como solicitar e implementar o suporte CNAM em [!DNL Target]:

### Posso fornecer meu próprio certificado? Em caso afirmativo, qual é o processo?

Sim, você pode fornecer seu próprio certificado para isso:

1. Pule a etapa 1 acima, mas conclua as etapas 2 e 3. Ao abrir um ticket do Adobe Client Care (etapa 3), informe-os de que você fornecerá seu próprio certificado.

   A Adobe gerará e enviará uma solicitação de assinatura de certificado (CSR).

1. Use o CSR para adquirir o certificado por meio da autoridade de certificação (CA) escolhida.

1. Envie o novo certificado público para a Adobe. Os representantes da Adobe implantarão o certificado público em seus servidores de produção.

1. Conclua a etapa 4 após o Adobe Client Care ter notificado que a implementação está pronta.

### Já tenho uma implementação CNAME para [!DNL Adobe Analytics], podemos usar o mesmo certificado ou nome do host?

Não, [!DNL Target] requer um nome de host e um certificado separados.

### Como posso validar se minha implementação CNAME está pronta para o tráfego?

Use o seguinte conjunto de comandos (no terminal de linha de comando do MacOs ou do Linux, usando bash e curl 7.49+):

1. Primeiro cole esta função bash no seu terminal:

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{17,21,22,26,{28..33}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. Em seguida, cole este comando (substituindo `target.example.com` pelo nome do host):

   ```
   validateEdgeFpsslSni target.example.com
   ```

   Se a implementação estiver pronta, você deverá ver a saída como abaixo. A parte importante é que todas as linhas são exibidas, o que corresponde ao nome do host desejado. `CN=target.example.com` Se algum deles mostrar `CN=*.tt.omtrdc.net`, a implementação **não** está pronta.

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
   mboxedge33.tt.omtrdc.net: *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   ```

1. Valide seu novo CNAME DNS com outra solicitação de curva, que também deve mostrar `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Se esse comando falhar, mas o `validateEdgeFpsslSni` comando acima for bem-sucedido, talvez seja necessário aguardar a propagação completa das atualizações de DNS.
