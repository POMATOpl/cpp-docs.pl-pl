---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 2) C4396'
title: Ostrzeżenie kompilatora (poziom 2) C4396
ms.date: 11/04/2016
f1_keywords:
- C4396
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
ms.openlocfilehash: ab8743c748044456fa1826c805f8d652d76c403d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173522"
---
# <a name="compiler-warning-level-2-c4396"></a>Ostrzeżenie kompilatora (poziom 2) C4396

"name": wbudowany specyfikator nie może być używany, gdy zaprzyjaźniona deklaracja odnosi się do specjalizacji szablonu funkcji

Specjalizacja szablonu funkcji nie może określać żadnego ze specyfikatorów [wbudowanych](../../cpp/inline-functions-cpp.md) . Kompilator wystawia ostrzeżenia C4396 i ignoruje Specyfikator wbudowany.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Usuń **`inline`** specyfikator, **`__inline`** , lub **`__forceinline`** z deklaracji funkcji zaprzyjaźnionej.

## <a name="example"></a>Przykład

Poniższy przykład kodu pokazuje niepoprawną deklarację funkcji zaprzyjaźnionej ze **`inline`** specyfikatorem.

```cpp
// C4396.cpp
// compile with: /W2 /c

class X;
template<class T> void Func(T t, int i);

class X {
    friend inline void Func<char>(char t, int i);  //C4396
// try the following line instead
//    friend void Func<char>(char t, int i);
    int i;
};
```
