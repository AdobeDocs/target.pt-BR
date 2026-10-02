---
keywords: Adobe Target;Colaborador;IA;habilidades;experimentação;Recommendations
title: Habilidades de colega de trabalho para o Adobe Target
description: Saiba mais sobre as habilidades de colaborador disponíveis para o Adobe Target, incluindo descoberta de atividades, criação de testes, análise, composição de público-alvo e solução de problemas do Recommendations.
feature: Overview
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: 4b90f47050b63c7e1e6ac5019d45a7b99b3a33b8
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 2%
---

# Habilidades de colega de trabalho para o Adobe Target {#coworker-skills}

>[!BEGINSHADEBOX]

**Nesta página:** descubra as habilidades de Colaborador disponíveis para o Adobe Target, incluindo habilidades para explorar atividades e públicos, criar e configurar testes, analisar desempenho, compor públicos e gerenciar Recomendações.

>[!ENDSHADEBOX]

As habilidades de colegas de trabalho ajudam os profissionais da Adobe Target a usar linguagem natural para explorar seus programas de teste e personalização, criar e configurar atividades, analisar resultados e resolver problemas de entrega. Descreva o que você deseja fazer no Chat do colaborador e, em seguida, revise as recomendações, a configuração ou a análise retornadas antes de tomar uma ação.

As ferramentas de MCP e o Colaborador do [!DNL Adobe Target] são documentadas separadamente e fornecem diferentes recursos:

