---
keywords: teste multivariado, mvt, plano de mvt, plano de teste multivariado
description: Saiba como planejar um [!UICONTROL Multivariate Test] no [!DNL Adobe Target] para criar um teste bem-sucedido.
title: Como planejo um [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: 130718d5-7bd9-4b1a-b81a-7a146f0ffd0d
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 64%

---

# Planejar um [!UICONTROL Multivariate Test]

[!UICONTROL Multivariate Tests] atividades (MVT) em [!DNL Adobe Target] exigem planejamento antes de você poder criar um teste bem-sucedido.

O MVT requer tráfego suficiente para gerar resultados úteis. Antes de configurar seu teste, verifique qual é quantidade de tráfego que geralmente recebe, incluindo o número de impressões e conversas. Ter essas informações ajuda a reduzir a probabilidade de projetar um teste com requisitos que excedem o tráfego do site.

Os elementos devem ser independentes um do outro. Por exemplo, não teste o layout e o conteúdo no mesmo teste.

Examine o código de HTML das páginas que você deseja testar. Verifique se os elementos HTML no site não têm IDs DOM duplicadas. IDs duplicadas podem resultar na entrega do mesmo conteúdo a mais de um local.

Planejar o teste dos elementos na sua página com maior probabilidade de produzir resultados significativos. Um banner ou uma imagem herói, por exemplo, provavelmente gerará mais conversões do que uma mudança no rodapé. A inclusão de elementos menos influentes no seu teste somente aumenta a quantidade de tráfego e o tempo necessários para testar os elementos de maior destaque na página.

Por fim, antes de criar seu teste, você deve criar o conteúdo que deseja testar. Entenda as diferenças de conteúdo de cada oferta e crie imagens, texto, e ofertas de HTML que você espera usar no teste.

## Vídeo de treinamento: Criação de testes multivariados (9:25) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo demonstra como planejar e criar um teste multivariado usando o fluxo de trabalho guiado de três etapas do [!DNL Target].

* Definir e projetar um teste multivariado
* Criar um teste multivariado

>[!VIDEO](https://video.tv.adobe.com/v/30985?captions=por_br)
