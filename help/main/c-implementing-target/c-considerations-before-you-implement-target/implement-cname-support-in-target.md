---
keywords: atendimento ao cliente; cname; programa de certificado; nome canônico; cookies; certificado; amc; certificado gerenciado da adobe; digicert; validação de controle de domínio; dcv
description: Trabalhar com [!DNL Adobe] Atendimento ao cliente para implementar o suporte CNAME (Canonical Name) no [!DNL Adobe Target] para lidar com problemas de bloqueio de anúncios.
title: Como uso o CNAME no Target?
feature: Privacy & Security
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '1195'
ht-degree: 1%

---

# CNAME e [!DNL Target]

Instruções para trabalhar com [!DNL Adobe] Atendimento ao cliente para implementar o suporte CNAME (Canonical Name) no [!DNL Adobe Target]. Use o CNAME para lidar com problemas de bloqueio de anúncios ou políticas de cookies relacionadas à ITP (Intelligent Tracking Prevention). Com o CNAME, as chamadas são feitas para um domínio pertencente ao cliente, em vez de um domínio pertencente ao [!DNL Adobe].

## Solicite suporte CNAME no [!DNL Target]

1. Determine a lista de nomes de host necessários para seu certificado SSL (consulte as Perguntas frequentes abaixo).

1. Para cada nome de host, crie um registro CNAME no DNS apontando para a função [!DNL Target] hostname `clientcode.tt.omtrdc.net`.

   Por exemplo, se o código de cliente for &quot;cliente de nome&quot; e o nome de host proposto for `target.example.com`, seu registro DNS CNAME é semelhante a:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >[!DNL Adobe]A autoridade de certificação da DigiCert não pode emitir um certificado até que esta etapa seja concluída. Por conseguinte, [!DNL Adobe] O não pode atender à solicitação de uma implementação CNAME até que essa etapa seja concluída.

