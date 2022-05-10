---
keywords: gdpr; ue; união europeia; privacidade; perguntas frequentes; perguntas frequentes; california consumer privacy act; ccpa; privacidade; proteção de dados; opt-out; recusar; governamental; regulamento
description: Saiba mais sobre [!DNL Target] e o Regulamento Geral sobre a Proteção de Dados da União Europeia (GDPR), a California Consumer Privacy Act (CCPA) e outros requisitos de privacidade.
title: Como [!DNL Target] Lidar com privacidade e regulamentos de proteção de dados?
feature: Privacy & Security
role: Developer
exl-id: 5013a9d2-a463-4787-90ee-3248d9cb02b2
source-git-commit: 2dad7d51935cd1550f60218e63277b84ce9088ac
workflow-type: tm+mt
source-wordcount: '2209'
ht-degree: 57%

---

# Privacidade e regulamentos sobre proteção de dados

Informações sobre o Regulamento Geral sobre a Proteção de Dados (GDPR) da União Europeia, a California Consumer Privacy Act (CCPA) e outros requisitos de privacidade internacionais. Saiba como esses regulamentos afetam sua organização e [!DNL Adobe Target].

## Visão geral de Privacidade e Regulamento Geral sobre a Proteção de Dados (GDPR)  {#topic_DE567ECB6C944695AEE5073889F1AEA9}

