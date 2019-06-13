---
description: Use o Target com o Adobe Campaign para otimizar o conteúdo de email.
keywords: Visão geral e referência
seo-description: Use o Target com o Adobe Campaign para otimizar o conteúdo de email.
seo-title: Integração do Target ao Adobe Campaign
solution: Target
title: Integração do Target ao Adobe Campaign
topic: Padrão
uuid: 1a5b70e6-d501-4b52-bec8-4ae2c419d331
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Integração do Target ao Adobe Campaign{#integrate-target-with-adobe-campaign}

Use o Target com o Adobe Campaign para otimizar o conteúdo de email.

Para otimizar seu conteúdo de email, por exemplo, para exibir diferentes ofertas para destinatários do sexo masculino ou feminino, você pode criar uma oferta de redirecionamento no Target e usar o Adobe Campaign para gerenciar as ofertas de email.

A integração ocorre quando o email é aberto. Quando o cliente abre o email, é feita uma chamada para o Target, e é exibida uma versão dinâmica do conteúdo. O conteúdo consiste em uma imagem estática compatível com todos os navegadores. O Target rastreia a reação à oferta no nível do público-alvo ou da sessão, e esses dados são disponibilizados nos relatórios do Target.

O Target pode rastrear os seguintes dados:

* Agente do usuário
* Endereço IP
* Localização geográfica
* Segmento associado à ID de visitante no Target (sujeito a aprovação legal)
* Dados do Campaign Datamart

Há várias limitações:

* Como somente uma imagem pode ser usada, não é possível personalizar o conteúdo.
* O rastreamento não é consolidado no Adobe Campaign.
* Sem unificação da experiência de usuário.

   Você deve usar o Target e o Campaign para configurar diferentes partes da integração:

   * O rawbox e a experiência no Target
   * A entrega no Campaign

## Antes de começar {#section_FF19BF1BCA064260930BF6C141313B0E}

Antes de usar o Adobe Campaign para configurar ofertas de email direcionadas, configure o seguinte no Target:

* Duas ou mais ofertas de redirecionamento no Target

   Consulte [Criar uma Oferta de redirecionamento](https://marketing.adobe.com/resources/help/pt_BR/target/target/t_offer_redirect.html).
* Uma atividade do Target com experiência para cada oferta e a [métrica de sucesso desejada](https://marketing.adobe.com/resources/help/pt_BR/target/target/r_success_metrics.html).

   Consulte [Redirecionar para um URL](https://marketing.adobe.com/resources/help/pt_BR/target/target/t_redirect_offer.html).

Inicie a atividade no Target antes de configurar a parte do Campaign na integração.

## Incluir uma oferta do Target em um email do Adobe Campaign {#section_B201BBE27A704E18AF0D553F35695837}

1. Crie um email no Adobe Campaign.
1. Nas propriedades de email, clique em **[!UICONTROL Incluir]** &gt; **[!UICONTROL Imagem dinâmica fornecida pelo Adobe Target]**.
1. Selecione a imagem padrão nos ativos compartilhados.
1. Especifique o local (rawbox).
1. Adicione quaisquer outros parâmetros de tomada de decisão, como o gênero do destinatário.
1. Visualize o email, selecionando pelo menos um destinatário por cada oferta (nesse caso, um destinatário do sexo masculino e um do sexo feminino).
1. No Campaign, defina o servidor do Target Edge que você está usando para controlar a atividade e o nome do usuário.
1. Especifique a conta externa usada para a Experience Cloud, de modo que você possa acessar os recursos na Experience Cloud.

Consulte a documentação do Adobe Campaign para obter mais informações.
