---
description: Informações sobre como trabalhar com o Adobe Client Care para implementar o suporte CNAME (Canonical Name) no Adobe Target.
keywords: atendimento ao cliente; cname; programa de certificado; nome canônico; cookies; certificado;amc;adobe certificado gerenciado
seo-description: Informações sobre como trabalhar com o Adobe Client Care para implementar o suporte CNAME (Canonical Name) no Adobe Target.
seo-title: CNAME e Adobe Target
solution: Target
title: CNAME e Adobe Target
topic: Padrão
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: b7a80326b0b89f6fe3bac70ccc6941be09d14ac1

---


# CNAME e Adobe Target {#cname-and-adobe-target}

Informações sobre como trabalhar com o Adobe Client Care para implementar o suporte CNAME (Canonical Name) no [!DNL Target]. Para melhor lidar com problemas de bloqueio de anúncios, ou políticas de cookies relacionadas ao ITP, um CNAME é usado, portanto, as chamadas são feitas para um domínio pertencente ao cliente em vez de um domínio pertencente à Adobe.

Execute as etapas a seguir para solicitar o suporte CNAME no [!DNL Target]:

1. Open a [Customer Care ticket requesting CNAME support](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) for your [!DNL Target] calls.

1. Crie registros CNAME (consulte as instruções abaixo).

   Ao receber o ticket, um especialista FPSSL deve fornecer um par de registros CNAME. Esses registros devem ser configurados no servidor DNS da sua empresa para que a Adobe possa comprar o certificado em seu nome.

   O CNAMES será semelhante ao seguinte exemplo:

   `DNS record: metrics.example.com IN CNAME metricsexample-fpssl.tt.omtrdc.net`

1. Quando esses CNAMES estiverem em vigor, a Adobe trabalhará com a DigiCert para comprar e instalar um certificado nos servidores de produção da Adobe.

1. Após concluir as tarefas anteriores, você deve atualizar o CNAME `serverDomain` para o novo CNAME em at.js.
