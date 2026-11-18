---
keywords: solução de problemas destino;solução de problemas destino;conteúdo padrão;teste não ativo;atividade não ativa;direcionamento não funcionando;a experiência anterior é exibida;não é possível criar atividades;não é possível criar atividades;criar atividades;estrutura de página alterada;estrutura de página modificada;mensagem de erro;script de perfil de exclusão de erro;ajax não está funcionando
description: Encontre sugestões para a solução de problemas se a atividade do Adobe [!DNL Target] não aparecer no seu site.
title: Como posso solucionar problemas de atividades?
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
TQID: 'https://experienceleague.adobe.com/L-011t7q6c3aICs0ZrM01m9pZByH86FKGiLG1A7Rl2s'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9621044454d3e1b47c06cac2ad5d08cba8e482c0
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 7%
---
# Introdução às atividades de solução de problemas {#troubleshooting-activities}

>[!BEGINSHADEBOX]

**Nesta página:** encontre soluções para problemas comuns quando uma atividade [!DNL Adobe Target] não aparecer no site ou não se comportar conforme esperado.

>[!ENDSHADEBOX]

Várias causas podem impedir que uma atividade [!DNL Adobe Target] apareça no site. Use os problemas a seguir e as soluções sugeridas para identificar a causa e aplicar a correção.

>[!NOTE]
>
>Além das seguintes informações de solução de problemas, consulte [Solução de Problemas](/help/main/r-troubleshooting-target/troubleshooting-target.md) a fim de obter os links para tópicos de solução de problemas adicionais, perguntas frequentes e outras informações úteis sobre como solucionar problemas de atividades e outros recursos no [!DNL Adobe Target].

## A atividade não é exibida conforme esperado {#not-displayed}

+++ Você está vendo o conteúdo padrão

Verifique se a atividade foi concluída e ativada.

+++

</br>

+++ A atividade não está ativa

**Validar:** na guia **[!UICONTROL Visão geral]**, verifique se a atividade está marcada como inativa ou rascunho.

**Opções:**

* Ativar a atividade.
* Use links de visualização para exibir a atividade inativa.

+++

</br>

+++ Você não está qualificado para as condições de direcionamento de público-alvo

**Validar:** Revise as condições de direcionamento na página **[!UICONTROL Visão geral]**.

**Opções:**

* Qualifique-se para o público-alvo e tente novamente.
* Use links de visualização para ignorar as condições de direcionamento.

+++

</br>

+++ A página não se qualifica para as condições de direcionamento de página

**Validar:** na página **[!UICONTROL Visão geral]**, determine se a página está fora das condições de direcionamento.

**Opções:**

* Vá para o **[!UICONTROL Visual Experience Composer]** e clique em URL > Avançado > página atual.

+++

</br>

+++ Uma experiência anterior é exibida em vez da nova experiência

**Validar:** Tente uma das seguintes opções e tente exibir a experiência novamente.

**Opções:**

* Limpe o cache e os cookies e tente novamente.
* Tente um navegador diferente.
* Use o modo privado ou anônimo.

+++

</br>

+++ A estrutura da página mudou desde a configuração da atividade

**Validar:** vá para o **[!UICONTROL Visual Experience Composer]** da atividade existente e procure uma mensagem de aviso que indique que os seletores (ou estrutura) foram alterados.

**Opções:**

* Recrie a atividade.

Para obter mais informações sobre como as modificações de página afetam a capacidade de [!DNL Target] exibir conteúdo, consulte [Cenários de Modificação de Página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md).

+++

</br>

+++ A estrutura da página é modificada durante o carregamento da página (em tempo de execução)

**Validar:** Pergunte ao desenvolvedor.

**Observação:** para [!DNL Target] reconhecer onde as alterações da atividade devem ser aplicadas, evite inserir dinamicamente um elemento com a mesma classe ou modificar dinamicamente a classe de qualquer irmão.

**Opções:**

* Atualize o código de página para identificar exclusivamente cada elemento testado, usando uma ID.
* Pare de modificar dinamicamente a classe ou seus irmãos, conforme descrito acima.

