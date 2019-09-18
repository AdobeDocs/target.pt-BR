---
description: Várias alterações ocorrem no processo de coleta de dados quando o Analytics é habilitado como a fonte de geração de relatórios para o Target (A4T).
keywords: Recommendations
seo-description: Várias alterações ocorrem no processo de coleta de dados quando o Analytics é habilitado como a fonte de geração de relatórios para o Target (A4T).
seo-title: Antes da implementação Adobe Analytics como origem de relatório do Adobe Target (A4T)
solution: Target
title: Antes da implementação
topic: Premium
uuid: fe603a4b-bd61-49f4-b1b7-a0329aa905f5
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Antes da implementação{#before-you-implement}

Várias alterações ocorrem no processo de coleta de dados quando o Analytics é habilitado como a fonte de geração de relatórios para o Target (A4T).

Antes de decidir usar essa integração, revise as seguintes seções e considere o impacto aos seus processos de relatórios:

## Requisitos de implementação {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Antes de começar a usar A4T, você precisa solicitar que sua conta seja provisionada para a integração. Use [este formulário](https://www.adobe.com/go/audiences) para solicitar o aprovisionamento.

Esta integração do A4T requer que você implemente as seguintes versões de biblioteca (ou mais recentes), dependendo se deseja ou não usar ofertas de redirecionamento com o A4T:

### Requisitos necessários se *não* estiver usando ofertas de redirecionamento com o A4T

Essa integração requer que você implemente as seguintes versões de biblioteca (ou mais recentes) se não planeja usar ofertas de redirecionamento com o A4T. A ordem listada é de operações.

* Experience Cloud Visitor ID Service: visitorAPI.js versão 1.8.0
* Adobe Target (dependendo de sua implementação): at.js versão 0.9.1 ou mbox.js versão 61
* Adobe Analytics: appMeasurement.js versão 1.7.0

### Requisitos necessários se estiver usando ofertas de redirecionamento com o A4T

Para usar ofertas de redirecionamento com A4T, você deve implementar as seguintes versões de biblioteca (ou mais recentes). A ordem listada é de operações.

* Experience Cloud Visitor ID Service: visitorAPI.js versão 2.3.0
* Adobe Target: at.js versão 1.6.2

   **Observação:** a biblioteca mbox.js não é compatível com as ofertas de redirecionamento com o A4T. Sua implementação deve usar at.js.

* Adobe Analytics: appMeasurement.js versão 2.1

Download and deployment instructions are listed in [Analytics for Target Implementation](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## O que você deve saber antes da implementação {#section_50D49CC52E11414089C89FB67F9B88F5}

* Esta integração é habilitada em novas atividades ao optar pelo uso do Analytics como fonte de relatórios. As alterações de implementação descritas neste documento não afetam suas atividades existentes.
* O processo de configuração do Analytics como fonte de relatórios para o Target inclui várias etapas da implementação, seguido por uma etapa de provisionamento. É recomendável ler durante o processo, conforme descrito abaixo, antes de fazer a implementação. Após concluir essas etapas, você estará pronto para usar o Analytics como sua fonte de relatórios, assim que ele estiver habilitado para você. O processo de provisionamento pode levar até cinco dias úteis.
* O serviço de ID de visitante cria uma ID de visitante compartilhada na Experience Cloud. Quando não substitui a ID do mboxPC do Target ou a UUID do Audience Manager, ela substitui a maneira como o Analytics identifica novos visitantes. Caso a configuração seja feita corretamente, os visitantes recorrentes do Analytics também deverão ser identificados pela ID antiga do Analytics para evitar o "cliffing" de visitantes. Do mesmo modo que a mboxPCid do Target permanece intacta, os dados de perfil de visitante do Target não são perdidos quando você faz a atualização para o serviço de ID de visitante.
* O serviço de ID do visitante deve executar antes do código de página do Analytics e Target. O `VisitorAPI.js` deve ser exibido acima das tags para todos os outros produtos da Experience Cloud.

## Latência {#section_9489BE6FD21641A4844E591711E3F813}

Após habilitar esta integração, você vai experimentar uma latência adicional de 5 a 10 minutos no Adobe Analytics. O aumento dessa latência permite que os dados do Analytics e Target sejam armazenados no mesmo hit, permitindo dividir os testes por página e seção do site.

Este aumento é refletido em todos os serviços e ferramentas do Adobe Analytics, incluindo a transmissão ao vivo e os relatórios em tempo real e aplicam-se nas seguintes situações:

* Para a transmissão ao vivo, relatórios em tempo real, solicitações de API e dados atualizados para as variáveis de tráfego, somente hits com uma ID de dados adicional são atrasadas.
* Para os dados atuais sobre as métricas de conversão, dados finalizados e feeds de dados, todos os hits são atrasados de 5 a 7 minutos.

Saiba que o aumento da latência começa depois de implementar o serviço de ID de visitante da Experience Cloud, mesmo que essa integração não tenha sido integralmente implementada.

## ID suplementar {#section_2C1F745A2B7D41FE9E30915539226E3A}

Todas as chamadas do Target usadas por uma atividade A4T para entregar conteúdo ou registrar a métrica de meta devem ter um hit do Analytics correspondente que compartilhe a mesma ID suplementar do A4T para funcionar corretamente.

Os hits que contêm dados do Analytics e do Target possuem uma ID de dados adicional. You can see this ID in the [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html) as the `sdid` parameter. Por exemplo: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Esta ID é gerada a qualquer momento em que os seguintes critérios estiverem em vigor:

* O serviço de ID de visitante for implementado
* A versão de [!DNL mbox.js] que suporta essa integração for implementada.

Ao solucionar problemas, confirme que a ID adicional está presente nos hits do Analytics.

## Registro de análises do cliente {#client-side}

Por padrão, quando a at.js, [!DNL Experience Cloud Visitor ID Service] e appMeasurement.js estão na página, [!DNL Adobe Analytics] e [!DNL Target] une os eventos corretamente para fins de relatório e análise no back-end, desde que a ID adicional correta esteja incluída na página, como mencionado acima. Não é necessário gerenciar e executar operações adicionais para a A4T funcionar corretamente.

No entanto, há casos em que você precisa ter mais controle sobre quando e como enviar dados de análise relacionados ao [!DNL Target] para o [!DNL Analytics] para fins de relatório. Você pode ter uma ferramenta de análise interna usada para fins internos, mas também pode enviar os dados de análise ao [!DNL Analytics] por meio de um produto de análise interno, de forma que os outros membros da organização possam continuar a utilizar o [!DNL Analytics] como uma fonte de relatórios visuais. Consulte a [Etapa 7: Referência a at.js ou mbox.js em todas as páginas do site](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) no *Analytics para implementação do Target* para obter mais informações.
