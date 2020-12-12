---
description: 'Dowiedz się więcej o: błąd kompilatora C2975'
title: Błąd kompilatora C2975
ms.date: 11/04/2016
f1_keywords:
- C2975
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
ms.openlocfilehash: 9f9108d1dc4e0fe61b6dd2135fb69bbaedfaedf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210351"
---
# <a name="compiler-error-c2975"></a>Błąd kompilatora C2975

> "*argument*": nieprawidłowy argument szablonu dla elementu "*Type*", oczekiwano wyrażenia stałej czasu kompilacji

Argument szablonu nie jest zgodny z deklaracją szablonu; wyrażenie stałe powinno pojawić się w nawiasach kątowych. Zmienne nie są dozwolone jako argumenty rzeczywiste szablonu. Sprawdź definicję szablonu, aby znaleźć prawidłowe typy.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2975, a także wyświetla poprawne użycie:

```cpp
// C2975.cpp
template<int I>
class X {};

int main() {
   int i = 4, j = 2;
   X<i + j> x1;   // C2975
   X<6> x2;   // OK
}
```

C2975 występuje również w przypadku używania&#95;&#95; wiersza &#95;&#95;jako stałej czasu kompilacji z [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md). Jednym z rozwiązań będzie Kompilowanie za pomocą [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) zamiast **/Zi**.

```cpp
// C2975b.cpp
// compile with: /ZI
// processor: x86
template<long line>
void test(void) {}

int main() {
   test<__LINE__>();   // C2975
}
```
