---
keywords: atendimento ao cliente; cname; programa de certificado; nome canônico; cookies; certificado; amc; certificado gerenciado da adobe; digicert; validação de controle de domínio; dcv
description: Trabalhe com o Adobe Client Care para implementar o suporte CNAME (Canonical Name) no Adobe [!DNL Target] para lidar com problemas de bloqueio de anúncios ou políticas de cookies relacionadas à ITP.
title: Como uso o CNAME no Target?
feature: Privacidade e segurança
role: Developer
exl-id: bf533771-6d46-48ba-964c-3ad9ce9f7352
source-git-commit: 0327f4450ad7b764b01091a106e3dfd3160ffbaf
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 2%

---

# CNAME e Adobe Target

Instruções para trabalhar com o [!DNL Adobe] Client Care para implementar o suporte CNAME (Canonical Name) em [!DNL Adobe Target]. Use o CNAME para lidar com problemas de bloqueio de anúncios ou políticas de cookies relacionadas à ITP (Intelligent Tracking Prevention). Com o CNAME, as chamadas são feitas para um domínio pertencente ao cliente, em vez de um domínio pertencente a [!DNL Adobe].

## Solicitar suporte CNAME no Target

1. Determine a lista de nomes de host necessários para seu certificado SSL (consulte as Perguntas frequentes abaixo).

1. Para cada nome de host, crie um registro CNAME no DNS apontando para seu nome de host [!DNL Target] comum `clientcode.tt.omtrdc.net`.

   Por exemplo, se o código de cliente for &quot;namecustomer&quot; e o nome de host proposto for `target.example.com`, o registro CNAME de DNS será semelhante a:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!IMPORTANT]
   >
   >Certificado até que a Digi esteja concluída. Portanto, [!DNL Adobe] não pode atender à solicitação de uma implementação CNAME até que essa etapa seja concluída.

1. [Preencha este ](/help/assets/FPC_Request_Form.xlsx) formulário e inclua-o ao  [abrir um tíquete de Atendimento ao cliente do Adobe solicitando o suporte](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) CNAME:

   * Código de cliente Adobe [!DNL Target]:
   * Nomes de host do certificado SSL (por exemplo: `target.example.com target.example.org`):
   * Comprador de certificado SSL (o Adobe é altamente recomendado, consulte as Perguntas frequentes): Adobe/cliente
   * Se o cliente estiver comprando o certificado, também conhecido como &quot;Traga seu próprio certificado&quot; (BYOC), preencha estes detalhes adicionais:
      * Organização de certificado (exemplo: Exemplo Empresa Inc):
      * Unidade organizacional do certificado (opcional, por exemplo: Marketing):
      * País do certificado (exemplo: EUA):
      * Estado/região do certificado (exemplo: Califórnia):
      * Cidade do certificado (exemplo: San Jose):

1. Se [!DNL Adobe] estiver comprando o certificado, [!DNL Adobe] funcionará com a DigiCert para comprar e implantar seu certificado nos servidores de produção Adobe.

   Se o cliente estiver comprando o certificado (BYOC), [!DNL Adobe] o Atendimento ao Cliente enviará a solicitação de assinatura de certificado (CSR). Use o CSR ao adquirir o certificado por meio da autoridade de certificação escolhida. Depois que o certificado for emitido, envie uma cópia do certificado e quaisquer certificados intermediários para o [!DNL Adobe] Atendimento ao cliente para implantação.

   [!DNL Adobe] O Atendimento ao cliente notifica quando sua implementação está pronta.

1. Atualize o `serverDomain` para o novo CNAME no at.js.

## Perguntas frequentes

As informações a seguir respondem a perguntas frequentes sobre a solicitação e a implementação do suporte CNAME em [!DNL Target]:

### Posso fornecer meu próprio certificado (Traga seu próprio certificado ou BYOC)?

Você pode fornecer seu próprio certificado. No entanto, [!DNL Adobe] não recomenda essa prática. O gerenciamento do ciclo de vida do certificado SSL é mais fácil para [!DNL Adobe] e você se [!DNL Adobe] comprar e controlar o certificado. Os certificados SSL devem ser renovados todos os anos. Portanto, [!DNL Adobe] o Atendimento ao cliente deve entrar em contato com você todos os anos para obter um novo certificado em tempo hábil. Alguns clientes podem ter dificuldade em produzir um certificado renovado em tempo hábil. Sua implementação [!DNL Target] fica comprometida quando o certificado expira porque os navegadores recusam as conexões.

>[!IMPORTANT]
>
>Se solicitar uma implementação [!DNL Target] de certificado próprio CNAME, você será responsável por fornecer certificados renovados ao [!DNL Adobe] Atendimento ao cliente a cada ano. Permitir que seu certificado CNAME expire antes de [!DNL Adobe] possa implantar um certificado renovado resulta em uma interrupção para sua implementação [!DNL Target] específica.

### Por quanto tempo até que meu novo certificado SSL expire?

