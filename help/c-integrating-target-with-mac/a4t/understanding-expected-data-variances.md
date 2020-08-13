---
keywords: data variances;analytics;differences;variance;a4t;analytics for target;analytics as the reporting source;discrepancies;discrepancy
description: Informações sobre as variâncias esperadas de dados entre o Target e o Adobe Analytics ao não usar o Analytics como fonte de relatórios (A4T), o que elimina a variância de dados completamente.
title: Variâncias esperadas de dados ao não usar o A4T
feature: a4t troubleshooting
topic: Advanced
uuid: 61bef460-8613-4251-b1b2-b6226ec86d9b
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 100%

---


# Variações de dados esperadas entre o Target e o Analytics ao usar e não usar A4T{#expected-data-variances-when-not-using-a-t}

Informações sobre as variações de dados esperadas entre o [!DNL Target] e o Adobe [!DNL Analytics] ao *usar* ou *não* o Analytics como a Fonte de relatórios (A4T). A4T reduz significativamente a variação de dados.

## Variação de dados esperada ao usar o A4T{#expected-using-a4t}

Com o A4T, os relatórios de atividades do Analytics e do Target usam os dados do Analytics exclusivamente, para que não haja variância entre as soluções nos relatórios de atividade do Target. No entanto, em algumas circunstâncias, os clientes podem comparar os dados do Target aos dados do Analytics fora do escopo da integração do A4T e, assim, experimentar os problemas de variância descritos abaixo.

Estes são alguns cenários nos quais você pode experimentar a variação de dados esperada:

* O A4T permite uma ocorrência do Target (parte superior da página), mas nenhuma ocorrência do Analytics (parte inferior página). Um exemplo disso seria se o usuário carregasse a página, mas fechasse o navegador antes da chamada do Analytics ser disparada. Nesses casos, o A4T exclui a ocorrência do Target de nossos dados. O motivo para isso é que permitir que ocorrências do Target (novamente, na parte superior da página) sejam contabilizadas como ocorrências do Analytics, na ausência de uma chamada real do Analytics, criaria inconsistências com o conjunto de dados no Analytics (aumento de visitantes, etc.).

   Se um teste de redirecionamento estiver configurado no Target para dividir o tráfego 50/50 (ou 25/25/25/25, etc.), o comportamento do usuário pode não ser dividido uniformemente. Caso veja uma divisão desigual, isso significa simplesmente que um grupo de usuários executou menos chamadas do Analytics na landing page do que os outros grupos. Essa falha na execução da chamada do Analytics para um grupo fez com que a ocorrência do Target para esse usuário fosse excluída, criando a desigualdade.

   Esperamos abordar isso no futuro, à medida que trabalhamos com o A4T na Adobe Experience Platform. Nossas equipes estão trabalhando em como lidar da melhor maneira com esses diferentes eventos em momentos distintos na página.

   >[!NOTE]
   >
   >Existe um problema conhecido que faz com que um número limitado de clientes que usam redirecionamentos com A4T vejam uma porcentagem maior de taxas de hit não unificadas. Consulte [Problemas conhecidos e problemas resolvidos](/help/r-release-notes/known-issues-resolved-issues.md#redirect).

* Suponha que você crie uma atividade de Alocação automática aberta a todos os visitantes para uma página específica. Já que as atividades de Alocação automática não são compatíveis com o A4T, todos os dados da atividade são coletados pelo [!DNL Target]. Você pode esperar que os visitantes da atividade no relatório [!DNL Target] correspondam aos visitantes dessa página nos relatórios [!DNL Analytics] para o mesmo intervalo de datas. Este é um cenário no qual a variância descrita abaixo é esperada.

   Para obter uma lista completa dos tipos de atividades que são compatíveis com o A4T, consulte [Tipos de atividade compatíveis](../../c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA).

## Variação de dados esperada quando *não está usando* A4T  {#expected-not-using-a4t}

Variações de 15-20% são normais, mesmo com conjuntos de dados semelhantes. Os sistemas de contam de forma diferente podem resultar em variações de dados muito maiores, como 35-50%. Em alguns casos, as variações podem ser até maiores que isso.

Apesar de os dados reais poderem variar de forma significativa, as tendências normalmente são consistentes. Contanto que as diferenças e as tendências permaneçam constantes, os dados permanecerão valiosos e úteis. Se as diferenças e as tendências forem inconsistentes, isso pode significar que algo foi configurado de forma incorreta. Neste caso, entre em contato com o seu representante de conta para obter ajuda.

[!DNL Analytics]O usa um sistema com base em visitas e transações, enquanto o usa métricas com base em visitantes. [!DNL Target] Isso significa que sempre que um visitante abrir uma página, ela será contada como uma visita, mas [!DNL Analytics] não [!DNL Target] contará a visita até que as condições definidas na atividade sejam atendidas.

Os relatórios do [!DNL Target]mostram o desempenho com base na mbox de conversão selecionada durante a definição da atividade, mas esses dados da mbox de conversão não são enviados para [!DNL Analytics], que tem suas próprias variáveis de conversão, conforme definido pela implementação de tags [!DNL Analytics]. Nos casos em que você espera dados idênticos (por exemplo, se a página de confirmação de pedido de um site de varejo contiver uma mbox de conversão e um [!DNL Analytics]evento de compra), os dados podem diferir devido à colocação dessas tags. Em geral, as tendências dos dois relatórios de produtos devem ser semelhantes.

As variações de dados esperadas podem ser causadas por variações técnicas e comerciais.

### Exemplos de variações técnicas  {#section_C3B50ED2E2F9416FAC91437CF1A87369}

Os itens a seguir podem causar variações técnicas com base em diferenças técnicas:

* [!DNL Target]Os visitantes do devem permitir cookies e JavaScript
* Os cookies próprios e de terceiros são processados de forma diferente e, como resultado, os dados desses tipos de cookies não correspondem
* Localização relativa de tags nas páginas e &quot;vazamento&quot; causado por visitantes que saem da página antes que ela carregue totalmente
* Considerações de fuso-horário
* Diferenças em que os dispositivos podem ser contados

### Exemplos de variações comerciais  {#section_2E1EB5E15BB64A1A80E4CDB1A5062AEE}

Os itens a seguir podem causar variações de dados com base em diferenças comerciais:

* Diferenças entre métricas de visitante e visita
* O direcionamento das atividades exclui alguns visitantes
* É possível localizar uma única mbox em várias páginas, contando visitantes em cada uma dessas páginas
* As prioridades da atividade podem incluir alguns visitantes e excluir outros em uma página
* Os visitantes que se converteram uma vez podem ser contados novamente quando entrarem novamente na atividade
* O [!DNL Analytics] conta todas as conversões de todas as visitas e visitantes, mas o [!DNL Target] conta somente as conversões das visitas e visitantes incluídos na atividade