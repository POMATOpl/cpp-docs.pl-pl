---
description: 'Dowiedz się więcej o: błąd kompilatora C2040'
title: Błąd kompilatora C2040
ms.date: 11/04/2016
f1_keywords:
- C2040
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
ms.openlocfilehash: 39e5152e012d793bcc174f5abe451e23f03b60d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175368"
---
# <a name="compiler-error-c2040"></a>Błąd kompilatora C2040

"operator": "Identifier1" różni się w poziomach pośrednich od "identifier2"

Wyrażenie obejmujące określone operandy ma niezgodne typy operandów lub niejawnie przekonwertowane Typy operandów. Jeśli oba operandy są arytmetyczne lub obie są niearytmetyczne (takie jak tablica lub wskaźnik), są używane bez zmian. Jeśli jeden operand jest arytmetyczny, a drugi nie, operand arytmetyczny jest konwertowany na typ operandu niearytmetycznego.

Ten przykład generuje C2040 i pokazuje, jak rozwiązać ten problem.

```cpp
// C2040.cpp
// Compile by using: cl /c /W3 C2040.cpp
bool test() {
   char c = '3';
   return c == "3"; // C2446, C2040
   // return c == '3'; // OK
}
```
