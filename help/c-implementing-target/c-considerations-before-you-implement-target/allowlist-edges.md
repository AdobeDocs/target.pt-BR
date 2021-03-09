---
keywords: implementar; implementação; lista de permissões; lista de permissões; lista de permissões; lista de permissões; borda; bordas
description: Exiba uma lista de hosts para ajudá-lo a adicionar as bordas do Adobe Target à lista de permissões (nós de serviço distribuídos geograficamente que garantem tempos de resposta ideais aos usuários finais).
title: Como faço para incluir nós de borda no Target?
feature: Privacidade e segurança
role: Desenvolvedor
translation-type: tm+mt
source-git-commit: 806c52e69cce636a56eb067759612f80829418f9
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 8%

---


# Nós de borda permitidos no Target

Informações e uma lista atualizada de hosts para ajudá-lo a adicionar [!DNL Adobe Target] bordas à lista de permissões.

Uma borda é uma arquitetura de fornecimento distribuída geograficamente que garante tempos de resposta ideais para usuários finais que solicitem o conteúdo, independentemente de onde estejam localizados. Cada nó de borda tem todas as informações necessárias para responder à solicitação de conteúdo do usuário e rastrear os dados de análise dessa solicitação. As solicitações do usuário são roteadas para o nó de borda mais próximo. Para obter mais informações, consulte [A rede de borda](/help/c-intro/how-target-works.md#concept_0AE2ED8E9DE64288A8B30FCBF1040934) em *Como o Adobe [!DNL Target] funciona*.

Você pode adicionar [!DNL Target] nós de borda à lista de permissões, se desejar.

## Endereços IP de NAT (Network Address Translation, tradução de endereço de rede) das bordas do Target

Lista de endereços IP de saída de bordas [!DNL Target]. Inclua esses IPs na lista de permissões se você planeja que o Target alcance seus serviços.

| Localização da borda | Endereços IP de saída |
| --- | --- |
| Edge31 (Mumbai) | 13.126.131.246<br>13.234.229.8 |
| Edge32 (Tóquio) | 3.115.154.28<br>3.115.227.146 |
| Edge34 (Costa Leste dos EUA) | 34.232.149.249<br>52.21.139.93 |
| Edge35 (Costa Oeste dos EUA) | 52.10.11.139<br>44.231.171.161 |
| Edge36 (Sydney) | 13.237.227.20<br>13.210.93.142 |
| Edge37 (Irlanda) | 54.72.21.68<br>52.208.139.19 |
| Edge38 (Cingapura) | 18.141.132.96<br>54.179.187.167 |

## Endereços IP de borda de destino

Lista de endereços IP de bordas [!DNL Target]. Inclua esses IPs na lista de permissões se desejar fazer chamadas de API nas bordas do Target.

| Localização da borda | Domínio | Endereço IP |
| --- | --- | --- |
|  | `CLIENTCODE.tt.omtrdc.net`<br>(onde CLIENTCODE é sua ID  [!DNL Target] de cliente) |  |
| Edge31 (Mumbai) | `mboxedge31.tt.omtrdc.net` | 15.207.157.131<br>15.206.8.2010 |
| Edge32 (Tóquio) | `mboxedge32.tt.omtrdc.net` | 54.199.66.101<br>54.64.93.37 |
| Edge34 (Costa Leste dos EUA) | `mboxedge34.tt.omtrdc.net` | 3.225.56.36<br>3.230.207.249<br>34.198.55.51<br>52.3.14.12<br>52.21.222.9 3<br>52.55.235.132<br>52.70.52.52<br>54.165.204.89 |
| Edge35 (Costa Oeste dos EUA) | `mboxedge35.tt.omtrdc.net` | 52.10.244.20<br>52.36.232.38<br>52.88.209.29<br>54.214.180.56<br>35.162 74.35<br>34.214.12.211<br>52.42.35.202<br>54.148.71.13 |
| Edge36 (Sydney) | `mboxedge36.tt.omtrdc.net` | 13.238.34.185<br>3.24.250.17<br>3.104.234.91<br>13.211.248.241 |
| Edge37 (Irlanda) | `mboxedge37.tt.omtrdc.net` | 52.212.193.208<br>52.19.133.54<br>52.51.251.137<br>34.252.156.174<br>5 2.213.168.74<br>34.252.166.160<br>52.18.150.20<br>18.203.205.32 |
| Edge38 (Cingapura) | `mboxedge38.tt.omtrdc.net` | 52.221.145.65<br>52.220.44.99<br>13.250.75.226<br>54.151.139.123 |





