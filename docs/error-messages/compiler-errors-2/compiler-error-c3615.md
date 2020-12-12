---
description: 'Dowiedz się więcej o: błąd kompilatora C3615'
title: Błąd kompilatora C3615
ms.date: 10/24/2017
f1_keywords:
- C3615
helpviewer_keywords:
- C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
ms.openlocfilehash: 9f3b95b96ff10a99f3ebeac1bc3b19f759dd0ab7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262285"
---
# <a name="compiler-error-c3615"></a>Błąd kompilatora C3615

> Funkcja constexpr "*Function*" nie może skutkować wyrażeniem stałym

Nie można ocenić *funkcji* funkcji w **`constexpr`** czasie kompilacji. Aby było możliwe **`constexpr`** , funkcja może wywołać tylko inne **`constexpr`** funkcje.

## <a name="example"></a>Przykład

Program Visual Studio 2017 poprawnie zgłasza błąd, gdy operand po lewej stronie operacji oceniania warunkowego jest nieprawidłowy w **`constexpr`** kontekście. Poniższy kod kompiluje się w programie Visual Studio 2015, ale nie w programie Visual Studio 2017.

```cpp
// C3615.cpp
// Compile with: /c

template<int N>
struct myarray
{
    int size() const { return N; }
};

constexpr bool f(const myarray<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615 starting in Visual Studio 2017
}
```

Aby rozwiązać ten problem, należy zadeklarować `array::size()` funkcję jako **`constexpr`** lub usunąć **`constexpr`** kwalifikator z elementu `f` .
