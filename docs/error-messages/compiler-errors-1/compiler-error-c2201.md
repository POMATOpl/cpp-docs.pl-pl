---
title: Błąd kompilatora C2201
ms.date: 11/04/2016
f1_keywords:
- C2201
helpviewer_keywords:
- C2201
ms.assetid: ed927659-6e9c-447d-9963-19969ae1e957
ms.openlocfilehash: 05f8bb3e9b77d547bce363ea82b8e3816ed998cc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216326"
---
# <a name="compiler-error-c2201"></a>Błąd kompilatora C2201

"Identyfikator": musi mieć zewnętrzne połączenie, aby można było je wyeksportować/zaimportować

Wyeksportowany identyfikator to **`static`** .

Poniższy przykład generuje C2286:

```cpp
// C2201.cpp
// compile with: /c
__declspec(dllexport) static void func() {}   // C2201 func() is static
__declspec(dllexport) void func2() {}   // OK
```

## <a name="see-also"></a>Zobacz także

[Typy połączeń](../../cpp/types-of-linkage.md)