* [MCP de Destino](../c-integrating-target-with-mac/mcp/target-mcp-tools-reference.md) documenta as ferramentas individuais expostas pelo servidor MCP direto, incluindo seus tipos de atividades, parâmetros, permissões e escopo de leitura ou gravação com suporte.
* O [Colaborador](https://experienceleague.adobe.com/pt-br/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/overview#target-activities-and-audiences) fornece uma camada de orquestração separada em linguagem natural que pode combinar recursos e aplicar fluxos de trabalho adicionais.

A tabela a seguir é uma comparação de alto nível de recursos relacionados.

| Recurso | MCP de destino | Coworker |
| --- | --- | --- |
| Listar experimentos em execução, públicos-alvo, ofertas ou itens alterados recentemente | Sim | Sim |
| Criar uma atividade de Automated Personalization | Não | Não |
| Criar um público do Target | Sim | Sim |
| Crie uma atividade do VEC do Target, uma atividade de Direcionamento de experiência ou um teste A/B | Sim | Sim |
| Criar uma atividade do Target Recommendations | Sim | Sim |
| Criar uma oferta HTML ou JSON no Target | Sim | Sim |
| Usar um fragmento de conteúdo do AEM em uma atividade do Target | Não | Sim |
| Recomende o que está funcionando e o que testar a seguir | Nenhum aviso ou aviso genérico | Sim |


## Plug-in do Target

As seguintes habilidades estão disponíveis no plug-in **Target**:

* **Navegação de Destino**

  Fornece descoberta, inspeção e contagem somente leitura de entidades do Target, incluindo atividades, públicos, ofertas e configurações relacionadas.

>[!BEGINSHADEBOX]

*Prompts de exemplo:*

* &quot;Listar minhas atividades ativas.&quot;
* &quot;Quantas atividades estão sendo executadas no momento?&quot;
* &quot;Mostrar os públicos-alvo e as ofertas usadas por esta atividade.&quot;

>[!ENDSHADEBOX]

* **Veredito da Atividade de Destino**

  Determina se uma atividade está pronta para ser enviada, deve aguardar mais dados, deve parar ou precisa de uma correção, usando cálculos de significância e verificações de configuração.

>[!BEGINSHADEBOX]

*Prompts de exemplo:*

* &quot;Devo enviar este teste?&quot;
* &quot;Esta atividade está pronta para ser interrompida?&quot;
* &quot;A configuração da atividade atual tem algum problema?&quot;

>[!ENDSHADEBOX]

* **Design de Destino**

  Cria e configura atividades e ofertas, gera URLs de controle de qualidade e cria ou otimiza conteúdo de oferta.

>[!BEGINSHADEBOX]

*Prompts de exemplo:*

* &quot;Criar um teste A/B para a página inicial.&quot;
* &quot;Criar uma oferta para a experiência de visitante recorrente.&quot;
* &quot;Gerar um URL de controle de qualidade para esta atividade.&quot;

>[!ENDSHADEBOX]

* **VEC do Target**

  Cria e edita atividades do Visual Experience Composer e seus públicos-alvo de entrega de página.

>[!BEGINSHADEBOX]

*Prompts de exemplo:*

* &quot;Criar um teste A/B do VEC para a página inicial.&quot;
* &quot;Editar o título principal na minha atividade do VEC.&quot;
* &quot;Crie um público-alvo de entrega de página para esta atividade do VEC.&quot;

>[!ENDSHADEBOX]

* **Configuração do Target**

  Os guias concluem a criação de atividades do A/B, de Direcionamento de experiência ou do Visual Experience Composer, incluindo pré-requisitos, agendamento, controle de qualidade e ativação.

>[!BEGINSHADEBOX]

    *Prompts de exemplo:*
    
    * &quot;Ajude-me a criar meu primeiro teste.&quot;
    * &quot;Do que preciso antes de criar uma atividade de Direcionamento de Experiência?&quot;
    * &quot;Mostre-me o agendamento, o QA e a ativação desta atividade.&quot;

>[!ENDSHADEBOX]

* **Inteligência do Destino**

  Auditorias Programas do Target para riscos, colisões, erros de configuração, problemas de higiene e vitórias rápidas.

>[!BEGINSHADEBOX]

*Prompts de exemplo:*

* &quot;Auditoria de minhas atividades do Target.&quot;
* &quot;Encontre riscos de colisões ou configuração em minhas atividades.&quot;
* &quot;Quais ganhos rápidos podem melhorar a higiene do meu programa do Target?&quot;

>[!ENDSHADEBOX]

* **Estrategista de Destino**

  Analisa dados históricos do Target para obter padrões vencedores e recomenda testes futuros.

>[!BEGINSHADEBOX]

*Prompts de exemplo:*

* &quot;O que devo testar a seguir com base em resultados anteriores?&quot;
* &quot;Quais padrões aparecem em meus testes de mais alto desempenho?&quot;
* &quot;Recomende um teste de acompanhamento com base nos resultados desta atividade.&quot;

>[!ENDSHADEBOX]

* **Calculadora de Teste de Destino**

  Planeja o tamanho da amostra A/B/n, a duração e o aumento detectável para métricas de conversão e receita, com a correção de Bonferroni para várias comparações.

>[!BEGINSHADEBOX]

*Prompts de exemplo:*

* &quot;De que tamanho de amostra preciso?&quot;
* Por quanto tempo devo executar esse teste A/B para detectar um aumento de 5%?
* &quot;Que aumento detectável posso medir com esse tráfego?&quot;

>[!ENDSHADEBOX]

* **Relatório do Target Portfolio**

  Fornece rollups de desempenho somente leitura em todo o programa e análise de tendência e momento da atividade.

>[!BEGINSHADEBOX]

*Prompts de exemplo:*

* &quot;Quais são meus melhores e piores testes?&quot;
* &quot;Mostre-me as tendências de desempenho em minhas atividades.&quot;
* &quot;Quais atividades ganharam ou perderam ímpeto recentemente?&quot;

>[!ENDSHADEBOX]

* **Audience Composer do Target**

  Cria ou edita públicos-alvo nativos de descrições de linguagem natural ou regras explícitas.

>[!BEGINSHADEBOX]

*Prompts de exemplo:*

* &quot;Crie um público-alvo para os visitantes móveis recorrentes.&quot;
* &quot;Edite esse público-alvo para incluir visitantes de pesquisa orgânica.&quot;
* &quot;Crie um público-alvo do Target para os visitantes que visualizaram a página de preços.&quot;

>[!ENDSHADEBOX]

* **Recomendações do Target**

  Gerencia e trabalha com atividades e configurações do Target Recommendations.

>[!BEGINSHADEBOX]

*Prompts de exemplo:*

* &quot;Criar uma atividade do Recommendations.&quot;
* &quot;Mostre-me minhas atividades e configurações do Recommendations.&quot;
* &quot;Atualizar as configurações desta atividade do Recommendations.&quot;

>[!ENDSHADEBOX]

* **Diagnóstico das Recomendações do Target**

  Diagnostica problemas de entrega, configuração, catálogo e feed do Recommendations.

>[!BEGINSHADEBOX]

*Prompts de exemplo:*

* &quot;Por que minhas recomendações não estão aparecendo?&quot;
* &quot;Diagnosticar a configuração do feed e do catálogo para esta atividade do Recommendations.&quot;
* &quot;Problemas de entrega ou configuração afetam minhas recomendações?&quot;

>[!ENDSHADEBOX]
