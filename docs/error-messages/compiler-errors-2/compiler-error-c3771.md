---
description: 'Dowiedz się więcej o: błąd kompilatora C3771'
title: Błąd kompilatora C3771
ms.date: 11/04/2016
f1_keywords:
- C3771
helpviewer_keywords:
- C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
ms.openlocfilehash: f7d71952411632ded02bc5121c6f6668eddeabc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291665"
---
# <a name="compiler-error-c3771"></a>Błąd kompilatora C3771

"Identyfikator": Deklaracja zaprzyjaźniona nie może zostać znaleziona w najbliższym zakresie przestrzeni nazw

W bieżącej przestrzeni nazw nie można znaleźć deklaracji szablonu klasy dla określonego *identyfikatora* szablonu.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Upewnij się, że deklaracja szablonu klasy dla identyfikatora szablonu jest zdefiniowana w bieżącej przestrzeni nazw lub że identyfikator szablonu jest w pełni kwalifikowaną nazwą.

## <a name="example"></a>Przykład

Poniższy przykład kodu deklaruje szablon klasy i funkcję w przestrzeni nazw `NA` , ale próbuje zadeklarować szablon funkcji zaprzyjaźnionej w przestrzeni nazw `NB` .

```cpp
// C3771.cpp
// compile with: /c

namespace NA {
template<class T> class A {
    void aFunction(T t) {};
    };
}
// using namespace NA;
namespace NB {
    class X {
        template<class T> friend void A<T>::aFunction(T); // C3771
// try the following line instead
//      template<class T> friend void NA::A<T>::aFunction(T);
// or try "using namespace NA;" instead.
    };
}
```

## <a name="see-also"></a>Zobacz też

[Szablony](../../cpp/templates-cpp.md)
