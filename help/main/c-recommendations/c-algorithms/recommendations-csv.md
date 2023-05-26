---
keywords: criar critérios personalizados, algoritmos, critérios, critérios de recomendações, csv, ftp, carregar csv
description: Saiba como fazer upload de um arquivo CSV para personalizar suas recomendações no Adobe [!DNL Target] Recommendations.
title: Como fazer upload dos critérios personalizados no Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 39%

---

# Upload dos critérios personalizados

Faça upload de um arquivo CSV para personalizar suas recomendações no [!DNL Adobe Target].

Existem vários meios de alcançar a tela [!UICONTROL Criar novos critérios]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* No **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]** tela da biblioteca, clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar critérios]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!DNL Recommendations].
* Ao criar uma [!DNL Recommendations] atividade usando o [!UICONTROL Visual Experience Composer] (VEC), você será levado imediatamente ao [!UICONTROL Selecionar critério] depois de selecionar um elemento na página e clicar em [!UICONTROL Substituir por Recommendations], [!UICONTROL Inserir Recommendations antes de]ou [!UICONTROL Inserir Recommendations após]. Você pode selecionar um critério disponível ou clicar em **[!UICONTROL Criar critérios]**. Se você criar um novo critério, poderá salvá-lo para uso com outros [!DNL Recommendations] atividades. Para obter mais informações, consulte [Criar uma atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Ao editar uma [!DNL Recommendations] atividade, clique em uma caixa de [!UICONTROL Localização do Recommendations] em sua página e selecione **[!UICONTROL Alterar critérios]**. No [!UICONTROL Selecionar critério] clique em **[!UICONTROL Criar critérios]**. Você pode salvar seu novo critério para uso com outros [!DNL Recommendations] atividades.

As etapas a seguir pressupõem que você acesse o [!UICONTROL Criar novos critérios] usando o primeiro método: a variável **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]** tela da biblioteca.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar critério]**.

1. Preencha as informações em [Informações básicas](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) seção.

   1. No **[!UICONTROL Selecionar algoritmo]** Lista suspensa Tipo, selecione **[!UICONTROL Critérios personalizados]**.

   1. No **[!UICONTROL Algoritmo]** selecione **[!UICONTROL Algoritmo personalizado]**.

      >[!NOTE]
      >
      >As etapas anteriores causam a [!UICONTROL Fazer upload de CSV] para exibir na parte inferior da [!UICONTROL Criar novos critérios] caixa de diálogo.

1. (Condicional) Preencha as informações na [Conteúdo de backup](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) seção.

1. (Condicional) Preencha as informações na [Regras de inclusão](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) seção.

1. No **[!UICONTROL Fazer upload de CSV]** , selecione a **[!UICONTROL Localização]** do seu arquivo CSV.

   ![Fazer upload de seção CSV](assets/upload-csv.png)

   O arquivo CSV deve estar formatado corretamente para ser carregado com sucesso. Clique em **[!UICONTROL Baixar o modelo CSV]** para obter um arquivo CSV formatado corretamente.

   Você tem duas opções de local:

   * **FTP:** para carregar seu arquivo CSV de um servidor FTP, selecione **[!UICONTROL FTP]** e insira as informações necessárias. Você pode usar SSL, que usa o protocolo FTPS para transferir seu arquivo CSV em segurança.
   * **URL:** Para carregar seu arquivo CSV de um URL, selecione **[!UICONTROL URL]** e, em seguida, insira um URL de feed.

1. Clique em **[!UICONTROL Salvar]**.

## Considerações

* As entidades com critérios personalizados (linhas) podem conter até 1.000 itens recomendados (colunas).

* As atualizações de critérios personalizados são &quot;cumulativas&quot; por padrão. Os novos pares de valor-chave especificados no arquivo de upload CSV substituem os pares existentes. Os pares de valores chave existentes que não têm chaves especificadas no upload de CSV ainda estarão disponíveis para entrega e expirarão em 31 dias a partir do momento em que forem carregados pela última vez, como parte do arquivo CSV.

   Entre em contato com o Atendimento ao Cliente para habilitar a configuração para descartar os resultados existentes que não estão inclusos upload CSV. Se essa configuração estiver ativada, somente as chaves presentes no arquivo de feed CSV personalizado estarão disponíveis para entrega. Essa configuração se aplica a todos os critérios personalizados.

* Os feeds de critérios personalizados atualizam uma vez a cada 24 horas.

   Você pode ver os status de carregamento e sincronização do seu critério personalizado na parte de baixo de cada cartão de critério na [!UICONTROL Recommendations] > [!UICONTROL Critérios] página. Você também pode ver o status na variável [!UICONTROL Editar] ao editar os critérios personalizados.

* O fluxo para um upload sem erros deve ser [!UICONTROL Agendado] > [!UICONTROL Baixando arquivo de feed] > [!UICONTROL Importando] > [!UICONTROL Bem-sucedido].

* A seguir estão possíveis mensagens de erro que você poderá receber se [!DNL Target] O encontra um problema com o upload:

   | Mensagem de erro | Detalhes |
   |--- |--- |
   | Erro desconhecido | Indica um erro interno técnico. |
   | Erro de análise | Provavelmente há um problema com o formato do arquivo de feed. Corrija o formato do arquivo e salve novamente o algoritmo, o que reinicia o processo de download do arquivo. |
   | Servidor não encontrado | Forneça um IP ou nome de host que seja visível na internet. |
   | Erro de credenciais | Forneça um usuário e senha válidos para uma conta ativa no servidor. |
   | Diretório não encontrado | Forneça um diretório que exista no servidor. |
   | Arquivo não encontrado | Forneça o nome de um arquivo que exista no servidor dentro do diretório indicado. |

## Vídeo de treinamento: criar critérios no Recommendations (12:33) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo contém as seguintes informações (os detalhes sobre o upload de critérios personalizados começam às 11h43):

* Criar critérios
* Criar sequências de critérios
* Upload dos critérios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
