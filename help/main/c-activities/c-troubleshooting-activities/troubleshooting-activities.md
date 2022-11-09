---
keywords: solucionar problemas do target, solução de problemas do target, conteúdo padrão, teste não ativo, atividade não ativa, não funcionamento do direcionamento, exibições da experiência anterior, não é possível criar atividades, não é possível criar atividades, criar atividades, estrutura de página alterada, estrutura de página modificada, mensagem de erro, script de perfil para a exclusão do erro, não funcionamento do ajax
description: Encontre sugestões para a solução de problemas se a atividade do Adobe  [!DNL Target]  não aparecer no seu site.
title: Como posso solucionar problemas de atividades?
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
source-git-commit: f1cbc46323f71c2fa091cd2c9a3e49d34676e7a1
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 50%

---

# Solução de problemas de atividades

Se a atividade do [!DNL Adobe Target] não aparecer no site, essas sugestões de solução de problemas ajudarão a encontrar uma solução.

>[!NOTE]
>
>Além das seguintes informações de solução de problemas, consulte [Solução de problemas do Target](/help/main/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) a fim de obter os links para tópicos de solução de problemas adicionais, perguntas frequentes e outras informações úteis sobre como solucionar problemas de atividades e outros recursos no [!DNL Adobe Target].

As seções a seguir contêm problemas que podem ser encontrados com as soluções sugeridas.

## Criei uma atividade usando a interface do [!DNL Target] e não consigo atualizá-la por meio da API.

Atividades criadas usando o [!DNL Target] A interface do usuário deve ser atualizada por meio do [!DNL Target] IU. As atividades criadas por meio da API devem ser atualizadas por meio da API. Por exemplo, se você criar uma atividade originalmente usando a API, mas depois editar a atividade por meio do [!DNL Target] IU, nem todas as alterações são atualizadas. Todas as alterações são armazenadas no back-end e podem ser atualizadas fazendo outra chamada de API.

Como prática recomendada, tente atualizar a atividade usando o mesmo método (interface do usuário ou API) usado para criar a atividade originalmente.

## Você está vendo conteúdo padrão.

Certifique-se de que a atividade esteja concluída e tenha sido ativada.

## O teste não está ativado.

**Validar:** Ir para [!UICONTROL Visão geral] e veja se o teste está marcado como inativo ou rascunho.

**Opções:**

* Ative o teste.
* Use os links de visualização para exibir o teste inativo.

## Você não se qualifica para as condições de direcionamento de público-alvo.

**Validar:** examine as condições de direcionamento na página de visão geral.

**Opções:**

* Qualifique-se e tente novamente.
* Use os links de visualização para ignorar as condições de direcionamento.

## A página não se qualifica para as condições de direcionamento de página.

**Validar:** No [!UICONTROL Visão geral] determine se a página está fora das condições de direcionamento.

**Opções:**

* Vá para o [!UICONTROL Visual Experience Composer], clique em URL > Avançado > página atual.

## Uma experiência anterior é exibida, em vez da nova experiência.

**Validar:** tente uma das opções abaixo e tente visualizar a experiência de novo.

**Opções:**

* Limpe o cache e os cookies e tente de novo.
* Tente um navegador diferente.
* Use o modo Privado/Incógnito.

## Você foi adicionado recentemente ao [!DNL Target], mas não pode criar atividades.

**Validar:**[!UICONTROL  Clique em Criar atividade]. Se a opção não estiver disponível, é possível que você não tenha recebido direitos suficientes para criar uma atividade.

**Opções:**

Depois de ser adicionado como usuário no [!DNL Target], você precisa ter a variável [!UICONTROL Aprovador] para criar atividades.

* Peça ao Administrador da sua conta para torná-lo um aprovador.
* Se você for o administrador, dê a si mesmo a [!UICONTROL Aprovador] função de **[!UICONTROL Administração]** > **[!UICONTROL Usuários]** em [!DNL Target].

   Consulte [Atribuir a função de aprovador a si próprio](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## A estrutura da página foi alterada desde a configuração da atividade.

**Validar:**[!UICONTROL  vá para o Visual Experience Composer para a atividade existente. ] Procure a mensagem de aviso indicando que os seletores (ou a estrutura) foram alterados.

**Opções:**

* Recrie a atividade.

Para obter mais informações sobre como as modificações de página afetam [!DNL Target]A capacidade de exibição do para ver [Cenários de modificação da página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## A estrutura da página é modificada durante seu carregamento (em tempo de execução).

**Validar:** pergunte ao desenvolvedor.

**Observação:** Para [!DNL Target] para reconhecer onde as alterações de atividade devem ser aplicadas, evite inserir dinamicamente um elemento com a mesma classe ou modificar dinamicamente a classe de quaisquer irmãos.

**Opções:**

* Atualize o código de página para identificar exclusivamente cada elemento que está sendo testado (usando uma id).
* Interrompa a modificação dinâmica da classe ou seus irmãos, conforme descrito acima.

Para obter mais informações sobre como as modificações de página afetam [!DNL Target]A capacidade de exibição do para ver [Cenários de modificação da página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Outras atividades estão em execução na mesma página.

**Validar:** Use o [!UICONTROL Colisões] para ver se outras atividades estão em execução.

**Observação:**[!UICONTROL  a guia Colisões não funciona com o módulo Teste de Modelo.]

**Opções:**

* Aumente a prioridade dessa atividade.
* Diminua a prioridade de outras atividades.
* Desative outras atividades.

## Uma mensagem de erro é exibida ao excluir um script de perfil.

**Validar:**[!DNL Target] a exclusão de um script de perfil do exibe a mensagem de erro: &quot;Falha ao excluir o script de perfil&quot;.

**Opções:**

Faça uma das seguintes opções:

* Exclua o script de perfil novamente. A mensagem de sucesso é exibida.
* Aguarde cerca de 10 minutos para a [!DNL Target] importador a ser executado. O importador atualiza a lista de scripts de perfil.

## Algumas chamadas ajax do [!DNL Target] não estão funcionando.

**Observação:** Múltiplo ajax [!DNL Target] chamadas com o mesmo nome, mas parâmetros diferentes, não funcionam na mesma página. Somente a primeira chamada é feita.

## Você ativou uma atividade usando a API do [!DNL Target], mas a atividade mostra um status de [!UICONTROL Inativo] na interface do [!DNL Target].

Quando você executa determinadas ações, como ativar uma atividade fora da interface do usuário usando o [!DNL Target] A API pode levar até dez minutos para se propagar para a interface do usuário.

## Após a conversão da atividade, o visitante não está em nenhuma experiência.

Em casos raros, se a métrica de conversão da atividade para se qualificar para uma experiência for enviada na mesma solicitação que a qualificação de atividade, o visitante pode não estar em nenhuma experiência depois que a solicitação é enviada. Nessa situação, o visitante vê o conteúdo padrão e a ID da experiência capturada pelos tokens como -1. [!DNL Adobe] não recomenda enviar qualificação de atividade e conversão na mesma [!DNL Target] solicitação.

Se você deseja enviar ambas as métricas na mesma solicitação, é possível usar [!UICONTROL Configurações avançadas] para especificar que o visitante permaneça na mesma experiência após a conversão.
