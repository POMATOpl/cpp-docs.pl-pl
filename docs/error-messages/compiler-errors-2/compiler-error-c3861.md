---
description: 'Dowiedz się więcej o: błąd kompilatora C3861'
title: Błąd kompilatora C3861
ms.date: 03/23/2018
f1_keywords:
- C3861
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
ms.openlocfilehash: bba259496de09e86b59f9cad1ac1bf89a697a1da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222908"
---
# <a name="compiler-error-c3861"></a>Błąd kompilatora C3861

> "*Identyfikator*": nie znaleziono identyfikatora

Kompilator nie mógł rozpoznać odwołania do identyfikatora, nawet przy użyciu wyszukiwania zależnego od argumentu.

## <a name="remarks"></a>Uwagi

Aby naprawić ten błąd, należy porównać użycie *identyfikatora* do deklaracji identyfikatora dla wielkości liter i pisowni. Upewnij się, że [Operatory rozpoznawania zakresów](../../cpp/scope-resolution-operator.md) i przestrzeń nazw [używające dyrektyw](../../cpp/namespaces-cpp.md#using_directives) są poprawnie używane. Jeśli identyfikator jest zadeklarowany w pliku nagłówkowym, sprawdź, czy nagłówek jest uwzględniony przed odwołaniem do identyfikatora. Jeśli identyfikator ma być widoczny na zewnątrz, upewnij się, że jest zadeklarowany w pliku źródłowym, który go używa. Sprawdź również, czy deklaracja identyfikatora lub definicja nie jest wykluczona przez [dyrektywy kompilacji warunkowej](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).

Zmiany w celu usunięcia przestarzałych funkcji z biblioteki środowiska uruchomieniowego języka C w programie Visual Studio 2015 mogą spowodować C3861. Aby rozwiązać ten problem, Usuń odwołania do tych funkcji lub zastąp je bezpiecznymi alternatywami (jeśli istnieją). Aby uzyskać więcej informacji, zobacz [funkcje przestarzałe](../../c-runtime-library/obsolete-functions.md).

Jeśli błąd C3861 pojawia się po migracji projektu ze starszych wersji kompilatora, mogą występować problemy związane z obsługiwanymi wersjami systemu Windows. Visual C++ nie obsługuje już elementów docelowych Windows 95, Windows 98, Windows ME, Windows NT lub Windows 2000. Jeśli makra **winver** lub **_WIN32_WINNT** są przypisane do jednej z tych wersji systemu Windows, należy zmodyfikować makra. Aby uzyskać więcej informacji, zobacz [modyfikowanie programu winver i _WIN32_WINNT](../../porting/modifying-winver-and-win32-winnt.md).

## <a name="examples"></a>Przykłady

### <a name="undefined-identifier"></a>Niezdefiniowany identyfikator

Poniższy przykład generuje C3861, ponieważ nie zdefiniowano identyfikatora.

```cpp
// C3861.cpp
void f2(){}
int main() {
   f();    // C3861
   f2();   // OK
}
```

### <a name="identifier-not-in-scope"></a>Identyfikator nie należy do zakresu

Poniższy przykład generuje C3861, ponieważ identyfikator jest widoczny tylko w zakresie pliku jego definicji, chyba że jest zadeklarowany w innych plikach źródłowych, które go używają.

```cpp
// C3861_a1.cpp
// Compile with: cl /EHsc /W4 C3861_a1.cpp C3861_a2.cpp
#include <iostream>
// Uncomment the following line to fix:
// int f();  // declaration makes external function visible
int main() {
   std::cout << f() << std::endl;    // C3861
}
```

```cpp
// C3861_a2.cpp
int f() {  // declared and defined here
   return 42;
}
```

### <a name="namespace-qualification-required"></a>Wymagana kwalifikacja przestrzeni nazw

Klasy wyjątków w standardowej bibliotece języka C++ wymagają `std` przestrzeni nazw.

```cpp
// C3861_b.cpp
// compile with: /EHsc
#include <iostream>
int main() {
   try {
      throw exception("Exception");   // C3861
      // try the following line instead
      // throw std::exception("Exception");
   }
   catch (...) {
      std::cout << "caught an exception" << std::endl;
   }
}
```

### <a name="obsolete-function-called"></a>Wywołano przestarzałą funkcję

Przestarzałe funkcje zostały usunięte z biblioteki CRT.

```cpp
// C3861_c.cpp
#include <stdio.h>
int main() {
   char line[21]; // room for 20 chars + '\0'
   gets( line );  // C3861
   // Use gets_s instead.
   printf( "The line entered was: %s\n", line );
}
```

### <a name="adl-and-friend-functions"></a>Funkcje ADL i zaprzyjaźnione

Poniższy przykład generuje C3767, ponieważ kompilator nie może użyć wyszukiwania zależnego od argumentu dla `FriendFunc` :

```cpp
namespace N {
   class C {
      friend void FriendFunc() {}
      friend void AnotherFriendFunc(C* c) {}
   };
}

int main() {
   using namespace N;
   FriendFunc();   // C3861 error
   C* pC = new C();
   AnotherFriendFunc(pC);   // found via argument-dependent lookup
}
```

Aby naprawić ten błąd, zadeklaruj przyjaciela w zakresie klasy i zdefiniuj go w zakresie przestrzeni nazw:

```cpp
class MyClass {
   int m_private;
   friend void func();
};

void func() {
   MyClass s;
   s.m_private = 0;
}

int main() {
   func();
}
```
