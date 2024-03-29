---
keywords: Recommendations
description: Saiba mais sobre os requisitos de implementação do Analytics para [!DNL Target] (A4T) e o que considerar antes de implementar essa integração.
title: O Que Devo Saber Antes De Implementar O A4T?
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 30%

---

# Antes de implementar o Analytics for Target (A4T) com a at.js

Várias alterações ocorrem no processo de coleta de dados ao ativar [!DNL Adobe Analytics] como fonte de relatórios para [!DNL Adobe Target] (A4T).

Antes de decidir usar essa integração, revise as seguintes seções e considere o impacto aos seus processos de relatórios.

>[!NOTE]
>
>Este artigo se aplica somente às implementações da at.js.

## Requisitos de implementação {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Antes de começar a usar o A4T, você deve solicitar que sua conta seja provisionada para a integração. Use o [Formulário de provisionamento de integrações do Marketing Cloud](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank} para solicitar o provisionamento.

Esta integração do A4T requer que você implemente as seguintes versões de biblioteca (ou mais recentes), dependendo se deseja ou não usar ofertas de redirecionamento com o A4T.

>[!NOTE]
>
>Os seguintes requisitos listam o *mínimo* versões da at.js necessárias para implementar o A4T. A variável [!DNL Target] A equipe do mantém apenas duas versões do [!DNL at.js]—a versão atual e a segunda versão mais recente. Atualize a [!DNL at.js] conforme necessário para garantir que você esteja executando uma versão suportada. Para obter mais informações sobre o que há de novo em cada versão, consulte [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

### Requisitos necessários se *não* estiver usando ofertas de redirecionamento com o A4T

Essa integração requer que você implemente as seguintes versões de biblioteca (ou mais recentes) se não planeja usar ofertas de redirecionamento com o A4T. A ordem listada é de operações.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versão 1.8.0
* [!DNL Adobe Target]: at.js versão 0.9.1
* Adobe Analytics: appMeasurement.js versão 1.7.0

Para obter informações sobre a implementação do A4T com o [!DNL Platform Web SDK], consulte [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

### Requisitos necessários se estiver usando ofertas de redirecionamento com o A4T

Para usar ofertas de redirecionamento com A4T, você deve implementar as seguintes versões de biblioteca (ou mais recentes). A ordem listada é de operações.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versão 2.3.0

   >[!NOTE]
   >
   >O at.js 1.8.0+ e o at.js 2.x+ não funcionam mais com as versões da API do visitante anteriores à 2.5.0 para transmitir parâmetros do Adobe Audience Manager (AAM).

* [!DNL Adobe Target]: at.js versão 1.6.2

* Adobe Analytics: appMeasurement.js versão 2.1

As instruções de download e implantação estão listadas em [Implementação do Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

Para obter informações sobre a implementação do A4T com o [!DNL Platform Web SDK], consulte [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

## O que você deve saber antes da implementação {#section_50D49CC52E11414089C89FB67F9B88F5}

* Essa integração é habilitada em novas atividades quando você seleciona para usar [!DNL Analytics] como fonte de relatórios. As alterações de implementação descritas neste documento não afetam suas atividades existentes.
* O processo de configuração [!DNL Analytics] como fonte de relatórios para [!DNL Target] O inclui várias etapas de implementação, seguidas por uma etapa de provisionamento. É recomendável ler durante o processo, conforme descrito abaixo, antes de fazer a implementação. Após concluir essas etapas, você estará pronto para usar [!DNL Analytics] como sua fonte de geração de relatórios quando ela estiver ativada para você. O processo de provisionamento pode levar até cinco dias úteis.
* A variável [!DNL Visitor ID service] cria um compartilhado [!DNL Visitor ID] em todo o [!DNL Adobe Experience Cloud]. Embora não substitua a [!DNL Target] mboxPC id ou [!DNL Audience Manager] UUID, ele substitui a maneira como [!DNL Analytics] O código identifica novos visitantes. Se configurado corretamente, retornando [!DNL Analytics] os visitantes também devem ser identificados por meio de seus [!DNL Analytics] ID. Do mesmo modo, uma vez que [!DNL Target] mboxPCid permanece intacta, não [!DNL Target] os dados do perfil do visitante são perdidos quando você atualiza para o [!DNL Visitor ID service].
* A variável [!DNL Visitor ID service] deve ser executado antes de seu [!DNL Analytics] e [!DNL Target] código de página. Verifique se `VisitorAPI.js` é exibido acima das tags para todos os outros [!DNL Experience Cloud] soluções.

## Latência {#section_9489BE6FD21641A4844E591711E3F813}

Após habilitar essa integração, haverá de 5 a 10 minutos extras de latência na [!DNL Analytics]. Esse aumento de latência permite que dados de [!DNL Analytics] e [!DNL Target] para ser armazenado na mesma ocorrência, permitindo dividir as atividades por página e seção do site.

Este aumento reflete-se em todos os [!DNL Analytics] e ferramentas, incluindo os relatórios em tempo real e em fluxo real, e se aplica nos seguintes cenários:

* Para a transmissão ao vivo, relatórios em tempo real, solicitações de API e dados atualizados para as variáveis de tráfego, somente hits com uma ID de dados adicional são atrasadas.
* Para dados atuais sobre métricas de conversão, dados finalizados e feeds de dados, todas as ocorrências são atrasadas em mais 5 a 7 minutos.

O aumento da latência começa após a implementação da variável [!DNL Experience Cloud] serviço de ID de visitante, mesmo que você não tenha implementado totalmente essa integração.

## ID suplementar  {#section_2C1F745A2B7D41FE9E30915539226E3A}

Todos [!DNL Target] As chamadas usadas por uma atividade do A4T para fornecer conteúdo ou registrar a métrica de meta devem ter uma [!DNL Analytics] que compartilha a ID complementar do A4T para funcionar corretamente.

Ocorrências que contêm dados de [!DNL Analytics] e [!DNL Target] contém uma ID de dados complementar. Você pode ver essa ID na [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) como o `sdid` parâmetro. Por exemplo: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Esta ID é gerada a qualquer momento em que os seguintes critérios estiverem em vigor:

* O serviço de ID de visitante for implementado

Quando [solução de problemas](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), confirme se a ID complementar está presente em [!DNL Analytics] ocorrências.

## Registro de análises do cliente {#client-side}

Se a at.js, a variável [!DNL Experience Cloud Visitor ID Service]e appMeasurement.js estão na página, [!DNL Analytics], e [!DNL Target] une corretamente os eventos para fins de relatório e análise no backend, desde que a ID adicional correta esteja incluída na página. Não é necessário gerenciar e executar operações adicionais para que o A4T funcione corretamente.

Há casos em que você precisa ter mais controle sobre quando e como enviar dados de análise relacionados ao [!DNL Target] para [!DNL Analytics] para fins de relatório. Você pode ter uma ferramenta de análise interna usada para fins internos. No entanto, também é necessário enviar os dados de análise para [!DNL Analytics] por meio do produto de análise interno, para que outros membros da organização possam continuar usando [!DNL Analytics] como uma fonte de relatórios visuais. Consulte [Etapa 7: Referência a at.js em todas as páginas do site](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) in *Implementação do Analytics for Target* para obter mais informações.

## Públicos-alvo compartilhados

Ao preencher o [Formulário de provisionamento de integrações do Marketing Cloud](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}devem estar cientes das seguintes informações importantes relativas à [!UICONTROL Públicos-alvo compartilhados] opção listada em &quot;[!UICONTROL Para quais recursos você está solicitando provisionamento]?&quot;

![Formulário de solicitação](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

Quando você solicitar [!UICONTROL Públicos-alvo compartilhados], você habilita [!UICONTROL Target] e [!UICONTROL Adobe Audience Manager] (AAM) para compartilhar informações, neste caso, públicos-alvo.

>[!IMPORTANT]
>
>Essa integração entre [!UICONTROL Target] e o AAM vem com custos extras. Você é cobrado por cada [!UICONTROL Target] chame no AAM.
