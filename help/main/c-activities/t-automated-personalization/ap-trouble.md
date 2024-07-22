---
kewords: Automated Personalization;ap;troublshoot;troubleshooting;model;lift
description: Explore os possíveis desafios que você pode enfrentar ao usar as atividades de [!UICONTROL Automated Personalization] (AP) no Adobe Target, juntamente com as soluções sugeridas.
title: Como solucionar problemas de atividades de [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
source-git-commit: 2cb2c2b68f6487d1af41ecc7e73750afa1ad85f9
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 32%

---

# Solução de problemas [!UICONTROL Automated Personalization]

Às vezes, as atividades não acontecem como o esperado. Aqui estão alguns possíveis desafios que você poderá enfrentar ao usar o [!UICONTROL Automated Personalization] (AP) e algumas soluções sugeridas.

## Minha atividade [!UICONTROL Automated Personalization] está demorando muito para criar modelos. {#section_20028B204DBB4D77A324BA193434AEE2}

+++Ver detalhes

Há várias alterações de configuração de atividade que podem diminuir o tempo esperado para criar modelos, incluindo o número de experiências em sua atividade [!UICONTROL Automated Personalization], o tráfego para seu site e sua métrica de sucesso selecionada.

**Solução:** revise sua configuração de atividade e veja se há alterações que você deseja fazer para melhorar a velocidade de criação dos modelos.

* Se sua métrica de sucesso estiver definida como RPV, será possível mudar para conversão? As atividades de conversão tendem a exigir menos tráfego para criar modelos. Você não perderá os dados da atividade se alterar a métrica de sucesso de RPV para conversão.
* Sua métrica de sucesso está bem abaixo do funil de vendas de suas experiências de atividade? Um índice de conversão de atividade mais baixo aumenta os requisitos de tráfego para a criação dos modelos, já que é necessário um número mínimo de conversões.
* É possível excluir alguma oferta ou experiência da sua atividade? A diminuição do número de experiências em uma atividade acelera o tempo de criação de modelos.
* Há uma página de tráfego mais alto em que essa atividade seria mais bem-sucedida? Quanto mais tráfego e conversões houver nos locais de atividade, mais rápido será a criação de modelos.

+++

## Minha atividade [!UICONTROL Automated Personalization] não gerou aumento. {#section_8900BC8968474438B8092F7A94C0C6CF}

+++Ver detalhes

Há vários fatores necessários para uma atividade [!UICONTROL Automated Personalization] gerar aumento:

* As ofertas devem ser diferentes o suficiente para influenciar os visitantes.
* As ofertas devem estar localizadas em algum lugar que faça diferença para a meta de otimização.
* Deve haver tráfego e &quot;potência&quot; estatística suficiente no teste para detectar o aumento.
* O algoritmo de personalização deve funcionar corretamente.

**Solução:** o melhor curso de ação é garantir que o conteúdo e os locais que compõem as experiências da atividade realmente façam diferença nas taxas de resposta geral usando um teste A/B simples e não personalizado. Certifique-se de calcular os tamanhos das amostras antecipadamente. A computação antecipada de tamanhos de amostra ajuda a garantir que haja energia suficiente para se observar um aumento razoável. Em seguida, você pode executar o teste A/B por uma duração fixa sem pará-lo ou fazer alterações. Se um resultado de teste A/B mostrar aumento estatisticamente significativo em uma ou mais experiências, é provável que uma atividade personalizada seja bem-sucedida. O Personalization pode funcionar mesmo se não houver diferenças nas taxas de resposta geral das experiências. Normalmente, o problema decorre das ofertas ou dos locais que não têm um impacto grande o suficiente na meta de otimização para serem detectados com significância estatística.

+++

## O URL da minha atividade [!UICONTROL Automated Personalization] está mostrando o conteúdo da oferta nas páginas incorretas. {#section_82A224406DBF4107B05204BEFBBE458C}

+++Ver detalhes

Em [!UICONTROL Automated Personalization], as regras de teste de modelo e URL são adicionadas à restrição de entrada de solicitação [!DNL Target] (por exemplo, target-global-mbox), onde são avaliadas apenas uma vez. Depois que um usuário é qualificado para uma atividade, as regras de direcionamento no nível da solicitação do Target não são reavaliadas. Entretanto, o público-alvo da segmentação é adicionado às regras de direcionamento por localização.

**Solução:** adicione as regras de modelo necessárias como o público-alvo de entrada da atividade. A avaliação do público-alvo ocorre a cada solicitação/chamada.

+++

## As métricas dependentes de uma métrica de conversão nunca convertem. {#section_076D1F44298C4E4A849AC52F5A33214D}

+++Ver detalhes

Isso é esperado.

Em uma atividade [!UICONTROL Automated Personalization], depois que uma métrica de conversão (objetivo de otimização ou de postagem) é convertida, o visitante é liberado da experiência e a atividade é reiniciada.

Por exemplo, há uma atividade com uma métrica de conversão (C1) e uma métrica adicional (A1). A1 depende de C1. Quando um visitante entra na atividade pela primeira vez, e os critérios de conversão de A1 e C1 não são convertidos, a métrica A1 não é convertida por depender da métrica de sucesso. Se o visitante converter C1 e depois converter A1, A1 ainda não será convertido porque quando C1 é convertido, o visitante é liberado.

+++

## Os URLs da minha experiência não estão funcionando como esperado.  {#section_7B08DA1F30AA483E9406336DAF361BA4}

+++Ver detalhes

* Se não conseguir ver a visualização na nova guia (devido ao cache do navegador), tente atualizar duas ou três vezes. Você também pode copiar o link e abri-lo em um novo navegador ou em uma nova sessão.
* Gere novamente os links de URL da experiência se tiver alterado algum conteúdo e compartilhe os novos links com seus colegas de equipe.

+++
