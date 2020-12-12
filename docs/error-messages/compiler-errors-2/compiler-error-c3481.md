---
description: 'Dowiedz się więcej o: błąd kompilatora C3481'
title: Błąd kompilatora C3481
ms.date: 11/04/2016
f1_keywords:
- C3481
helpviewer_keywords:
- C3481
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
ms.openlocfilehash: 31f13b56a2b5df66a5765ee63313ffe265c15fe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113405"
---
# <a name="compiler-error-c3481"></a>Błąd kompilatora C3481

"var": nie znaleziono zmiennej przechwytywania lambda

Kompilator nie może odnaleźć definicji zmiennej, która została przeniesiona do listy przechwytywania wyrażenia lambda.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Usuń zmienną z listy przechwytywania wyrażenia lambda.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3481, ponieważ zmienna `n` nie jest zdefiniowana:

```cpp
// C3481.cpp

int main()
{
   [n] {}(); // C3481
}
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)
