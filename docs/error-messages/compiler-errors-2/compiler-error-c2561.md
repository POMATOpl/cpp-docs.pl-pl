---
description: 'Dowiedz się więcej o: błąd kompilatora C2561'
title: Błąd kompilatora C2561
ms.date: 11/04/2016
f1_keywords:
- C2561
helpviewer_keywords:
- C2561
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
ms.openlocfilehash: 11ec708d25af9fc9603977c33741a1f74a406e92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144875"
---
# <a name="compiler-error-c2561"></a>Błąd kompilatora C2561

"Identyfikator": funkcja musi zwracać wartość

Funkcja została zadeklarowana jako zwracająca wartość, ale definicja funkcji nie zawiera **`return`** instrukcji.

Ten błąd może być spowodowany przez nieprawidłowy prototyp funkcji:

1. Jeśli funkcja nie zwraca wartości, zadeklaruj funkcję z typem zwracanym [void](../../cpp/void-cpp.md).

1. Sprawdź, czy wszystkie możliwe gałęzie funkcji zwracają wartość typu zadeklarowanego w prototypie.

1. Funkcje języka C++ zawierające wbudowane procedury asemblera, które przechowują wartość zwracaną w `AX` rejestrze, mogą potrzebować instrukcji return. Skopiuj wartość `AX` do zmiennej tymczasowej i zwróć tę zmienną z funkcji.

Poniższy przykład generuje C2561:

```cpp
// C2561.cpp
int Test(int x) {
   if (x) {
      return;   // C2561
      // try the following line instead
      // return 1;
   }
   return 0;
}

int main() {
   Test(1);
}
```
