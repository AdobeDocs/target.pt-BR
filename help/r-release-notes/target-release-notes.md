---
keywords: release notes;releases;updates;future release;enhancements;new features;fixes;updates
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as versões mais recentes ou futuras do Adobe Target DNL.
title: Notas de pré-lançamento de Adobe Target
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 26447c745cf56f3e04ad477bc05446e5d8ab76c1
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 16%

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Este artigo contém informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos à mudança sem aviso prévio.

**Última atualização: 22 de julho de 2020**

Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser as mesmas, dependendo do tempo das versões. Os números de edição entre parênteses são para uso interno da [!DNL Adobe].

>[!NOTE]
>
>* **desaprovação** da mbox.js: Em 30 de agosto de 2020, o Adobe Target não oferecerá mais suporte à biblioteca mbox.js. Após 30 de agosto de 2020, todas as chamadas feitas do mbox.js falharão e afetarão suas páginas que possuem atividades do Público alvo em execução, atendendo ao conteúdo padrão. Recomendamos que todos os clientes migrem para a versão mais recente da biblioteca do at.js antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Como o At.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e o Construtor de habilidades [Adobe Target: Bate-papo do desenvolvedor, migre o Adobe Target mbox.js para o at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Embora a mbox.js seja atualmente compatível, não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. O mais recente at.js oferece muitas vantagens sobre o mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única.
   >
   >   
   Ao mudar todos os clientes para o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferta do suporte que você espera da Adobe.
   >
   >
* **Anúncios** do Público alvo: Consulte a página de anúncios do Público alvo para obter informações sobre eventos futuros, incluindo sessões do Target Skill Builder, bate-papos para desenvolvedores, webinars e sessões do Target Coffee Break. Para obter mais informações, consulte Anúncios de [Públicos alvos](/help/r-release-notes/target-announcements.md).


## Target Standard/Premium 20.7.1 (22 de julho de 2020)

Essa versão inclui os seguintes aprimoramentos:

### [!UICONTROL Atualização da interface da seção de administração]

Estamos gradualmente reescrevendo a interface inteira usando uma nova pilha técnica para oferta de melhor desempenho, reduzir o tempo de manutenção necessário ao lançar novos recursos e melhorar a experiência do usuário em todo o produto. [!DNL Target] A primeira seção atualizada é a seção [!UICONTROL Configuração] , que foi renomeada para [!UICONTROL Administração].

Como parte dessa atualização, você poderá executar facilmente muitas ações usando as páginas na seção [!UICONTROL Administração] , como:

* Baixe o arquivo at.js mais recente na guia [!UICONTROL Implementação] (**[!UICONTROL Administração]** > **[!UICONTROL Implementação]**).
* Personalize suas configurações do at.js e possa revisar facilmente suas alterações (**[!UICONTROL Administração]** > **[!UICONTROL Implementação]**).
* Modifique as configurações de relatórios aprimoradas, como moeda e fuso horário padrão, IPs a serem excluídos do relatórios etc. (**[!UICONTROL Administração]** > **[!UICONTROL Relatórios]**)
* Ofuscar endereços IP de visitante por motivos de privacidade (**[!UICONTROL Administração]** > **[!UICONTROL Implementação]**)
* Visualização a lista existente de usuários por espaço de trabalho e suas funções, antes de gerenciá-los no Adobe Admin Console (**[!UICONTROL Administração]** > **[!UICONTROL Usuários]**).
* Pesquise e filtre todas as tabelas na seção [!UICONTROL Administração] .

### Melhorias, correções e alterações

Esta versão contém os seguintes aprimoramentos, correções e alterações:

* Correção de um problema que impedia a retenção das preferências do site após a atualização. (TGT-37239)
* Correção de um problema que impedia o funcionamento correto de [!UICONTROL Inserir após] > [!UICONTROL Imagem] com imagens SVG (Scalable Vetor Graphics). (TGT-37242)
* Correção de um problema para usuários com a função [!UICONTROL Publisher] que impedia a exclusão de atividades de rascunho. (TGT-37358)
* Correção de um problema que impedia os usuários de editar uma atividade quando [!UICONTROL Todos os Meus Espaços de Trabalho] estava selecionado. (TGT-37276)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
