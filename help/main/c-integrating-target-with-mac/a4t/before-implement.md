---
keywords: Recommendations
description: Saiba mais sobre os requisitos de implementação do Analytics for [!DNL Target] (A4T) e o que considerar antes de implementar essa integração.
title: O Que Devo Saber Antes De Implementar O A4T?
feature: Analytics for Target (A4T)
exl-id: 1c98b20b-4dd1-4011-b0cd-5096471af095
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '936'
ht-degree: 23%

---

# Antes de implementar o Analytics for Target (A4T) com a at.js

Várias alterações ocorrem no seu processo de coleta de dados ao habilitar o [!DNL Adobe Analytics] como fonte de relatórios para o [!DNL Adobe Target] (A4T).

Antes de decidir usar essa integração, analise as seções a seguir e considere o impacto nos processos de relatório.

>[!NOTE]
>
>Este artigo se aplica somente às implementações da at.js.

## Requisitos de implementação {#section_A0D2EF18033D4C3997B08A6EBB34C17A}

>[!IMPORTANT]
>
>Antes de começar a usar o A4T, você deve solicitar que sua conta seja provisionada para a integração. Use o [Formulário de Provisionamento de Integrações do Marketing Cloud](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank} para solicitar o provisionamento.

Essa integração do A4T requer que você implemente as seguintes versões de biblioteca (ou mais recentes), dependendo se deseja ou não usar ofertas de redirecionamento com o A4T.

>[!NOTE]
>
>Os seguintes requisitos listam as *versões mínimas* da at.js necessárias para implementar o A4T. A equipe do [!DNL Target] mantém apenas duas versões do [!DNL at.js]—a versão atual e a segunda versão mais recente. Atualize a [!DNL at.js] conforme necessário para garantir que você esteja executando uma versão suportada. Para obter mais informações sobre o que há de novo em cada versão, consulte [Detalhes da versão da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank}.

### Requisitos necessários se *não* estiver usando ofertas de redirecionamento com o A4T

Essa integração requer que você implemente as seguintes versões de biblioteca (ou mais recentes) se não planeja usar ofertas de redirecionamento com o A4T. A ordem listada é de operações.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versão 1.8.0
* [!DNL Adobe Target]: at.js versão 0.9.1
* Adobe Analytics: appMeasurement.js versão 1.7.0

Para obter informações sobre como implementar o A4T com o [!DNL Platform Web SDK], consulte [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank}.

### Requisitos necessários se estiver usando ofertas de redirecionamento com o A4T

Para usar ofertas de redirecionamento com A4T, você deve implementar as seguintes versões de biblioteca (ou mais recentes). A ordem listada é de operações.

* [!DNL Experience Cloud Visitor ID Service]: visitorAPI.js versão 2.3.0

  >[!NOTE]
  >
  >O at.js 1.8.0+ e o at.js 2.x+ não funcionam mais com as versões da API do visitante anteriores à 2.5.0 para transmitir parâmetros do Adobe Audience Manager (AAM).

* [!DNL Adobe Target]: at.js versão 1.6.2

* Adobe Analytics: appMeasurement.js versão 2.1