1. [Preencha este formulário](/help/main/assets/FPC_Request_Form.xlsx) e inclua ao [abra um [!DNL Adobe] ticket do Atendimento ao cliente solicitando o suporte CNAME](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C):

   * [!DNL Adobe Target] código de cliente:
   * Nomes de host do certificado SSL (por exemplo: `target.example.com target.example.org`):
   * comprador de certificado SSL ([!DNL Adobe] é altamente recomendado, consulte as Perguntas frequentes: Adobe/cliente
   * Se o cliente estiver comprando o certificado, também conhecido como &quot;Traga seu próprio certificado&quot; (BYOC), preencha estes detalhes adicionais:
      * Organização de certificado (exemplo: Exemplo Empresa Inc):
      * Unidade organizacional do certificado (opcional, por exemplo: Marketing):
      * País do certificado (exemplo: EUA):
      * Estado/região do certificado (exemplo: Califórnia):
      * Cidade do certificado (exemplo: San Jose):

1. If [!DNL Adobe] compra do certificado, [!DNL Adobe] O funciona com a DigiCert para comprar e implantar seu certificado em [!DNL Adobe]Servidores de produção da .

   Se o cliente estiver comprando o certificado (BYOC), [!DNL Adobe] O Atendimento ao cliente envia a solicitação de assinatura de certificado (CSR). Use o CSR ao adquirir o certificado por meio da autoridade de certificação escolhida. Após a emissão do certificado, enviar uma cópia do certificado e dos certificados intermédios ao [!DNL Adobe] Atendimento ao cliente para implantação.

   [!DNL Adobe] O Atendimento ao cliente notifica quando sua implementação está pronta.

1. Atualize o `serverDomain` ([documentação](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}){target=_blank} para o novo nome de host CNAME e definir `overrideMboxEdgeServer` para `false` ([documentação](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank}){target=_blank} em sua configuração do at.js.

## Perguntas frequentes

As informações a seguir respondem perguntas frequentes sobre a solicitação e a implementação do suporte CNAME no [!DNL Target]:

### Posso fornecer meu próprio certificado (Traga seu próprio certificado ou BYOC)?

Você pode fornecer seu próprio certificado. No entanto, [!DNL Adobe] não recomenda essa prática. O gerenciamento do ciclo de vida do certificado SSL é mais fácil para ambos [!DNL Adobe] e você se [!DNL Adobe] compra e controla o certificado. Os certificados SSL devem ser renovados todos os anos. Por conseguinte, [!DNL Adobe] O Atendimento ao cliente deve entrar em contato com você todos os anos para obter um novo certificado em tempo hábil. Alguns clientes podem ter dificuldade em produzir um certificado renovado em tempo hábil. Seu [!DNL Target] A implementação é comprometida quando o certificado expira porque os navegadores recusam as conexões.

>[!IMPORTANT]
>
>Se você solicitar um [!DNL Target] forneça sua própria implementação de CNAME de certificado, você é responsável por fornecer certificados renovados a [!DNL Adobe] Atendimento ao cliente todos os anos. Permitir que seu certificado CNAME expire antes de [!DNL Adobe] pode implantar um certificado renovado e resultar em uma interrupção para seu [!DNL Target] implementação.

### Por quanto tempo até que meu novo certificado SSL expire?

Todos [!DNL Adobe]Os certificados adquiridos são válidos por um ano. Consulte [Artigo da DigiCert sobre certificados de 1 ano](https://www.digicert.com/blog/position-on-1-year-certificates) para obter mais informações.

### Quais nomes de host devo escolher? Quantos nomes de host por domínio devo escolher?

[!DNL Target] As implementações CNAME exigem apenas um nome de host por domínio no certificado SSL e no DNS do cliente. [!DNL Adobe] A recomenda um nome de host por domínio. Alguns clientes exigem mais nomes de host por domínio para seus próprios fins (teste em preparo, por exemplo), o que é compatível.

A maioria dos clientes escolhe um nome de host como `target.example.com`. [!DNL Adobe] A recomenda seguir essa prática, mas a escolha é, em última análise, sua. Não solicite um nome de host de um registro DNS existente. Isso causa um conflito e atrasa o tempo para a resolução do seu [!DNL Target] Solicitação CNAME.

### Já tenho uma implementação CNAME para [!DNL Adobe Analytics], posso usar o mesmo certificado ou nome de host?

Não, [!DNL Target] requer um nome de host e certificado separados.

### Minha implementação atual de [!DNL Target] afetado pela ITP 2.x?

A Apple Intelligent Tracking Prevention (ITP) versão 2.3 apresentou seu recurso de Mitigação de cloaking CNAME, que é capaz de detectar [!DNL Adobe Target] Implementações CNAME e reduz a expiração do cookie para sete dias. Atualmente [!DNL Target] não tem solução alternativa para a Mitigação de cloaking CNAME da ITP. Para obter mais informações sobre ITP, consulte [Apple Intelligent Tracking Prevention (ITP) 2.x](https://developer.adobe.com/target/before-implement/privacy/apple-itp-2x/){target=_blank}.

### Que tipo de interrupções de serviço posso esperar quando minha implementação CNAME é implantada?

Não há interrupção de serviço quando o certificado é implantado (incluindo renovações de certificado).

No entanto, depois de alterar o nome do host em seu [!DNL Target] código de implementação (`serverDomain` na at.js) para o novo nome de host CNAME (`target.example.com`), os navegadores da Web tratam visitantes recorrentes como novos visitantes. O retorno dos dados de perfil dos visitantes é perdido porque o cookie anterior está inacessível com o nome de host antigo (`clientcode.tt.omtrdc.net`). O cookie anterior está inacessível devido a modelos de segurança do navegador. Essa interrupção ocorre somente no corte inicial para o novo CNAME. As renovações de certificado não têm o mesmo efeito porque o nome de host não é alterado.

### Qual tipo de chave e algoritmo de assinatura de certificado é usado para minha implementação CNAME?

Todos os certificados são RSA SHA-256 e as chaves são RSA 2048 bits, por padrão. No momento, não há suporte para tamanhos de chave maiores que 2048 bits.

### Como posso validar se minha implementação CNAME está pronta para o tráfego?

Use o seguinte conjunto de comandos (no terminal de linha de comando macOS ou Linux, usando bash e curl >=7.49):

1. Copie e cole essa função bash no terminal ou cole a função no arquivo de script de inicialização bash (normalmente `~/.bash_profile` ou `~/.bashrc`) para que a função esteja disponível nas sessões do terminal:

   ```
   function adobeTargetCnameValidation {
     local hostname="$1"
     if [ -z "$hostname" ]; then
       echo "ERROR: no hostname specified"
       return 1
     fi
   
     local service="Adobe Target CNAME implementation"
     local edges="31 32 34 35 36 37 38"
     local edgeDomain="tt.omtrdc.net"
     local edgeFormat="mboxedge%d%s.$edgeDomain"
     local shardFormat="-alb%02d"
     local shards=5
     local shardsFoundCount=0
     local shardsFound
     local shardsFoundOutput
     local curlRegex="subject:.*CN=|expire date:|issuer:"
     local curlValidation="SSL certificate verify ok"
     local curlResponseValidation='"OK"'
     local curlEndpoint="/uptime?mboxClient=uptime3"
     local url="https://$hostname$curlEndpoint"
     local sslLabsUrl="https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=$hostname"
     local success="✅"
     local failure="🚫"
     local info="🔎"
     local rule="="
     local horizontalRule="$(seq ${COLUMNS:-30} | xargs printf "$rule%.0s")"
     local miniRule="$(seq 5 | xargs printf "$rule%.0s")"
     local curlVersion="$(curl --version | head -1 | cut -d' ' -f2 )"
     local curlVersionRequired=">=7.49"
     local edgeCount="$(wc -w <<< "$edges" | tr -d ' ')"
     local edge
     local shard
     local currEdgeShard
     local dnsOutput
     local cnameExists
     local endToEndTestSucceeded
     local curlResult
   
     for shard in $(seq $shards); do
       if [ "$shardsFoundCount" -eq 0 ]; then
         for edge in $edges; do
           if [ "$shard" -eq 1 ]; then
             currEdgeShard="$(printf "$edgeFormat" "$edge" "")"
           else
             currEdgeShard="$(
               printf "$edgeFormat" "$edge" "$(
                 printf -- "$shardFormat" "$shard"
               )"
             )"
           fi
           curlResult="$(curl -vsm20 --connect-to "$hostname:443:$currEdgeShard:443" "$url" 2>&1)"
           if grep -q "$curlValidation" <<< "$curlResult"; then
             shardsFound+=" $currEdgeShard"
             if grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundCount=$((shardsFoundCount+1))
               shardsFoundOutput+="\n\n$miniRule $success $hostname [edge shard: $currEdgeShard] $miniRule\n"
             else
               shardsFoundOutput+="\n\n$miniRule $failure $hostname [edge shard: $currEdgeShard] $miniRule\n"
             fi
             shardsFoundOutput+="$(grep -E "$curlRegex" <<< "$curlResult" | sort)"
             if ! grep -q "$curlResponseValidation" <<< "$curlResult"; then
               shardsFoundOutput+="\nERROR: unexpected HTTP response from this shard using $url"
             fi
           fi
         done
       fi
     done
   
     echo
     echo "$horizontalRule"
     echo
     echo "$service validation for hostname $hostname:"
     dnsOutput="$(dig -t CNAME +short "$hostname" 2>&1)"
     if grep -qFi ".$edgeDomain" <<< "$dnsOutput"; then
       echo "$success $hostname passes DNS CNAME validation"
       cnameExists=true
     else
       echo -n "$failure $hostname FAILED DNS CNAME validation -- "
       if [ -n "$dnsOutput" ]; then
         echo -e "$dnsOutput is not in the subdomain $edgeDomain"
       else
         echo "required DNS CNAME record pointing to <target-client-code>.$edgeDomain not found"
       fi
     fi
   
     curlResult="$(curl -vsm20 "$url" 2>&1)"
     if grep -q "$curlValidation" <<< "$curlResult"; then
       if grep -q "$curlResponseValidation" <<< "$curlResult"; then
         echo -en "$success $hostname passes TLS and HTTP response validation"
         if [ -n "$cnameExists" ]; then
           echo
         else
           echo " -- the DNS CNAME is not pointing to the correct subdomain for ${service}s with Adobe-managed certificates" \
             "(bring-your-own-certificate implementations don't have this requirement), but this test passes as configured"
         fi
         endToEndTestSucceeded=true
       else
         echo -n "$failure $hostname FAILED HTTP response validation --" \
           "unexpected response from $url -- "
         if [ -n "$cnameExists" ]; then
           echo "DNS is NOT pointing to the correct shard, notify Adobe Client Care"
         else
           echo "the required DNS CNAME record is missing, see above"
         fi
       fi
     else
   
       echo -n "$failure $hostname FAILED TLS validation -- "
       if [ -n "$cnameExists" ]; then
         echo "DNS is likely NOT pointing to the correct shard or there's a validation issue with the certificate or" \
           "protocols, see curl output below and optionally SSL Labs ($sslLabsUrl):"
         echo ""
         echo "$horizontalRule"
         echo "$curlResult" | sed 's/^/    /g'
         echo "$horizontalRule"
         echo ""
       else
         echo "the required DNS CNAME record is missing, see above"
       fi
     fi
   
     if [ "$shardsFoundCount" -ge "$edgeCount" ]; then
       echo -n "$success $hostname passes shard validation for the following $shardsFoundCount edge shards:"
       echo -e "$shardsFoundOutput"
       echo
   
       if [ -n "$cnameExists" ] && [ -n "$endToEndTestSucceeded" ]; then
         echo "$horizontalRule"
         echo ""
         echo "  For additional TLS/SSL validation, including detailed browser/client support,"
         echo "  see SSL Labs (click the first IP address if prompted):"
         echo ""
         echo "    $info  $sslLabsUrl"
         echo ""
         echo "  To check DNS propagation around the world, see whatsmydns.net:"
         echo ""
         echo "    $info  DNS A records:     https://whatsmydns.net/#A/$hostname"
         echo "    $info  DNS CNAME record:  https://whatsmydns.net/#CNAME/$hostname"
       fi
     else
       echo -n "$failure $hostname FAILED shard validation -- shards found: $shardsFoundCount," \
         "expected: $edgeCount"
       if bc -l <<< "$(cut -d. -f1,2 <<< "$curlVersion") $curlVersionRequired" 2>/dev/null | grep -q 0; then
         echo -n " -- insufficient curl version installed: $curlVersion, but this script requires curl version" \
           "$curlVersionRequired because it uses the curl --connect-to flag to bypass DNS and directly test" \
           "each Adobe Target edge shards' SNI confirguation for $hostname"
       fi
       if [ -n "$shardsFoundOutput" ]; then
         echo -e ":\n$shardsFoundOutput"
       fi
       echo
     fi
     echo
     echo "$horizontalRule"
     echo
   }
   ```

1. Colar este comando (substituindo `target.example.com` com seu nome de host):

   ```
   adobeTargetCnameValidation target.example.com
   ```

   Se a implementação estiver pronta, você verá a saída como abaixo. A parte importante é que todas as linhas de status de validação mostram `✅` em vez de `🚫`. Cada [!DNL Target] o compartilhamento CNAME de borda deve mostrar `CN=target.example.com`, que corresponde ao nome do host principal no certificado solicitado (nomes de host SAN adicionais no certificado não são impressos nesta saída).

   ```
   $ adobeTargetCnameValidation target.example.com
   
   ==========================================================
   
   Adobe Target CNAME implementation validation for hostname target.example.com:
   ✅ target.example.com passes DNS CNAME validation
   ✅ target.example.com passes TLS and HTTP response validation
   ✅ target.example.com passes shard validation for the following 7 edge shards:
   
   ===== ✅ target.example.com [edge shard: mboxedge31-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge32-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge34-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge35-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge36-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge37-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ===== ✅ target.example.com [edge shard: mboxedge38-alb02.tt.omtrdc.net] =====
   *  expire date: Jul 22 23:59:59 2022 GMT
   *  issuer: C=US; O=DigiCert Inc; CN=DigiCert TLS RSA SHA256 2020 CA1
   *  subject: C=US; ST=California; L=San Jose; O=Adobe Systems Incorporated; CN=target.example.com
   
   ==========================================================
   
     For additional TLS/SSL validation, including detailed browser/client support,
     see SSL Labs (click the first IP address if prompted):
   
       🔎  https://ssllabs.com/ssltest/analyze.html?hideResults=on&latest&d=target.example.com
   
     To check DNS propagation around the world, see whatsmydns.net:
   
       🔎  DNS A records:     https://whatsmydns.net/#A/target.example.com
       🔎  DNS CNAME record:  https://whatsmydns.net/#CNAME/target.example.com
   
   ==========================================================
   ```

   >[!NOTE]
   >
   >Se esse comando de validação falhar na validação de DNS, mas você já tiver feito as alterações de DNS necessárias, talvez seja necessário aguardar a propagação completa das atualizações de DNS. Os registros DNS têm um [TTL (tempo de vida útil)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) que determina o tempo de expiração do cache para as respostas DNS desses registros. Como resultado, talvez seja necessário aguardar pelo menos tanto tempo quanto os TTLs. Você pode usar o `dig target.example.com` comando ou [Caixa de ferramentas do G Suite](https://toolbox.googleapps.com/apps/dig/#CNAME) para pesquisar seus TTLs específicos. Para verificar a propagação de DNS pelo mundo, consulte [whatsmydns.net](https://whatsmydns.net/#CNAME).

### Como usar um link para opção de não participação com CNAME

Se você estiver usando CNAME, o link para opção de não participação deverá conter &quot;client=`clientcode` , por exemplo:
`https://my.cname.domain/optout?client=clientcode`.

Substituir `clientcode` com seu código de cliente, em seguida, adicione o texto ou a imagem a ser vinculada à variável [URL de não participação](https://developer.adobe.com/target/before-implement/privacy/privacy/){target=_blank}.

## Limitações conhecidas

* O modo de QA não é aderente quando você tem CNAME e at.js 1.x porque é baseado em um cookie de terceiros. A solução alternativa é adicionar os parâmetros de visualização a cada URL no qual você navega. O modo de QA é aderente quando você tem CNAME e at.js 2.x.
* Ao usar CNAME, é mais provável que o tamanho do cabeçalho do cookie para [!DNL Target] chamadas aumentam. [!DNL Adobe] A recomenda manter o tamanho do cookie abaixo de 8 KB.
