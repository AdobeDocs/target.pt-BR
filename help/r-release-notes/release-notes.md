---
keywords: Notas de versão, novos recursos, versões, atualizações, atualização, versão, aprimoramento, aprimoramentos, correções, correções de erros, atualizações
description: Saiba mais sobre os novos recursos, melhorias e correções incluídos na versão atual do Adobe Target, incluindo SDKs, APIs e bibliotecas JavaScript.
title: Quais novos recursos estão incluídos na versão atual?
feature: ' Notas de versão '
translation-type: tm+mt
source-git-commit: 8dc0e5084834102e387492eb4668761382e699f3
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 36%

---


# Notas de versão do Target (atual)

Essas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para cada versão [!DNL Adobe Target Standard] e [!DNL Target Premium]. Além disso, as notas de versão para APIs do Target, SDKs, biblioteca de JavaScript (at.js) e outras alterações na plataforma também são incluídas, quando aplicável.

>[!IMPORTANT]
>
>**Fim da vida útil** da mbox.js: Em 31 de março de 2021, o não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js normalmente falharão e afetarão suas páginas que têm [!DNL Target] atividades em execução ao veicular conteúdo padrão.
>
>Migre para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

## at.js 2.4.1 (23 de março de 2021)

Essa versão do at.js é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:

* Correção de um problema em que `targetPageParams` era incluído nas solicitações da mbox. `targetPageParams` deve ser incluído somente em  `pageLoad` solicitações. (TNT-40247)
* Correção de um problema com objetos globais de documento e janela na extensão A[!DNL dobe Experience Platform Launch] ao substituir as dependências do objeto global do Platform launch por referências diretas a eles. (TNT-37124)

## Alterações de endereço IP para servidores de processamento de feed do Recommendations (16 de março de 2021)

Os endereços IP do servidor de processamento de feed [!DNL Target Recommendations] foram atualizados em 16 de março de 2021. Para obter mais informações, consulte [Endereços IP usados pelos servidores de processamento de feed do Recommendations](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md).

## Target Standard/Premium 21.2.1 (9 de março de 2021) 

Esta versão de manutenção contém os seguintes aprimoramentos, correções e alterações.

Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

* Aumento do tamanho permitido da oferta (TGT-38304):

   | Tipo | Limite anterior | Novo limite |
   | --- | --- | --- |
   | HTML | 256 KB | 1024 KB |
   | Ofertas visuais da interface do usuário do Target | 64 KB | 1024 KB para cada experiência |
   | Via API | 512 KB | 1024 KB |

* [!UICONTROL Os relatórios de ] Insights de personalização para atividades de Direcionamento  [!UICONTROL automático]  (AT) e  [!UICONTROL Automated Personalization]  (AP) agora são produzidos diariamente. Você pode escolher um relatório que fornece [!UICONTROL Segmentos automatizados] ou [!UICONTROL Atributos importantes] para os últimos 15, 30 e 60 dias. As opções de 45 dias e 90 dias foram removidas para permitir que as outras configurações da janela de lookback sejam executadas diariamente. (TGT-39472)
* Correção de um problema que fazia com que a dependência atual não fosse exibida quando os clientes clicavam em [!UICONTROL Editar dependência] na página [!UICONTROL Metas e configurações] de uma atividade. (TGT-39340)
* Correção de um problema ao atualizar a [!UICONTROL Biblioteca de público-alvo] de um espaço de trabalho. Antes da atualização, os públicos-alvo do espaço de trabalho selecionado no momento eram exibidos. Após a atualização, o [!UICONTROL Espaço de trabalho padrão] e seus públicos-alvo eram exibidos. O espaço de trabalho atual e seus públicos-alvo agora persistem após a atualização. (TGT-38871)
* Correção de um problema ao copiar uma atividade [!UICONTROL Recommendations] e editar posteriormente a atividade original alterando sua sequência de critérios. A alteração na sequência de critérios na atividade original também foi aplicada incorretamente à atividade copiada. (TGT-39155)
* Correção de um problema que fazia com que o número incorreto de produtos fosse exibido para exclusões [!UICONTROL Recommendations]. (TGT-39599)

## Notas de versão adicionais e detalhes da versão

| Recurso | Detalhes |
|--- |--- |
| [Detalhes da versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target]. |

## Alterações na documentação, notas de versão anteriores e notas de versão da Experience Cloud

Além das notas para cada versão, os recursos a seguir oferecem informações adicionais:

| Recurso | Detalhes |
|--- |--- |
| Alterações de documentação | Veja informações detalhadas sobre atualizações neste guia que não estão incluídas nestas notas de versão.<br>Para obter mais informações, consulte [Alterações de documentação](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notas de versão para versões anteriores | Veja informações sobre os novos recursos e aprimoramentos das versões anteriores do Target Standard e do Target Premium.<br>Para obter mais informações, consulte [Notas de versões anteriores](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notas de versão da Adobe Experience Cloud | Veja as notas de versão mais recentes para as soluções da Adobe Experience Cloud.<br>Para obter mais informações, consulte Notas de versão do  [Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html). |

## Informações de pré-lançamento {#section_5D588F0415A2435B851A4D0113ACA3A0}

Os recursos a seguir permitem ver as novidades previstas para a próxima versão do Target.

| Recurso | Detalhes |
|--- |--- |
| Atualização prioritária de produto do Adobe | Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notas de versão futuras | Para obter informações sobre os lançamentos do Target do mês atual, incluindo informações de pré-lançamento, consulte a página [Notas de versão do Target - Pré-lançamento](/help/r-release-notes/target-release-notes.md). |
