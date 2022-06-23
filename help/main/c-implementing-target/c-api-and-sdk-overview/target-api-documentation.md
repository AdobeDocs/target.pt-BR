---
keywords: api;adobe i/o
description: Saiba como fazer a transição do Adobe [!DNL Target] APIs herdadas clássicas para as novas APIs no Adobe I/O.
title: Como fazer a transição das APIs herdadas para o Adobe I/O?
feature: Implement Server-side
role: Developer
exl-id: 4b4274a9-b91a-4a79-9b40-8b1909a2d1d1
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 82%

---

# Transição de [!DNL Target] APIs herdadas para o Adobe I/O

Informações para ajudá-lo a usar a transição das APIs herdadas do Target para as novas APIs no Adobe I/O.

Com a desativação do Adobe Target Classic, as APIs que conectadas na conta do Target Classic também ficaram indisponíveis. Esse documento ajudará você a fazer a transição das integrações baseadas em API antigas às APIs do Target capacitadas pelo Adobe I/O.

Para obter mais informações sobre a documentação do Target API, consulte  [APIs do Target e SDK do NodeJS](https://developer.adobe.com/target/implement/server-side/).

## Terminologia {#section_D8286EDAE3B24D208DA432AEF2E88FD9}

| Termo | Descrição |
|--- |--- |
| API antigas | As APIs vinculadas à sua conta do Target Classic. Essas chamadas de API são baseadas em um nome de usuário e uma autenticação por senha e usam o nome de host `testandtarget.omniture.com`. Se as chamadas de API contiverem um nome de usuário e uma senha no URL de solicitação, você deverá fazer a transição para as do Adobe I/O. |
| Adobe I/O | A Adobe I/O é o novo gateway para APIs do Target. Essas APIs são conectadas à sua conta do Target Standard/Premium. As APIs do Target APIs no Adobe I/O usam uma autenticação baseada em JWT, que é o padrão do setor para APIs corporativas seguras. |

## Linha do tempo  {#section_A478EBF637554A2DB5A31661955121ED}

As APIs antigas serão descontinuadas quando o Target Classic for descomissionado:

| Data | Detalhes |
|--- |--- |
| 17 de outubro de 2017 | Todos os métodos da API que executam uma operação de gravação (`saveCampaign`, `copyCampaign`, `saveHTMLOfferContent`e `setCampaignState`) foram descontinuados.<br>Esta é a mesma data em que todas as contas de usuário do Target Classic foram definidas para o status de somente leitura. |
| 14 de novembro de 2017 | As APIs restantes foram desativadas. Esta é a data em que a interface do usuário do Target Classic foi desativada. |

As APIs do Recommendations Classic não serão afetadas por essa linha do tempo.

## Métodos equivalentes  {#section_DDB42CCC172545B09CB728D794CC466B}

A tabela a seguir lista os novos métodos de API do Target equivalentes para os métodos de API herdados. As novas APIs retornam JSON quando comparadas à resposta de XML fornecida pelas APIs antigas.

Os novos métodos de API são vinculados à seção correspondente no site de documentação da API. Um exemplo é fornecido para cada método de API. Você também pode usar Admin Postman Collection que contém as chamadas de exemplo de API para todos os novos métodos de API do Adobe no Adobe I/O.

| Grupos | Método de API antigo | Novo método de API | Notas |
|--- |--- |--- |--- |
| Campanha/Atividade | Criação de campanha | [Criar atividade AB](https://developers.adobetarget.com/api/#create-ab-activity)<br>[Criar atividade XT](https://developers.adobetarget.com/api/#create-xt-activity) | As novas APIs fornecem métodos de criação separados para AB e XT |
|  | Atualização da campanha | [Atualização de atividade AB](https://developers.adobetarget.com/api/#update-ab-activity)<br>[Atualização de atividade XT](https://developers.adobetarget.com/api/#update-xt-activity) |  |
|  | Copiar campanha | N/A | Usar APIs de criação de atividade |
|  | Lista de campanhas | [Listar atividades](https://developers.adobetarget.com/api/#list-activities) |  |
|  | Estado da campanha | [Atualizar estado da atividade](https://developers.adobetarget.com/api/#update-activity-state) |  |
|  | Exibição de campanha | [Obter atividade AB por ID](https://developers.adobetarget.com/api/#get-ab-activity-by-id)<br>[Obter atividade XT por ID](https://developers.adobetarget.com/api/#get-xt-activity-by-id) |  |
|  | ID de campanha de terceiros | N/D | Se estiver usando thirdpartyID, os métodos de Atividade relevantes podem ser usados |
| Ofertas | Criação de oferta | [Criar oferta](https://developers.adobetarget.com/api/#create-offer) |  |
|  | Obtenção de oferta | [Obter oferta por ID](https://developers.adobetarget.com/api/#get-offer-by-id) |  |
|  | Lista de ofertas | [Listar ofertas](https://developers.adobetarget.com/api/#list-offers) |  |
|  | Lista de pastas | N/D | As pastas não são suportadas no Target Standard/Premium |
| Relatório | Relatório de desempenho da campanha | [Relatório de desempenho AB](https://developers.adobetarget.com/api/#get-ab-performance-report)<br>[Relatório de desempenho XT](https://developers.adobetarget.com/api/#get-xt-performance-report) |  |
|  | Relatório de auditoria | [Obter relatório de auditoria](https://developers.adobetarget.com/api/#get-audit-report) |  |
|  | Relatório de conteúdo 1-1 | [Obter relatório de desempenho AP](https://developers.adobetarget.com/api/#get-ap-activity-performance-report) |  |
| Configurações da conta | Obter grupos de Hosts | [Listar ambientes](https://developers.adobetarget.com/api/#list-environments) |  |

## Exceções {#section_09CF9A0E289149279783B4801D1B6D4C}

Se você precisar de uma exceção, entre em contato com o seu Gerente de sucesso do cliente.

## Ajuda  {#section_591F850E2B7A4342B1C233693425415C}

Entre em contato com o Atendimento ao cliente do Adobe Target (tt-support@adobe.com) se tiver qualquer pergunta ou precisar de ajuda na transição para as novas APIs do Target no Adobe I/O.
