---
description: 'Dowiedz się więcej o: błąd kompilatora C2146'
title: Błąd kompilatora C2146
ms.date: 11/04/2016
f1_keywords:
- C2146
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
ms.openlocfilehash: ccca0099401838a918ad5443ce8194df853184bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223506"
---
# <a name="compiler-error-c2146"></a>Błąd kompilatora C2146

Błąd składniowy: Brak tokenu "token" przed identyfikatorem "identifier"

Oczekiwano kompilatora `token` i znaleziono go `identifier` .  Możliwe przyczyny:

1. Błąd pisowni lub wielkości liter.

1. Brak specyfikatora typu w deklaracji identyfikatora.

Ten błąd może być spowodowany przez błąd typograficzne. Błąd [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) zazwyczaj poprzedza ten błąd.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2146.

```cpp
// C2146.cpp
class CDeclaredClass {};

class CMyClass {
   CUndeclared m_myClass;   // C2146
   CDeclaredClass m_myClass2;   // OK
};

int main() {
   int x;
   int t x;   // C2146 : missing semicolon before 'x'
}
```

Ten błąd może być również wygenerowany jako wynik zgodności kompilatora, który został wykonany dla programu Visual Studio .NET 2003: brak **`typename`** słowa kluczowego.

Poniższy przykład kompiluje w programie Visual Studio .NET 2002, ale zakończy się niepowodzeniem w programie Visual Studio .NET 2003:

```cpp
// C2146b.cpp
// compile with: /c
template <typename T>
struct X {
   struct Y {
      int i;
   };
   Y memFunc();
};

template <typename T>
X<T>::Y func() { }   // C2146

// OK
template <typename T>
typename X<T>::Y func() { }
```

Ten błąd zostanie również wyświetlony w wyniku działania kompilatora, który został wykonany dla programu Visual Studio .NET 2003: jawne specjalizacje nie szukają już parametrów szablonu z szablonu podstawowego.

Użycie `T` z szablonu podstawowego nie jest dozwolone w jawnej specjalizacji. Aby kod był prawidłowy w Visual Studio .NET 2003 i Visual Studio .NET, Zamień wszystkie wystąpienia parametru szablonu w specjalizacji z jawnie wyspecjalizowanym typem.

Poniższy przykład kompiluje w programie Visual Studio .NET, ale zakończy się niepowodzeniem w programie Visual Studio .NET 2003:

```cpp
// C2146_c.cpp
// compile with: /c
template <class T>
struct S;

template <>
struct S<int> {
   T m_t;   // C2146
   int m_t2;   // OK
};
```
