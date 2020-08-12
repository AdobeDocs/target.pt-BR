---
keywords: Overview and Reference
description: Use o Target com o Adobe Campaign para otimizar o conteúdo de email.
title: Integração do Target ao Adobe Campaign
feature: null
topic: Standard
uuid: 1a5b70e6-d501-4b52-bec8-4ae2c419d331
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 51%

---


# Integração do Target ao Adobe Campaign{#integrate-target-with-adobe-campaign}

Use [!DNL Target] with [!DNL Adobe Campaign] to optimize email content.

To optimize your email content--for example, to display different offers for male and female recipients--you can create a redirect offer in [!DNL Target], then use [!DNL Adobe Campaign] to manage the email offers.

A integração ocorre quando o email é aberto. When the customer opens the email, a call is made to [!DNL Target] and a dynamic version of the content appears. O conteúdo consiste em uma imagem estática compatível com todos os navegadores. [!DNL Target]O rastreia a reação à oferta no nível do público-alvo ou da sessão, e esses dados são disponibilizados nos relatórios do [!DNL Target]

O Target pode rastrear os seguintes dados:

* Agente do usuário
* Endereço IP
* Localização geográfica
* Segmento associado à ID de visitante no Target (sujeito a aprovação legal)
* Data from [!DNL Campaign] Datamart

Há várias limitações:

* Como somente uma imagem pode ser usada, não é possível personalizar o conteúdo.
* Tracking is not consolidated in [!DNL Adobe Campaign].
* Sem unificação da experiência de usuário.

   You must use both [!DNL Target] and [!DNL Campaign] to set up different parts of the integration:

   * O rawbox e a experiência no [!DNL Target]
   >[!NOTE]
   >
   >Ao usar uma rawbox e [!DNL Target], consulte o aviso de segurança importante em [Criar lista de permissões que especificam hosts autorizados a enviar chamadas de mbox para o Público alvo](/help/administrating-target/hosts.md#allowlist).

   * The delivery in [!DNL Campaign]



## Antes de começar  {#section_FF19BF1BCA064260930BF6C141313B0E}

Before you use [!DNL Adobe Campaign] to set up your targeted email offers, set up the following in [!DNL Target]:

* Two or more [!DNL Target] redirect offers

   See [Create redirect offer](/help/c-experiences/c-manage-content/offer-redirect.md).
* Uma atividade do Target com uma experiência para cada oferta e a [métrica de sucesso](/help/c-activities/r-success-metrics/success-metrics.md) desejada.

   Consulte [Redirecionar para um URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Start the activity in [!DNL Target] before setting up the [!DNL Campaign] portion of the integration.

## Incluir uma oferta do Target em um email do Adobe Campaign  {#section_B201BBE27A704E18AF0D553F35695837}

1. Create an email in [!DNL Adobe Campaign].
1. Nas propriedades do email, clique em **[!UICONTROL Incluir]** > **[!UICONTROL Imagem dinâmica fornecida pelo Adobe Target]**.
1. Selecione a imagem padrão nos ativos compartilhados.
1. Especifique o local (rawbox).
1. Adicione quaisquer outros parâmetros de tomada de decisão, como o gênero do destinatário.
1. Visualize o email, selecionando pelo menos um destinatário por cada oferta (nesse caso, um destinatário do sexo masculino e um do sexo feminino).
1. In [!DNL Campaign], define the [!DNL Target] Edge server you are using to control the activity and the name of the tenant.
1. Specify the external account used for the [!DNL Adobe Experience Cloud] so you can access the resources in the [!DNL Experience Cloud].

For more information, refer to the [!DNL Adobe Campaign] documentation.
