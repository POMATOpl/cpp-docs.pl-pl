---
title: Błąd kompilatora C2201
ms.date: 11/04/2016
f1_keywords:
- C2201
helpviewer_keywords:
- C2201
ms.assetid: ed927659-6e9c-447d-9963-19969ae1e957
ms.openlocfilehash: d6697de48c4868170e8c7afa287b0eb43e9523f5
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501642"
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

## <a name="see-also"></a>Zobacz też

[Typy połączeń](../../cpp/program-and-linkage-cpp.md)
