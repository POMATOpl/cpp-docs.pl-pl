---
description: 'Dowiedz się więcej o: błąd kompilatora C3531'
title: Błąd kompilatora C3531
ms.date: 11/04/2016
f1_keywords:
- C3531
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
ms.openlocfilehash: 996a9cbda0bf1719c5fd14a1b36632d1710f8beb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113184"
---
# <a name="compiler-error-c3531"></a>Błąd kompilatora C3531

"symbol": symbol, którego typ zawiera "Auto", musi mieć inicjator

Określona zmienna nie ma wyrażenia inicjatora.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Określ wyrażenie inicjatora, takie jak proste przypisanie, które używa składni znaku równości, podczas deklarowania zmiennej.

## <a name="example"></a>Przykład

Poniższy przykład daje C3531 ze względu na to, że zmienne `x1` , `y1, y2, y3` i `z2` nie zostały zainicjowane.

```cpp
// C3531.cpp
// Compile with /Zc:auto
int main()
{
   auto x1;                  // C3531
   auto y1, y2, y3;          // C3531
   auto z1 = 1, z2, z3 = -1; // C3531
   return 0;
}
```

## <a name="see-also"></a>Zobacz też

[Słowo kluczowe "Autouzupełnianie"](../../cpp/auto-cpp.md)
