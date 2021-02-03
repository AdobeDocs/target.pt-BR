---
keywords: visualização de experiência, urls de experiências, gerar urls, ver urls de experiências
description: É possível gerar URLs de pré-visualização de experiência para o Público alvo Automated Personalization atividade para ver o conteúdo de experiência diretamente no seu site antes que a atividade esteja ativa para fins de pré-visualização e QA. URLs de pré-visualização de experiência ignoram a definição de metas para forçar a visualização de uma experiência específica.
title: Pré-visualização do Automated Personalization Atividade com URLs de Pré-visualização da experiência
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 64%

---


# ![automated personalization atividade ](/help/assets/premium.png) PREMIUMPreview com URLs de pré-visualização de experiência

É possível gerar URLs de pré-visualização de experiência para o Público alvo Automated Personalization atividade para ver o conteúdo de experiência diretamente no seu site antes que a atividade esteja ativa para fins de pré-visualização e QA. URLs de pré-visualização de experiência ignoram a definição de metas para forçar a visualização de uma experiência específica.

>[!NOTE]
>
>Os URLs de pré-visualização da experiência para Automated Personalization diferem do modo de QA da Atividade. O modo controle de qualidade da atividade permite que você crie URLs de atividades para outros tipos de atividades. Para obter mais informações, consulte [Garantia de qualidade da atividade](/help/c-activities/c-activity-qa/activity-qa.md).
>
>Os URLs de pré-visualização de experiência para atividades AP só estão disponíveis ao usar o at.js 1.x. No momento, os URLs de pré-visualização de experiência para atividades AP não são suportados para at.js 2.x.

Use URLs de pré-visualização de experiência para compartilhar experiências com membros da equipe e para experiências de QA em navegadores e ambientes, sem criar uma atividade de QA separada. Este recurso é particularmente útil se um site for complexo ou se as políticas de segurança não permitirem que o site seja visualizado em um simulador.

1. Crie uma [atividade de Personalização automatizada](/help/c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou clique na atividade para abri-la.

   A atividade não precisa estar inicializada para visualizar uma experiência.
1. Na página de resumo da atividade, clique nos três pontos verticais e clique em **[!UICONTROL Exibir URLs da experiência]**.
1. Reveja e/ou especifique seus URLs.

   * Se você está usando o Visual Experience Composer, o URL padrão que você especificou para a atividade é inserido automaticamente e um link é gerado para cada experiência na sua atividade. Você pode alterar este URLS e adicionar outros, se quiser.
   * Se você está usando o Experience Composer baseado em formulário, nenhum URL padrão é inserido automaticamente. Se você ainda não criou os URLs de pré-visualização da experiência, clique em **Adicionar novo URL**. Você deve especificar todos URLs que quer visualizar além de um nome para cada URL.

   Você pode adicionar vários URLs, o que é útil ao executar um teste multipágina ou um teste de modelo e você quer visualizar a atividade em mais de uma página.

   Uma janela modal exibe links para suas experiências em seu site para obter uma &quot;visualização real&quot; das experiências fora do Visual Experience Composer do Target. É necessário compartilhar os links da mensagem para compartilhar a visualização. Clicar em um link e copiar o URL resultante da página não funciona porque o URL contém um parâmetro que só exibe a página corretamente quando você acessa a página a partir do link na mensagem. Em vez disso, copie o texto na janela modal e envie o texto inteiro por email para sua equipe.
1. Clique em **[!UICONTROL Gerar tudo]** e, em seguida, clique em cada experiência para visualizá-la.

   Se você fizer alterações na experiência, certifique-se de gerar novos links de pré-visualização para sua equipe, retornando à janela modal e clicando em **Renovar links** para obter novos links.

   **Observação:** os links de visualização abrem em novas guias e requerem que o bloqueador de pop-up do seu navegador esteja desabilitado.

1. Clique no nome de cada experiência para visualizar a atividade.

   A página é aberta, exibindo a atividade.
1. Clique em **[!UICONTROL Concluído]** para retornar ao resumo da atividade.

## Considerações {#example_9F2B333BC63143FF99AE331F57E8BA4C}

**Geração de URLs de Pré-visualização de experiência**

* O URL da pré-visualização da experiência não é afetado pela divisão de tráfego entre experiências.
* Direcionamento no nível do público-alvo não afeta a visualização.
* Você pode gerar automaticamente um máximo de 300 URLs de experiência por atividade. Após isso, você deve gerar os URLs manualmente.
* Você pode gerar automaticamente um máximo de 300 URLs de experiência por atividade. Após isso, você deve gerar os URLs manualmente.
* Dependendo do número de experiências, gerar os URLs pode levar até cinco minutos. Não feche caixa de diálogo ou os URLs gerados serão perdidos.
* Os links de visualização gerados são válidos por dois meses. Após este período, você deve gerar seus URLs de visualização novamente.
* Você deve gerar novamente a qualquer momento que uma experiência é alterada.

**Compartilhamento de URLs de Pré-visualização de experiência**

* Você pode visualizar uma experiência mesmo que não faça parte do público-alvo.
* Você pode compartilhar URLs de pré-visualização de experiência com colegas que não têm acesso ao Adobe Target.

**Exibição de experiências com URLs de Pré-visualização de experiência**

* A visualização funciona para qualquer atividade salva, desde que a página não tenha sido alterada.
* O URL de pré-visualização da experiência está disponível se a atividade estiver ativa ou inativa.
* Não é possível pré-visualização de uma experiência com status de Rascunho.
* O relatórios não é afetado pela exibição de URLs de pré-visualização de experiência.

**Solução de problemas de URLs de Pré-visualização da experiência**

* Se você não conseguir ver a visualização na nova guia (devido ao cache do navegador), tente atualizar duas ou três vezes ou copiar o link e abri-lo em um novo navegador, nova sessão ou no modo privado do navegador.
