---
title: pop_macro
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.pop_macro
- pop_macro_CPP
helpviewer_keywords:
- pop_macro pragma
- pragmas, pop_macro
ms.assetid: 3b5489d0-69ba-4c66-b572-2748af0f12bb
ms.openlocfilehash: 0ea7d37332ce50fd1d21acba058da721a23f2097
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030342"
---
# <a name="popmacro"></a>pop_macro
Ustawia wartość *macro_name* do wartości w górnej części stosu dla tego makra.

## <a name="syntax"></a>Składnia

```
#pragma pop_macro("
macro_name
")
```

## <a name="remarks"></a>Uwagi

Najpierw należy wygenerować [push_macro](../preprocessor/push-macro.md) dla *macro_name* przed rozpoczęciem **pop_macro**.

## <a name="example"></a>Przykład

```cpp
// pragma_directives_pop_macro.cpp
// compile with: /W1
#include <stdio.h>
#define X 1
#define Y 2

int main() {
   printf("%d",X);
   printf("\n%d",Y);
   #define Y 3   // C4005
   #pragma push_macro("Y")
   #pragma push_macro("X")
   printf("\n%d",X);
   #define X 2   // C4005
   printf("\n%d",X);
   #pragma pop_macro("X")
   printf("\n%d",X);
   #pragma pop_macro("Y")
   printf("\n%d",Y);
}
```

```Output
1
2
1
2
1
3
```

## <a name="see-also"></a>Zobacz także

[Dyrektywy pragma i słowo kluczowe __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)