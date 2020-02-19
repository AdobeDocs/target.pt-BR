---
keywords: experience preview;experience urls;generate urls;view experience urls
description: Os URLs de visualização de experiência podem ser gerados para as atividades de Personalização automatizada do Target para ver o conteúdo de experiência diretamente no site antes que a atividade esteja ativa para fins de visualização e QA. URLs de visualização de experiência ignoram a definição de metas para forçar a visualização de uma experiência específica.
title: Visualizar atividades de personalização automatizada com URLs de visualização de experiência
topic: Standard
uuid: 2ef07b6c-086d-43ac-bf02-efe217652a3a
translation-type: tm+mt
source-git-commit: 4ab572a0466381854d70eb47e0fc0b4a2874b833

---


# ![Atividades de personalização automatizada de visualização PREMIUM](/help/assets/premium.png) com URLs de visualização de experiência{#share-experience-urls-to-preview-automated-personalization-outside-of-target}

Os URLs de visualização de experiência podem ser gerados para as atividades de Personalização automatizada do Target para ver o conteúdo de experiência diretamente no site antes que a atividade esteja ativa para fins de visualização e QA. URLs de visualização de experiência ignoram a definição de metas para forçar a visualização de uma experiência específica.

>[!NOTE]
>
>Os URLs de visualização da experiência para personalização automatizada diferem do modo de QA da atividade. O modo controle de qualidade da atividade permite que você crie URLs de atividades para outros tipos de atividades. Para obter mais informações, consulte [Garantia de qualidade da atividade](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40).
>
>Os URLs de visualização de experiência para atividades AP só estão disponíveis ao usar o at.js 1.x. Os URLs de visualização de experiência para atividades AP não são suportados atualmente para at.js 2.x.

Use os URLs de visualização de experiência para compartilhar experiências com os membros da equipe e experiências de QA em navegadores e ambientes, sem criar uma atividade de QA separada. Este recurso é particularmente útil se um site for complexo ou se as políticas de segurança não permitirem que o site seja visualizado em um simulador.

1. Crie uma [atividade de Personalização automatizada](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou clique na atividade para abri-la.

   A atividade não precisa estar inicializada para visualizar uma experiência.
1. Na página de resumo da atividade, clique nos três pontos verticais e clique em **[!UICONTROL Exibir URLs da experiência]**.
1. Reveja e/ou especifique seus URLs.

   * Se você está usando o Visual Experience Composer, o URL padrão que você especificou para a atividade é inserido automaticamente e um link é gerado para cada experiência na sua atividade. Você pode alterar este URLS e adicionar outros, se quiser.
   * Se você está usando o Experience Composer baseado em formulário, nenhum URL padrão é inserido automaticamente. If you haven&#39;t previously created experience preview URLs, click **Add New URL**. Você deve especificar todos URLs que quer visualizar além de um nome para cada URL.
   Você pode adicionar vários URLs, o que é útil ao executar um teste multipágina ou um teste de modelo e você quer visualizar a atividade em mais de uma página.

   Uma janela modal exibe links para suas experiências em seu site para obter uma &quot;visualização real&quot; das experiências fora do Visual Experience Composer do Target. É necessário compartilhar os links da mensagem para compartilhar a visualização. Clicar em um link e copiar o URL resultante da página não funciona porque o URL contém um parâmetro que só exibe a página corretamente quando você acessa a página a partir do link na mensagem. Em vez disso, copie o texto na janela modal e envie o texto inteiro por email para sua equipe.
1. Clique em **[!UICONTROL Gerar tudo]** e, em seguida, clique em cada experiência para visualizá-la.

   If you then make changes to the experience, make sure to generate new preview links for your team by returning to the modal window and clicking **Renew Links** to get new links.

   **Observação:** os links de visualização abrem em novas guias e requerem que o bloqueador de pop-up do seu navegador esteja desabilitado.

1. Clique no nome de cada experiência para visualizar a atividade.

   A página é aberta, exibindo a atividade.
1. Clique em **[!UICONTROL Concluído]** para retornar ao resumo da atividade.

## Considerações {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Geração de URLs de visualização de experiência**

* O URL de visualização da experiência não é afetado pela divisão de tráfego entre experiências.
* Direcionamento no nível do público-alvo não afeta a visualização.
* Você pode gerar automaticamente um máximo de 300 URLs de experiência por atividade. Após isso, você deve gerar os URLs manualmente.
* Você pode gerar automaticamente um máximo de 300 URLs de experiência por atividade. Após isso, você deve gerar os URLs manualmente.
* Dependendo do número de experiências, gerar os URLs pode levar até cinco minutos. Não feche caixa de diálogo ou os URLs gerados serão perdidos.
* Os links de visualização gerados são válidos por dois meses. Após este período, você deve gerar seus URLs de visualização novamente.
* Você deve gerar novamente a qualquer momento que uma experiência é alterada.

**Compartilhando URLs de visualização de experiência**

* Você pode visualizar uma experiência mesmo que não faça parte do público-alvo.
* Você pode compartilhar URLs de visualização de experiência com colegas que não têm acesso ao Adobe Target.

**Exibição de experiências com URLs de visualização de experiência**

* A visualização funciona para qualquer atividade salva, desde que a página não tenha sido alterada.
* O URL de visualização da experiência está disponível se a atividade está ativa ou inativa.
* Não é possível visualizar uma experiência que esteja em status de Rascunho.
* Os relatórios não são afetados pela exibição dos URLs de visualização da experiência.

**Solução de problemas de URLs de visualização da experiência**

* Se você não conseguir ver a visualização na nova guia (devido ao cache do navegador), tente atualizar duas ou três vezes ou copiar o link e abri-lo em um novo navegador, nova sessão ou no modo privado do navegador.
