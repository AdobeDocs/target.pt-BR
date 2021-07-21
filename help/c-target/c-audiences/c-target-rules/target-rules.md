---
keywords: Direcionamento, categoria de metas, condições de meta, audience manager, parâmetros de perfil personalizados, perfil do visitante, parâmetros de usuário personalizado, regras de metas
description: Saiba como usar categorias (como Navegador, Geo, Rede, Sistema operacional, Perfil do visitante) para direcionar conteúdo.
title: Quais são as categorias para públicos-alvo?
feature: Públicos-alvo
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 50%

---

# Categorias para públicos

Você pode direcionar qualquer um dos vários atributos de categoria usando [!DNL Adobe Target]. Para criar regras de direcionamento (ou grupos) para cada atributo, arraste e solte os atributos desejados no construtor de público-alvo .

![Atributos para públicos-alvo](/help/c-target/c-audiences/assets/attributes.png)

Quando uma categoria específica é selecionada, você pode aplicar uma ou mais condições de definição de metas. Por exemplo, na categoria Geo, defina uma regra como Cidade=São Francisco. Uma condição OR é criada quando múltiplos valores são adicionados. O visitante somente deve corresponder a um dos valores para atender à condição de definição de metas. Para condições E no mesmo parâmetro, crie uma meta de expressão personalizada.

Após criar uma regra, clique em **[!UICONTROL Concluído]**. Um resumo das regras é exibido ao lado do link de direcionamento do nível.

Você pode refinar uma regra ao adicionar mais condições, ou criar regras adicionais em outras categorias. Por exemplo, você pode direcionar somente usuários do Firefox de São Francisco que acessaram seu site pelo Google. Defina a categoria [!UICONTROL Geo] para direcionar usuários de São Francisco, a categoria [!UICONTROL Navegador] para direcionar usuários usando o Firefox e a categoria [!UICONTROL Fontes de Tráfego] para direcionar usuários provenientes de [!UICONTROL Do Google]. As regras criadas em várias categorias são combinadas com o operador AND.

Para criar regras de definição de metas complexas que incluem operações OR entre categorias, crie uma meta de expressão.

Você também pode direcionar parâmetros de perfis personalizados e parâmetros de `user.`. Ao adicionar um público-alvo, arraste e solte **[!UICONTROL Perfil do visitante]** e escolha o parâmetro que deseja usar para direcionar sua atividade. Se o parâmetro desejado não for exibido, ele não foi acionado por uma mbox.

Use a caixa de pesquisa para pesquisar sua lista de [!UICONTROL Públicos-alvo]. Você pode procurar qualquer parte de um nome de público-alvo ou pode colocar uma determinada sequência de caracteres entre aspas.

Você pode classificar a lista [!UICONTROL Audience] por nome de público ou pela data da última modificação. Para classificar por nome ou data, clique no cabeçalho da coluna e selecione para exibir os públicos-alvo em ordem crescente ou decrescente.

## Vídeo de treinamento: Criação de públicos-alvo ![Selo tutorial](/help/assets/tutorial.png)

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)
