---
title: Ostrzeżenie kompilatora (poziom 4) C4389
description: Ostrzeżenie kompilatora Microsoft C/C++ C4389, jego przyczyny i rozwiązania.
ms.date: 10/16/2020
f1_keywords:
- c4389
helpviewer_keywords:
- C4389
ms.openlocfilehash: b06b013151ed12b4f66bb23a7e862992d05e6b30
ms.sourcegitcommit: f19f02f217b80804ab321d463c76ce6f681abcc6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2020
ms.locfileid: "92176267"
---
# <a name="compiler-warning-level-4-c4389"></a>Ostrzeżenie kompilatora (poziom 4) C4389

> "*równość-operator*": niezgodność ze znakiem/bez znaku

**`==`** **`!=`** Operacje **`signed`** i **`unsigned`** zmienne. Może to spowodować utratę danych.

## <a name="remarks"></a>Uwagi

Jednym ze sposobów na rozwiązanie tego ostrzeżenia jest rzutowanie jednego z dwóch typów podczas porównywania **`signed`** i **`unsigned`** typów.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4389:

```cpp
// C4389.cpp
// compile with: cl /EHsc /W4 C4389.cpp

int main()
{
   int a = 9;
   unsigned int b = 10;
   int result = 0;

   if (a == b)   // C4389
      result = 1;
   else
      result = 2;

   if (unsigned(a) == b) // OK
      result = 3;
   else
      result = 4;

   return result;
}
```

## <a name="see-also"></a>Zobacz też

[Ostrzeżenie kompilatora C4018](compiler-warning-level-3-c4018.md)\
[Ostrzeżenie kompilatora (poziom 4) C4388](c4388.md)
