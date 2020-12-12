---
description: 'Dowiedz się więcej o: wywołaniu funkcji (C)'
title: Wywołanie funkcji (C)
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
ms.openlocfilehash: 7ebe8ded3e64f7b636aaf438ee2bff8e4f221610
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195973"
---
# <a name="function-call-c"></a>Wywołanie funkcji (C)

*Wywołanie funkcji* jest wyrażeniem, które zawiera nazwę wywoływanej funkcji lub wartość wskaźnika funkcji oraz, opcjonalnie, argumenty, które są przekazane do funkcji.

## <a name="syntax"></a>Składnia

*wyrażenie przyrostkowe*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*przyrostkowe wyrażenie***(***opt-expression-list*<sub></sub> **)**    

*argument-lista wyrażeń*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*przypisanie — wyrażenie*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*argumenty argumentu-list* **,** *przypisanie-wyrażenie*

*Wyrażenie przyrostkowe* musi być szacowane do adresu funkcji (na przykład identyfikatora funkcji lub wartości wskaźnika funkcji), a *Lista argumentów wyrażenia* jest listą wyrażeń (rozdzielonych przecinkami), których wartości ("argumenty") są przekazane do funkcji. Argument *-Expression-List* może być pusty.

Wyrażenie wywołania funkcji ma wartość i typ wartości zwracanej funkcji. Funkcja nie może zwracać obiektu typu Array. Jeśli typem zwracanym funkcji jest **`void`** (to oznacza, że funkcja została zadeklarowana nigdy do zwrócenia wartości), wyrażenie wywołania funkcji również ma **`void`** Typ. (Zobacz [wywołania funkcji](../c-language/function-calls.md) , aby uzyskać więcej informacji).

## <a name="see-also"></a>Zobacz też

[Operator wywołania funkcji: ()](../cpp/function-call-operator-parens.md)
