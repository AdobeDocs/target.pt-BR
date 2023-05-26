---
keywords: variâncias de dados; análises; diferenças; variance; a4T; analytics para target; análises como fonte de relatórios; discrepâncias; discrepância
description: Saiba mais sobre as variações de dados esperadas entre Adobe [!DNL Target] e Analytics quando não estiver usando o Analytics para [!DNL Target] (A4T), que elimina a variância dos dados completamente.
title: Qual é a variação de dados esperada entre o Analytics e o A4T?
feature: Analytics for Target (A4T)
exl-id: 9e63f309-8ec1-4ed5-a1f9-6c3098a7b8f6
source-git-commit: 4abd24f63dd65e65a1d8b07647630eeb640e7a1d
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 46%

---

# Variações de dados esperadas entre Adobe [!DNL Target] e Adobe Analytics ao usar e não usar A4T

Informações sobre as variações de dados esperadas entre o [!DNL Target] e o Adobe [!DNL Analytics] ao *usar* ou *não* o Analytics como a Fonte de relatórios (A4T). A4T reduz significativamente a variação de dados.

## Variação de dados esperada ao usar o A4T {#expected-using-a4t}

Com o A4T, os relatórios de atividades do Analytics e do Target usam os dados do Analytics exclusivamente, para que não haja variância entre as soluções nos relatórios de atividade do Target. No entanto, em algumas circunstâncias, os clientes comparam os dados do Target aos dados do Analytics fora do escopo da integração do A4T e, assim, enfrentam os problemas de variância descritos abaixo.

Estes são alguns cenários nos quais você pode experimentar a variação de dados esperada:

* O A4T permite uma ocorrência do Target (parte superior da página), mas nenhuma ocorrência do Analytics (parte inferior página). Por exemplo, suponha que um visitante carregue a página, mas feche o navegador antes que a chamada do Analytics seja acionada. Nesses casos, o A4T exclui a ocorrência do Target dos dados. Permitir que ocorrências do Target (novamente, na parte superior da página) sejam contadas como ocorrências do Analytics, na ausência de uma chamada real do Analytics, cria inconsistências com o conjunto de dados no Analytics (aumento de visitantes e assim por diante).

   Se um teste de redirecionamento estiver configurado no Target para dividir o tráfego 50/50 (ou 25/25/25/25, e assim por diante), o comportamento do usuário pode não ser dividido uniformemente. Se você vir uma divisão desigual, isso significa simplesmente que um grupo de usuários executou menos chamadas do Analytics na landing page do que os outros grupos. Essa falha na execução da chamada do Analytics para um grupo fez com que a ocorrência do Target para esse usuário fosse excluída, criando a desigualdade.

   A Adobe espera abordar esse problema no futuro, à medida que as equipes do Adobe trabalham em direção ao A4T no Adobe Experience Platform. As equipes do Adobe estão determinando como lidar com esses diferentes eventos em momentos distintos na página.

## Variação de dados esperada quando *não está usando* A4T {#expected-not-using-a4t}

Variações de 15-20% são normais, mesmo com conjuntos de dados semelhantes. Os sistemas de contam de forma diferente podem resultar em variações de dados muito maiores, como 35-50%. Às vezes, as variações podem ser ainda maiores.

Apesar de os dados reais poderem variar de forma significativa, as tendências normalmente são consistentes. Contanto que as diferenças e as tendências permaneçam constantes, os dados permanecerão valiosos e úteis. Se as diferenças e as tendências forem inconsistentes, isso pode significar que algo foi configurado de forma incorreta. Neste caso, entre em contato com o seu representante de conta para obter ajuda.

[!DNL Analytics]O usa um sistema com base em visitas e transações, enquanto o usa métricas com base em visitantes. [!DNL Target] Sempre que um visitante abrir uma página, ela será contada como uma visita no [!DNL Analytics], mas [!DNL Target] O não conta a visita até que as condições definidas na atividade sejam atendidas.

Relatórios em [!DNL Target] mostrar desempenho com base na mbox de conversão selecionada ao definir a atividade. No entanto, esses dados da mbox de conversão não são enviados para [!DNL Analytics], que tem suas próprias variáveis de conversão, conforme definido pela [!DNL Analytics] implementação de marcação. Onde você espera dados idênticos (por exemplo, se o pedido de um varejista confirmar que a página contém uma mbox de conversão e uma [!DNL Analytics] evento de compra), os dados podem diferir devido à colocação dessas tags. Em geral, as tendências nos relatórios dos dois produtos são semelhantes.

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
* Uma única mbox em várias páginas, contando os visitantes em cada uma dessas páginas
* As prioridades de atividade podem incluir alguns visitantes e excluir outros em uma página
* Os visitantes que se converteram uma vez podem ser contados novamente ao entrarem na atividade novamente
* O [!DNL Analytics] conta todas as conversões de todas as visitas e visitantes, mas o [!DNL Target] conta somente as conversões das visitas e visitantes incluídos na atividade
