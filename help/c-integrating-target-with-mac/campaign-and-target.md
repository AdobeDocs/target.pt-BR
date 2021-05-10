---
keywords: Visão geral e referência
description: Saiba como usar o Adobe [!DNL Target] com o Adobe Campaign para otimizar o conteúdo de email.
title: Como integrar [!DNL Target] ao Adobe Campaign?
feature: Integrações
exl-id: 605b8fe4-e32f-43bc-9131-245008b655e1
translation-type: tm+mt
source-git-commit: f3a9ee9827d635d335cb9707d3d92d0de1bd0304
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 37%

---

# Integrar [!DNL Target] ao Adobe Campaign

Use [!DNL Target] com [!DNL Adobe Campaign] para otimizar o conteúdo do email.

Para otimizar seu conteúdo de email, você pode criar uma oferta de redirecionamento em [!DNL Target], em seguida, usar [!DNL Adobe Campaign] para gerenciar as ofertas de email. Por exemplo, você pode exibir diferentes ofertas para recipients do sexo masculino e feminino.

A integração ocorre quando o email é aberto. Quando o cliente abre o email, é feita uma chamada para [!DNL Target] e é exibida uma versão dinâmica do conteúdo. O conteúdo consiste em uma imagem estática compatível com todos os navegadores. [!DNL Target]O rastreia a reação à oferta no nível do público-alvo ou da sessão, e esses dados são disponibilizados nos relatórios do [!DNL Target]

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

Use [!DNL Target] e [!DNL Campaign] para configurar partes diferentes da integração:

    * A caixa bruta e a experiência em [!DNL Target]
    
     >[!NOTA]
     > 
     > Ao usar um rawbox e [!DNL Target], see the important security notice under [Create allowlists that specify hosts that are authorized to send mbox calls to Target] (/help/administrating-target/hosts.md#lista de permissões).
    
    * O delivery em [!DNL Campaign]

## Antes de começar {#section_FF19BF1BCA064260930BF6C141313B0E}

Antes de usar [!DNL Adobe Campaign] para configurar suas ofertas de email direcionadas, configure o seguinte em [!DNL Target]:

* Duas ou mais ofertas de redirecionamento [!DNL Target]

   Consulte [Criar oferta de redirecionamento](/help/c-experiences/c-manage-content/offer-redirect.md).

* Uma atividade [!DNL Target] com uma experiência para cada oferta e a [métrica de sucesso](/help/c-activities/r-success-metrics/success-metrics.md) desejada.

   Consulte [Redirecionar para um URL](/help/c-experiences/c-visual-experience-composer/redirect-offer.md).

Inicie a atividade em [!DNL Target] antes de configurar a parte [!DNL Campaign] da integração.

## Inclua uma oferta [!DNL Target] em um email [!DNL Adobe Campaign] {#section_B201BBE27A704E18AF0D553F35695837}

1. Crie um email em [!DNL Adobe Campaign].
1. Nas propriedades do email, clique em **[!UICONTROL Incluir]** > **[!UICONTROL Imagem dinâmica fornecida pelo Adobe Target]**.
1. Selecione a imagem padrão nos ativos compartilhados.
1. Especifique o local (rawbox).
1. Adicione quaisquer outros parâmetros de tomada de decisão, como o gênero do destinatário.
1. Visualize o email, selecionando pelo menos um destinatário por cada oferta (nesse caso, um destinatário do sexo masculino e um do sexo feminino).
1. Em [!DNL Campaign], defina o [!DNL Target] servidor de borda que você está usando para controlar a atividade e o nome do locatário.
1. Especifique a conta externa usada para o [!DNL Adobe Experience Cloud] para que você possa acessar os recursos no [!DNL Experience Cloud].

Para obter mais informações, consulte a documentação [!DNL Adobe Campaign] .

## Vídeo: Integrar [!DNL Target] com [!DNL Campaign]

>[!VIDEO](https://video.tv.adobe.com/v/35149)
