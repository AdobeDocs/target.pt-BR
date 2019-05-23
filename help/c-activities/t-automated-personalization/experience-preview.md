---
description: Os URLs de experiência podem ser gerados para as atividades de Personalização automatizada do Target para ver o conteúdo da experiência diretamente em seu site antes que a atividade seja ativada para fins de visualização e controle de qualidade. Os URLs de experiência ignoram o direcionamento para forçar a visualização de uma experiência específica.
keywords: visualização de experiência, urls de experiências, gerar urls, ver urls de experiências
seo-description: Os URLs de experiência podem ser gerados para as atividades de Personalização automatizada do Target para ver o conteúdo da experiência diretamente em seu site antes que a atividade seja ativada para fins de visualização e controle de qualidade. Os URLs de experiência ignoram o direcionamento para forçar a visualização de uma experiência específica.
seo-title: Compartilhar URLs de experiências para visualização de Automated Personalization fora do Target
solution: Target
title: Compartilhar URLs de experiências para visualização de Automated Personalization fora do Target
title-outputclass: premium
topic: Padrão
uuid: 2ef07b6c-086d-43ac-bf02-efe217652a3a
badge: premium
translation-type: tm+mt
source-git-commit: 761771a48c0ae957d455974b1f04fa3a8350a8a0

---


# ![PREMIUM](/help/assets/premium.png) Compartilhar URLs de experiência para visualização de Personalização automatizada do Target{#share-experience-urls-to-preview-automated-personalization-outside-of-target}

Os URLs de experiência podem ser gerados para as atividades de Personalização automatizada do Target para ver o conteúdo da experiência diretamente em seu site antes que a atividade seja ativada para fins de visualização e controle de qualidade. Os URLs de experiência ignoram o direcionamento para forçar a visualização de uma experiência específica.

>[!NOTE]
>
>O modo controle de qualidade da atividade permite que você crie URLs de atividades para outros tipos de atividades. Para obter mais informações, consulte [Garantia de qualidade da atividade](../../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40)

.

Para usar URLs de experiência, você deve compartilhar os links gerados pelo Target e não o URL final que você acessa ao visualizar a experiência. Além disso, se o conteúdo mudar, novos URLs devem ser gerados. Se você gerar novos URLs, os antigos podem não funcionar.

Use URLs de experiência para compartilhar experiências com membros da equipe e fazer controle de qualidade em experiências entre navegadores e ambientes, sem criar uma atividade de controle de qualidade separada. Este recurso é particularmente útil se um site for complexo ou se as políticas de segurança não permitirem que o site seja visualizado em um simulador.

1. Crie uma [atividade de Personalização automatizada](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou clique na atividade para abri-la.

   A atividade não precisa estar inicializada para visualizar uma experiência.
1. Na página de resumo da atividade, clique nos três pontos verticais e clique em **[!UICONTROL Exibir URLs da experiência]**.
1. Reveja e/ou especifique seus URLs.

   * Se você está usando o Visual Experience Composer, o URL padrão que você especificou para a atividade é inserido automaticamente e um link é gerado para cada experiência na sua atividade. Você pode alterar este URLS e adicionar outros, se quiser.
   * Se você está usando o Experience Composer baseado em formulário, nenhum URL padrão é inserido automaticamente. Se você não criou URLs de experiência anteriormente, clique em **Adicionar novo URL**. Você deve especificar todos URLs que quer visualizar além de um nome para cada URL.
   Você pode adicionar vários URLs, o que é útil ao executar um teste multipágina ou um teste de modelo e você quer visualizar a atividade em mais de uma página.

   Uma janela modal exibe links para suas experiências em seu site para obter uma &quot;visualização real&quot; das experiências fora do Visual Experience Composer do Target. É necessário compartilhar os links da mensagem para compartilhar a visualização. Clicar em um link e copiar o URL resultante da página não funciona porque o URL contém um parâmetro que só exibe a página corretamente quando você acessa a página a partir do link na mensagem. Em vez disso, copie o texto na janela modal e envie o texto inteiro por email para sua equipe.
1. Clique em **[!UICONTROL Gerar tudo]** e, em seguida, clique em cada experiência para visualizá-la.

   Então se você fizer alterações na experiência, certifique-se de gerar novos links de visualização para sua equipe voltando para a janela modal e clicando em **Gerar todos** para obter novos links.

   **Observação:** os links de visualização abrem em novas guias e requerem que o bloqueador de pop-up do seu navegador esteja desabilitado.

1. Clique no nome de cada experiência para visualizar a atividade.

   A página é aberta, exibindo a atividade.
1. Clique em **[!UICONTROL Concluído]** para retornar ao resumo da atividade.

## Considerações {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Gerando URLs de experiência**

* O URL de experiência não é impactado por divisão de tráfego entre experiências.
* Direcionamento no nível do público-alvo não afeta a visualização.
* Você pode gerar automaticamente um máximo de 300 URLs de experiência por atividade. Após isso, você deve gerar os URLs manualmente.
* Você pode gerar automaticamente um máximo de 300 URLs de experiência por atividade. Após isso, você deve gerar os URLs manualmente.
* Dependendo do número de experiências, gerar os URLs pode levar até cinco minutos. Não feche caixa de diálogo ou os URLs gerados serão perdidos.
* Os links de visualização gerados são válidos por dois meses. Após este período, você deve gerar seus URLs de visualização novamente.
* Você deve gerar novamente a qualquer momento que uma experiência é alterada.

**Compartilhando URLs de experiência**

* Você pode visualizar uma experiência mesmo que não faça parte do público-alvo.
* Você pode compartilhar URLs de experiência com colegas que não tenham acesso ao Adobe Target.

**Visualizando experiências com URLs de experiência**

* A visualização funciona para qualquer atividade salva, desde que a página não tenha sido alterada.
* O URL de experiência está disponível independentemente da atividade estar ativa ou inativa.
* Não é possível visualizar uma experiência com status Rascunho
* Os relatórios não são impactados pela visualização dos URLs de experiência.

**Resolvendo problemas de URLs de experiência**

* Se você não conseguir ver a visualização na nova guia (devido ao cache do navegador), tente atualizar duas ou três vezes ou copiar o link e abri-lo em um novo navegador, nova sessão ou no modo privado do navegador.
* Se estiver executando o seu próprio controle de qualidade para a atividade ou se encaminhar links para outra equipe, você pode visualizar facilmente as experiências específicas sem a configuração de testes separados.

