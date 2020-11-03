---
title: Operatory przypisania w języku C
description: Standardowe operatory przypisania języka C, ich składnia i znaczenie.
ms.date: 10/30/2020
helpviewer_keywords:
- remainder assignment operator (%=)
- '&= operator'
- bitwise-AND assignment operator
- operators [C], assignment
- operators [C], shift
- ^= operator, assignment operators
- += operator
- '>>= operator'
- '|= operator'
- division assignment operator
- subtraction operator
- right shift operators
- subtraction operator, C assignment operators
- = operator, assignment operators
- '*= operator'
- '>> operator'
- '%= operator'
- assignment operators, C
- = operator
- assignment operators
- assignment conversions
- -= operator
- multiplication assignment operator (*=)
- shift operators, right
- /= operator
- operator >>=, C assignment operators
- <<= operator
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
ms.openlocfilehash: 460e18772689de0d28fcfda3295a49b2f8a3c0d7
ms.sourcegitcommit: 4abc6c4c9694f91685cfd77940987e29a51e3143
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "93238515"
---
# <a name="c-assignment-operators"></a>Operatory przypisania w języku C

Operacja przypisania przypisuje wartość operandu po prawej stronie do lokalizacji magazynu o nazwie przez operand z lewej strony. W związku z tym, operand z lewej strony operacji przypisania musi być modyfikowalną wartością l. Po przypisaniu wyrażenie przypisania ma wartość lewego operandu, ale nie jest l-wartością.

## <a name="syntax"></a>Składnia

*`assignment-expression`* :\
&emsp;*`conditional-expression`*\
&emsp;*`unary-expression`* *`assignment-operator`* *`assignment-expression`*

*`assignment-operator`* : jedno z<br/>
&emsp;**`=`** **`*=`** **`/=`** **`%=`** **`+=`** **`-=`** **`<<=`** **`>>=`** **`&=`** **`^=`** **`|=`**

Operatory przypisania w języku C mogą przetwarzać i przypisywać wartości w jednej operacji. C udostępnia następujące operatory przypisania:

|Operator|Wykonano operację|
|--------------|-------------------------|
|**`=`**|Przypisanie proste|
|**`*=`**|Mnożenie i przypisanie|
|**`/=`**|Dzielenie i przypisanie|
|**`%=`**|Przypisanie reszty|
|**`+=`**|Dodawanie i przypisanie|
|**`-=`**|Odejmowanie i przypisanie|
|**`<<=`**|Przesunięcie bitowe w lewo i przypisanie|
|**`>>=`**|Przesunięcie bitowe w prawo i przypisanie|
|**`&=`**|Przypisanie bitowe i|
|**`^=`**|Przypisanie bitowe i wyłączne|
|**`|=`**|Bitowe lub przydzielenie|

W obszarze przypisanie typ wartości po prawej stronie jest konwertowany na typ wartości po lewej stronie, a wartość jest przechowywana w lewym operandzie po przypisaniu. Lewy argument operacji nie może być tablicą, funkcją ani stałą. Określona ścieżka konwersji, która zależy od dwóch typów, została szczegółowo zakreślona w [konwersji typów](../c-language/type-conversions-c.md).

## <a name="see-also"></a>Zobacz też

- [Operatory przypisania](../cpp/assignment-operators.md)
