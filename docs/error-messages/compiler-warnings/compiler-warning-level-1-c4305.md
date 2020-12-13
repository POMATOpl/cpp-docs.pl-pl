---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4305'
title: Ostrzeżenie kompilatora (poziom 1) C4305
ms.date: 01/17/2018
f1_keywords:
- C4305
helpviewer_keywords:
- C4305
ms.openlocfilehash: a6cee5be3b5929c0fbf487a8c40d37e269e6a994
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340089"
---
# <a name="compiler-warning-level-1-c4305"></a>Ostrzeżenie kompilatora (poziom 1) C4305

> "*Context*": obcinanie z "*Type1*" do "*Type2*"

## <a name="remarks"></a>Uwagi

To ostrzeżenie jest generowane, gdy wartość zostanie przekonwertowana na mniejszy typ w inicjacji lub jako argument konstruktora, co spowodowało utratę informacji.

## <a name="example"></a>Przykład

Ten przykład pokazuje dwa sposoby wyświetlania tego ostrzeżenia:

```cpp
// C4305.cpp
// Compile by using: cl /EHsc /W4 C4305.cpp

struct item
{
    item(float) {}
};

int main()
{
    float f = 2.71828;          // C4305 'initializing'
    item i(3.14159);            // C4305 'argument'
    return static_cast<int>(f);
}
```

Aby rozwiązać ten problem, należy zainicjować przy użyciu wartości poprawnego typu lub użyć jawnego rzutowania do poprawnego typu. Na przykład użyj **`float`** literału, takiego jak 2.71828 f zamiast **`double`** (domyślny typ dla literałów zmiennoprzecinkowych), aby zainicjować **`float`** zmienną lub przekazać do konstruktora, który przyjmuje **`float`** argument.
