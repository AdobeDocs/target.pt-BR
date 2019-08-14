---
description: Informações sobre como trabalhar com o Adobe Client Care para implementar o suporte CNAME (Canonical Name) no Adobe Target.
keywords: atendimento ao cliente; cname; programa de certificado; nome canônico; cookies; certificado; amc; certificado gerenciado da adobe
seo-description: Informações sobre como trabalhar com o Adobe Client Care para implementar o suporte CNAME (Canonical Name) no Adobe Target.
seo-title: CNAME e Adobe Target
solution: Target
title: CNAME e Adobe Target
topic: Padrão
uuid: 3fb0ea31-e91d-4359-a8cc-64c547e6314e
translation-type: tm+mt
source-git-commit: d21838bdf17327b394f6e3106ea5ce4bc72605e6

---


# CNAME e Adobe Target{#cname-and-adobe-target}

Informações sobre como trabalhar com o Adobe Client Care para implementar o suporte CNAME (Canonical Name) no Adobe Target. Para lidar com problemas de bloqueio de anúncios, um CNAME é usado para que as chamadas sejam feitas em um domínio pertencente ao cliente, em vez de um domínio da Adobe.

Execute as etapas a seguir para solicitar o suporte CNAME no Target:

1. Abra uma [uma chamada no Atendimento ao cliente](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) solicitando o suporte CNAME para as chamadas do Adobe Target.
1. Inscreva-se no programa [Adobe Managed Certificate (AMC)](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) e siga as etapas de implementação fornecidas no guia [!DNL Adobe Analytics]*Cookies próprios.* [!DNL Target] usa o mesmo método usado pelo suporte [!DNL Analytics] CNAME.

   O programa AMC ajuda a eliminar o esforço e a confusão percebidas pelos clientes ao implementarem cookies próprios. Após se inscrever nesse programa, a Adobe comprará e emitirá o certificado para instalar em servidores seguros.

   >[!NOTE]
   >
   >O CNAME deve ser configurado antes de se inscrever no programa AMC.

1. Após concluir as tarefas anteriores, você deve atualizar o `serverDomain` arquivo para o novo CNAME em at. js.

## Vídeo de treinamento: Cookies próprios e usando certificados gerenciados da Adobe

This video is a recording of [Office Hours](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7), an initiative led by the Adobe Customer Care team. A discussão do programa Adobe Managed Certificate é iniciada às 1.:2.

[Adobe Analytics: Cookies próprios e usando certificados gerenciados da Adobe](https://helpx.adobe.com/customer-care-office-hours/analytics/first-party-cookies-adobe-managed-certificates.html)