Os certificados emitidos antes de 1º de setembro de 2020 são certificados de dois anos. Os certificados emitidos a partir de 1 de setembro de 2020 são certificados de um ano. Você pode ler mais sobre a mudança para certificados de um ano [aqui](https://www.digicert.com/position-on-1-year-certificates).

### Quais nomes de host devo escolher? Quantos nomes de host por domínio devo escolher?

[!DNL Target] As implementações CNAME exigem apenas um nome de host por domínio no certificado SSL e no DNS do cliente. O Adobe recomenda um nome de host. Alguns clientes exigem mais nomes de host por domínio para seus próprios fins (teste em preparo, por exemplo), o que é compatível.

A maioria dos clientes escolhe um nome de host como `target.example.com`. A Adobe recomenda seguir essa prática, mas a escolha é, em última análise, sua. Não solicite um nome de host de um registro DNS existente. Isso causa um conflito e atrasa o tempo para a resolução da solicitação CNAME [!DNL Target].

### Já tenho uma implementação CNAME para [!DNL Adobe Analytics], podemos usar o mesmo certificado ou nome de host?

Não, [!DNL Target] requer um nome de host e certificado separados.

### Minha implementação atual de [!DNL Target] é afetada pela ITP 2.x?

Em um navegador do Safari, navegue até o site em que você tem uma biblioteca JavaScript [!DNL Target]. Se você vir um cookie [!DNL Target] definido no contexto de um CNAME, como `analytics.company.com`, você não é afetado pela ITP 2.x.

Os problemas de ITP podem ser resolvidos para [!DNL Target] com apenas um [!DNL Analytics] CNAME. Você precisa de um [!DNL Target] CNAME separado somente em cenários de bloqueio de anúncios em que [!DNL Target] esteja bloqueado.

Para obter mais informações sobre ITP, consulte [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### Que tipo de interrupções de serviço posso esperar quando minha implementação CNAME é implantada?

Não há interrupção de serviço quando o certificado é implantado (incluindo renovações de certificado).

No entanto, depois de alterar o nome do host em seu código de implementação [!DNL Target] (`serverDomain` em at.js) para o novo nome do host CNAME (`target.example.com`), os navegadores da Web tratam os visitantes recorrentes como novos visitantes. O retorno dos dados de perfil dos visitantes é perdido porque o cookie anterior está inacessível com o nome de host antigo (`clientcode.tt.omtrdc.net`). O cookie anterior está inacessível devido a modelos de segurança do navegador. Essa interrupção ocorre somente no corte inicial para o novo CNAME. As renovações de certificado não têm o mesmo efeito porque o nome de host não é alterado.

### Qual tipo de chave e algoritmo de assinatura de certificado é usado para minha implementação CNAME?

Todos os certificados são RSA SHA-256 e as chaves são RSA 2048 bits, por padrão. No momento, não há suporte para tamanhos de chave maiores que 2048 bits.

### Como posso validar se minha implementação CNAME está pronta para o tráfego?

Use o seguinte conjunto de comandos (no terminal de linha de comando macOS ou Linux, usando bash e curl 7.49+):

1. Cole esta função bash no terminal:

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

   Se a implementação estiver pronta, você verá a saída como abaixo. A parte importante é que todas as linhas incluem `CN=target.example.com`, que corresponde ao nome de host desejado. Se alguma linha incluir `CN=*.tt.omtrdc.net`, a implementação está **não** pronta.

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

1. Valide seu novo CNAME DNS com outra solicitação curl, que também deve mostrar `CN=target.example.com`:

   ```
   curl -sSv https://target.example.com 2>&1 | grep subject:
   ```

   >[!NOTE]
   >
   >Se esse comando falhar, mas o comando `validateEdgeFpsslSni` acima for bem-sucedido, aguarde até que as atualizações de DNS se propaguem totalmente. Os registros DNS têm um [TTL (time-to-live)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) associado que determina o tempo de expiração do cache para as respostas DNS desses registros. Como resultado, talvez seja necessário aguardar pelo menos tanto tempo quanto os TTLs. Você pode usar o comando `dig target.example.com` ou [a caixa de ferramentas do G Suite](https://toolbox.googleapps.com/apps/dig/#CNAME) para procurar seus TTLs específicos.

### Como usar um link para opção de não participação com CNAME

Se você estiver usando CNAME, o link para opção de não participação deverá conter o parâmetro &quot;client=`clientcode` , por exemplo:
`https://my.cname.domain/optout?client=clientcode`.

Substitua `clientcode` pelo código de cliente e adicione o texto ou imagem a ser vinculado ao [URL de não participação](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#reference_E7A62B7B99C94B3A806CB262D16E27FC).

## Limitações conhecidas

* O modo de QA não é aderente quando você tem CNAME e at.js 1.x porque é baseado em um cookie de terceiros. A solução alternativa é adicionar os parâmetros de visualização a cada URL no qual você navega. O modo de QA é aderente quando você tem CNAME e at.js 2.x.
* Atualmente, a configuração `overrideMboxEdgeServer` não funciona corretamente com CNAME ao usar versões da at.js anteriores à at.js 1.8.2 e à at.js 2.3.1. Se estiver usando uma versão mais antiga da at.js, essa configuração deve ser definida como `false` para evitar solicitações com falha. Como alternativa, considere [atualizar a at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) para uma versão mais recente e compatível.
* Ao usar CNAME, é mais provável que o tamanho do cabeçalho do cookie para chamadas [!DNL Target] aumente. [!DNL Adobe] A recomenda manter o tamanho do cookie abaixo de 8 KB.
