---
kewords: redirect;redirect url;send to different page
description: Saiba como usar a opção Redirecionar para URL no Adobe [!DNL Target] quando quiser enviar o visitante para uma página diferente, em vez de mostrar o conteúdo na mesma página.
title: Posso redirecionar uma página para um URL diferente?
feature: Visual Experience Composer (VEC)
exl-id: bd448482-0079-4689-aa24-65ecbb31b8ae
TQID: https://experienceleague.adobe.com/8Bh5z7SRWw3QqKQMHZck01GKVBtMufwLbw9JxLsSACU
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 485
ht-degree: 80%

---

# Redirecionar para um URL

Use a opção [!UICONTROL Redirecionar para URL] em [!DNL Adobe Target] quando desejar enviar o visitante para uma página diferente em vez de mostrar o conteúdo na mesma página.

Você pode ter duas páginas completamente diferentes para testar, em vez de mudar apenas partes do conteúdo dentro de uma página. Neste caso, o teste A/B compara a página A versus a página B. Configure uma campanha de testes A/B, com duas experiências: uma apontando para a página A padrão e a outra redirecionando para a página B. No menu Ação da experiência, localizado ao clicar no rótulo da letra da experiência, escolha **[!UICONTROL Redirecionar para URL]** e especifique o URL da página B. A oferta é configurada para redirecionar o visitante para uma página diferente.

A oferta de redirecionamento executa um código JavaScript para redirecionar o navegador. Ela usa o método `window.location.replace();`, de forma que a página a partir da qual o visitante é redirecionado não é armazenada no histórico do navegador. Isso permite que o visitante consiga utilizar o botão Voltar de seu navegador.

Ofertas de redirecionamento possuem algumas limitações:

* Para ofertas de redirecionamento em atividades usando A4T, sua implementação deve atender certos requisitos mínimos. Além disso, há informações importantes que você precisa saber. Para obter mais informações, consulte [Perguntas frequentes das Ofertas de redirecionamento - A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* Ao usar o Experience Composer baseado em formulários, ofertas de redirecionamento não devem ser usadas em mboxes que façam parte da página. Uma oferta de redirecionamento deve ser usada somente a partir de uma tag de script que faz parte do `<head>` do HTML. Você sempre deve usar a criação automática e definir a oferta de redirecionamento para a mbox global.

>[!NOTE]
>
>Se desejar passar o valor referenciador da página de destino, é recomendado usar uma oferta HTML em vez de uma oferta de redirecionamento.

Para criar uma oferta de redirecionamento:

1. Crie uma experiência.
1. No quadro [!UICONTROL Experiências], clique no ícone **[!UICONTROL Mais Ações]** ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmallList.svg) ) para a experiência desejada.
1. Clique em **[!UICONTROL Redirecionar para a URL]**.
1. Na caixa de diálogo Redirecionar para URL, digite o URL.
1. Se desejar, selecione a opção para incluir parâmetros de consulta atuais.

   Se essa opção for selecionada, tudo depois de ? no URL do visitante será anexado ao URL de redirecionamento no momento do redirecionamento.

1. (Opcional) Crie regras adicionais.

   Regras adicionais podem ser baseadas em qualquer um dos seguintes:

   * URL
   * Domínio
   * Caminho
   * Fragmento em hash (#)
   * Consulta
   * Parâmetro da mbox

   Regras adicionais podem ser unidas no URL da atividade com AND ou OR. Todas regras que você adicionar são avaliadas contra si próprias com AND.

## Problemas conhecidos

* As atividades de redirecionamento nas implementações da at.js podem fazer com que o URL de visualização entre em loop (a oferta é entregue repetidamente). Você pode usar o [Modo de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md) para realizar a Visualização e o QA. Esse problema não afeta o recebimento real da oferta. (TGT-23019)
