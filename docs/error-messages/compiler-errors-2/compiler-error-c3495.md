---
title: Błąd kompilatora C3495 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3495
dev_langs:
- C++
helpviewer_keywords:
- C3495
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dda1e2f2699969ad0bc446d9f79a0004e043998d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067392"
---
# <a name="compiler-error-c3495"></a>Błąd kompilatora C3495

"var": przechwytywania lambda musi mieć automatycznym okresem magazynu

Nie można dokonać przechwytu zmiennej, która nie ma czas trwania automatycznego przechowywania, takie jak zmienna, która jest oznaczona `static` lub `extern`.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Nie przekazuj `static` lub `extern` zmiennej do listy przechwytywania wyrażenia lambda.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3495, ponieważ `static` zmiennej `n` pojawia się na liście przechwytywania wyrażenia lambda:

```
// C3495.cpp

int main()
{
   static int n = 66;
   [&n]() { return n; }(); // C3495
}
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)


