---
description: Testes multivariados no Adobe Target exigem planejamento antes de você poder criar um teste bem-sucedido.
keywords: teste multivariado, mvt, plano de mvt, plano de teste multivariado
seo-description: Testes multivariados no Adobe Target exigem planejamento antes de você poder criar um teste bem-sucedido.
seo-title: Planeje um teste multivariado no Adobe Target
solution: Target
title: Planejar um teste multivariado
uuid: f286d08a-e11d-4a39-8c62-3eba99885299
translation-type: tm+mt
source-git-commit: c6085fae6428cb837eed6eadd778140687348817

---


# Planejar um teste multivariado{#plan-a-multivariate-test}

[!UICONTROL Testes multivariados] (MVT) exigem [!DNL Adobe Target] planejamento antes de você poder criar um teste bem-sucedido.

O MVT requer tráfego suficiente para gerar resultados úteis. Antes de configurar seu teste, verifique qual é quantidade de tráfego que geralmente recebe, incluindo o número de impressões e conversas. Essa informação reduzirá a probabilidade de projetar um teste com requisitos que excedam o tráfego do site.

Recomenda-se que os elementos sejam independentes entre si. (Por exemplo, não teste o layout e o conteúdo no mesmo teste.)

Examine o código HTML das páginas que você deseja testar. Verifique se os elementos HTML no site não têm IDs DOM duplicadas. IDs duplicadas podem resultar na entrega do mesmo conteúdo a mais de um local.

Planejar o teste dos elementos na sua página com maior probabilidade de produzir resultados significativos. Por exemplo, um banner ou uma imagem principal provavelmente resultará em mais conversões do que uma alteração no rodapé. A inclusão de elementos menos influentes no seu teste somente aumenta a quantidade de tráfego e o tempo necessários para testar os elementos de maior destaque na página.

Por fim, antes de criar seu teste, você deve criar o conteúdo que deseja testar. Entenda as diferenças de conteúdo de cada oferta e crie imagens, texto, e ofertas de HTML que você espera usar no teste.

## Vídeo de treinamento: Criação de testes multivariados (9:25)

Este vídeo monstra como planejar e criar um teste multivariado usando o fluxo de trabalho orientado de três etapas do Target.

* Definir e projetar um teste multivariado
* Criar um teste multivariado

>[!VIDEO](https://video.tv.adobe.com/v/17395?captions=por_br)