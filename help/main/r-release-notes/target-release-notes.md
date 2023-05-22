---
keywords: notas de versão;versões;atualizações;versão futura;melhorias;novos recursos;correções;atualizações;pré-lançamento
description: Saiba mais sobre os novos recursos, melhorias e correções adicionados na próxima versão do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais são os novos recursos e melhorias que serão incluídos na próxima versão do  [!DNL Target] ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 2f553151e480d48178389132a0a97fa7de4e04c5
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 54%

---

# Notas de versão do [!DNL Target] (pré-lançamento)

Este artigo contém informações de pré-lançamento das próximas versões do [!DNL Adobe Target], incluindo SDKs, APIs e bibliotecas JavaScript.

**Última atualização: 22 de maio de 2023**

>[!NOTE]
>
>As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.
>
>Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do momento dos lançamentos. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

## [!DNL Target] Standard/Premium 23.5.1 (23 a 25 de maio de 2023)

Esta versão estará disponível de acordo com o seguinte agendamento:

23 de maio: Europa, Oriente Médio e África (EMEA) região 24 de maio: Ásia-Pacífico (APAC) região 25 de maio: região das Américas

Essa versão contém os seguintes novos recursos, aprimoramentos e correções:

| Recurso | Detalhes |
|--- |--- |
| Atributos de perfil da Real-Time CDP compartilhados com o [!DNL Target] | Os [!UICONTROL atributos de perfil da Real-Time CDP] podem ser compartilhados com o [!DNL Target] para uso em ofertas HTML e JSON.<P>Para obter mais informações, consulte [Compartilhar atributos de perfil da Real-Time CDP com o [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes). |

* Correção de um problema que impedia determinados clientes de criar públicos-alvo com perfis de visitante usando operadores &quot;maior que&quot; ou &quot;menor que&quot;. (TGT-45271)

## [!DNL Target] Standard/Premium 23.5.2 (31 de maio de 2023)

Essa versão conta com os seguintes aprimoramentos e correções:

* Correção de um problema que resultava na exibição de uma página em branco ao gerar um token de autorização de API de perfil. (TGT-45387)
* Correção de um problema que impedia a exibição de uma imagem no [!UICONTROL Criar design] se o nome da imagem contiver 18030 caracteres GB. (TGT-44614)
* Correção de um problema que causava relatórios do [!UICONTROL Personalização automática] atividades a serem congeladas durante a análise. (TGT-44820)
* Correção de um problema que fazia com que nenhuma atividade fosse exibida na interface do usuário do Target para o espaço de trabalho Padrão para determinados clientes. (TGT-45286)
* Atualização do comportamento do sinalizador &quot;Não permitir duplicatas&quot;. Os sinalizadores de ofertas repetitivas excluídas são atualizados para permitir ofertas repetitivas se forem a oferta de conteúdo padrão (para APIs v3, v4) e permitir opções duplicadas se as opções referenciarem a oferta de conteúdo padrão e não tiverem modelos definidos. (TNT-46617)
* Correção de um problema em que um parâmetro de consulta era adicionado a um URL que impedia o carregamento da página no Visual Experience Composer (VEC). (TGT-44873)
* Correção de um problema em que alguns caracteres eram evitados incorretamente em Text/HTML nas experiências. (TGT-44600)

## [!DNL Target] Standard/Premium 23.5.3 (Data a ser determinada)

Esta versão inclui as seguintes melhorias:

| Recurso | Detalhes |
|--- |--- |
| [!UICONTROL Modo de controle de qualidade] para [!UICONTROL Automated Personalization] atividades | [!DNL Adobe Target] [!UICONTROL Modo de controle de qualidade] agora está disponível para [!UICONTROL Automated Personalization] atividades, substituição [!UICONTROL Visualizar links] funcionalidade.<P>Para obter mais informações, consulte [Garantia de qualidade da atividade.](/help/main/c-activities/c-activity-qa/activity-qa.md) |

* Aprimoramentos de desempenho para impedir a funcionalidade de duplicatas (incluindo redução no tempo de carregamento) enquanto [gerenciamento de exclusões](/help/main/c-activities/t-automated-personalization/managing-exclusions.md#concept_4EF78013F80E48EFA024AE0274C9F037) in [!UICONTROL Automated Personalization] atividades.

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Notas de versão: SDK da Web da Platform Experience do Adobe Target](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) | Detalhes sobre alterações em cada versão do SDK da Web da Platform. |
| [Detalhes da versão da at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o [!DNL Target] e outras soluções do [!DNL Adobe Experience Cloud], inscreva-se na [!DNL Adobe Priority Product Update]:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
