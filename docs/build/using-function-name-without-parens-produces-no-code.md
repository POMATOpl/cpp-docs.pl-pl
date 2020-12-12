---
description: 'Dowiedz się więcej o: Używanie funkcji Name bez () nie tworzy kodu'
title: Korzystanie z nazwy funkcji bez () nie tworzy kodu
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
ms.openlocfilehash: 1fedc296422a759878c26469ccc20955043b3913
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277261"
---
# <a name="using-function-name-without--produces-no-code"></a>Korzystanie z nazwy funkcji bez () nie tworzy kodu

Gdy nazwa funkcji zadeklarowana w programie jest używana bez nawiasów, kompilator nie tworzy kodu. Dzieje się tak niezależnie od tego, czy funkcja przyjmuje parametry, ponieważ kompilator oblicza adres funkcji; Jednak ze względu na to, że operator wywołania funkcji "()" nie istnieje, wywołanie nie zostało wykonane. Ten wynik jest podobny do następującego:

```
// compile with /Wall to generate a warning
int a;
a;      // no code generated here either
```

W Visual C++, nawet przy użyciu poziomu ostrzeżeń 4 nie generuje danych wyjściowych. Nie wydano ostrzeżenia; nie jest tworzony żaden kod.

Przykładowy kod poniżej kompiluje (z ostrzeżeniem) i łączy się prawidłowo bez błędów, ale nie tworzy kodu w odwołaniu do `funcn( )` . Aby to działanie działało prawidłowo, Dodaj operator wywołania funkcji "()".

```
#include <stdio.h>
void funcn();

int main() {
   funcn;      /* missing function call operator;
                  call will fail.  Use funcn() */
   }

void funcn() {
   printf("\nHello World\n");
}
```

## <a name="see-also"></a>Zobacz też

[Optymalizowanie kodu](optimizing-your-code.md)
