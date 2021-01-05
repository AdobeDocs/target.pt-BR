---
kewords: Automated Personalization;ap;troublshoot;troubleshooting;model;lift
description: Às vezes, as atividades não acontecem como o esperado. Aqui estão alguns possíveis desafios que você pode enfrentar ao usar a Personalização automatizada e algumas soluções sugeridas.
title: Solução de problemas de Personalização automatizada
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 94%

---


# ![PREMIUM](/help/assets/premium.png) Solução de problemas de personalização automatizada{#troubleshoot-automated-personalization}

Às vezes, as atividades não acontecem como o esperado. Aqui estão alguns possíveis desafios que você pode enfrentar ao usar a Personalização automatizada e algumas soluções sugeridas.

## Minha atividade de AP está demorando muito para criar modelos. {#section_20028B204DBB4D77A324BA193434AEE2}

Há várias alterações na configuração das atividades que podem reduzir o tempo esperado para criar modelos, incluindo o número de experiências no teste de Personalização automatizada, o tráfego no site e a métrica de sucesso selecionada.

**Solução:** revise a configuração da atividade e veja se deseja fazer alguma alteração para melhorar a velocidade de criação dos modelos.

* Se sua métrica de sucesso estiver definida como RPV, será possível mudar para conversão? As atividades de conversão tendem a exigir menos tráfego para criar modelos. Você não perderá os dados da atividade se alterar a métrica de sucesso de RPV para conversão.
* Sua métrica de sucesso está bem abaixo do funil de vendas de suas experiências de atividade? Um índice de conversão de atividade mais baixo aumenta os requisitos de tráfego para a criação dos modelos, já que é necessário um número mínimo de conversões.
* É possível excluir alguma oferta ou experiência da sua atividade? Diminuir o número de experiências em uma atividade acelera o tempo para construir os modelos.
* Existe uma página de tráfego mais alto, em tal página essa atividade seria mais bem-sucedida? Quanto mais tráfego e conversões em seus locais de atividade, mais rápidos serão os modelos.

## Minha atividade de AP não gerou nenhum aumento.   {#section_8900BC8968474438B8092F7A94C0C6CF}

Vários fatores são necessários para uma atividade de AP gerar aumento:

* As ofertas precisam ser diferentes o suficiente para influenciar os visitantes.
* As ofertas precisam estar localizadas em um lugar que faça diferença na meta de otimização.
* Deve haver tráfego e &quot;potência&quot; estatística suficiente no teste para detectar o aumento.
* O algoritmo de personalização deve funcionar corretamente.

**Solução:** o melhor curso de ação é garantir que o conteúdo e os locais que compõem as experiências da atividade realmente façam diferença nas taxas de resposta geral usando um teste A/B simples e não personalizado. Certifique-se de calcular os tamanhos das amostras antecipadamente para garantir que haja energia suficiente para ver um aumento razoável e executar o teste A/B por um período fixo sem interrompê-lo ou fazer quaisquer alterações. Se um resultado do teste A/B mostrar um aumento estatisticamente significativo em uma ou mais das experiências, é provável que uma atividade personalizada funcione. Claro, a personalização pode funcionar mesmo se não houver diferenças nas taxas de resposta geral das experiências. Normalmente, o problema decorre de ofertas/locais que não têm um impacto suficientemente grande na meta da otimização para serem detectados com significância estatística.

## O URL da minha atividade de AP está mostrando o conteúdo da oferta nas páginas incorretas.   {#section_82A224406DBF4107B05204BEFBBE458C}

No AP, as regras de teste de URL e modelo são adicionadas à restrição de entrada de solicitação [!DNL Target] (por exemplo, público alvo-global-mbox), onde são avaliadas apenas uma vez. Quando um usuário se qualifica para uma atividade, as regras de definição de metas no nível da solicitação do Público alvo não são reavaliadas. Entretanto, o público-alvo da segmentação é adicionado às regras de direcionamento por localização.

**Solução:** adicione as regras de modelo necessárias como o público-alvo de entrada da campanha. A avaliação do público-alvo ocorre a cada solicitação/chamada.

Isso será corrigido em uma versão futura.

## As métricas dependentes de métrica de conversão nunca convertem. {#section_076D1F44298C4E4A849AC52F5A33214D}

Isso é esperado.

Em uma atividade de AP, depois que uma métrica de conversão (meta de otimização ou meta de publicação) é convertida, o usuário é liberado da experiência e a atividade é reiniciada.

Por exemplo, há uma atividade com uma métrica de conversão (C1) e uma métrica adicional (A1). A1 depende de C1. Quando um visitante entra na atividade pela primeira vez, e os critérios de conversão de A1 e C1 não são convertidos, a métrica A1 não é convertida por depender da métrica de sucesso. Se o visitante converte C1 e depois converte A1, A1 ainda não é convertida porque, assim que C1 é convertida, o visitante é liberado.

## Os URLs da minha experiência não estão funcionando como esperado.   {#section_7B08DA1F30AA483E9406336DAF361BA4}

* Se você não conseguir ver a visualização na nova guia (devido ao cache do navegador), tente atualizar duas ou três vezes ou copie o link e abra-o em um novo navegador ou em uma nova sessão.
* Gere novamente os links de URL da experiência se tiver alterado algum conteúdo e compartilhe os novos links com seus colegas de equipe.

