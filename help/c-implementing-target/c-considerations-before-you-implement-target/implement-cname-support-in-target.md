---
keywords: client care;cname;certificate programa;canonical name;cookies;certificate;amc;adobe managed certificate;digicert;domain control validation;dcv
description: Trabalhe com o Adobe Client Care para implementar o suporte CNAME (Nome Canônico) no Adobe Target para lidar com problemas de bloqueio de anúncios ou políticas de cookies relacionadas ao ITP.
title: Como uso o CNAME no Público alvo?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 1%

---


# CNAME e Adobe Target

Instruções para trabalhar com o Adobe Client Care para implementar o suporte a CNAME (Nome Canônico) em [!DNL Adobe Target]. Para melhor lidar com problemas de bloqueio de anúncios, ou políticas de cookies relacionadas ao ITP, um CNAME é usado, portanto, as chamadas são feitas para um domínio pertencente ao cliente em vez de um domínio pertencente ao Adobe.

## Solicitar suporte CNAME

Execute as etapas a seguir para solicitar o suporte CNAME no [!DNL Target]:

1. Determine a lista de nomes de host necessários para seu certificado SSL (consulte as Perguntas frequentes).

1. Para cada nome de host, crie um registro CNAME em seu DNS apontando para seu nome de host regular [!DNL Target] `clientcode.tt.omtrdc.net`.

   Por exemplo, se seu código de cliente for &quot;cnamecustomer&quot; e seu nome de host proposto for `target.example.com`, seu registro CNAME de DNS deverá ser semelhante a:

   ```
   target.example.com.  IN  CNAME  cnamecustomer.tt.omtrdc.net.
   ```

   >[!NOTE]
   >
   >Certificado até que a DigiCert não emita uma etapa seja concluída. Portanto, o Adobe não pode atender à solicitação de uma implementação CNAME até que essa etapa seja concluída.

