---
keywords: opções do visual experience composer, opções do experience composer, opções de experiência, decisão da oferta, offer decisioning, ajo, jornada otimizer
description: Saiba como adicionar uma decisão de oferta criada em [!DNL Adobe Journey Optimizer] para uma atividade .
title: Como Uso As Decisões De Oferta?
feature: Integrations
exl-id: cec46d5c-bb5e-4cc9-8785-370f158d3f8e
source-git-commit: c6e14884dd0972a2de8c659ddb7a6fd659d083fc
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 2%

---

# Usar decisões de oferta

Use [!DNL Adobe Target] com [!DNL Adobe Journey Optimizer] ofereça decisões para determinar e entregar a próxima melhor oferta para seus visitantes na Web e em dispositivos móveis.

Adicionar decisões de oferta criadas em [!DNL Adobe Journey Optimizer] para [!DNL Target] atividades (manual [!UICONTROL Teste A/B] ou [!UICONTROL Direcionamento de experiência]) usando a variável [!UICONTROL Visual Experience Composer] (VEC) ou [!UICONTROL Compositor baseado em formulário] para testar e entregar ofertas personalizadas para seus visitantes em seus canais de entrada com a tecnologia [!DNL Target].

Para obter mais informações sobre [!DNL Adobe Journey Optimizer] e das decisões de oferta, consulte os seguintes tópicos na *[!DNL Journey Optimizer]* documentação:

* [Introdução ao Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html)

* [Sobre o Gerenciamento de decisões](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html)

## Pré-requisitos

Para usar as decisões de oferta em [!DNL Target], você precisa do seguinte:

* [!DNL Adobe Target Standard] ou [!DNL Adobe Target Premium] implementado com o [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank}.

   O recurso não está disponível ao implementar [!DNL Target] com at.js ou outras [!DNL Target] SDKs.

* [!DNL Adobe Journey Optimizer Ultimate] (AJO + Offer decisioning) ou [!DNL Adobe Experience Platform] e [!UICONTROL offer decisioning] complemento do serviço de aplicativos.

## Casos de uso de exemplo

Os exemplos a seguir são casos de uso de como você pode usar a variável [!DNL Target]/[!DNL Adobe Journey Optimizer] integração para usar as decisões de oferta no [!DNL Target] atividades:

### Comercialização de esportes

Como profissional de marketing de uma liga esportiva, você deseja personalizar o conteúdo de sua página inicial (tanto no desktop quanto no site móvel). Você deseja personalizar o conteúdo com base em várias dimensões e apresentar uma oferta para comprar mercadorias de franquia relacionadas. Você está interessado em:

* A equipe favorita do visitante
* Atividade recente do atleta/reprodutor (por exemplo, movimento de equipe, atualizações de contrato ou ferimentos)

Por exemplo, você deseja fornecer uma experiência personalizada para cada uma das seguintes regiões: Dortmund, Frankfurt e Bochum e para usuários que são fãs implícitos e explícitos dessas equipes. Como métricas, você deseja observar visitas e cliques no site de mercadorias.

Você deseja criar um [!UICONTROL Teste A/B] atividade (divisão 50/50) entre a experiência padrão e a experiência personalizada (que inclui uma decisão de oferta com ofertas para cada região e equipe). Você deseja usar essa atividade para determinar a conversão e o incentivo da experiência personalizada versus controle.

### Plataformas de transmissão de jogos

Como comerciante de uma organização de jogos, você deseja oferecer uma oferta personalizada para uma plataforma de streaming de jogos para usuários de desktop e móveis de diferentes regiões: Alemanha, França, México e Brasil. Quando um visitante acessa o desktop ou site móvel de uma dessas regiões, você deseja oferecer uma oferta de streaming de jogos na linguagem local e com um preço correspondente para a moeda local.

Em [!DNL Adobe Journey Optimizer], você pode criar uma oferta de herói de página inicial personalizada para cada uma das geografias direcionadas mais uma oferta de fallback com um herói de página inicial padrão. Em seguida, é possível criar uma decisão de oferta que incorpore essas ofertas e suas regras de qualificação. Em seguida, em [!DNL Target], você pode criar um [!DNL Experience Targeting] (XT) e insira a decisão da oferta em seu desktop ou site para dispositivos móveis para fornecer a experiência personalizada aos visitantes.

## Crie uma experiência que use uma decisão de oferta:

