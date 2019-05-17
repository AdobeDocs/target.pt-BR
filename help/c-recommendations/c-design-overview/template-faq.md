---
description: Lista de perguntas frequentes sobre os designs de recomendações.
keywords: recomendações, perguntas frequentes, faq
seo-description: Lista de perguntas frequentes sobre os designs de recomendações.
seo-title: Perguntas e respostas sobre design
solution: Target
title: Perguntas e respostas sobre design
title-outputclass: premium
topic: Premium
uuid: ac222ade-ddd9-4b32-a16f-4d83b8766384
badge: premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) Perguntas frequentes sobre o design {#design-faq}

Lista de perguntas frequentes sobre os designs de recomendações.

## Por que a categoria não está sendo exibida no design? Eu estou usando $entity1.categoryId. {#section_073309B8051049C7953D396A93EA0713}

A ID da categoria não pode ser exibida no design. Como várias categorias podem ser armazenadas, o sistema não saberia qual categoria exibir.

## Como devo mudar um design para obter uma atualização instantânea? {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

A alteração do design que está atualmente em uso leva um tempo para atualizar. Para alterar o design imediatamente, crie um novo design, selecione-o na campanha e salve a recomendação.

## Como posso capturar as principais informações para exibir no design? Exemplo: se desejarmos exibir a principal categoria do produto, como codificamos esse valor no design da velocidade? {#section_F08043B14BA24BC8815FEF25F4F84C39}

O parâmetro `$key. *`value`*` captura a maioria das informações do produto para exibir dentro do design. Por exemplo: se você deseja exibir a miniatura dos principais produtos, use `$key.thumbnailURL`.

## Qual versão do Velocity é utilizada? {#section_28F00E15A4A54A768782A3F5BB0CDB21}

A versão 1.7 sem ferramentas adicionais ou bibliotecas incorporadas. O recurso Basic Velocity está disponível.

## O que devo fazer para deixar um valor de entidade existente em branco? Por exemplo: a entity.message de um item precisa ser limpa quando uma promoção termina. {#section_B88F2C2925DC4508974B2F8B13F961CB}

Enviar um espaço sem quebra do JavaScript parece ser suficiente. Peça que os desenvolvedores enviem `\u00A0` como o valor. Exemplo: `entity.message=\u00A0`. Você pode considerar esse como sendo o valor padrão, ao invés de um valor nulo, quando nenhum valor estiver presente.

## Posso usar um script de perfil em um design de recomendações? {#section_6BD55203984A4D80A0C6F241AD7806DF}

Sim. No entanto, você deve adicionar uma barra invertida (\) antes do $ no nome do script de perfil.
