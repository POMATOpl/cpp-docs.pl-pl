---
title: Błąd kompilatora C3531
ms.date: 11/04/2016
f1_keywords:
- C3531
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
ms.openlocfilehash: 6961d99d1a0d7d0ea063aee5544a1009af2547c7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031264"
---
# <a name="compiler-error-c3531"></a>Błąd kompilatora C3531

'symbol': symbol, którego typ zawiera "auto" musi mieć inicjator

Określona zmienna nie ma wyrażenia inicjatora.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Określ wyrażenie inicjatora, takich jak przypisanie proste, w której używana jest składnia znaku równości, kiedy Deklarujesz zmienną.

## <a name="example"></a>Przykład

Poniższy przykład daje C3531, ponieważ zmienne `x1`, `y1, y2, y3`, i `z2` nie jest zainicjowany.

```
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

## <a name="see-also"></a>Zobacz także

[Auto, słowo kluczowe](../../cpp/auto-keyword.md)