---
keywords: visualização de experiência, urls de experiências, gerar urls, ver urls de experiências
description: Saiba como usar URLs de visualização de experiência para o Adobe [!DNL Target] Atividades do Automated Personalization para ver o conteúdo da experiência diretamente no site antes da atividade ser ativada.
title: Como posso usar URLs de visualização de experiência nas atividades do Automated Personalization?
feature: Automated Personalization
exl-id: 9f329b8a-5f86-4cae-a3be-eed24fa0a9cd
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 50%

---

# ![PREMIUM](/help/main/assets/premium.png) Visualizar atividades do Automated Personalization com URLs de visualização da experiência

Os URLs de visualização da experiência podem ser gerados para [!DNL Target] [!UICONTROL Automated Personalization] para ver o conteúdo da experiência diretamente no site antes que a atividade seja ativada para fins de visualização e controle de qualidade. Os URLs de visualização de experiência ignoram o direcionamento para forçar a visualização de uma experiência específica.

>[!NOTE]
>
>Você pode criar URLs de visualização de experiência para outros tipos de [!DNL Target] atividades. No entanto, o processo é um pouco diferente. Para obter mais informações, consulte [Garantia de qualidade da atividade.](/help/main/c-activities/c-activity-qa/activity-qa.md#preview)

Use URLs de visualização de experiência para compartilhar experiências com membros da equipe e para fazer QA de experiências em navegadores e ambientes, sem criar uma atividade de QA separada. Este recurso é particularmente útil se um site for complexo ou se as políticas de segurança não permitirem que o site seja visualizado em um simulador.

1. Crie uma [atividade de Personalização automatizada](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou clique na atividade para abri-la.

   A atividade não precisa estar inicializada para visualizar uma experiência.

1. Na página Visão geral da atividade , clique nos três pontos verticais e clique em **[!UICONTROL Exibir URLs de experiência]**.

1. Reveja e/ou especifique seus URLs.

   * Se estiver usando o [!UICONTROL Visual Experience Composer] (VEC), o URL padrão especificado para a atividade é inserido automaticamente e um link é gerado para cada experiência na atividade. Você pode alterar este URLS e adicionar outros, se quiser.
   * Se estiver usando o [!UICONTROL Experience Composer baseado em formulário], nenhum URL padrão é inserido automaticamente. Se você não criou URLs de visualização da experiência anteriormente, clique em **Adicionar novo URL**. Você deve especificar todos URLs que quer visualizar além de um nome para cada URL.

   Você pode adicionar vários URLs, o que é útil ao executar um teste multipágina ou um teste de modelo e você quer visualizar a atividade em mais de uma página.

   Uma janela modal exibe links para suas experiências no site para obter uma &quot;visualização real&quot; das experiências fora do [!DNL Target] VEC. É necessário compartilhar os links da mensagem para compartilhar a visualização. Clicar em um link e copiar o URL resultante da página não funciona porque o URL contém um parâmetro que só exibe a página corretamente quando você acessa a página a partir do link na mensagem. Em vez disso, copie o texto na janela modal e envie o texto inteiro por email para sua equipe.

1. Clique em **[!UICONTROL Gerar tudo]** e, em seguida, clique em cada experiência para visualizá-la.

   Se você fizer alterações na experiência, certifique-se de gerar novos links de visualização para sua equipe retornando à janela modal e clicando em **Renovar links** para obter novos links.

   >[!NOTE]
   >
   >Os links de visualização abrem em novas guias e exigem que o bloqueador de pop-up do seu navegador esteja desativado.

1. Clique no nome de cada experiência para visualizar a atividade.

   A página é aberta, exibindo a atividade.

1. Clique em **[!UICONTROL Concluído]** para retornar ao resumo da atividade.

## Considerações {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Gerar URLs de visualização da experiência**

* O URL de visualização da experiência não é afetado pela divisão de tráfego entre experiências.
* Direcionamento no nível do público-alvo não afeta a visualização.
* Você pode gerar automaticamente um máximo de 300 URLs de experiência por atividade. Após isso, você deve gerar os URLs manualmente.
* Dependendo do número de experiências, gerar os URLs pode levar até cinco minutos. Não feche a caixa de diálogo ou os URLs gerados serão perdidos.
* Os links de visualização gerados são válidos por dois meses. Após este período, você deve gerar seus URLs de visualização novamente.
* Você deve gerar novamente a qualquer momento que uma experiência é alterada.

**Compartilhamento de URLs de visualização da experiência**

* Você pode visualizar uma experiência mesmo que não faça parte do público-alvo.
* Você pode compartilhar URLs de visualização de experiência com colegas que não têm acesso ao [!DNL Adobe Target].

**Exibindo experiências com URLs de visualização da experiência**

* A visualização funciona para qualquer atividade salva, desde que a página não tenha sido alterada.
* O URL de visualização da experiência está disponível independentemente da atividade estar ativa ou inativa.
* Não é possível visualizar uma experiência que esteja em [!UICONTROL Rascunho] status.
* Os relatórios não são afetados pela visualização dos URLs de visualização da experiência.

**Solução de problemas de URLs de visualização da experiência**

* Se você não conseguir ver a visualização na nova guia (devido ao cache do navegador), tente atualizar duas ou três vezes ou copiar o link e abri-lo em um novo navegador, nova sessão ou no modo privado do navegador.
