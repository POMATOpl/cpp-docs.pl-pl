---
description: 'Dowiedz się więcej na temat: pop_macro pragma'
title: pop_macro, pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.pop_macro
- pop_macro_CPP
helpviewer_keywords:
- pop_macro pragma
- pragmas, pop_macro
ms.assetid: 3b5489d0-69ba-4c66-b572-2748af0f12bb
ms.openlocfilehash: 395e107586b9534b2e9db616f30ddd88b15b93ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325709"
---
# <a name="pop_macro-pragma"></a>pop_macro, pragma

Ustawia wartość makra *Nazwa makra* na wartość w górnej części stosu dla tego makra.

## <a name="syntax"></a>Składnia

> **#pragma pop_macro (** "*Nazwa makra*" **)**

## <a name="remarks"></a>Uwagi

Aby można było wykonać **pop_macro**, należy wydać [push_macro](../preprocessor/push-macro.md) dla *nazwy makra* .

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

[Dyrektywy pragma i słowo kluczowe __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
