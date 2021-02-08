---
keywords: Visão geral e referência
description: Saiba como usar o Adobe Target com a Adobe Campaign para otimizar o conteúdo de email.
title: Como integrar o Público alvo ao Adobe Campaign?
feature: Integrations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 47%

---


# Integração do Target ao Adobe Campaign{#integrate-target-with-adobe-campaign}

Use [!DNL Target] com [!DNL Adobe Campaign] para otimizar o conteúdo de email.

Para otimizar seu conteúdo de e-mail, por exemplo, para exibir ofertas diferentes para recipient machos e fêmeas, você pode criar uma oferta de redirecionamento em [!DNL Target], em seguida, usar [!DNL Adobe Campaign] para gerenciar as ofertas de e-mail.

A integração ocorre quando o email é aberto. Quando o cliente abre o email, uma chamada é feita para [!DNL Target] e uma versão dinâmica do conteúdo é exibida. O conteúdo consiste em uma imagem estática compatível com todos os navegadores. [!DNL Target]O rastreia a reação à oferta no nível do público-alvo ou da sessão, e esses dados são disponibilizados nos relatórios do [!DNL Target]

O Target pode rastrear os seguintes dados:

* Agente do usuário
* Endereço IP
* Localização geográfica
* Segmento associado à ID de visitante no Target (sujeito a aprovação legal)
* Dados do Datamart [!DNL Campaign]

Há várias limitações:

* Como somente uma imagem pode ser usada, não é possível personalizar o conteúdo.
* O rastreamento não é consolidado em [!DNL Adobe Campaign].
* Sem unificação da experiência de usuário.

   Você deve usar [!DNL Target] e [!DNL Campaign] para configurar diferentes partes da integração:

   * O rawbox e a experiência no [!DNL Target]
   >[!NOTE]
   >
   >Ao usar uma rawbox e [!DNL Target], consulte o aviso de segurança importante em [Criar lista de permissões que especificam hosts autorizados a enviar chamadas de mbox para o Público alvo](/help/administrating-target/hosts.md#allowlist).

   * O delivery em [!DNL Campaign]



## Antes de começar   {#section_FF19BF1BCA064260930BF6C141313B0E}

Antes de usar [!DNL Adobe Campaign] para configurar suas ofertas de email direcionadas, configure o seguinte em [!DNL Target]:

* Duas ou mais ofertas de redirecionamento [!DNL Target]

   Consulte [Criar oferta de redirecionamento](/help/c-experiences/c-manage-content/offer-redirect.md).
* Uma atividade do Target com uma experiência para cada oferta e a [métrica de sucesso](/help/c-activities/r-success-metrics/success-metrics.md) desejada.

   Consulte [Redirecionar para um URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Start a atividade em [!DNL Target] antes de configurar a parte [!DNL Campaign] da integração.

## Incluir uma oferta do Target em um email do Adobe Campaign   {#section_B201BBE27A704E18AF0D553F35695837}

1. Crie um email em [!DNL Adobe Campaign].
1. Nas propriedades do email, clique em **[!UICONTROL Incluir]** > **[!UICONTROL Imagem dinâmica fornecida pelo Adobe Target]**.
1. Selecione a imagem padrão nos ativos compartilhados.
1. Especifique o local (rawbox).
1. Adicione quaisquer outros parâmetros de tomada de decisão, como o gênero do destinatário.
1. Visualize o email, selecionando pelo menos um destinatário por cada oferta (nesse caso, um destinatário do sexo masculino e um do sexo feminino).
1. Em [!DNL Campaign], defina o [!DNL Target] servidor de Borda que você está usando para controlar a atividade e o nome do locatário.
1. Especifique a conta externa usada para [!DNL Adobe Experience Cloud] para que você possa acessar os recursos em [!DNL Experience Cloud].

Para obter mais informações, consulte a documentação [!DNL Adobe Campaign].
