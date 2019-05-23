---
description: Se a atividade não aparecer no site, essas sugestões de solução de problemas ajudarão a encontrar uma solução.
keywords: solucionar problemas do target, solução de problemas do target, conteúdo padrão, teste não ativo, atividade não ativa, não funcionamento do direcionamento, exibições da experiência anterior, não é possível criar atividades, não é possível criar atividades, criar atividades, estrutura de página alterada, estrutura de página modificada, mensagem de erro, script de perfil para a exclusão do erro, não funcionamento do ajax
seo-description: Se a atividade não aparecer no site, essas sugestões de solução de problemas ajudarão a encontrar uma solução.
seo-title: Solução de problemas de atividades
solution: Target
title: Solução de problemas de atividades
topic: Advanced,Standard,Classic
uuid: 5b22c369-0efc-48c0-a0dc-0179b18536fe
translation-type: tm+mt
source-git-commit: fef00b45291c5e73cb476c3da28b4d7242300f10

---


# Solução de problemas de atividades{#troubleshoot-activities}

Se a atividade não aparecer no site, essas sugestões de solução de problemas ajudarão a encontrar uma solução.

>[!NOTE]
>
>Além das seguintes informações de solução de problemas, consulte [Solução de problemas](../../r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) a fim de obter os links para tópicos de solução de problemas adicionais, perguntas frequentes e outras informações úteis sobre como solucionar problemas de atividades e outros recursos.[!DNL Adobe Target]

As seções a seguir contêm problemas que podem ser encontrados com as soluções sugeridas.

## Você está vendo conteúdo padrão.

Verifique se a sua atividade foi concluída e ativada.

## O teste não está ativado.

**Validar:** vá para a guia de visão geral e veja se o teste está marcado como inativo ou rascunho.

**Opções:**

* Ative o teste.
* Use os links de visualização para exibir o teste inativo.

## Você não está qualificado para as condições de direcionamento de público-alvo.

**Validar:** examine as condições de direcionamento na página de visão geral.

**Opções:**

* Qualifique-se e tente novamente.
* Use os links de visualização para ignorar as condições de direcionamento.

## A página não está qualificada para as condições de direcionamento de página.

**Validar:** na página de visão geral, determine se a página está fora das condições de direcionamento.

**Opções:**

* Vá para o Visual Experience Composer, clique em URL\&gt; Avançado\&gt; página atual.

## Uma experiência anterior é exibida, em vez da nova experiência.

**Validar:** tente uma das opções abaixo e tente visualizar a experiência de novo.

**Opções:**

* Limpe o cache e os cookies e tente de novo.

* Tente um navegador diferente.
* Use o modo Privado/Incógnito.

## Você foi adicionado recentemente ao Target, mas não pode criar atividades.

**Validar:** Clique em Criar atividade. Se a opção não estiver disponível, é possível que você não tenha recebido direitos suficientes para criar uma atividade.

**Opções:**

Depois que você for adicionado como um usuário do Target, precisará ter a função Aprovador para criar Atividades.

* Peça que o administrador da sua conta o atribua como um Aprovador.
* Se você for o administrador, atribua a si mesmo a função de Aprovador em Configurar &gt; Usuários no Target Standard.

   Consulte [Atribuir a função de aprovador a si próprio](../../administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## A estrutura da página foi alterada desde a configuração da atividade.

**Validar:** vá para o Visual Experience Composer para a atividade existente. Procure a mensagem de aviso indicando que os seletores (ou a estrutura) foram alterados.

**Opções:**

* Recrie a atividade.

Para mais informações sobre como as modificações da página afetam a capacidade do Target de ser exibido, consulte [Cenários de modificação da página](../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## A estrutura da página é modificada durante seu carregamento (em tempo de execução).

**Validar:** pergunte ao desenvolvedor.

**Observação:** para que o Target reconheça onde as alterações de atividade devem ser aplicadas, evite inserir dinamicamente com elementos com a mesma classe ou modificar dinamicamente a classe de qualquer um de seus irmãos.

**Opções:**

* Atualize o código de página para identificar exclusivamente cada elemento que será testado (usando uma id).
* Interrompa a modificação dinâmica da classe ou seus irmãos, conforme descrito acima.

Para mais informações sobre como as modificações da página afetam a capacidade do Target de ser exibido, consulte [Cenários de modificação da página](../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Mbox.js está preenchendo todo o código subsequente fora do cabeçalho e no corpo do texto.

**Validar:** veja a origem para determinar se uma declaração segue o arquivo mbox.js antes de fechar </body> tag.

**Opções:**

* Coloque o mbox.js como o último item na seção `<head>` da página.
* Use ids div exclusivas nos elementos de nível mais alto do corpo.

## Outras atividades estão em execução na mesma página.

**Validar:** use a guia Colisões para ver se outras atividades estão em execução.

**Observação:** a guia Colisões não funciona com o módulo Teste de Modelo.

**Opções:**

* Aumente a prioridade dessa atividade.
* Diminua a prioridade de outras atividades.
* Desative outras atividades.

## Uma mensagem de erro é exibida ao excluir um script de perfil.

**Validar:** a exclusão de um script de perfil do Target Standard/Premium exibe a mensagem de erro: &quot;Falha ao excluir o script de perfil&quot;.

**Opções:**

Faça uma das seguintes opções:

* Exclua novamente. A mensagem de sucesso é exibida.
* Aguarde cerca de 10 minutos para que o importador do Target Standard/Premium seja executado. O importador atualiza a lista de scripts de perfil.

## Algumas chamadas ajax da mbox não estão funcionando.

**Observação:** várias chamadas de mbox ajax com o mesmo nome de mbox mas diferentes parâmetros não funcionarão na mesma página. Somente a primeira chamada será feita.

## Você ativou uma atividade usando a API do Target, mas a atividade mostra um status Inativo na interface do Target.

Ao executar determinadas ações, como ativar uma atividade fora da interface usando a API do Target, a atualização poderá levar até dez minutos para se propagar na interface do usuário.