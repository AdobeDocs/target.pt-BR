---
keywords: redirecionar;redirecionar URL;enviar para página diferente;redirect;redirect url;send to different page
description: Saiba como usar a opção Redirecionar para URL no Adobe [!DNL Target] quando quiser enviar o visitante para uma página diferente, em vez de mostrar o conteúdo na mesma página.
title: Posso redirecionar uma página para um URL diferente?
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
TQID: 'https://experienceleague.adobe.com/8Bh5z7SRWw3QqKQMHZck01GKVBtMufwLbw9JxLsSACU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 2%
---
# Redirecionar para um URL {#redirect-to-url}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como usar a opção **[!UICONTROL Redirecionar para URL]** para enviar visitantes para uma página diferente, em vez de mostrar o conteúdo na mesma página.

>[!ENDSHADEBOX]

A opção **[!UICONTROL Redirecionar para URL]** em [!DNL Adobe Target] envia um visitante para uma página diferente em vez de mostrar o conteúdo na mesma página. Ela se adapta à comparação de duas páginas completamente diferentes, em vez de alterações em partes de conteúdo dentro de uma página. Em seguida, um teste A/B compara a página A com a página B: uma experiência aponta para a página A padrão e a outra redireciona para a página B.

Uma oferta de redirecionamento executa o código JavaScript que redireciona o navegador. O código usa o método `window.location.replace();`, de modo que a página a partir da qual o visitante é redirecionado não é armazenada no histórico do navegador. Portanto, o visitante ainda pode usar o botão Voltar do navegador.

## Criar uma oferta de redirecionamento {#create-redirect-offer}

A experiência de redirecionamento define a página para a qual os visitantes são enviados e, opcionalmente, as condições do redirecionamento.

1. Crie uma experiência.

1. No quadro **[!UICONTROL Experiências]**, clique no ícone **[!UICONTROL Mais Ações]** ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmallList.svg) ) da experiência com redirecionamentos.

1. Clique em **[!UICONTROL Redirecionar para a URL]**.

   ![Ícone Mais Ações](assets/redirect_1.png)

1. Na caixa de diálogo **[!UICONTROL Redirecionar para URL]**, digite a URL da página B.

   ![Ícone Mais Ações](assets/redirect_2.png)

1. (Opcional) Selecione a opção para incluir os parâmetros de consulta atuais.

   Quando essa opção é selecionada, tudo depois de `?` no URL do visitante é anexado ao URL de redirecionamento no momento do redirecionamento.

## Limitações

As ofertas de redirecionamento têm as seguintes limitações:

* **A4T:** uma oferta de redirecionamento em uma atividade que usa o A4T requer uma implementação que atende a certos requisitos mínimos, e outras informações importantes se aplicam. Consulte [Ofertas de redirecionamento - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
* **Experience Composer baseado em formulário:** não use uma oferta de redirecionamento em mboxes que façam parte da página. Use uma oferta de redirecionamento somente a partir de uma marca de script que faz parte da HTML `<head>`, e sempre use a criação automática e defina a oferta de redirecionamento para a mbox global.

>[!NOTE]
>
>Para passar o valor do referenciador da landing page, use uma oferta do HTML em vez de uma oferta de redirecionamento.

## Problemas conhecidos

As atividades de redirecionamento nas implementações da at.js podem fazer com que o URL de visualização entre em loop, com a oferta entregue repetidamente. Em vez disso, use o [Modo de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md) para visualizar e testar a atividade. Esse problema não afeta o delivery real da oferta. (TGT-23019)
