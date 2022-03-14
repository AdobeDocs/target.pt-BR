---
keywords: Visão geral e referência
description: Saiba como usar o Adobe [!DNL Target] com o Adobe Campaign para otimizar o conteúdo de email.
title: Como integrar [!DNL Target] com o Adobe Campaign?
feature: Integrations
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 41%

---

# Integrar [!DNL Target] com o Adobe Campaign

Use [!DNL Target] com [!DNL Adobe Campaign] para otimizar o conteúdo de email.

Para otimizar seu conteúdo de email, você pode criar uma oferta de redirecionamento em [!DNL Target], em seguida use [!DNL Adobe Campaign] para gerenciar as ofertas de email. Por exemplo, você pode exibir diferentes ofertas para recipients do sexo masculino e feminino.

A integração ocorre quando o email é aberto. Quando o cliente abre o email, é feita uma chamada para [!DNL Target] e uma versão dinâmica do conteúdo é exibida. O conteúdo consiste em uma imagem estática compatível com todos os navegadores. [!DNL Target]O rastreia a reação à oferta no nível do público-alvo ou da sessão, e esses dados são disponibilizados nos relatórios do [!DNL Target]

[!DNL Target]O pode rastrear os seguintes dados:

* Agente do usuário
* Endereço IP
* Localização geográfica
* Segmento associado à ID do visitante em [!DNL Target] (sujeito a aprovação legal)
* Dados de [!DNL Campaign] Datamart

Há várias limitações:

* Como somente uma imagem pode ser usada, não é possível personalizar o conteúdo.
* O rastreamento não é consolidado em [!DNL Adobe Campaign].
* Sem unificação da experiência de usuário.

Use ambos [!DNL Target] e [!DNL Campaign] para configurar diferentes partes da integração:

* A caixa bruta e a experiência em [!DNL Target]

>[!NOTE]
>
>Ao usar um rawbox e o [!DNL Target], consulte o aviso de segurança importante em [Criar listas de permissões que especificam hosts autorizados a enviar chamadas de mbox para o Target](/help/main/administrating-target/hosts.md#allowlist).

* O delivery em [!DNL Campaign]

## Antes de começar {#section_FF19BF1BCA064260930BF6C141313B0E}

Antes de utilizar [!DNL Adobe Campaign] para configurar suas ofertas de email direcionadas, configure o seguinte em [!DNL Target]:

* Dois ou mais [!DNL Target] ofertas de redirecionamento

   Consulte [Criar oferta de redirecionamento](/help/main/c-experiences/c-manage-content/offer-redirect.md).

* A [!DNL Target] com uma experiência para cada oferta e a [métrica de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md).

   Consulte [Redirecionar para um URL](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md).

Inicie a atividade em [!DNL Target] antes de configurar o [!DNL Campaign] parte da integração.

## Inclua um [!DNL Target] em uma [!DNL Adobe Campaign] email {#section_B201BBE27A704E18AF0D553F35695837}

1. Crie um email em [!DNL Adobe Campaign].
1. Nas propriedades do email, clique em **[!UICONTROL Incluir]** > **[!UICONTROL Imagem dinâmica fornecida pelo Adobe Target]**.
1. Selecione a imagem padrão nos ativos compartilhados.
1. Especifique o local (rawbox).
1. Adicione quaisquer outros parâmetros de tomada de decisão, como o gênero do destinatário.
1. Visualize o email, selecionando pelo menos um destinatário por cada oferta (nesse caso, um destinatário do sexo masculino e um do sexo feminino).
1. Em [!DNL Campaign], defina o [!DNL Target] Servidor de borda que você está usando para controlar a atividade e o nome do locatário.
1. Especifique a conta externa usada para o [!DNL Adobe Experience Cloud] para que você possa acessar os recursos no [!DNL Experience Cloud].

Para obter mais informações, consulte [!DNL Adobe Campaign] documentação.

## Vídeo: Integrar [!DNL Target] com [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)
