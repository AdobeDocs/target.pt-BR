---
title: Usar contexto nas regras de público
description: Saiba como usar atributos de contexto em regras de público-alvo para sinalizadores de recursos e grupos de recursos em Sinalizadores.
badge: label="Beta" type="Informative"
hide: true
exl-id: 0367f475-9209-4d53-86b4-a739a73a23a7
source-git-commit: 8fffd619232b2cae2f5dd0aa1e0a55183c4be698
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 1%

---

# Usar contexto nas regras de público {#context-in-audience-rules}

Os atributos de contexto são valores fornecidos pelo aplicativo cliente no tempo de execução. Eles permitem definir usuários como alvo com base em informações dinâmicas no nível da sessão, como idioma ativo do usuário, tipo de dispositivo ou estado do aplicativo.

Os atributos de contexto são relevantes para clientes da Web e móveis.

## Como os atributos de contexto funcionam {#how-context-attributes-work}

Seu aplicativo passa atributos de contexto a Sinalizadores ao avaliar um sinalizador de recurso. Você define regras no console que verificam esses valores, e a plataforma os usa no momento da avaliação para determinar se o usuário se qualifica.

## Adição de um atributo de contexto {#adding-context-attribute}

Para adicionar um atributo de contexto a uma regra de público:

1. Abra o sinalizador de recurso ou o grupo de recursos no console.
2. Vá para a guia **Público-alvo**.
3. Em **Context**, adicione uma nova condição.
4. Selecione o atributo de contexto, operador e valor.

Se o atributo de contexto necessário não aparecer na lista, você poderá criar um novo — consulte [Criação dos atributos de contexto](creating-your-context-attributes.md).

## Consulte também {#see-also}

* [Público-alvo em sinalizadores e grupos de recursos](audience-in-feature-flags-and-feature-groups.md)

<!-- -->
