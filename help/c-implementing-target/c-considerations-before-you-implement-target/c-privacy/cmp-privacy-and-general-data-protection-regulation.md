---
description: Informações sobre o Regulamento geral de proteção de dados da União Europeia (RGPD) e a Lei de privacidade do consumidor da Califórnia (CCPA) e como esses regulamentos afetam sua organização e o Adobe Target.
keywords: rgropr; eu; união europeia; privacidade; perguntas frequentes; perguntas frequentes; california consumer privacy act; ccpa; privacidade; proteção de dados; recusar; recusar; governamental; regulamento
seo-description: Informações sobre o Regulamento geral de proteção de dados da União Europeia (RGPD) e a Lei de privacidade do consumidor da Califórnia (CCPA) e como esses regulamentos afetam sua organização e o Adobe Target.
seo-title: Regulamento geral de proteção de dados (RGPD), California Consumer Privacy Act (CCPA) e Adobe Target
solution: Target
title: Normas de privacidade e proteção de dados
topic: Padrão
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: aa077c92e0b6aaec27429acd9292a5edcf6c60fa

---


# Normas de privacidade e proteção de dados {#privacy-and-general-data-protection-regulation-gdpr}

Informações sobre o Regulamento geral de proteção de dados da União Europeia (RGPD) e a Lei de privacidade do consumidor da Califórnia (CCPA) e como essas regulamentações afetam sua organização e [!DNL Adobe Target].

## Privacy and General Data Protection Regulation (GDPR) overview {#topic_DE567ECB6C944695AEE5073889F1AEA9}

