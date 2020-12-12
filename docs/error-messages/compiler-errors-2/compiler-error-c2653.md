---
description: 'Dowiedz się więcej o: błąd kompilatora C2653'
title: Błąd kompilatora C2653
ms.date: 11/30/2017
f1_keywords:
- C2653
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
ms.openlocfilehash: f3be7ade8a6dcfc6aa8c5a83cc8a055fc230789d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286153"
---
# <a name="compiler-error-c2653"></a>Błąd kompilatora C2653

> "*Identyfikator*": nie jest nazwą klasy lub przestrzeni nazw

Składnia języka wymaga tutaj nazwy klasy, struktury, Unii lub przestrzeni nazw.

Ten błąd może wystąpić, gdy używasz nazwy, która nie została zadeklarowana jako Klasa, struktura, Unia lub przestrzeń nazw przed operatorem zakresu. Aby rozwiązać ten problem, zadeklaruj nazwę lub Dołącz nagłówek, który deklaruje nazwę przed użyciem.

C2653 jest również możliwe w przypadku próby zdefiniowania *złożonej przestrzeni nazw*, przestrzeni nazw zawierającej co najmniej jedną zagnieżdżoną nazwę zakresu nazw. Definicje złożonych przestrzeni nazw są niedozwolone w języku C++ przed C++ 17. Złożone przestrzenie nazw są obsługiwane począwszy od programu Visual Studio 2015 Update 3 w przypadku określenia opcji kompilatora [/std: c + +](../../build/reference/std-specify-language-standard-version.md) . Począwszy od programu Visual Studio 2017 w wersji 15,5, kompilator obsługuje definicje przestrzeni nazw złożonych, gdy jest określona opcja [/std: c++ 17](../../build/reference/std-specify-language-standard-version.md) .

## <a name="examples"></a>Przykłady

Ten przykład generuje C2653, ponieważ nazwa zakresu jest używana, ale nie została zadeklarowana. Kompilator oczekuje nazwy klasy, struktury, Unii lub przestrzeni nazw przed operatorem zakresu (::).

```cpp
// C2653.cpp
// compile with: /c
class yy {
   void func1(int i);
};

void xx::func1(int m) {}   // C2653, xx is not declared
void yy::func1(int m) {}   // OK
```

W kodzie, który nie jest kompilowany dla standardów C++ 17 lub nowszych, zagnieżdżone przestrzenie nazw muszą używać jawnej deklaracji przestrzeni nazw na każdym poziomie zagnieżdżania:

```cpp
// C2653b.cpp
namespace a::b {int i;}   // C2653 prior to Visual Studio 2015 Update 3,
                          // C2429 thereafter. Use /std:c++17 or /std:c++latest to fix.

namespace a {             // Use this form for compliant code under /std:c++14 (the default)
   namespace b {          // or when using compilers before Visual Studio 2015 update 3.
      int i;
   }
}

int main() {
   a::b::i = 2;
}
```
