---
description: 'Dowiedz się więcej o: ALIAS'
title: ALIAS (MASM)
ms.date: 12/17/2019
f1_keywords:
- Alias
helpviewer_keywords:
- ALIAS directive
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
ms.openlocfilehash: 7d5072cec8ef56f3dd2202617b3274c958a25d66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121761"
---
# <a name="alias"></a>ALIAS

Dyrektywa **aliasu** tworzy alternatywną nazwę dla funkcji.  Dzięki temu można utworzyć wiele nazw dla funkcji lub utworzyć biblioteki, które umożliwiają konsolidatorowi (LINK.exe) mapowanie starej funkcji do nowej funkcji.

## <a name="syntax"></a>Składnia

> **Użyj \<**_alias_**> = \<**_actual-name_**>**

#### <a name="parameters"></a>Parametry

*Rzeczywista nazwa*\
Rzeczywista nazwa funkcji lub procedury.  Nawiasy kątowe są wymagane.

*Użyj*\
Nazwa alternatywna lub aliasu.  Nawiasy kątowe są wymagane.

## <a name="see-also"></a>Zobacz też

[Dokumentacja dyrektyw](directives-reference.md)\
[MASM BNF, gramatyka](masm-bnf-grammar.md)
