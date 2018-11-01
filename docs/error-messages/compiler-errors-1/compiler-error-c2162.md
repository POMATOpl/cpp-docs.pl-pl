---
title: Błąd kompilatora C2162
ms.date: 11/04/2016
f1_keywords:
- C2162
helpviewer_keywords:
- C2162
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
ms.openlocfilehash: 02c0101324b28ebe548c38c6dc617faaa62315b7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602409"
---
# <a name="compiler-error-c2162"></a>Błąd kompilatora C2162

Oczekiwany parametr formalny makra

Token po operator tworzenia ciągu (#) nie jest nazwą parametrów formalnych.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C2162:

```
// C2162.cpp
// compile with: /c
#include <stdio.h>

#define print(a) printf_s(b)   // OK
#define print(a) printf_s(#b)    // C2162
```