Para obter mais informações sobre como as modificações de página afetam a capacidade de [!DNL Target] exibir conteúdo, consulte [Cenários de Modificação de Página](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md).

+++

</br>

+++ Outras atividades estão sendo executadas na mesma página

**Validar:** Use a guia **[!UICONTROL Conflitos]** para ver se há outras atividades em execução.

**Observação:** a guia **[!UICONTROL Conflitos]** não funciona com o módulo de Teste de Modelo.

**Opções:**

* Aumente a prioridade dessa atividade.
* Diminua a prioridade das outras atividades.
* Desative as outras atividades.

+++

## Usuários, API e a interface do {#users-api-ui}

+++ Criei uma atividade usando a interface do usuário [!DNL Target] e não consigo atualizá-la por meio da API

As atividades criadas usando a interface do usuário [!DNL Target] devem ser atualizadas por meio da interface do usuário [!DNL Target]. As atividades criadas por meio da API devem ser atualizadas por meio da API. Por exemplo, se você criar uma atividade usando a API, mas depois editar a atividade por meio da interface do usuário do [!DNL Target], nem todas as alterações serão atualizadas. Todas as alterações são armazenadas no back-end e podem ser atualizadas fazendo outra chamada de API.

Como prática recomendada, atualize a atividade usando o mesmo método (interface do usuário ou API) usado para criá-la.

+++

</br>

+++ Você foi adicionado recentemente a [!DNL Target], mas não pode criar atividades

**Validar:** Clique Em **[!UICONTROL Criar Atividade]**. Se a opção não estiver disponível, é possível que você não tenha recebido direitos suficientes para criar uma atividade.

**Opções:**

Depois de ser adicionado como usuário em [!DNL Target], você precisará da função de **[!UICONTROL Aprovador]** para criar atividades.

* Peça ao administrador de sua conta para torná-lo um aprovador.
* Se você for o administrador, atribua a si mesmo a função **[!UICONTROL Aprovador]** de **[!UICONTROL Administração]** > **[!UICONTROL Usuários]** em [!DNL Target]. Consulte [Atribuir a função de Aprovador a si próprio](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

+++

</br>

+++ Você ativou uma atividade usando a API [!DNL Target], mas a atividade mostra um status de [!UICONTROL Inativo] na interface [!DNL Target]

Quando você executa determinadas ações, como ativar uma atividade fora da interface usando a API [!DNL Target], a atualização pode levar até dez minutos para se propagar para a interface.

+++

</br>

+++ Uma mensagem de erro é exibida ao excluir um script de perfil

**Validar:** a exclusão de um script de perfil de [!DNL Target] exibe a mensagem de erro &quot;Falha ao excluir script de perfil.&quot;

**Opções:**

Faça uma das seguintes opções:

* Exclua o script de perfil novamente. A mensagem de sucesso é exibida.
* Aguarde cerca de 10 minutos para que o importador [!DNL Target] seja executado. O importador atualiza a lista de scripts de perfil.

+++

## Chamadas e conversão {#calls-and-conversion}

+++ Algumas chamadas ajax [!DNL Target] não estão funcionando

**Observação:** várias chamadas de ajax [!DNL Target] com o mesmo nome mas diferentes parâmetros não funcionam na mesma página. Somente a primeira chamada é feita.

+++

</br>

+++ Após a conversão da atividade, o visitante não está em nenhuma experiência

Em casos raros, se a métrica de conversão da atividade que qualifica um visitante para uma experiência for enviada na mesma solicitação que a qualificação de atividade, o visitante pode não estar em nenhuma experiência após o envio da solicitação. Nessa situação, o visitante vê o conteúdo padrão e a ID de experiência capturada por tokens é -1. [!DNL Adobe] não recomenda enviar qualificação e conversão de atividade na mesma solicitação [!DNL Target].

Se quiser enviar ambas as métricas na mesma solicitação, use as **[!UICONTROL Configurações avançadas]** para especificar que o visitante permaneça na mesma experiência após a conversão.

+++
