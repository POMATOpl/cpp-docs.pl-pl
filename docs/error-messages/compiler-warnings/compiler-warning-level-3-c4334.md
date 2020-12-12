---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4334'
title: Ostrzeżenie kompilatora (poziom 3) C4334
ms.date: 11/04/2016
f1_keywords:
- C4334
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
ms.openlocfilehash: 3c7a84efc3c98779c5b50dc1b3fb28e687f856eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344032"
---
# <a name="compiler-warning-level-3-c4334"></a>Ostrzeżenie kompilatora (poziom 3) C4334

"operator": wynik 32-bit Shift niejawnie przekonwertowany na 64 bitów (czy został on 64-bitowe przesunięcia?)

Wynik 32-bitowego przesunięcia został niejawnie przekonwertowany na 64-bitowy, a kompilator podejrzewa, że przeznaczenie 64-bit zostało zamierzone.  Aby rozwiązać ten problem, należy użyć 64-bitowego przesunięcia lub jawnie rzutować wynik przesunięcia do 64-bitowego.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4334.

```cpp
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```