Em 25 de maio de 25 18, o RGPD da União Europeia entrou em vigor. Para obter mais informações sobre o que isso significa para você, consulte [GDPR e seus negócios](https://www.adobe.com/privacy/general-data-protection-regulation.html).

When [!DNL Adobe] is providing software and services to an enterprise, [!DNL Adobe] is acting as a Data Processor for any personal data it processes and stores as part of providing these services. As a Data Processor, [!DNL Adobe] processes personal data in accordance with your company's permission and instructions (for example, as set out in your agreement with [!DNL Adobe]).

As the Data Controller, you determine the personal data that [!DNL Adobe] processes and stores on your behalf. If you use [!DNL Adobe Experience Cloud] solutions, [!DNL Adobe] might host personal data for you, depending on the solutions you use and the information you choose to send to your [!DNL Adobe Experience Cloud] account. Para obter uma lista detalhada de exemplos, consulte [Privacidade na Adobe Experience Cloud](https://www.adobe.com/privacy/marketing-cloud.html#collect).

[!DNL Adobe Experience Cloud] fornecer apis PRONTAS para o RGPD para controladores de dados que permitem concluir as seguintes tarefas:

* Acessar informações do titular de dados armazenadas no [!DNL Target]
* Excluir informações do titular de dados armazenadas no [!DNL Target]

Para obter mais informações, consulte:

* [Site da API do Regulamento Geral sobre a Proteção de Dados da Adobe](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [Documentação do GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## Visão geral de Privacy Consumer Privacy Act (CCPA)

A CCPA (Privacy Consumer Privacy Act) está a partir de 1 de janeiro de 2january 20. Por padrão, a lei dá ao regulador da Califórnia leiautes para fazer ajustes e esclarecer os detalhes, o que significa que você pode fazer muitas perguntas. Se você tiver dúvidas, você não será o único a trabalhar com as incertezas na lei e tentar entender e desenvolver uma abordagem para atender aos requisitos legais, operacionais e técnicos.

A CCPA fornece aos consumidores da Califórnia novos direitos sobre suas informações pessoais e impõe responsabilidades proteção de dados em determinadas entidades que conduzem negócios na Califórnia. Em um nível superior, a lei fornece à Califórnia vários direitos principais, incluindo direitos para:

* Solicitação de informações (acesso a dados)
* Recusar a venda de informações pessoais (um direito definido amplamente amplamente para recusar o compartilhamento de informações com terceiros)
* Ter informações pessoais excluídas
* Seja informado de que as informações pessoais estão sendo divulgadas ou vendidas

Se estiver ocupado para a lei de privacidade da Europa (RGPD) no ano passado, alguns desses direitos podem ser familiares e muito do trabalho que você realizou pode ser redefinido.

## Adobe Target and [!DNL Experience Platform Launch] opt-in {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] fornece suporte à funcionalidade de aceitação por meio [!DNL Launch] do suporte à estratégia de gerenciamento de consentimento. Opt-in functionality lets customers control how and when the [!DNL Target] tag is fired. There is also an option via [!DNL Launch] to pre-approve the [!DNL Target] tag. To enable the ability to use Opt-In in the [!DNL Target] at.js library, you should use `targetGlobalSettings` and add the `optinEnabled=true` setting. In [!DNL Launch] you'll need to select "enable" from the [!UICONTROL GDPR Opt-In] drop-down list in the [!DNL Launch] extension installation view. Consulte a documentação do [Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) para obter mais detalhes.

O trecho de código a seguir mostra como ativar a configuração `optinEnabled=true`:

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>A funcionalidade de aceitação é compatível com o at. js versão 1.7.0 e o at. js 2.1.0 ou posterior. Não há suporte para o at. js versão 2.0.0 e 2.0.1.
>
>Using [!DNL Experience Platform Launch] to manage opt-in is the recommended approach. Further granular control exists in [!DNL Launch] to hide selected elements of your page prior to [!DNL Target] firing that are helpful to leverage as part of your consent strategy.

Há três cenários a serem considerados ao usar a inclusão:

1. **A[!DNL Target]tag é aprovada previamente por ([!DNL Launch]ou o assunto de dados aprovado[!DNL Target]anteriormente):** [!DNL Target] A tag não é mantida para consentimento e funções conforme esperado.
1. **[!DNL Target]A tag do NÃO é pré-aprovada e`bodyHidingEnabled`é FALSE:** A tag do é acionada somente após o consentimento ser coletado do cliente. [!DNL Target] Antes de o consentimento ser coletado, apenas o conteúdo padrão está disponível. After consent is received, [!DNL Target] is called and personalized content is available to the data subject (visitor). Como apenas o conteúdo padrão está disponível antes do consentimento, é importante utilizar uma estratégia apropriada, como uma página inicial que cubra qualquer parte da página ou conteúdo que possa ser personalizado. Isso garante que a experiência permaneça consistente para o titular dos dados (visitante).
1. **[!DNL Target]A tag do NÃO é pré-aprovada e`bodyHidingEnabled`é TRUE:** A tag do é acionada somente após o consentimento ser coletado do cliente. [!DNL Target] Antes de o consentimento ser coletado, apenas o conteúdo padrão está disponível. No entanto, como `bodyHidingEnabled` é definido para verdadeiro, `bodyHiddenStyle` determina qual conteúdo na página fica oculto até que a tag do seja acionada (ou o titular dos dados recuse a inclusão, sendo que nesse caso o conteúdo padrão é exibido). [!DNL Target] Por padrão, `bodyHiddenStyle` está configurado como `body { opacity:0;`}, o que oculta a tag do corpo HTML. Nossa configuração de página recomendada é apresentada abaixo para que todo o corpo da página, além da caixa de diálogo do gerenciador de consentimento, fique oculto, colocando o conteúdo da página em um contêiner e o diálogo do gerenciador de consentimento em um contêiner separado. This setup configures [!DNL Target] so that it hides the page content container only. Consulte a [documentação do Launch para obter mais informações sobre como definir essas configurações](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html).

   A configuração de página recomendada para o cenário 3 é:

   ```
   <html> 
   <head> 
   //visitor, at.js 
   </head> 
   
   <body> 
   <div id = "consentManagerDialog"> 
   
   //consent manager html dialog goes here 
   </div> 
   
   <div id="pageContent"> 
   // page content goes here 
   </div> 
   
   </body> 
   </html> 
   ```

   Considerando o `bodyHiddenStyle` de:

   ```
   #pageContent { opacity:0;}
   ```

## Perguntas frequentes sobre privacidade e proteção de dados {#concept_41F88DE95D2943178BEC382736B5C038}

Perguntas frequentes sobre o Regulamento geral de Proteção de dados (RGPD) e da Califórnia Consumer Privacy Act (CCPA) para [!DNL Target].

### Qual é a política da Adobe para esses regulamentos? {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe]A já atende às obrigações como um Processador de dados ou está fazendo implementações de acordo. Temos uma forte base de controles de segurança e privacidade certificados por design e fizemos melhorias de produtos antes do prazo de May 018 de maio. Clientes empresariais terão a responsabilidade de implementar essas melhorias, além de atualizar quaisquer políticas e procedimentos necessários.

### Will my company, the Data Controller, need to submit a GDPR or CCPA request to each [!DNL Adobe Experience Cloud] solution that it uses? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

No, [!DNL Adobe] is providing a central way to help Data Controllers meet their GDPR and CCPA requirements. Os Controladores de dados não precisarão acessar diretamente cada solução.

All GDPR and CCPA requests across [!DNL Experience Cloud] solutions, including [!DNL Target], will be made through a central Adobe API, currently called the GDPR API. The API will then complete the request across the Data Controller's [!DNL Experience Cloud] solution suite.

### What information will [!DNL Adobe] enable our customers to delete in response to a data subject/user request? {#section_4B51D00924EC4166B2442218B69214F0}

The information related to an individual visitor within [!DNL Target] is contained within the [!DNL Target] Visitor Profile. [!DNL Target]O permitirá que nossos clientes excluam todos os dados associados a uma ID em seus respectivos Perfis do visitante. Para obter exemplos dos armazenamentos de dados [!DNL Target] de perfil, consulte [Perfil do visitante](../../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

Dados agregados ou anônimos (por exemplo, dados de relatórios) não usados para identificar um certo indivíduo, ou dados não relevantes a um indivíduo específico (por exemplo, dados de conteúdo), não estão no escopo de uma solicitação de exclusão de usuário.

[!DNL Target]Por padrão, os perfis do visitante do que ficaram inativos por 90 dias são excluídos, sem nenhuma ação necessária.

### What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for [!DNL Target]? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target]O é compatível com os seguintes tipos de ID para localizar um perfil de cliente:

| ID de usuário | Tipo de ID de namespace | ID de namespace | Definição |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Padrão | 4 | Adobe Experience Cloud ID, anteriormente conhecida como ID de visitante ou Marketing Cloud ID. É possível usar a API do JavaScript para localizar esta ID (veja os detalhes abaixo). |
| ID de TnT / ID de cookie(TNTID) | Padrão | 9 | Identificador do Target definido como cookie no navegador do visitante. É possível usar a API do JavaScript para localizar esta ID (veja os detalhes abaixo). |
| ID de terceiros / ID de CRM (THIRDPARTYID) | Específico do Target | N/A | Se você fornecer seu CRM ao Target ou qualquer outra informação de identificador exclusivo referente a seus clientes. |

>[!NOTE]
>
>Although [!DNL Target] supports both first-party and third-party cross-domain cookies, first-party [!DNL Target] cookies only are recommended for GDPR and CCPA.

### How does [!DNL Target] handle consent management? {#section_C86BF5EE4FAA47039659850E7594A6BA}

O RGPD e a CCPA não mudam quando você precisa obter o consentimento, mas como obtê-lo. A estratégia de consentimento de cada cliente depende de sua coleta de dados e práticas de uso, bem como da política de privacidade. Consent management isn’t supported by and shouldn’t be achieved via [!DNL Target] for GDPR and CCPA.

[!DNL Adobe]No momento, a não oferece uma solução de Administração de consentimento, mas há várias ferramentas em desenvolvimento no mercado para atender a alguns dos novos requisitos. For more information on privacy tools in general, including consent managers, see the [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) on the *International Association of Privacy Professionals (iaap)* website.

[!DNL Target] fornece suporte à funcionalidade de aceitação para [!DNL Launch] fornecer suporte à estratégia de gerenciamento de consentimento. Opt-in functionality lets customers control how and when the [!DNL Target] tag is fired. There is also an option via [!DNL Launch] to pre-approve the [!DNL Target] tag. Using [!DNL Launch] to manage opt-in is the recommended approach. Further granular control exists in [!DNL Launch] to hide select elements of your page prior to the [!DNL Target] firing that might be helpful to leverage as part of your consent strategy.

For more information on GDPR, CCPA, and [!DNL Launch], see [The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). Also, see the *Adobe Target and Experience Platform Launch opt-in* section above.

### O AdobePrivacy.js envia informações para a API do GDPR? {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] *não* envia essas informações para a API. Isso deve ser feito pelo cliente. Esta biblioteca fornece apenas as IDs armazenadas no navegador para esse visitante específico.

### O que é removido por removeIdentities? {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities]O *remove somente*[!DNL Adobe] essas identidades do navegador, e depende apenas se a solução da implementou isso.

For example, [!DNL Target] deletes the cookies storing its IDs, but [!DNL Adobe Audience Manager] (AAM) does not delete the demdex ID that is stored in a third-party cookie.

### What information needs to be included in a Target GDPR or CCPA request? {#section_D29A4744AE6344E68AD7710B185FD6D0}

In addition to the requirements from Central Privacy Service, a valid GDPR or CCPA message for [!DNL Target] contains:

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            "namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            "namespace":"TNTID", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"THIRDPARTYID", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
}
```

### Que tipos de respostas posso esperar do Target por meio da API do GDPR? {#section_F67263D2A72B4641A47CE36729CCAE8F}

| Status da solicitação | Mensagem de resposta do Target | Cenário |
|--- |--- |--- |
| Processando | Processando | O Target recebeu a solicitação do RGPD ou CCPA e está processando. |
| Concluído | Não aplicável - o contexto da empresa não é aplicável | A ID IMS na solicitação RGPD ou CCPA não é mapeada para qualquer cliente do Target.<br>Observe que algumas empresas têm várias IDs de IMS. Você deve enviar a ID de IMS na qual o Target é provisionado. |
| Concluído | Não aplicável - contexto do usuário não encontrado | A ID fornecida na solicitação RGPD ou CCPA para o visitante específico ou o assunto de dados não está presente na loja de perfil do Target.<br>Observe que esse resultado também será retornado se você tentar enviar um tipo de ID de namespace que não seja suportado pelo Target (veja acima as IDs suportadas). |
| Erro | Mensagem de erro (os detalhes dependem do tipo de erro) | Erro ao buscar ou excluir o perfil do titular de dados solicitado.<br>Erro ao fazer upload no Azure para a solicitação de acesso. |

### Que resposta é enviada pelo Target à API do GDPR para uma solicitação de acesso? {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Responses to access data requests contain a summary of the [!DNL Target] profile for the visitor in question. Note that this return is sent to the [!DNL Experience Cloud] GDPR API, which in turn sends Data Controllers a response.

A sample [!DNL Target] access API response could look like this:

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            ~"namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            ~"namespace":"tntId", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"thirdPartyId", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
} 
```

| Campo | Descrição |
|--- |--- |
| jobId | Indica a ID do trabalho RGPD ou CCPA da API central do RGPD. |
| imsOrgID | Oferece um identificador exclusivo para sua empresa. |
| namespace | Também conhecido como fonte de dados. Consulte "Quais IDs têm suporte para ajudar os clientes a concluir uma solicitação de acesso e exclusão RGPCCPA e a solicitação de exclusão do Target?" neste tópico. |
| type | O tipo de ID para o qual você solicitou o acesso aos dados do RGPD ou CCPA. O Target aceita diversos tipos de ID, alguns são padrão e outros são específicos ao Target. Consulte "Quais IDs têm suporte para ajudar os clientes a concluir uma solicitação de acesso e exclusão RGPCCPA e a solicitação de exclusão do Target?" neste tópico. |
| value | A ID do namespace/fonte de dados. Consulte "Quais IDs têm suporte para ajudar os clientes a concluir uma solicitação de acesso e exclusão RGPCCPA e a solicitação de exclusão do Target?" para saber mais sobre os valores aceitos. |
| código de integração | Códigos de integração são nomes amigáveis para suas fontes de dados e ajudam a monitorar suas fontes de dados de maneira mais fácil do que seria com IDs de fontes de dados. |

Quando diversos valores são fornecidos para identificar os perfis, cada identificador válido terá um arquivo de perfil. The profile file(s) are sent to the central GDPR Azure Blob through the GDPR Central API, in the format of [!DNL Target] Profile JSON response.

A sample [!DNL Target] Profile JSON could look like the following example:

```
{"profileAttributes": 
 
"Sample_Parameter":{"value":"Gold Loyalty Status","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"user.ReturnTimeOfDay":{"value":"44.0","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"firstSessionStart":{"value":"1523497450602","modifiedAt":"2018-04-11T21:44:10.000-04:00"}, 
 
"user.sessionCountScript":{"value":"1","modifiedAt":"2018-04-11T21:44:14.000-04:00"} 
   } 
} 
```

A seguinte tabela apresenta descrições dos campos ilustrativos de JSON de perfil:

| Campo | Descrição |
|--- |--- |
| Sample_Parameter | Many pieces of information in the [!DNL Target] profile are uploaded or directly provided by the Data Controller. In this example, a parameter was uploaded into the [!DNL Target] profile using the Profile Update API. Para obter mais informações, consulte [Métodos para obter dados no Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md). |
| user.ReturnTimeOfDay | Este campo padrão inclui o horário da visita de retorno mais recente de um usuário. |
| firstSessionStart | Este campo padrão inclui o horário de início da primeira sessão do usuário. |
| user.sessionCountScript | Many pieces of information in the [!DNL Target] profile are uploaded or directly provided by the Data Controller. Neste exemplo, um script de perfil está incrementando o número de sessões que este visitante fez ao site do Controlador de dados. Para obter mais informações, consulte [Atributos de script de perfil](/help/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>This is a shortened version of a [!DNL Target] profile JSON for the purpose of illustration. Many of the fields of the [!DNL Target] profile are not standard. O que é retornado depende de quais informações estão nesse perfil do visitante específico.

## O Target suporta ofuscação de IP? {#section_428907B0CD9842D9B245B38C66A53C6A}

[!DNL Target] suporta ofuscação de IP se optar por usá-la como parte da estratégia de implementação do RGPD ou CCPA. Para obter mais informações, consulte [Privacidade](../../../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).
