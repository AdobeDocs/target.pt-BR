---
keywords: Recommendations
description: Várias alterações ocorrem no processo de coleta de dados quando o Analytics é habilitado como a fonte de geração de relatórios para o Target (A4T).
title: Antes de implementar o Adobe Analytics como a fonte de relatórios para Adobe Target (A4T)
feature: a4t implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 53%

---


# Antes da implementação{#before-you-implement}

Várias alterações ocorrem no processo de coleta de dados ao ativar [!DNL Analytics] como a fonte de relatórios para [!DNL Target] (A4T).

Antes de decidir usar essa integração, revise as seguintes seções e considere o impacto aos seus processos de relatórios:

## Requisitos de implementação {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Antes de começar a usar A4T, você precisa solicitar que sua conta seja provisionada para a integração. Use o [Formulário de Provisionamento de Integrações de Marketing Cloud](https://www.adobe.com/go/audiences) para solicitar o provisionamento.

Esta integração do A4T requer que você implemente as seguintes versões de biblioteca (ou mais recentes), dependendo se deseja ou não usar ofertas de redirecionamento com o A4T:

### Requisitos necessários se *não* estiver usando ofertas de redirecionamento com o A4T

Essa integração requer que você implemente as seguintes versões de biblioteca (ou mais recentes) se não planeja usar ofertas de redirecionamento com o A4T. A ordem listada é de operações.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versão 1.8.0
* [!DNL Adobe Target] (dependendo de sua implementação): at.js versão 0.9.1 ou mbox.js versão 61
* Adobe Analytics: appMeasurement.js versão 1.7.0

### Requisitos necessários se estiver usando ofertas de redirecionamento com o A4T

Para usar ofertas de redirecionamento com A4T, você deve implementar as seguintes versões de biblioteca (ou mais recentes). A ordem listada é de operações.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versão 2.3.0
* [!DNL Adobe Target]: at.js versão 1.6.2

   **Observação:** a biblioteca mbox.js não é compatível com as ofertas de redirecionamento com o A4T. Sua implementação deve usar at.js.

* Adobe Analytics: appMeasurement.js versão 2.1

As instruções de download e implantação estão listadas em [Analytics para implementação de Públicos alvos](/help/c-integrating-target-with-mac/a4t/a4timplementation.md).

## O que você deve saber antes da implementação {#section_50D49CC52E11414089C89FB67F9B88F5}

* Essa integração é ativada nas novas atividades quando você seleciona usar [!DNL Analytics] como a fonte de relatórios. As alterações de implementação descritas neste documento não afetam suas atividades existentes.
* O processo de configuração de [!DNL Analytics] como fonte de relatórios para [!DNL Target] inclui várias etapas de implementação, seguidas por uma etapa de provisionamento. É recomendável ler durante o processo, conforme descrito abaixo, antes de fazer a implementação. Depois de concluir essas etapas, você estará pronto para usar [!DNL Analytics] como fonte de relatórios assim que ele for ativado para você. O processo de provisionamento pode levar até cinco dias úteis.
* O [!DNL Visitor ID service] cria um [!DNL Visitor ID] compartilhado em [!DNL Adobe Experience Cloud]. Embora não substitua a [!DNL Target] ID da mboxPC ou [!DNL Audience Manager] UUID, ela substitui a maneira como [!DNL Analytics] identifica novos visitantes. Se configurados corretamente, os visitantes de retorno [!DNL Analytics] também devem ser identificados por meio de sua antiga ID [!DNL Analytics] para evitar o cliques em visitantes. Da mesma forma, como a [!DNL Target] mboxPCid permanece intacta, nenhum dado de perfil de visitante [!DNL Target] é perdido quando você atualiza para a [!DNL Visitor ID service].
* O [!DNL Visitor ID service] deve ser executado antes do código [!DNL Analytics] e [!DNL Target] das páginas. Certifique-se de que `VisitorAPI.js` seja exibido acima das tags para todas as outras soluções [!DNL Experience Cloud].

