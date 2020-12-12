---
description: 'Dowiedz się więcej o: błąd kompilatora C3495'
title: Błąd kompilatora C3495
ms.date: 11/04/2016
f1_keywords:
- C3495
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
ms.openlocfilehash: 3c04c80182dad32b539e09224fd9e303b3325578
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113171"
---
# <a name="compiler-error-c3495"></a>Błąd kompilatora C3495

"var": Przechwytywanie lambda musi mieć automatyczny czas trwania magazynu

Nie można przechwycić zmiennej, która nie ma automatycznego czasu trwania magazynu, na przykład zmiennej oznaczonej jako **`static`** lub **`extern`** .

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Nie przekazuj **`static`** ani **`extern`** zmiennej do listy przechwytywania wyrażenia lambda.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3495, ponieważ **`static`** zmienna `n` pojawia się na liście przechwytywania wyrażenia lambda:

```cpp
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)
