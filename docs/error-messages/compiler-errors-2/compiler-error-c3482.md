---
description: 'Dowiedz się więcej o: błąd kompilatora C3482'
title: Błąd kompilatora C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: 752ce53b590ef5c10c25e0d0e850c7c4cc2776bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315702"
---
# <a name="compiler-error-c3482"></a>Błąd kompilatora C3482

elementu "This" można użyć tylko jako przechwytywania lambda w obrębie niestatycznej funkcji składowej

Nie można przekazać **`this`** do listy przechwytywania wyrażenia lambda, która jest zadeklarowana w metodzie statycznej lub funkcji globalnej.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Przekonwertuj otaczającą funkcję na niestatyczną metodę lub

- Usuń **`this`** wskaźnik z listy przechwytywania wyrażenia lambda.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3482:

```cpp
// C3482.cpp
// compile with: /c

class C
{
public:
   static void staticMethod()
   {
      [this] {}(); // C3482
   }
};
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)
