---
keywords: Recommendations
description: Saiba mais sobre os requisitos de implementação do Analytics para [!DNL Target] (A4T) e o que deve ser considerado antes de implementar essa integração.
title: O que devo saber antes de implementar o A4T?
feature: 'Analytics for Target (A4T) '
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 8c0cdfbe02e9159cf8348e68a782a4268a8df687
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Antes de implementar o Analytics for Target (A4T) com a at.js

Várias alterações ocorrem no processo de coleta de dados ao ativar [!DNL Adobe Analytics] como a fonte de relatórios para [!DNL Adobe Target] (A4T).

Antes de decidir usar essa integração, revise as seguintes seções e considere o impacto aos seus processos de relatórios.

>[!NOTE]
>
>Este artigo se aplica somente às implementações da at.js.

## Requisitos de implementação {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Antes de começar a usar A4T, você deve solicitar que sua conta seja provisionada para a integração. Use o [Formulário de Provisionamento de Integrações do Marketing Cloud](https://www.adobe.com/go/audiences) para solicitar o provisionamento.

Esta integração do A4T requer que você implemente as seguintes versões de biblioteca (ou mais recentes), dependendo se deseja ou não usar ofertas de redirecionamento com o A4T:

### Requisitos necessários se *não* estiver usando ofertas de redirecionamento com o A4T

Essa integração requer que você implemente as seguintes versões de biblioteca (ou mais recentes) se não planeja usar ofertas de redirecionamento com o A4T. A ordem listada é de operações.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versão 1.8.0
* [!DNL Adobe Target] (dependendo de sua implementação): at.js versão 0.9.1 ou mbox.js versão 61
* Adobe Analytics: appMeasurement.js versão 1.7.0

### Requisitos necessários se estiver usando ofertas de redirecionamento com o A4T

Para usar ofertas de redirecionamento com A4T, você deve implementar as seguintes versões de biblioteca (ou mais recentes). A ordem listada é de operações.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versão 2.3.0

   **Observação:**  a at.js 1.8.0 ou superior não funciona mais com as versões da API do visitante anteriores à 2.5.0 para transmitir parâmetros  [!DNL Adobe Audeince Manager] (AAM).

* [!DNL Adobe Target]: at.js versão 1.6.2

   **Observação**: A biblioteca mbox.js não é compatível com as ofertas de redirecionamento com o A4T. Sua implementação deve usar at.js.

* Adobe Analytics: appMeasurement.js versão 2.1

