---
keywords: Direcionamento, categoria de metas, condições de meta, audience manager, parâmetros de perfil personalizados, perfil do visitante, parâmetros de usuário personalizado, regras de metas
description: Saiba como usar categorias (como Navegador, Geografia, Rede, Sistema operacional, Perfil do visitante) para direcionar conteúdo.
title: Quais são as categorias para públicos-alvo?
feature: Audiences
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 47%

---

# Categorias para públicos

Você pode direcionar qualquer um dos vários atributos de categoria usando [!DNL Adobe Target]. Para criar regras de direcionamento (ou grupos) para cada atributo, arraste e solte os atributos desejados no painel do Audience Builder.

![Atributos para públicos-alvo](/help/main/c-target/c-audiences/assets/attributes.png)

Quando uma categoria específica é selecionada, você pode aplicar uma ou mais condições de definição de metas. Por exemplo, na categoria Geo, defina uma regra como Cidade=São Francisco. Uma condição OR é criada quando múltiplos valores são adicionados. O visitante somente deve corresponder a um dos valores para atender à condição de definição de metas. Para condições E no mesmo parâmetro, crie uma meta de expressão personalizada.

Depois de criar uma regra, clique em **[!UICONTROL Done]**. Um resumo das regras é exibido ao lado do link de direcionamento do nível.

Você pode refinar uma regra ao adicionar mais condições, ou criar regras adicionais em outras categorias. Por exemplo, você pode direcionar somente usuários do Firefox de São Francisco que acessam seu site pelo Google. Defina a categoria [!UICONTROL Geo] para usuários de destino de São Francisco, a categoria [!UICONTROL Browser] para usuários de destino usando Firefox e a categoria [!UICONTROL Traffic Sources] para usuários de destino provenientes de [!UICONTROL From Google]. As regras criadas entre categorias são combinadas com o operador AND.

Para criar regras de direcionamento complexas que incluem operações OR entre categorias, crie um target de expressão.

Você também pode direcionar parâmetros de perfis personalizados e parâmetros de `user.`. Ao adicionar um público-alvo, arraste e solte **[!UICONTROL Visitor Profile]** e escolha o parâmetro que você deseja usar para direcionar sua atividade. Se o parâmetro desejado não for exibido, o parâmetro não foi acionado por uma mbox.

Use a caixa de pesquisa para pesquisar a lista [!UICONTROL Audiences]. Você pode procurar qualquer parte de um nome de público-alvo ou pode colocar uma determinada sequência de caracteres entre aspas.

Você pode classificar a lista [!UICONTROL Audience] por nome de público-alvo ou pela data da última modificação. Para classificar por nome ou data, clique no cabeçalho da coluna e selecione para exibir os públicos-alvo em ordem crescente ou decrescente.

## Vídeo de treinamento: Criando públicos-alvo ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)