As instruções de download e implantação estão listadas em [Implementação do Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

Para obter informações sobre como implementar o A4T com o [!DNL Platform Web SDK], consulte [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank}.

## O que você deve saber antes da implementação {#section_50D49CC52E11414089C89FB67F9B88F5}

* Essa integração é habilitada em novas atividades quando você seleciona usar [!DNL Analytics] como fonte de relatórios. As alterações de implementação descritas neste documento não afetam suas atividades existentes.
* O processo de configurar o [!DNL Analytics] como fonte de relatórios para [!DNL Target] inclui várias etapas de implementação, seguidas por uma etapa de provisionamento. É recomendável ler durante o processo, conforme descrito abaixo, antes de fazer a implementação. Após concluir essas etapas, você estará pronto para usar o [!DNL Analytics] como fonte de relatórios quando ele estiver habilitado para você. O processo de provisionamento pode levar até cinco dias úteis.
* O [!DNL Visitor ID service] cria um [!DNL Visitor ID] compartilhado em [!DNL Adobe Experience Cloud]. Embora não substitua a ID de mboxPC [!DNL Target] ou a UUID [!DNL Audience Manager], ela substitui a forma como [!DNL Analytics] identifica novos visitantes. Se configurada corretamente, os visitantes [!DNL Analytics] recorrentes também deverão ser identificados por meio de sua ID [!DNL Analytics] antiga. Da mesma forma, como a mboxPCid [!DNL Target] permanece intacta, nenhum dado de perfil de visitante do [!DNL Target] é perdido ao atualizar para o [!DNL Visitor ID service].
* O [!DNL Visitor ID service] deve ser executado antes do código de página [!DNL Analytics] e [!DNL Target]. Verifique se `VisitorAPI.js` aparece acima das marcas para todas as outras soluções [!DNL Experience Cloud].

## Latência {#section_9489BE6FD21641A4844E591711E3F813}

Após habilitar esta integração, haverá de 5 a 10 minutos extras de latência em [!DNL Analytics]. O aumento dessa latência permite que os dados de [!DNL Analytics] e [!DNL Target] sejam armazenados na mesma ocorrência, permitindo dividir as atividades por página e seção do site.

Esse aumento se reflete em todos os serviços e ferramentas do [!DNL Analytics], incluindo os relatórios em tempo real e em fluxo ao vivo, e se aplica aos seguintes cenários:

* Para a transmissão ao vivo, relatórios em tempo real, solicitações de API e dados atualizados para as variáveis de tráfego, somente hits com uma ID de dados adicional são atrasadas.
* Para dados atuais sobre métricas de conversão, dados finalizados e feeds de dados, todas as ocorrências são atrasadas em mais 5 a 7 minutos.

O aumento da latência começa após a implementação do serviço de ID de visitante do [!DNL Experience Cloud], mesmo que essa integração não tenha sido integralmente implementada.

## ID suplementar  {#section_2C1F745A2B7D41FE9E30915539226E3A}

Todas as chamadas [!DNL Target] usadas por uma atividade do A4T para fornecer conteúdo ou registrar a métrica de meta devem ter uma ocorrência [!DNL Analytics] correspondente que compartilhe a ID complementar do A4T para funcionar corretamente.

Ocorrências que contêm dados de [!DNL Analytics] e [!DNL Target] contêm uma ID de dados complementar. Você pode ver esta ID no [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=pt-BR) como o parâmetro `sdid`. Por exemplo: `sdid=2F3C18E511F618CC-45F83E994AEE93A0`. Esta ID é gerada a qualquer momento em que os seguintes critérios estiverem em vigor:

* O serviço de ID de visitante for implementado

Ao [solucionar problemas](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md), confirme se a ID complementar está presente nas [!DNL Analytics] ocorrências.

## Registro de análises do cliente {#client-side}

Se a at.js, o [!DNL Experience Cloud Visitor ID Service] e o appMeasurement.js estiverem na página, o [!DNL Analytics] e o [!DNL Target] une os eventos corretamente para fins de relatório e análise no back-end, desde que a ID adicional correta esteja incluída na página. Não é necessário gerenciar e executar operações adicionais para que o A4T funcione corretamente.

Há casos em que você precisa ter mais controle sobre quando e como enviar dados de análise relacionados a [!DNL Target] para [!DNL Analytics] para fins de relatório. Você pode ter uma ferramenta de análise interna usada para fins internos. No entanto, você também deseja enviar os dados de análise para [!DNL Analytics] por meio de seu produto de análise interno, para que outros membros de sua organização possam continuar usando o [!DNL Analytics] como uma fonte de relatórios visuais. Consulte [Etapa 7: Referência a at.js em todas as páginas do site](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#step7) em *Analytics para implementação do Target* para obter mais informações.

## Públicos-alvo compartilhados

Ao preencher o [Formulário de provisionamento de Integrações do Marketing Cloud](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}, esteja ciente das seguintes informações importantes sobre a opção [!UICONTROL Shared Audiences] listada em &quot;[!UICONTROL For which capabilities are you requesting provisioning]?&quot;

![Formulário de solicitação](/help/main/c-integrating-target-with-mac/a4t/assets/request-form.png)

Ao solicitar o [!UICONTROL Shared Audiences], você habilita o [!UICONTROL Target] e o [!UICONTROL Adobe Audience Manager] (AAM) para compartilhar informações, neste caso, públicos-alvo.

>[!IMPORTANT]
>
>Essa integração entre o [!UICONTROL Target] e o AAM vem com custos extras. Você é cobrado por cada chamada [!UICONTROL Target] no AAM.
