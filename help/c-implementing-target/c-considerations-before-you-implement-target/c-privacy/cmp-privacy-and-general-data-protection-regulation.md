---
description: Informações sobre o Regulamento Geral sobre a Proteção de Dados da União Europeia (GDPR) e uma lista de perguntas frequentes sobre como essa regulamentação afeta a empresa e o Adobe Target.
keywords: gdpr;eu;união europeia;privacidade;perguntas frequentes;perguntas mais frequentes
seo-description: Informações sobre o Regulamento Geral sobre a Proteção de Dados da União Europeia (GDPR) e uma lista de perguntas frequentes sobre como essa regulamentação afeta a empresa e o Adobe Target.
seo-title: Privacidade e o Regulamento Geral sobre a Proteção de Dados (GDPR)
solution: Target
title: Privacidade e o Regulamento Geral sobre a Proteção de Dados (GDPR)
topic: Padrão
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Privacidade e o Regulamento Geral sobre a Proteção de Dados (GDPR){#privacy-and-general-data-protection-regulation-gdpr}

Informações sobre o Regulamento Geral sobre a Proteção de Dados da União Europeia (GDPR) e uma lista de perguntas frequentes sobre como essa regulamentação afeta a empresa e o Adobe Target.

## Visão Geral da Privacidade e o Regulamento Geral sobre a Proteção de Dados (GDPR) {#topic_DE567ECB6C944695AEE5073889F1AEA9}

Informações sobre como a Adobe trabalha com você para que fique preparado para o GDPR com o Regulamento Geral sobre a Proteção de Dados (GDPR) da União europeia.

## Visão geral do GDPR {#section_8C99434A431B4494998B01B869E7EA5D}

O GDPR da União Europeia entra em vigor em 25 de maio de 2018. Para obter mais informações sobre o que isso significa para você, consulte [GDPR e seus negócios](https://www.adobe.com/privacy/general-data-protection-regulation.html).

Quando a Adobe oferece software e serviços para uma empresa, ela age como um Processador de dados de quaisquer dados pessoais que processa e armazena como parte do oferecimento desses serviços. Como Processador de dados, a Adobe processa dados pessoais de acordo com a permissão e as instruções de sua empresa (por exemplo, como definido em seu contrato com a Adobe).

Como o Controlador de dados, você determinará os dados pessoais que a Adobe processa e armazena em seu nome. Se você usa as soluções da Adobe Experience Cloud, a Adobe pode hospedar dados pessoais, dependendo das soluções usadas e das informações que você escolher enviar para a sua conta da Adobe Experience Cloud. Para obter uma lista detalhada de exemplos, consulte [Privacidade na Adobe Experience Cloud](https://www.adobe.com/privacy/marketing-cloud.html#collect).

A Adobe Experience Cloud fornecerá APIs compatíveis com o GDPR para Controladores de dados que permitem concluir as seguintes tarefas, antes da data em que o GDPR entra em vigor:

* Acessar informações do titular de dados armazenadas no Target
* Excluir informações do titular de dados armazenadas no Target

## O site da API do Regulamento Geral sobre a Proteção de Dados {#section_51B8FA3CBE234E9592BDA7083B5CE4CD}

Para obter mais informações, consulte:

* [Site da API do Regulamento Geral sobre a Proteção de Dados da Adobe](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [Documentação do GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## Inclusão do Adobe Target e Adobe Launch {#section_6F7B53F5E40C4425934627B653E831B0}

O Target oferece suporte a funcionalidade de inclusão por meio do Adobe Launch, para ajudar a apoiar a sua estratégia de gerenciamento de consentimento. A funcionalidade de inclusão permite que os clientes controlem como e quando a tag do Target é acionada. Além disso, há uma opção por meio do Adobe Launch para pré-aprovar a tag do Target. Para ativar a capacidade de usar a Aceitação no at.js do Target, você deve usar `targetGlobalSettings` e adicionar a configuração do `optinEnabled=true`. No Lançamento, você deverá selecionar &quot;habilitar&quot; na lista suspensa de Aceitação do GDPR na exibição de instalação do Target Launch Extension. Consulte a documentação do [Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) para obter mais detalhes.

O trecho de código a seguir mostra como ativar a configuração `optinEnabled=true`:

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>A funcionalidade de aceitação é compatível com o at. js versão 1.7.0 e o at. js 2.1.0. Não há suporte para o at. js versão 2.0.0 e 2.0.1.
>
>O uso do Adobe Launch para gerenciar a inclusão é a abordagem recomendada. Existe ainda mais controle granular no Adobe Launch para ocultar elementos selecionados da sua página, antes do acionamento do Target, que pode ser útil como parte de sua estratégia de consentimento.

Há três cenários a serem considerados ao usar a inclusão:

1. **A tag do Target é pré-aprovada por meio do Adobe Launch (ou pelo titular dos dados previamente aprovado pelo Target):** a tag do Target não é mantida para consentimento e funciona conforme esperado.
1. **A tag do Target NÃO é pré-aprovada e`bodyHidingEnabled`é FALSE:** A tag do Target é acionada somente após o consentimento ser coletado do cliente. Antes de o consentimento ser coletado, apenas o conteúdo padrão está disponível. Após o recebimento do consentimento, o Target é chamado e o conteúdo personalizado fica disponível para o titular dos dados (visitante). Como apenas o conteúdo padrão está disponível antes do consentimento, é importante utilizar uma estratégia apropriada, como uma página inicial que cubra qualquer parte da página ou conteúdo que possa ser personalizado. Isso garante que a experiência permaneça consistente para o titular dos dados (visitante).
1. **A tag do Target NÃO é pré-aprovada e`bodyHidingEnabled`é TRUE:** A tag do Target é acionada somente após o consentimento ser coletado do cliente. Antes de o consentimento ser coletado, apenas o conteúdo padrão está disponível. No entanto, como `bodyHidingEnabled` é definido para verdadeiro, `bodyHiddenStyle` determina qual conteúdo na página fica oculto até que a tag do Target seja acionada (ou o titular dos dados recuse a inclusão, sendo que nesse caso o conteúdo padrão é exibido). Por padrão, `bodyHiddenStyle` está configurado como `body { opacity:0;`}, o que oculta a tag do corpo HTML. Nossa configuração de página recomendada é apresentada abaixo para que todo o corpo da página, além da caixa de diálogo do gerenciador de consentimento, fique oculto, colocando o conteúdo da página em um contêiner e o diálogo do gerenciador de consentimento em um contêiner separado. Essa configuração define o Target para que ele apenas oculte o contêiner de conteúdo da página. Consulte a [documentação do Adobe Launch para obter mais informações sobre como definir essas configurações](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html).

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

## Perguntas frequentes sobre o Regulamento Geral sobre a Proteção de Dados {#concept_41F88DE95D2943178BEC382736B5C038}

Perguntas frequentes sobre o Regulamento Geral sobre a Proteção de Dados (GDPR) específicas para o Adobe Target.

### Qual é a política da Adobe para o Regulamento Geral sobre a Proteção de Dados (GDPR)? {#section_A6849628D6524C80A6E16946DC5D25A9}

A Adobe já atende às obrigações como um Processador de dados ou está fazendo implementações de acordo. Nós temos uma base sólida de controles de segurança e privacidade certificados por padrão e continuaremos a fazer melhorias até o prazo de maio de 2018. Clientes empresariais terão a responsabilidade de implementar essas melhorias, além de atualizar quaisquer políticas e procedimentos necessários.

### Minha empresa, a Controladora de dados, precisará enviar uma solicitação de GDPR para cada solução da Adobe Experience Cloud usada? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

Não, a Adobe está oferecendo uma maneira central para ajudar Controladores de dados a atender os requisitos do GDPR. Os Controladores de dados não precisarão acessar diretamente cada solução.

Todas as solicitações de GDPR nas soluções da Experience Cloud, incluindo o Target, serão feitas por meio de uma API central da Adobe, atualmente denominada API do GDPR. A API concluirá a solicitação no conjunto de soluções da Experience Cloud do Controlador de dados.

### Quais informações a Adobe permitirá que nossos clientes excluam em resposta a uma solicitação de usuário/titular de dados? {#section_4B51D00924EC4166B2442218B69214F0}

As informações relacionadas a um visitante individual dentro do Target são contidas no Perfil de visitante do Target. O Adobe Target permitirá que nossos clientes excluam todos os dados associados a uma ID em seus respectivos Perfis do visitante. Para obter exemplos dos dados armazenados pelo Adobe Target, consulte [Perfil do visitante](../../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E).

Dados agregados ou anônimos (por exemplo, dados de relatórios) não usados para identificar um certo indivíduo, ou dados não relevantes a um indivíduo específico (por exemplo, dados de conteúdo), não estão no escopo de uma solicitação de exclusão de usuário.

Por padrão, os perfis do visitante do Target que ficaram inativos por 90 dias são excluídos, sem nenhuma ação necessária.

### Quais IDs são compatíveis para ajudar os clientes a concluírem uma solicitação de acesso e exclusão de GDPR para o Target? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

O Target é compatível com os seguintes tipos de ID para localizar um perfil de cliente:

| ID de usuário | Tipo de ID de namespace | ID de namespace | Definição |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Padrão | 4 | Adobe Experience Cloud ID, anteriormente conhecida como ID de visitante ou Marketing Cloud ID. É possível usar a API do JavaScript para localizar esta ID (veja os detalhes abaixo). |
| ID de TnT / ID de cookie(TNTID) | Padrão | 9 | Identificador do Target definido como cookie no navegador do visitante. É possível usar a API do JavaScript para localizar esta ID (veja os detalhes abaixo). |
| ID de terceiros / ID de CRM (THIRDPARTYID) | Específico do Target | N/A | Se você fornecer seu CRM ao Target ou qualquer outra informação de identificador exclusivo referente a seus clientes. |

>[!NOTE]
>
>Embora o Adobe Target seja compatível com cookies de domínios cruzados próprios e de terceiros, apenas cookies próprios do Adobe Target são recomendados para GDPR.

### Como o Adobe Target aborda a administração de consentimento? {#section_C86BF5EE4FAA47039659850E7594A6BA}

O GDPR não altera quando é necessário obter consentimento, mas como obtê-lo. A estratégia de consentimento de cada cliente depende de sua coleta de dados e práticas de uso, bem como da política de privacidade. O gerenciamento do consentimento não é suportado e não deve ser acessado pelo Target para obter o GDPR.

No momento, a Adobe não oferece uma solução de Administração de consentimento, mas há várias ferramentas em desenvolvimento no mercado para atender a alguns dos novos requisitos. Para obter mais informações sobre as ferramentas de privacidade em geral, consulte o [Relatório de fornecedores de tecnologia de privacidade de 2017](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) (2017 Privacy Tech Vendor Report) no site da International Association of Privacy Professionals (iaap).

O Adobe Target oferece suporte a funcionalidade de inclusão por meio do Adobe Launch, para fornecer apoio à sua estratégia de gerenciamento de consentimento. A funcionalidade de inclusão permite que os clientes controlem como e quando a tag do Adobe Target é acionada. Além disso, há uma opção por meio do Adobe Launch para pré-aprovar a tag do Adobe Target. O uso do Adobe Launch para gerenciar a inclusão é a abordagem recomendada. Existe ainda mais controle granular no Adobe Launch para ocultar elementos selecionados da sua página, antes do acionamento do Adobe Target, que pode ser útil como parte de sua estratégia de consentimento.

Para obter mais informações sobre o GDPR e o Adobe Launch, consulte [A biblioteca de JavaScript de privacidade e o GDPR do Adobe](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). Além disso consulte a seção “Inclusão do Adobe Target e Adobe Launch” acima.

### O AdobePrivacy.js envia informações para a API do GDPR? {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] *não* envia essas informações para a API. Isso deve ser feito pelo cliente. Esta biblioteca fornece apenas as IDs armazenadas no navegador para esse visitante específico.

### O que é removido por removeIdentities? {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities]O *remove somente* essas identidades do navegador, e depende apenas se a solução da Adobe implementou isso.

Por exemplo, o Target exclui os cookies que armazenam suas IDs, mas o Adobe Audience Manager (AAM) não exclui a ID do demdex armazenada em um cookie de terceiros.

### Quais informações precisam ser incluídas em uma solicitação de GDPR do Target? {#section_D29A4744AE6344E68AD7710B185FD6D0}

Além dos requisitos do Serviço central de privacidade, uma mensagem do GDPR válida para o Target contém:

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
| Processando | Processando | O Target recebeu a solicitação de GDPR e está processando. |
| Concluído | Não aplicável - o contexto da empresa não é aplicável | A ID de IMS na solicitação de GDPR não está mapeada para nenhum cliente do Target.<br>Observe que algumas empresas têm várias IDs de IMS. Você deve enviar a ID de IMS na qual o Target é provisionado. |
| Concluído | Não aplicável - contexto do usuário não encontrado | A ID fornecida na solicitação de GDPR para o visitante específico ou o titular de dados não está presente no armazenamento de perfil do Target.<br>Observe que esse resultado também será retornado se você tentar enviar um tipo de ID de namespace que não seja suportado pelo Target (veja acima as IDs suportadas). |
| Erro | Mensagem de erro (os detalhes dependem do tipo de erro) | Erro ao buscar ou excluir o perfil do titular de dados solicitado.<br>Erro ao fazer upload no Azure para a solicitação de acesso. |

### Que resposta é enviada pelo Target à API do GDPR para uma solicitação de acesso? {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Respostas a solicitações de acesso a dados contêm um resumo do perfil do Target referente ao visitante em questão. Observe que esse retorno é enviado para a API do GDPR da Experience Cloud que, por sua vez, envia uma resposta aos Controladores de dados.

Este é um exemplo de resposta da API de acesso do Target:

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
| jobId | Indica a ID de tarefa do GDPR da API central do GDPR. |
| imsOrgID | Oferece um identificador exclusivo para sua empresa. |
| namespace | Também conhecido como fonte de dados. Consulte &quot;Quais IDs são compatíveis para ajudar os clientes a concluírem uma solicitação de acesso e exclusão do GDPR para o Target?&quot; neste tópico. |
| type | O tipo de ID para a qual você solicitou o acesso de dados do GDPR. O Target aceita diversos tipos de ID, alguns são padrão e outros são específicos ao Target. Consulte &quot;Quais IDs são compatíveis para ajudar os clientes a concluírem uma solicitação de acesso e exclusão do GDPR para o Target?&quot; neste tópico. |
| value | A ID do namespace/fonte de dados. Consulte &quot;Quais IDs são compatíveis para ajudar os clientes a concluírem uma solicitação de acesso e exclusão do GDPR para o Target?&quot; para saber mais sobre os valores aceitos. |
| código de integração | Códigos de integração são nomes amigáveis para suas fontes de dados e ajudam a monitorar suas fontes de dados de maneira mais fácil do que seria com IDs de fontes de dados. |

Quando diversos valores são fornecidos para identificar os perfis, cada identificador válido terá um arquivo de perfil. Os arquivos de perfil são enviados central de GDPR do Azure Blob por meio da API do GDPR central, no formato de resposta JSON de perfil do Target.

Uma amostra JSON de perfil do Target pode ser semelhante ao seguinte exemplo:

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
| Sample_Parameter | Várias informações no perfil do Target são enviadas por upload ou fornecidas diretamente pelo Controlador de dados. Neste exemplo, um parâmetro foi enviado por upload para o perfil do Target usando a API de atualização de perfil. Para obter mais informações, consulte [Métodos para obter dados no Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md). |
| user.ReturnTimeOfDay | Este campo padrão inclui o horário da visita de retorno mais recente de um usuário. |
| firstSessionStart | Este campo padrão inclui o horário de início da primeira sessão do usuário. |
| user.sessionCountScript | Várias informações no perfil do Target são enviadas por upload ou fornecidas diretamente pelo Controlador de dados. Neste exemplo, um script de perfil está incrementando o número de sessões que este visitante fez ao site do Controlador de dados. Para obter mais informações, consulte [Atributos de script de perfil](/help/c-target/c-visitor-profile/profile-parameters.md). |

>[!NOTE]
>
>Esta é uma versão reduzida de um JSON do perfil do Target para fins de ilustração. Vários campos do perfil do Target não são padrão. O que é retornado depende de quais informações estão nesse perfil do visitante específico.

## O Target suporta ofuscação de IP? {#section_428907B0CD9842D9B245B38C66A53C6A}

O Target suporta ofuscação de IP se você optar por usá-lo como parte de sua estratégia de implementação de GDPR. Para obter mais informações, consulte [Privacidade](../../../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).
