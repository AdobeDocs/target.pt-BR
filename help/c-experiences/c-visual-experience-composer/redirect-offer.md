---
description: Use esta opção quando quiser direcionar o visitante para uma página diferente em vez de mostrar o conteúdo na mesma página.
title: Redirecionar para um URL
feature: vec
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 100%

---


# Redirecionar para um URL{#redirect-to-a-url}

Use esta opção quando quiser direcionar o visitante para uma página diferente em vez de mostrar o conteúdo na mesma página.

Você pode ter duas páginas completamente diferentes para testar, em vez de mudar apenas partes do conteúdo dentro de uma página. Neste caso, o teste A/B compara a página A versus a página B. Configure uma campanha de testes A/B, com duas experiências: uma apontando para a página A padrão e a outra redirecionando para a página B. No menu Ação da experiência, localizado ao clicar no rótulo da letra da experiência, escolha **[!UICONTROL Redirecionar para URL]** e especifique o URL da página B. A oferta é configurada para redirecionar o visitante para uma página diferente.

A oferta de redirecionamento executa um código JavaScript para redirecionar o navegador. Ela usa o método `window.location.replace();`, de forma que a página a partir da qual o visitante é redirecionado não é armazenada no histórico do navegador. Isso permite que o visitante consiga utilizar o botão Voltar de seu navegador.

Ofertas de redirecionamento possuem algumas limitações:

* Para ofertas de redirecionamento em atividades usando A4T, sua implementação deve atender certos requisitos mínimos. Além disso, há informações importantes que você precisa saber. Para obter mais informações, consulte [Ofertas de redirecionamento - Perguntas frequentes do A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* Ao usar o Experience Composer baseado em formulários, ofertas de redirecionamento não devem ser usadas em mboxes que façam parte da página. Uma oferta de redirecionamento deve ser usada somente a partir de uma tag de script que faz parte do `<head>` do HTML. Você sempre deve usar a criação automática e definir a oferta de redirecionamento para a mbox global.

>[!NOTE]
>
>Se desejar passar o valor referenciador da página de aterrissagem, é recomendado usar uma oferta HTML em vez de uma oferta de redirecionamento.

Para criar uma oferta de redirecionamento:

1. Crie uma experiência.
1. Passe com o mouse sobre uma experiência, depois clique no ícone Redirecionar para URL (![](assets/icon_redirect_url.png)).

   ![](assets/exp_actions.png)

1. Digite o URL.
1. Se desejar, selecione a opção para incluir parâmetros de consulta atuais.

   Se essa opção for selecionada, tudo depois de ? no URL do visitante será anexado ao URL de redirecionamento no momento do redirecionamento.

   Essa opção está selecionada por padrão.
1. (Opcional) Crie regras adicionais.

   Regras adicionais podem ser baseadas em qualquer um dos seguintes:

   * URL
   * Domínio
   * Caminho
   * Fragmento em hash (#)
   * Consulta
   * Parâmetro da mbox
   Regras adicionais podem ser unidas no URL da atividade com AND ou OR. Todas regras que você adicionar são avaliadas contra si próprias com AND.
