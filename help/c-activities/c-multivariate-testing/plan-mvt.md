---
keywords: multivariate test;mvt;mvt plan;multivariate test plan
description: Testes multivariados no Adobe Target exigem planejamento antes de você poder criar um teste bem-sucedido.
title: Planejar um teste multivariado no Adobe Target
feature: mvt
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 97%

---


# Planejar um teste multivariado{#plan-a-multivariate-test}

[!UICONTROL Testes multivariados] (MVT) no [!DNL Adobe Target] exigem planejamento antes de você poder criar um teste bem-sucedido.

Os testes MVT requerem tráfego suficiente para gerar resultados úteis. Antes de configurar seu teste, verifique qual é quantidade de tráfego que geralmente recebe, incluindo o número de impressões e conversas. Essa informação reduzirá a probabilidade de projetar um teste com requisitos que excedam o tráfego do site.

Recomenda-se que os elementos sejam independentes entre si. (Por exemplo, não teste o layout e o conteúdo no mesmo teste.)

Examine o código HTML das páginas que você deseja testar. Verifique se os elementos HTML no site não têm IDs DOM duplicadas. IDs duplicadas podem resultar na entrega do mesmo conteúdo a mais de um local.

Planejar o teste dos elementos na sua página com maior probabilidade de produzir resultados significativos. Um banner ou uma imagem herói, por exemplo, provavelmente gerará mais conversões do que uma mudança no rodapé. A inclusão de elementos menos influentes no seu teste somente aumenta a quantidade de tráfego e o tempo necessários para testar os elementos de maior destaque na página.

Por fim, antes de criar seu teste, você deve criar o conteúdo que deseja testar. Entenda as diferenças de conteúdo de cada oferta e crie imagens, texto, e ofertas de HTML que você espera usar no teste.

## Vídeo de treinamento: Criando testes multivariados (9:25) ![Etiqueta do tutorial](/help/assets/tutorial.png)

Este vídeo monstra como planejar e criar um teste multivariado usando o fluxo de trabalho orientado de três etapas do Target.

* Definir e projetar um teste multivariado
* Criar um teste multivariado

>[!VIDEO](https://video.tv.adobe.com/v/17395)