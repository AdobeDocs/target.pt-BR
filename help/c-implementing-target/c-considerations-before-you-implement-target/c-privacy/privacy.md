---
keywords: privacidade; endereço ip; geosegmentação; recusar; recusar; recusar; privacidade de dados; regulamentos governamentais; regulamentos; gdpr; ccpa
description: Saiba como o Adobe [!DNL Target] está em conformidade com as leis de privacidade de dados aplicáveis, incluindo a coleta e o tratamento de endereços IP e instruções de recusa.
title: Como o [!DNL Target] lida com problemas de privacidade?
feature: Privacidade e segurança
role: Developer
exl-id: fb632923-fa36-4553-88a6-f27860472eb6
source-git-commit: 2403f63a6b993818fdc845d17f1a0dde72be664d
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 56%

---

# Privacidade

[!DNL Adobe Target] O habilitou processos e configurações que permitem usar o  [!DNL Target] em conformidade com as leis de privacidade de dados aplicáveis.

## Coleta de endereços IP {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

O endereço IP de um visitante do seu site é transmitido para um Centro de processamento de dados da Adobe (DPC). Dependendo da configuração de rede do visitante, o endereço IP não representa necessariamente o endereço IP do computador dele. Por exemplo, o endereço IP pode ser o endereço IP externo de um firewall NAT (Network Address Translation, tradução de endereço de rede), proxy HTTP ou gateway de Internet. O Target não armazena nenhum endereço IP do usuário ou nenhuma informação pessoal identificável (PII). Os endereços IP são usados somente pelo Target durante a sessão (na memória, nunca persistem).

## Substituição do último octeto de endereços IP {#section_AE84EB0D7CE04E93B279B77732ADD61E}

O Adobe desenvolveu uma nova configuração de &quot;privacidade por design&quot; que pode ser ativada pelo Adobe Client Care para o Adobe Target. Quando a configuração estiver ativada, o último octeto (a última parte) do endereço IP será omitido imediatamente quando o endereço IP for coletado pela Adobe. Essa anonimização é executada antes de qualquer processamento do endereço IP, incluindo antes de uma geolocalização opcional do endereço IP.

Quando esse recurso é ativado, o endereço IP fica anônimo de forma que não seja mais identificado como informações pessoais. Assim, o Adobe Target pode ser usado em conformidade com as leis de privacidade de dados em países que não permitem a coleta de informações pessoais. A obtenção de informações do nível da cidade provavelmente será muito afeta pela ofuscação do endereço IP. A obtenção de informações do nível da região e do país será pouco afetada.

As seguintes configurações estão disponíveis:

* Sem ofuscação: O Target não oculta nenhuma parte do endereço IP.
* Último octeto: O Target oculta o último octeto do endereço IP.
* IP completo: O Target oculta todo o endereço IP.

O Target recebe o endereço IP completo e o ofusca (se estiver definido como Último octeto ou IP completo) conforme especificado. O Target mantém o endereço IP ofuscado na memória durante a sessão.

>[!NOTE]
>
>[Entre em contato com o ](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) Atendimento ao cliente do Adobe para determinar qual configuração você está usando no momento ou para ativar o recurso de ofuscação de IP.

## GeoSegmentation  {#section_BB69F96559BD44BDA4177537C4A5345A}

Se você ativar a substituição do último octeto do endereço IP, os valores restantes do endereço IP poderão ser analisados por meio de relatórios no Adobe Target. Se o último octeto do endereço IP não for ofuscado, o endereço IP inteiro poderá ser analisado no Adobe Target. Você pode usar o recurso GeoSegmentation para mapear o local do visitante por área geográfica. Os dados de GeoSegmentation são granulares somente no nível da cidade ou no nível de código postal, e não no nível individual.

Se os endereços IP forem completamente ofuscados, a GeoSegmentation e a geolocalização não estarão disponíveis.

## Link de cancelamento {#section_E7A62B7B99C94B3A806CB262D16E27FC}

Você pode adicionar um link para opção de não participação a seus sites para permitir que os visitantes optem por não participar de todas as contagens e entregas de conteúdo.

1. Adicione o seguinte link a seu site:

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`

1. (Condicional) Se você estiver usando CNAME, o link deverá conter o parâmetro &quot;client=`clientcode` , por exemplo:
https://my.cname.domain/optout?client=clientcode.

1. Substitua `clientcode` por seu código de cliente e adicione o texto ou imagem a ser vinculado ao URL de não participação.

Qualquer visitante que clicar neste link não será incluído em qualquer solicitação de mbox chamadas de suas sessões de navegação até que excluam seus cookies, ou por dois anos, o que acontecer primeiro. Isto funciona através da configuração um cookie chamado `disableClient` para o visitante no domínio `clientcode.tt.omtrdc.net`.

Mesmo se estiver usando uma implementação de cookie primário, a opção de não participação fornecida é definida por meio de um cookie de terceiros. Se o cliente estiver usando apenas um cookie próprio, o Target verificará se um cookie de não participação foi definido.

## Coleta de dados de uso de recursos {#feature-usage}

Os dados de uso de recursos individuais são coletados para fins internos [!DNL Adobe] a fim de identificar se os recursos [!DNL Target] estão funcionando como pretendido ou para identificar os recursos que estão sendo subutilizados. Várias medidas de latência são coletadas para ajudar a resolver problemas de desempenho. Os dados pessoais não são coletados.

Você pode recusar o relatório de dados de uso definindo `telemetryEnabled` no arquivo de configuração como `false`.

## Privacidade e regulamentos sobre proteção de dados

Consulte [Regras de privacidade e proteção de dados](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) para obter informações sobre o Regulamento Geral sobre a Proteção de Dados (GDPR) da União Europeia, a Lei de Privacidade do Consumidor da Califórnia (CCPA) e outros requisitos de privacidade internacionais, e como esses regulamentos afetam sua organização e a Adobe Target.
