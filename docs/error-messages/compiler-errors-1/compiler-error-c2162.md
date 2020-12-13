---
description: 'Dowiedz się więcej o: błąd kompilatora C2162'
title: Błąd kompilatora C2162
ms.date: 11/04/2016
f1_keywords:
- C2162
helpviewer_keywords:
- C2162
ms.assetid: 34923628-d35e-48ab-9072-b95e3b5f6b45
ms.openlocfilehash: 39b7cc4828cad50e9ac5056e489de319a7eb7db8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177968"
---
# <a name="compiler-error-c2162"></a>Błąd kompilatora C2162

oczekiwany parametr formalny makra

Token następujący po operatorze tworzenia ciągu (#) nie jest formalnej nazwy parametru.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2162:

```cpp
// C2162.cpp
// compile with: /c
#include <stdio.h>

#define print(a) printf_s(b)   // OK
#define print(a) printf_s(#b)    // C2162
```
