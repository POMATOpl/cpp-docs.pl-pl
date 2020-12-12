---
description: 'Dowiedz się więcej o: błąd kompilatora C3484'
title: Błąd kompilatora C3484
ms.date: 11/04/2016
f1_keywords:
- C3484
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
ms.openlocfilehash: 6d3e72ef89ad33333c840b549cfc5c7c40495130
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315689"
---
# <a name="compiler-error-c3484"></a>Błąd kompilatora C3484

Oczekiwano "->" przed typem zwracanym

Należy podać `->` przed typem zwracanym wyrażenia lambda.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Podaj `->` przed typem zwracanym.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3484:

```cpp
// C3484a.cpp

int main()
{
   return []() . int { return 42; }(); // C3484
}
```

Poniższy przykład rozwiązuje C3484, dostarczając `->` przed zwracanym typem wyrażenia lambda:

```cpp
// C3484b.cpp

int main()
{
   return []() -> int { return 42; }();
}
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)
