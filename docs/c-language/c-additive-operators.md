---
description: Dowiedz się więcej na temat operatorów dodatków C
title: Operatory dodawania języka C
ms.date: 10/18/2018
helpviewer_keywords:
- usual arithmetic conversions
- operators [C], addition
- + operator, additive operators
- additive operators
- arithmetic operators [C++], additive operators
ms.assetid: bb8ac205-b061-41fc-8dd4-dab87c8b900c
ms.openlocfilehash: b77c3e9716cba716f625fa142129f5c1ce095907
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211599"
---
# <a name="c-additive-operators"></a>Operatory dodawania języka C

Operatory addytywne wykonują dodawanie ( **+** ) i odejmowanie ( **-** ).

## <a name="syntax"></a>Składnia

*wyrażenie addytywne*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*mnożenia — wyrażenie*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie addytywne* **+** *mnożenia — wyrażenie*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*wyrażenie addytywne* **-** *mnożenia — wyrażenie*

> [!NOTE]
> Mimo że składnia *wyrażenia addytywne* zawiera *mnożenia-Expression*, nie oznacza to, że wyrażenia używające mnożenia są wymagane. Zobacz składnię w artykule [składnia składni języka C](../c-language/c-language-syntax-summary.md), dla *mnożenia-Expression*, *Cast-* Expression i *wyrażenie jednoargumentowe*.

Operandy mogą być wartości całkowitych lub zmiennoprzecinkowych. Niektóre operacje addytywne można także wykonać na wartościach wskaźnika, jak opisano w omówieniu każdego operatora.

Operatory addytywne wykonują zwykle konwersje arytmetyczne na całkowitych i zmiennoprzecinkowych operandach. Typ wyniku jest typem operandów po konwersji. Ponieważ konwersje wykonywane przez Operatory addytywne nie zapewniają dla warunków przepełnienia lub niedomiaru, informacje mogą zostać utracone, jeśli wynik operacji addytywnej nie może być reprezentowany w typie operandów po konwersji.

## <a name="see-also"></a>Zobacz też

[Operatory addytywne: + i-](../cpp/additive-operators-plus-and.md)
