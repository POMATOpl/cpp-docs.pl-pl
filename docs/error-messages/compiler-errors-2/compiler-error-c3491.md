---
description: 'Dowiedz się więcej o: błąd kompilatora C3491'
title: Błąd kompilatora C3491
ms.date: 11/04/2016
f1_keywords:
- C3491
helpviewer_keywords:
- C3491
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
ms.openlocfilehash: 8bd01c47e05d7cf266a22dfc713ae28bffe08e49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315640"
---
# <a name="compiler-error-c3491"></a>Błąd kompilatora C3491

"var": nie można zmodyfikować przechwycenia przez wartość w niemodyfikowalnym wyrażeniu lambda

Niemodyfikowalne wyrażenie lambda nie może zmodyfikować wartości zmiennej, która jest przechwytywana przez wartość.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Zadeklaruj wyrażenie lambda za pomocą **`mutable`** słowa kluczowego lub

- Przekaż zmienną przez odwołanie do listy przechwytywania wyrażenia lambda.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3491, ponieważ treść niemodyfikowalnego wyrażenia lambda modyfikuje zmienną przechwytywania `m` :

```cpp
// C3491a.cpp

int main()
{
   int m = 55;
   [m](int n) { m = n; }(99); // C3491
}
```

Poniższy przykład rozwiązuje C3491 przez zadeklarowanie wyrażenia lambda za pomocą **`mutable`** słowa kluczowego:

```cpp
// C3491b.cpp

int main()
{
   int m = 55;
   [m](int n) mutable { m = n; }(99);
}
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)