As instruções de download e implantação estão listadas em [Implementação do Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## O que você deve saber antes da implementação {#section_50D49CC52E11414089C89FB67F9B88F5}

* Essa integração é habilitada em novas atividades ao optar por usar [!DNL Analytics] como fonte de relatórios. As alterações de implementação descritas neste documento não afetam suas atividades existentes.
* O processo de configuração [!DNL Analytics] como fonte de relatórios para [!DNL Target] inclui várias etapas de implementação, seguidas por uma etapa de provisionamento. É recomendável ler durante o processo, conforme descrito abaixo, antes de fazer a implementação. Após concluir essas etapas, você estará pronto para usar [!DNL Analytics] como fonte de relatórios quando ele estiver ativado para você. O processo de provisionamento pode levar até cinco dias úteis.
* O [!DNL Visitor ID service] cria um [!DNL Visitor ID] compartilhado no [!DNL Adobe Experience Cloud]. Embora não substitua a [!DNL Target] mboxPC id ou [!DNL Audience Manager] UUID, ela substitui a maneira como [!DNL Analytics] identifica novos visitantes. Se configurada corretamente, os visitantes recorrentes [!DNL Analytics] também devem ser identificados por meio de sua ID [!DNL Analytics] antiga. Da mesma forma, como [!DNL Target] mboxPCid permanece intacta, nenhum dado de perfil de visitante [!DNL Target] é perdido ao atualizar para [!DNL Visitor ID service].
* O [!DNL Visitor ID service] deve ser executado antes do código da página [!DNL Analytics] e [!DNL Target]. Certifique-se de que `VisitorAPI.js` apareça acima das tags para todas as outras soluções [!DNL Experience Cloud].

## Latência {#section_9489BE6FD21641A4844E591711E3F813}

Após habilitar essa integração, haverá de 5 a 10 minutos adicionais de latência em [!DNL Analytics]. O aumento dessa latência permite que os dados de [!DNL Analytics] e [!DNL Target] sejam armazenados na mesma ocorrência, permitindo dividir as atividades por página e seção do site.

Esse aumento é refletido em todos os [!DNL Analytics] serviços e ferramentas, incluindo o fluxo ao vivo e os relatórios em tempo real, e se aplica nos seguintes cenários:

* Para a transmissão ao vivo, relatórios em tempo real, solicitações de API e dados atualizados para as variáveis de tráfego, somente hits com uma ID de dados adicional são atrasadas.
* Para dados atuais sobre métricas de conversão, dados finalizados e feeds de dados, todas as ocorrências são atrasadas de 5 a 7 minutos extras.

O aumento da latência começa após a implementação do serviço de ID de visitante [!DNL Experience Cloud], mesmo que essa integração não tenha sido integralmente implementada.

## ID suplementar  {#section_2C1F745A2B7D41FE9E30915539226E3A}

Todas as chamadas [!DNL Target] usadas por uma atividade A4T para fornecer conteúdo ou registrar a métrica de meta devem ter uma ocorrência [!DNL Analytics] correspondente que compartilha a ID adicional para o A4T para funcionar corretamente.

As ocorrências que contêm dados de [!DNL Analytics] e [!DNL Target] contêm uma ID de dados complementar. Você pode ver essa ID no [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) como o parâmetro `sdid`. Por exemplo: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Esta ID é gerada a qualquer momento em que os seguintes critérios estiverem em vigor:

* O serviço de ID de visitante for implementado
* A versão de [!DNL mbox.js] que suporta essa integração for implementada.

Ao [solucionar problemas](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), confirme se a ID adicional está presente nas ocorrências de [!DNL Analytics].

## Registro de análises do cliente {#client-side}

Se at.js, [!DNL Experience Cloud Visitor ID Service] e appMeasurement.js estiverem na página, [!DNL Analytics] e [!DNL Target] compilarem corretamente os eventos para fins de relatório e análise no back-end, desde que a ID adicional correta esteja incluída na página. Não é necessário gerenciar e executar operações adicionais para que o A4T funcione corretamente.

Há casos em que você pode querer ter mais controle sobre quando e como enviar dados de análise relacionados a [!DNL Target] para [!DNL Analytics] para fins de relatório. Você pode ter uma ferramenta de análise interna usada para fins internos. No entanto, você também deseja enviar os dados de análise para [!DNL Analytics] por meio de seu produto de análise interno, de modo que outros membros da organização possam continuar a usar [!DNL Analytics] como uma fonte de relatórios visuais. Consulte a [Etapa 7: Referência a at.js ou mbox.js em todas as páginas do site](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) no *Analytics para implementação do Target* para obter mais informações.

## Públicos-alvo compartilhados

Ao preencher o [Formulário de Provisionamento de Integrações do Marketing Cloud](https://www.adobe.com/go/audiences), esteja ciente das seguintes informações importantes sobre a opção [!UICONTROL Públicos compartilhados] listada em &quot;[!UICONTROL Para quais recursos você está solicitando o provisionamento]?&quot;

![Formulário de solicitação](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

Ao solicitar [!UICONTROL Públicos-alvo compartilhados], ative [!UICONTROL Target] e [!UICONTROL Adobe Audience Manager] (AAM) para compartilhar informações, neste caso públicos-alvo.

>[!IMPORTANT]
>
>Essa integração entre [!UICONTROL Target] e AAM vem com custos adicionais. Você é cobrado por cada chamada [!UICONTROL Target] no AAM.