O GDPR da União Europeia entra em vigor em 25 de maio de 2018. Para mais informações sobre o significado deste regulamento para si, consulte [GDPR e seu negócio](https://business.adobe.com/privacy/general-data-protection-regulation.html).

Quando a [!DNL Adobe] oferece software e serviços para uma empresa, a [!DNL Adobe] age como um Processador de dados de quaisquer dados pessoais que processa e armazena como parte do oferecimento desses serviços. Como Processador de dados, a [!DNL Adobe] processa dados pessoais de acordo com a permissão e as instruções de sua empresa (por exemplo, como definido em seu contrato com a [!DNL Adobe]).

Como o Controlador de dados, você determinará os dados pessoais que a [!DNL Adobe] processa e armazena em seu nome. Se você usa as soluções da [!DNL Adobe Experience Cloud], a [!DNL Adobe] pode hospedar dados pessoais, dependendo das soluções usadas e das informações que você escolher enviar para a sua conta da [!DNL Adobe Experience Cloud]. Para obter uma lista detalhada de exemplos, consulte [Privacidade na Adobe Experience Cloud](https://www.adobe.com/privacy/experience-cloud.html#collect).

[!DNL Adobe Experience Cloud] O fornece APIs prontas para GDPR para Controladores de dados que permitem realizar as seguintes tarefas:

* Acessar informações do titular de dados armazenadas no [!DNL Target]
* Excluir informações do titular de dados armazenadas no [!DNL Target]

Para obter mais informações, consulte:

* [Visão geral do Privacy Service Adobe](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target=-blank}
* [Guia da API do Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target=_blank}
* [Visão geral da interface do usuário do Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target=_blank}

## Visão geral da California Consumer Privacy Act (CCPA)

A lei California Consumer Privacy Act (CCPA) concede aos consumidores da Califórnia novos direitos sobre suas informações pessoais e impõe responsabilidades de proteção de dados em determinadas entidades que fazem negócios na Califórnia. A CCPA entrou em vigor em 1º de janeiro de 2020.

Em um nível superior, a lei concede aos cidadãos da Califórnia vários direitos cruciais, incluindo o seguinte:

* Solicitar informações (acesso a dados)
* Recusar a venda de informações pessoais (um direito amplamente definido de recusar o compartilhamento de informações com terceiros)
* Excluir informações pessoais
* Ser informado que as informações pessoais estão sendo divulgadas ou vendidas

Se estava ocupado se preparando para a lei de privacidade da Europa (GDPR) no ano passado, alguns desses direitos podem ser familiares e grande parte do trabalho que você realizou pode ser redefinida.

>[!NOTE]
>
>O acesso e a exclusão de dados conforme se aplicam à CCPA seguem o mesmo processo do GDPR.

## Adobe [!DNL Target] e [!DNL Adobe Experience Platform] opt-in {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] O oferece suporte à funcionalidade de opt-in por meio de tags no [!DNL Adobe Experience Platform] para ajudar a apoiar sua estratégia de gerenciamento de consentimento. A funcionalidade de opt-in permite que os clientes controlem como e quando a tag do [!DNL Target] é acionada. Além disso, há uma opção por meio do [!DNL Adobe Experience Platform] para pré-aprovar a tag do [!DNL Target]. Para ativar a capacidade de usar o Opt-in na biblioteca at.js do [!DNL Target], você deve usar `targetGlobalSettings` e adicionar a configuração do `optinEnabled=true`. Em [!DNL Adobe ExperiencePlatform], selecione &quot;ativar&quot; no [!UICONTROL Aceitação do GDPR] lista suspensa na exibição de instalação da extensão. Consulte [Implementar [!DNL Target] usar [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) para obter mais detalhes.

O trecho de código a seguir mostra como ativar a configuração `optinEnabled=true`:

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>A funcionalidade de Opt-in é compatível com o at.js versão 1.7.0 e o at.js 2.1.0 ou posterior. O Opt-in não é compatível com o at.js versões 2.0.0 e 2.0.1.
>
>O uso do [!DNL Adobe Experience Platform] para gerenciar o opt-in é a abordagem recomendada. Existe ainda mais controlo granular no mercado [!DNL Adobe Experience Platform] para ocultar elementos selecionados da página antes de [!DNL Target] disparos que são úteis para usar como parte de sua estratégia de consentimento.

Há três cenários a serem considerados ao usar a inclusão:

1. **A tag do [!DNL Target] é pré-aprovada por meio do [!DNL Adobe Experience Platform] (ou pelo titular dos dados previamente aprovado pelo [!DNL Target]):** a tag do [!DNL Target] não é mantida para consentimento e funciona conforme esperado.
1. **[!DNL Target]A tag do NÃO é pré-aprovada e `bodyHidingEnabled` é FALSE:** A tag do é acionada somente após o consentimento ser coletado do cliente. [!DNL Target] Antes de o consentimento ser coletado, apenas o conteúdo padrão está disponível. Após o recebimento do consentimento, o [!DNL Target] é chamado e o conteúdo personalizado fica disponível para o titular dos dados (visitante). Como somente o conteúdo padrão está disponível antes do consentimento, é importante usar uma estratégia apropriada, como uma página inicial que cubra qualquer parte da página ou conteúdo que possa ser personalizado. Esse processo garante que a experiência permaneça consistente para o titular dos dados (visitante).
1. **[!DNL Target]A tag do NÃO é pré-aprovada e `bodyHidingEnabled` é TRUE:** A tag do é acionada somente após o consentimento ser coletado do cliente. [!DNL Target] Antes de o consentimento ser coletado, apenas o conteúdo padrão está disponível. No entanto, como `bodyHidingEnabled` é definido para verdadeiro, `bodyHiddenStyle` determina qual conteúdo na página fica oculto até que a tag do seja acionada (ou o titular dos dados recuse a inclusão, sendo que nesse caso o conteúdo padrão é exibido). [!DNL Target] Por padrão, `bodyHiddenStyle` está definida como `body { opacity:0;}`, que oculta a tag HTML body . o gerenciador de página recomendado é o corpo inteiro da página, exceto a caixa de diálogo de consentimento, que fica oculto, colocando o conteúdo da página em um e a caixa de diálogo de consentimento em um contêiner separado. Essa configuração define o [!DNL Target] para que ele apenas oculte o container da página. Consulte a [Visão geral do Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en).

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

## Perguntas frequentes sobre privacidade e regulamentos sobre proteção de dados FAQ {#concept_41F88DE95D2943178BEC382736B5C038}

Perguntas frequentes sobre o Regulamento Geral sobre a Proteção de Dados (GDPR) da União Europeia, a California Consumer Privacy Act (CCPA) e outros requisitos de privacidade internacionais específicos para o [!DNL Target].

### O que é [!DNL Adobe] política para estes regulamentos? {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] O já atende às obrigações como um Processador de dados ou está fazendo implementações de acordo. A Adobe tem uma base sólida de controles de segurança e privacidade certificados por design e fez aprimoramentos de produtos antes do prazo de maio de 2018. Clientes empresariais têm a responsabilidade de implementar essas melhorias e atualizar quaisquer políticas e procedimentos necessários.

### Minha empresa, o Controlador de dados, deve enviar uma solicitação do GDPR ou da CCPA para cada [!DNL Adobe Experience Cloud] solução usada? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

Não, [!DNL Adobe] O fornece uma maneira central para ajudar Controladores de dados a atender aos requisitos do GDPR e da CCPA. Os controladores de dados não precisam acessar diretamente cada solução.

Todas as solicitações do GDPR e da CCPA [!DNL Experience Cloud] , incluindo [!DNL Target], são por meio de um [!DNL Adobe] API, atualmente chamada de API do GDPR. A API então conclui a solicitação no [!DNL Experience Cloud] conjunto de soluções.

### Que informações faz [!DNL Adobe] permitir que os clientes excluam em resposta a uma solicitação do usuário/titular dos dados? {#section_4B51D00924EC4166B2442218B69214F0}

As informações relacionadas a um visitante individual dentro do [!DNL Target] são contidas no Perfil do visitante do [!DNL Target]. [!DNL Target] permite que os clientes excluam todos os dados associados a uma ID em seus respectivos Perfis do visitante. Para obter exemplos dos dados de perfil armazenados no [!DNL Target], consulte [Perfil do visitante](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

Dados agregados ou anônimos (por exemplo, dados de relatórios) não usados para identificar um certo indivíduo, ou dados não relevantes a um indivíduo específico (por exemplo, dados de conteúdo), não estão no escopo de uma solicitação de exclusão de usuário.

Por padrão, os perfis do visitante do [!DNL Target] que ficaram inativos por 90 dias são excluídos, sem nenhuma ação necessária.

### Quais IDs são compatíveis para ajudar os clientes a concluírem uma solicitação de acesso e exclusão do GDPR ou da CCPA para o [!DNL Target]? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

O [!DNL Target] é compatível com os seguintes tipos de ID para localizar um perfil de cliente:

| ID de usuário | Tipo de ID de namespace | ID de namespace | Definição |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Padrão | 4 | [!UICONTROL Adobe Experience Cloud ID], anteriormente conhecida como ID de visitante ou ID de Experience Cloud. É possível usar a API do JavaScript para localizar esta ID (veja os detalhes abaixo). |
| ID de TnT / ID de cookie(TNTID) | Padrão | 9 | [!DNL Target]Identificador do definido como cookie no navegador do visitante. É possível usar a API do JavaScript para localizar esta ID (veja os detalhes abaixo). |
| ID de terceiros / ID de CRM  (THIRDPARTYID) | [!DNL Target]-Específico | N/A | Se você fornecer [!DNL Target] com seu CRM ou outras informações de identificador exclusivo para seus clientes. |

>[!NOTE]
>
>Embora o [!DNL Target] seja compatível com cookies próprios e de terceiros entre domínios, apenas cookies próprios do [!DNL Target]são recomendados para o GDPR e para a CCPA.

### Como o [!DNL Target] aborda o gerenciamento de consentimento? {#section_C86BF5EE4FAA47039659850E7594A6BA}

O GDPR e a CCPA não mudam quando é necessário obter consentimento, mas como obtê-lo. A estratégia de consentimento de cada cliente depende de sua coleta de dados e práticas de uso e de sua política de privacidade. O gerenciamento do consentimento não é compatível com o [!DNL Target] e não deve ser obtido por meio dele para GDPR e CCPA.

No momento, a [!DNL Adobe] não oferece uma Solução de gerenciamento de consentimento, mas há várias ferramentas em desenvolvimento no mercado para atender a alguns dos novos requisitos. Para obter mais informações sobre as ferramentas de privacidade em geral, incluindo gerenciadores de consentimento, consulte o [Relatório de fornecedores de tecnologia de privacidade de 2017](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) no *Associação Internacional de Profissionais de Privacidade (iaap)* site.

[!DNL Target] O oferece suporte à funcionalidade de opt-in por meio do [!DNL Adobe Experience Platform] para apoiar sua estratégia de gerenciamento de consentimento. A funcionalidade de opt-in permite que os clientes controlem como e quando a tag do [!DNL Target] é acionada. Além disso, há uma opção por meio do [!DNL Adobe Experience Platform] para pré-aprovar a tag do [!DNL Target]. O uso do [!DNL Adobe Experience Platform] para gerenciar o opt-in é a abordagem recomendada. Existe ainda mais controlo granular no mercado [!DNL Adobe Experience Platform] para ocultar elementos selecionados da página antes da variável [!DNL Target] disparar que pode ser útil para usar como parte de sua estratégia de consentimento.

Para obter mais informações sobre GDPR, CCPA e [!DNL Adobe Experience Platform], consulte [A biblioteca JavaScript de privacidade do Adobe e o GDPR](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en). Além disso, consulte o *Opt-in da Adobe Target e da Adobe Experience Platform* acima.

### `AdobePrivacy.js`O   envia informações para a API do GDPR? {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] *não* envia essas informações para a API. Isso deve ser feito pelo cliente. Esta biblioteca fornece apenas as IDs armazenadas no navegador para esse visitante específico.

### O que `removeIdentities` remover? {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL `removeIdentities`]O *remove somente* essas identidades do navegador, e depende apenas se a [!DNL Adobe] solução da implementou isso.

Por exemplo, o [!DNL Target] exclui os cookies que armazenam suas IDs, mas o [!DNL Adobe Audience Manager] (AAM) não exclui a ID do demdex armazenada em um cookie de terceiros.

### Quais informações devem ser incluídas em um [!DNL Target] Solicitação do GDPR ou da CCPA? {#section_D29A4744AE6344E68AD7710B185FD6D0}

Além dos requisitos do Serviço central de privacidade, uma mensagem válida do GDPR ou da CCPA para o [!DNL Target] contém:

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

### Que tipos de respostas posso esperar [!DNL Target] por meio da API do GDPR? {#section_F67263D2A72B4641A47CE36729CCAE8F}

| Status da solicitação | [!DNL Target] Mensagem de resposta | Cenário |
|--- |--- |--- |
| Processando | Processando | [!DNL Target]O recebeu a solicitação do GDPR ou da CCPA e está processando. |
| Concluído | Não aplicável - o contexto da empresa não é aplicável | A ID IMS na solicitação do GDPR ou da CCPA não está mapeada para [!DNL Target] cliente.<br>Algumas empresas têm várias IDs de IMS. Envie a ID IMS, onde [!DNL Target] é provisionado. |
| Concluído | Não aplicável - contexto do usuário não encontrado | A ID fornecida na solicitação do GDPR ou da CCPA para o visitante específico ou titular dos dados não está presente na variável [!DNL Target] armazenamento de perfil.<br>Esse resultado também será retornado se você tentar enviar um tipo de ID de namespace que não seja suportado pela [!DNL Target] (veja acima as IDs compatíveis). |
| Erro | Mensagem de erro (os detalhes dependem do tipo de erro) | Erro ao buscar ou excluir o perfil do titular de dados solicitado.<br>Erro ao fazer upload no Azure para a solicitação de acesso. |

### Qual resposta [!DNL Target] enviar para a API do GDPR para uma solicitação de acesso? {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

As respostas para acessar solicitações de dados contêm um resumo do perfil do [!DNL Target] para o visitante em questão. Este retorno é enviado para a [!DNL Experience Cloud] A API do GDPR, que, por sua vez, envia uma resposta aos Controladores de dados.

Este é um exemplo de resposta da API de acesso do [!DNL Target]:

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
| jobId | Indica a ID de trabalho do GDPR ou da CCPA da API central do GDPR. |
| imsOrgID | Oferece um identificador exclusivo para sua empresa. |
| namespace | Também conhecido como fonte de dados. Consulte “Quais IDs são compatíveis para ajudar os clientes a concluírem uma solicitação de acesso e exclusão do GDPR ou da CCPA para o [!DNL Target]?&quot; neste tópico. |
| type | O tipo de ID para a qual você solicitou o acesso de dados do GDPR ou da CCPA. [!DNL Target] aceita vários tipos de ID, alguns são padrão e outros são específicos para [!DNL Target]. Consulte “Quais IDs são compatíveis para ajudar os clientes a concluírem uma solicitação de acesso e exclusão do GDPR ou da CCPA para o [!DNL Target]?&quot; neste tópico. |
| value | A ID do namespace/fonte de dados. Consulte “Quais IDs são compatíveis para ajudar os clientes a concluírem uma solicitação de acesso e exclusão do GDPR ou da CCPA para o [!DNL Target]?&quot; para saber mais sobre os valores aceitos. |
| código de integração | Códigos de integração são nomes amigáveis para suas fontes de dados e ajudam a monitorar suas fontes de dados de maneira mais fácil do que seria com IDs de fontes de dados. |

Quando diversos valores são fornecidos para identificar os perfis, cada identificador válido terá um arquivo de perfil. Um ou mais arquivos de perfil são enviados ao GDPR Azure Blob central por meio da API central do GDPR, no formato de [!DNL Target] Resposta JSON de perfil.

Uma amostra do JSON de perfil do [!DNL Target] pode ser semelhante ao seguinte exemplo:

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
| Sample_Parameter | Várias informações no perfil do [!DNL Target] são enviadas por upload ou fornecidas diretamente pelo Controlador de dados. Neste exemplo, um parâmetro foi enviado por upload para o perfil do [!DNL Target] usando a API de atualização de perfil. Para obter mais informações, consulte [Métodos para obter dados no [!DNL Target]](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md). |
| user.ReturnTimeOfDay | Este campo padrão inclui o horário da visita de retorno mais recente de um usuário. |
| firstSessionStart | Este campo padrão inclui o horário de início da primeira sessão do usuário. |
| user.sessionCountScript | Várias informações no perfil do [!DNL Target] são enviadas por upload ou fornecidas diretamente pelo Controlador de dados. Neste exemplo, um script de perfil está incrementando o número de sessões que este visitante fez ao site do Controlador de dados. Para obter mais informações, consulte [Atributos de script de perfil](/help/main/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>Esta amostra de código é uma versão reduzida de um [!DNL Target] perfil JSON para ilustração. Vários campos do perfil do [!DNL Target] não são padrão. O que é retornado depende de quais informações estão nesse perfil do visitante específico.

### Does [!DNL Target] suporta ofuscação de IP? {#section_428907B0CD9842D9B245B38C66A53C6A}

O [!DNL Target] suporta ofuscação de IP se você optar por usá-lo como parte de sua estratégia de implementação do GDPR ou da CCPA. Para obter mais informações, consulte [Privacidade](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).

### Devo fazer algo para impedir que meus dados sejam compartilhados ou vendidos a terceiros?

[!DNL Target] não permite que os clientes compartilhem ou vendam dados diretamente de [!DNL Target] para terceiros, portanto, não há cancelamento da venda para [!DNL Target].