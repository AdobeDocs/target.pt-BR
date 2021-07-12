---
keywords: aumento de receita, receita, estimativa de aumento de receita, calcular aumento, valor estimado
description: Estime o aumento que você pode alcançar se cada visitante visualizar a experiência vencedora, se as tendências continuarem como durante o teste.
title: Qual é a estimativa de aumento da receita?
feature: Administração e configuração
role: Admin
exl-id: a3c5e20e-f5d5-4b6f-b169-59d5916584ab
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 88%

---

# Aumento estimado na receita

Use [!DNL Adobe Target] para fazer uma estimativa do aumento de receita que você obterá se todos os usuários visualizarem a experiência vencedora.

>[!NOTE]
>
>O aumento estimado não está disponível para atividades [!UICONTROL Direcionamento de experiência] (XT) no momento.

Por padrão, o recurso de estimativa de aumento fica desativado. Isso pode ser ativado nas suas preferências de conta. Apenas usuários de Administração da Experience Cloud podem habilitar ou desabilitar esse recurso. Se uma estimativa de aumento for desabilitada, os campos correspondentes não aparecerão na interface. Desabilitar o recurso não resulta em perda de dados, inclusive os dados usados para as estimativas. As estimativas são baseadas em dados coletados independentemente de o recurso estar habilitado ou não.

>[!IMPORTANT]
>
>O aumento estimado é apenas uma estimativa. Sua exatidão depende de uma série de fatores, incluindo números projetados se as tendências atuais continuarem. Esses valores são estimativas baseadas no último desempenho e não devem ser usadas para orientação financeira. Os resultados futuros podem variar.

Esta estimativa calcula a quantidade de aumento alcançado pela experiência vencedora e o seu número total de visitantes durante a atividade e mostra o aumento que você pode alcançar se todos os visitantes visualizarem a experiência vencedora, se as tendências continuarem sendo como durante o teste.

O aumento estimado na receita é calculado com base na receita por visita (RPV) obtida da métrica da meta primária.

O aumento estimado é calculado com o uso da seguinte fórmula: (&lt;RPV de experiência vencedora> - &lt;RPV de experiência de controle&lt;)*&lt;número total de visitantes na atividade>

O número resultante será arredondado para a casa decimal máxima, se a forma condensada tiver apenas um único dígito antes do decimal. Por exemplo: US$ 1,6 milhões, US$ 60 mil, US$ 900, US$ 8,5 mil, US$ 205 mil

Por exemplo, se a sua experiência vencedora mostrar um aumento de US$ 0,59, e sua experiência de controle mostrar um aumento de US$ 0,15, a estimativa calculará um aumento de US$ 0,44 por visitante. Se você tivesse 75.000 visitantes, o aumento resultante na receita seria de US$ 33.000 se todos os visitantes visualizassem a experiência vencedora e se as tendências atuais continuassem.

Da mesma forma, se a sua experiência vencedora mostrar um aumento de US$ 0,17 sobre a experiência de controle, e se você tiver 192.000 visitantes durante o teste, se as tendências atuais continuarem, você poderá esperar um aumento de receita de US$ 32.640.

O aumento estimado no campo de receita será mostrado como &quot;---&quot; nas seguintes circunstâncias:

* Caso não tenha havido visitas suficientes para calcular uma estimativa razoável
* Se o valor estimado da métrica não tiver sido fornecido na página de configuração da métrica
* Se a melhor experiência de execução for o controle

Ao configurar as metas de uma atividade, o campo Valor estimado fornece um valor para sua meta. Este valor permite que o Target calcule o aumento estimado da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. O tipo de dados é a moeda. Este campo é exibido progressivamente depois que o usuário indica a ação realizada para satisfazer o objetivo.

A receita estimada se 100% dos visitantes visualizarem a experiência vencedora será mostrada na parte superior dos relatórios do Target.
