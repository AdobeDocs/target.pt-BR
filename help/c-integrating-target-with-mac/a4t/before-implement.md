---
keywords: Recommendations
description: Várias alterações ocorrem no processo de coleta de dados quando o Analytics é habilitado como a fonte de geração de relatórios para o Target (A4T).
title: Antes de implementar o Adobe Analytics como a fonte de relatórios para Adobe Target (A4T)
feature: a4t implementation
uuid: fe603a4b-bd61-49f4-b1b7-a0329aa905f5
translation-type: tm+mt
source-git-commit: 75fa021c00940c87cf4b2bfa0e2875bb396079a1
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 53%

---


# Antes da implementação{#before-you-implement}

Several changes occur in your data collection process when enabling [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

Antes de decidir usar essa integração, revise as seguintes seções e considere o impacto aos seus processos de relatórios:

## Requisitos de implementação {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Antes de começar a usar A4T, você precisa solicitar que sua conta seja provisionada para a integração. Use o Formulário [de Provisionamento de Integrações de](https://www.adobe.com/go/audiences) Marketing Cloud para solicitar o provisionamento.

Esta integração do A4T requer que você implemente as seguintes versões de biblioteca (ou mais recentes), dependendo se deseja ou não usar ofertas de redirecionamento com o A4T:

### Requisitos necessários se *não* estiver usando ofertas de redirecionamento com o A4T

Essa integração requer que você implemente as seguintes versões de biblioteca (ou mais recentes) se não planeja usar ofertas de redirecionamento com o A4T. A ordem listada é de operações.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versão 1.8.0
* [!DNL Adobe Target] (dependendo de sua implementação): at.js versão 0.9.1 ou mbox.js versão 61
* Adobe Analytics: appMeasurement.js versão 1.7.0

### Requisitos necessários se estiver usando ofertas de redirecionamento com o A4T

Para usar ofertas de redirecionamento com A4T, você deve implementar as seguintes versões de biblioteca (ou mais recentes). A ordem listada é de operações.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versão 2.3.0
* [!DNL Adobe Target]: at.js versão 1.6.2

   **Observação:** a biblioteca mbox.js não é compatível com as ofertas de redirecionamento com o A4T. Sua implementação deve usar at.js.

* Adobe Analytics: appMeasurement.js versão 2.1

Download and deployment instructions are listed in [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## O que você deve saber antes da implementação {#section_50D49CC52E11414089C89FB67F9B88F5}

* This integration is enabled on new activities when you select to use [!DNL Analytics] as the reporting source. As alterações de implementação descritas neste documento não afetam suas atividades existentes.
* The process of setting up [!DNL Analytics] as the reporting source for [!DNL Target] includes several implementation steps, followed by a provisioning step. É recomendável ler durante o processo, conforme descrito abaixo, antes de fazer a implementação. After you complete these steps, you will be ready to use [!DNL Analytics] as your reporting source as soon as it is enabled for you. O processo de provisionamento pode levar até cinco dias úteis.
* O [!DNL Visitor ID service] cria um compartilhado [!DNL Visitor ID] no [!DNL Adobe Experience Cloud]. Although it does not replace the [!DNL Target] mboxPC id or [!DNL Audience Manager] UUID, it does replace the way [!DNL Analytics] identifies new visitors. If set up properly, returning [!DNL Analytics] visitors should also be identified via their old [!DNL Analytics] ID to prevent visitor cliffing. Similarly, because the [!DNL Target] mboxPCid remains intact, no [!DNL Target] visitor profile data is lost when you upgrade to the [!DNL Visitor ID service].
* O [!DNL Visitor ID service] deve ser executado antes do código [!DNL Analytics] e [!DNL Target] da página. Make sure that `VisitorAPI.js` appears above the tags for all other [!DNL Experience Cloud] solutions.

## Latência {#section_9489BE6FD21641A4844E591711E3F813}

Após habilitar esta integração, você vai experimentar uma latência adicional de 5 a 10 minutos no [!DNL Analytics]. This latency increase allows data from [!DNL Analytics] and [!DNL Target] to be stored on the same hit, allowing you to break down activities by page and site section.

This increase is reflected in all [!DNL Analytics] services and tools, including the live-stream and real-time reporting, and applies in the following scenarios:

* Para a transmissão ao vivo, relatórios em tempo real, solicitações de API e dados atualizados para as variáveis de tráfego, somente hits com uma ID de dados adicional são atrasadas.
* Para os dados atuais sobre as métricas de conversão, dados finalizados e feeds de dados, todos os hits são atrasados de 5 a 7 minutos.

Be aware that the latency increase starts after you implement the [!DNL Experience Cloud] visitor ID service, even if you have not fully implemented this integration.

## ID suplementar  {#section_2C1F745A2B7D41FE9E30915539226E3A}

All [!DNL Target] calls used by an A4T activity to deliver content or record the goal metric must have a corresponding [!DNL Analytics] hit that shares the same supplemental ID for A4T to work properly.

Hits that contain data from [!DNL Analytics] and [!DNL Target] contain a supplemental data ID. You can see this ID in the [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) as the `sdid` parameter. Por exemplo: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Esta ID é gerada a qualquer momento em que os seguintes critérios estiverem em vigor:

* O serviço de ID de visitante for implementado
* A versão de [!DNL mbox.js] que suporta essa integração for implementada.

When troubleshooting, be sure to confirm that the supplemental ID is present on [!DNL Analytics] hits.

## Registro de análises do cliente {#client-side}

Por padrão, quando a at.js, [!DNL Experience Cloud Visitor ID Service] e appMeasurement.js estão na página, [!DNL Analytics] e [!DNL Target] une os eventos corretamente para fins de relatório e análise no back-end, desde que a ID adicional correta esteja incluída na página, como mencionado acima. Não é necessário gerenciar e executar operações adicionais para a A4T funcionar corretamente.

No entanto, há casos em que você precisa ter mais controle sobre quando e como enviar dados de análise relacionados ao [!DNL Target] para o [!DNL Analytics] para fins de relatório. Você pode ter uma ferramenta de análise interna usada para fins internos, mas também pode enviar os dados de análise ao [!DNL Analytics] por meio de um produto de análise interno, de forma que os outros membros da organização possam continuar a utilizar o [!DNL Analytics] como uma fonte de relatórios visuais. Consulte a [Etapa 7: Referência a at.js ou mbox.js em todas as páginas do site](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) no *Analytics para implementação do Target* para obter mais informações.

## Públicos-alvo compartilhados

Ao preencher o Formulário [de Provisionamento de Integrações de](https://www.adobe.com/go/audiences)Marketing Cloud, esteja ciente das seguintes informações importantes sobre a opção Audiências  compartilhadas listadas em &quot;[!UICONTROL Para quais recursos você está solicitando o provisionamento]?&quot;

![Formulário de solicitação](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

Ao solicitar Audiências compartilhadas, você ativa o [!UICONTROL Público alvo] e o [!UICONTROL Adobe Audience Manager] (AAM) para compartilhar informações, neste caso, o audiência.

>[!IMPORTANT]
>
>Essa integração entre o [!UICONTROL Público alvo] e o AAM acarreta custos adicionais. Você será cobrado por cada chamada de [!UICONTROL Público alvo] em AAM.