1. Ao editar ou criar um manual [!UICONTROL Teste A/B] ou [!UICONTROL Direcionamento de experiência] (XT) na atividade do [!UICONTROL Visual Experience Composer] (VEC), clique em um elemento de página para exibir a variável [menu opções](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   ![Menu Opções no Visual Experience Composer](assets/options-menu1.png)

   >[!NOTE]
   >
   >Você também pode criar uma experiência que use [!UICONTROL Decisões de oferta] no [[!UICONTROL Experience Composer baseado em formulário]](/help/main/c-experiences/form-experience-composer.md).

1. Clique em **[!UICONTROL Inserir antes]**, **[!UICONTROL Inserir depois de]** ou **[!UICONTROL Substituir conteúdo]**, depois clique em **[!UICONTROL Decisão da oferta]**.

   O [!UICONTROL Decisão da oferta] está disponível ao editar ou criar [manual [!UICONTROL Teste A/B]](/help/main/c-activities/t-test-ab/test-ab.md#types) ou [[!UICONTROL Direcionamento de experiência]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) somente. Essa opção não está disponível para outros tipos de atividades. As opções disponíveis no menu variam de acordo com o elemento selecionado.

   ![Menu Opções no Visual Experience Composer](assets/options-menu.png)

1. No **[!UICONTROL Adicionar decisão de oferta]** , selecione a sandbox e o posicionamento desejados.

   A [sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/overview.html){target=_blank} in the [!DNL Adobe Experience Platform] lets you partition your instance into virtual environments. For example, you might have a production environment and a staging environment. A [placement](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/create-components/creating-placements.html){target=_blank} em [!DNL Adobe Journey Optimizer] ajuda a garantir que o conteúdo da oferta correto seja exibido no local certo.

   ![Listas suspensas de sandbox e disposições na caixa de diálogo Adicionar decisão da oferta](/help/main/c-integrating-target-with-mac/ajo/assets/sandbox-placement.png)

1. Selecione a decisão de oferta desejada e clique em **[!UICONTROL Criar]**.

   ![Decisão de oferta selecionada na caixa de diálogo Adicionar decisão de oferta](assets/offer-decision.png)

   Seu site é exibido no VEC, onde você pode ver a decisão da oferta recém-criada na seção [!UICONTROL Modificações] no lado direito. Você pode passar o mouse sobre a modificação e clicar no botão [!UICONTROL Visualizar] ícone para examinar a decisão da oferta.

   ![Ícone Visualizar](assets/preview-icon.png)

   Você pode examinar as várias ofertas contidas na oferta clicando no ícone apropriado na parte inferior da [!UICONTROL Visualização da oferta] , incluindo a oferta de fallback. Uma oferta de fallback é a oferta padrão exibida quando um visitante não está qualificado para nenhuma das ofertas personalizadas na coleção.

   ![Visualização da oferta](assets/offer-preview.png)

1. Termine de criar a atividade completando o [!UICONTROL Direcionamento] e [!UICONTROL Metas e configurações] etapas do fluxo de trabalho guiado de três partes.

   >[!IMPORTANT]
   >
   >Para garantir que [!DNL Target] atividade é personalizada, verifique se as datas de início/término da atividade atual estão sincronizadas com as datas de início/término da decisão de oferta em [!DNL Adobe Journey Optimizer]. Se a variável [!DNL Target] as datas de início/término estão fora do intervalo de datas de início/término da decisão de oferta, o padrão [!DNL Target] conteúdo é exibido para os visitantes.

   ![Mensagem de aviso de decisão de oferta](/help/main/c-integrating-target-with-mac/ajo/assets/offer-decision-warning.png)

## Notas e limitações

Considere as seguintes informações ao trabalhar com as decisões de oferta:

* A integração do offer decisioning funciona para [!DNL Target] com base na variável [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank}. Este recurso não está disponível ao implementar [!DNL Target] com at.js ou outras [!DNL Target] SDKs.

* O [!DNL Target]/[!DNL Adobe Journey Optimizer] suporte à integração [manual [!UICONTROL Teste A/B]](/help/main/c-activities/t-test-ab/test-ab.md#types) e [[!UICONTROL Direcionamento de experiência]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) somente. Esse recurso não está disponível para outros tipos de atividades.

* Não é possível usar [[!UICONTROL Analytics como fonte de relatórios]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) se estiver usando decisões de oferta em uma atividade do . Choose [!DNL Target] como a fonte de relatórios no [!UICONTROL Metas e configurações] durante a configuração da atividade, se você usar as decisões da oferta na atividade .

* As ofertas com o tipo de conteúdo text/html não são compatíveis com a entrega de conteúdo deliveryURL. O deliveryURL é compatível com o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) somente onde o cliente é responsável por buscar e compor explicitamente o conteúdo.

* [!DNL Target] O relatório não fornece relatórios de nível de decisão de oferta.

* Visualização [Links de Controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md) para [!DNL Target] as experiências que contêm decisões de oferta afetam o limite de frequência definido em [!DNL Adobe Journey Optimizer] para essas decisões de oferta.
