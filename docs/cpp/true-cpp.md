---
description: 'Dowiedz się więcej o: true (C++)'
title: true (C++)
ms.date: 11/04/2016
f1_keywords:
- true_cpp
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
ms.openlocfilehash: 6f3a9a183a30057ab3a013dad6e03458e6532658
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186457"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>Składnia

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>Uwagi

To słowo kluczowe jest jedną z dwóch wartości dla zmiennej typu [bool](../cpp/bool-cpp.md) lub wyrażenia warunkowego (wyrażenie warunkowe to teraz prawdziwe wyrażenie logiczne). Jeśli `i` jest typu **`bool`** , instrukcja `i = true;` przypisuje **`true`** do `i` .

## <a name="example"></a>Przykład

```cpp
// bool_true.cpp
#include <stdio.h>
int main()
{
    bool bb = true;
    printf_s("%d\n", bb);
    bb = false;
    printf_s("%d\n", bb);
}
```

```Output
1
0
```

## <a name="see-also"></a>Zobacz także

[Słowa kluczowe](../cpp/keywords-cpp.md)