1. [Preencha este ](https://experienceleague.adobe.com/docs/core-services/assets/FPC_Request_Form.xlsx?lang=en) formulário e inclua-o ao  [abrir um ticket do Atendimento ao cliente do Adobe solicitando suporte](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) CNAME:

   * Adobe [!DNL Target] código do cliente:
   * Nomes de host de certificado SSL (por exemplo: `target.example.com target.example.org`):
   * Comprador de certificados SSL (o Adobe é altamente recomendado, consulte as Perguntas frequentes): Adobe/cliente
   * Se o cliente estiver comprando o certificado (conhecido como BYOC), preencha estes detalhes adicionais:
      * Organização do certificado (por exemplo: Exemplo de Empresa Inc):
      * Unidade organizacional do certificado (opcional, por exemplo: Comercialização):
      * País do certificado (por exemplo: EUA):
      * Estado/região do certificado (exemplo: Califórnia):
      * Cidade do certificado (por exemplo: San Jose):

1. Se a Adobe comprar o certificado, a Adobe trabalhará com a DigiCert para comprar e implantar seu certificado nos servidores de produção Adobe.

   Se o cliente comprar o certificado (BYOC), o Adobe Client Care enviará a você a solicitação de assinatura de certificado (CSR), que você precisará usar ao adquirir o certificado por meio da autoridade de certificação de sua escolha. Depois que o certificado for emitido, você deverá enviar uma cópia do certificado e quaisquer certificados intermediários de volta ao Adobe Client Care para implantação.

   O Atendimento ao cliente Adobe notificará você quando sua implementação estiver pronta.

1. Depois de concluir o tarefa e o Adobe Client Care anterior ter notificado que a implementação está pronta, você deve atualizar o `serverDomain` para o novo CNAME em at.js.

## Perguntas frequentes

As informações a seguir respondem a perguntas frequentes sobre como solicitar e implementar o suporte CNAME em [!DNL Target]:

### Posso fornecer meu próprio certificado (também conhecido como trazer seu próprio certificado ou BYOC)?

Sim, você pode fornecer seu próprio certificado; no entanto, não é recomendado. O gerenciamento do ciclo de vida do certificado SSL é significativamente mais fácil para o Adobe e para você quando o Adobe compra e controla o certificado. Os certificados SSL devem ser renovados todos os anos, o que significa que o Adobe Client Care deve entrar em contato com você todos os anos para enviar ao Adobe um novo certificado em tempo hábil. Alguns clientes podem ter dificuldade em produzir um certificado renovado em tempo hábil a cada ano, o que compromete sua implementação [!DNL Target], pois os navegadores recusarão conexões quando o certificado expirar.

>[!IMPORTANT]
>
>Esteja ciente de que, se você solicitar uma implementação CNAME [!DNL Target] do seu próprio certificado, você será responsável por fornecer certificados renovados ao Atendimento ao cliente da Adobe todos os anos. Permitir que seu certificado CNAME expire antes que o Adobe possa implantar um certificado renovado resultará em uma interrupção para sua implementação específica de [!DNL Target].

### Quanto tempo até que meu novo certificado SSL expire?

Os certificados emitidos antes de 1º de setembro de 2020 serão certificados de dois anos. Os certificados emitidos a partir de 1º de setembro de 2020 serão de um ano. Você pode ler mais sobre a mudança para certificados de um ano [aqui](https://www.digicert.com/position-on-1-year-certificates).

### Quais nomes de host devo escolher? Quantos nomes de host por domínio devo escolher?

[!DNL Target] As implementações CNAME exigem apenas um nome de host por domínio no certificado SSL e no DNS do cliente, portanto, é isso que recomendamos. Alguns clientes podem exigir nomes de host adicionais por domínio para seus próprios fins (teste em armazenamento temporário, por exemplo), o que é suportado.

A maioria dos clientes escolhe um nome de host como `target.example.com`, portanto, é isso que recomendamos, mas a escolha é, em última análise, sua. Certifique-se de não solicitar um nome de host de um registro DNS existente, pois isso causaria um conflito e atrasaria o tempo para a resolução da solicitação CNAME de [!DNL Target].

### Já tenho uma implementação CNAME para [!DNL Adobe Analytics], podemos usar o mesmo certificado ou nome do host?

Não, [!DNL Target] requer um nome de host e um certificado separados.

### Minha implementação atual do Público alvo é afetada pelo ITP 2.x?

Em um navegador Safari, navegue até seu site no qual você tem uma biblioteca JavaScript de Públicos alvos. Se você vir um cookie de Público alvo definido no contexto de um CNAME, como `analytics.company.com`, você não será afetado pelo ITP 2.x.

Os problemas de ITP podem ser resolvidos para Público alvo com apenas um CNAME do Analytics. Você precisará de um Público alvo separado CNAME somente no caso de cenários de bloqueio de anúncios em que o Público alvo estiver bloqueado.

Para obter mais informações sobre o ITP, consulte [Apple Intelligent Tracking Prevention (ITP) 2.x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md).

### Que tipo de interrupções de serviço posso esperar quando minha implementação CNAME é implantada?

Não há interrupção de serviço quando o certificado é implantado (incluindo renovações de certificados). No entanto, quando você altera o nome do host em seu [!DNL Target] código de implementação (`serverDomain` em at.js) para o novo nome do host CNAME (`target.example.com`), os navegadores da Web tratarão os visitantes recorrentes como novos visitantes e seus dados de perfil serão perdidos porque o cookie anterior estará inacessível sob o nome do host antigo (`clientcode.tt.omtrdc.net`) devido aos modelos de segurança do navegador. Esta é uma interrupção única somente no recorte inicial do novo CNAME. As renovações de certificados não têm o mesmo efeito, pois o nome do host não é alterado.

### Que tipo de chave e algoritmo de assinatura de certificado serão usados para minha implementação CNAME?

Todos os certificados são RSA SHA-256 e as chaves são RSA 2048-bit, por padrão. Os tamanhos de chave maiores que 2048 bits não são suportados no momento.

### Como posso validar se minha implementação CNAME está pronta para o tráfego?

Use o seguinte conjunto de comandos (no terminal de linha de comando do MacOs ou do Linux, usando bash e curl 7.49+):

1. Primeiro cole esta função bash no seu terminal:

   ```
   function validateEdgeFpsslSni {
       domain=$1
       for edge in mboxedge{31,32,{34..38}}.tt.omtrdc.net; do
           echo "$edge: $(curl -sSv --connect-to $domain:443:$edge:443 https://$domain 2>&1 | grep subject:)"
       done
   }
   ```

1. Em seguida, cole este comando (substituindo `target.example.com` pelo seu nome de host):

   ```
   validateEdgeFpsslSni target.example.com
   ```

   Se a implementação estiver pronta, você deverá ver a saída como abaixo. A parte importante é que todas as linhas mostram `CN=target.example.com`, que corresponde ao nome do host desejado. Se algum deles mostrar `CN=*.tt.omtrdc.net`, a implementação está **não** pronta.

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
   >Se esse comando falhar, mas o comando `validateEdgeFpsslSni` acima for bem-sucedido, talvez seja necessário aguardar a propagação completa das atualizações de DNS. Os registros de DNS têm um [TTL (time-to-live)](https://en.wikipedia.org/wiki/Time_to_live#DNS_records) associado que determina o tempo de expiração do cache para as respostas de DNS desses registros, portanto, talvez seja necessário aguardar pelo menos tanto tempo quanto os TTLs. Você pode usar o comando `dig target.example.com` ou [a G Suite Toolbox](https://toolbox.googleapps.com/apps/dig/#CNAME) para procurar seus TTLs específicos.

## Limitações conhecidas

* O modo de QA não ficará fixo quando você tiver CNAME e at.js 1.x porque ele é baseado em um cookie de terceiros. A solução alternativa é adicionar os parâmetros de pré-visualização a cada URL para o qual você navega. O modo de QA é fixo quando você tem CNAME e at.js 2.x.
* Atualmente, a configuração `overrideMboxEdgeServer` não funciona corretamente com CNAME ao usar versões do at.js anteriores ao at.js 1.8.2 e ao at.js 2.3.1. Se você estiver usando uma versão mais antiga do at.js, isso deve ser definido como `false` para evitar solicitações com falha. Como alternativa, você deve considerar [atualizar o at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) para uma versão mais recente e compatível.
* Ao usar CNAME, é mais provável que o tamanho do cabeçalho do cookie para chamadas de Público alvo aumente. Recomendamos manter o tamanho do cookie abaixo de 8 KB.