## Latência {#section_9489BE6FD21641A4844E591711E3F813}

Após habilitar esta integração, você vai experimentar uma latência adicional de 5 a 10 minutos no [!DNL Analytics]. Esse aumento de latência permite que os dados de [!DNL Analytics] e [!DNL Target] sejam armazenados na mesma ocorrência, permitindo que você detalhe as atividades por página e seção do site.

Esse aumento se reflete em todos os [!DNL Analytics] serviços e ferramentas, incluindo o relatórios em tempo real e em tempo real, e se aplica nos seguintes cenários:

* Para a transmissão ao vivo, relatórios em tempo real, solicitações de API e dados atualizados para as variáveis de tráfego, somente hits com uma ID de dados adicional são atrasadas.
* Para os dados atuais sobre as métricas de conversão, dados finalizados e feeds de dados, todos os hits são atrasados de 5 a 7 minutos.

Esteja ciente de que a latência aumenta os start após implementar o serviço de ID do visitante [!DNL Experience Cloud], mesmo que você não tenha implementado essa integração totalmente.

## ID suplementar   {#section_2C1F745A2B7D41FE9E30915539226E3A}

Todas as chamadas [!DNL Target] usadas por uma atividade A4T para fornecer conteúdo ou registrar a métrica de objetivo devem ter uma ocorrência [!DNL Analytics] correspondente que compartilha a mesma ID suplementar para que o A4T funcione corretamente.

As ocorrências que contêm dados de [!DNL Analytics] e [!DNL Target] contêm uma ID de dados adicional. Você pode ver essa ID no [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) como o parâmetro `sdid`. Por exemplo: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Esta ID é gerada a qualquer momento em que os seguintes critérios estiverem em vigor:

* O serviço de ID de visitante for implementado
* A versão de [!DNL mbox.js] que suporta essa integração for implementada.

Ao [solucionar problemas](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), confirme se a ID adicional está presente em [!DNL Analytics] ocorrências.

## Registro de análises do cliente {#client-side}

Por padrão, quando a at.js, [!DNL Experience Cloud Visitor ID Service] e appMeasurement.js estão na página, [!DNL Analytics] e [!DNL Target] une os eventos corretamente para fins de relatório e análise no back-end, desde que a ID adicional correta esteja incluída na página, como mencionado acima. Não é necessário gerenciar e executar operações adicionais para a A4T funcionar corretamente.

No entanto, há casos em que você precisa ter mais controle sobre quando e como enviar dados de análise relacionados ao [!DNL Target] para o [!DNL Analytics] para fins de relatório. Você pode ter uma ferramenta de análise interna usada para fins internos, mas também pode enviar os dados de análise ao [!DNL Analytics] por meio de um produto de análise interno, de forma que os outros membros da organização possam continuar a utilizar o [!DNL Analytics] como uma fonte de relatórios visuais. Consulte a [Etapa 7: Referência a at.js ou mbox.js em todas as páginas do site](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) no *Analytics para implementação do Target* para obter mais informações.

## Públicos-alvo compartilhados

Ao preencher o [Formulário de Provisionamento de Integrações de Marketing Cloud](https://www.adobe.com/go/audiences), esteja ciente das seguintes informações importantes sobre a opção [!UICONTROL Audiências compartilhadas] listadas em &quot;[!UICONTROL Para quais recursos você está solicitando o provisionamento]?&quot;

![Formulário de solicitação](/help/c-integrating-target-with-mac/a4t/assets/request-form.png)

Ao solicitar [!UICONTROL Audiências compartilhadas], ative [!UICONTROL Público alvo] e [!UICONTROL Adobe Audience Manager] (AAM) para compartilhar informações, neste caso, audiência.

>[!IMPORTANT]
>
>Essa integração entre [!UICONTROL Público alvo] e AAM acarreta custos adicionais. Você será cobrado por cada chamada [!UICONTROL Público alvo] no AAM.
