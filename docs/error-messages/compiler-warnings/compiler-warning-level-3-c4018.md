---
title: Ostrzeżenie kompilatora (poziom 3) C4018
description: Ostrzeżenie kompilatora Microsoft C/C++ C4018, jego przyczyny i rozwiązania.
ms.date: 10/16/2020
f1_keywords:
- C4018
helpviewer_keywords:
- C4018
ms.openlocfilehash: b9d01f6b733c2ca18880aa6f4b6fca9771f8123f
ms.sourcegitcommit: f19f02f217b80804ab321d463c76ce6f681abcc6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2020
ms.locfileid: "92176171"
---
# <a name="compiler-warning-level-3-c4018"></a>Ostrzeżenie kompilatora (poziom 3) C4018

> "*token*": niezgodność ze znakiem/bez znaku

Użycie operatora *tokenów* do porównywania **`signed`** i **`unsigned`** liczb wymaganych przez kompilator do konwersji **`signed`** wartości na **`unsigned`** .

## <a name="remarks"></a>Uwagi

Jednym ze sposobów na rozwiązanie tego ostrzeżenia jest rzutowanie jednego z dwóch typów podczas porównywania **`signed`** i **`unsigned`** typów.

## <a name="example"></a>Przykład

Ten przykład generuje C4018 i pokazuje, jak go naprawić:

```cpp
// C4018.cpp
// compile with: cl /EHsc /W4 C4018.cpp
int main() {
    unsigned int uc = 0;
    int c = 0;
    unsigned int c2 = c; // implicit conversion

    if (uc < c)           // C4018
        uc = 0;

    if (uc < unsigned(c)) // OK
        uc = 0;

    if (uc < c2)          // Also OK
       uc = 0;
}
```

## <a name="see-also"></a>Zobacz też

[Ostrzeżenie kompilatora (poziom 4) C4388](c4388.md)\
[Ostrzeżenie kompilatora (poziom 4) C4389](compiler-warning-level-4-c4389.md)
