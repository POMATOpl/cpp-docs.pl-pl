---
description: 'Dowiedz się więcej o: błąd kompilatora C3480'
title: Błąd kompilatora C3480
ms.date: 11/04/2016
f1_keywords:
- C3480
helpviewer_keywords:
- C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
ms.openlocfilehash: dbeed462410d36b466e807d576549c1b73ee4917
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113418"
---
# <a name="compiler-error-c3480"></a>Błąd kompilatora C3480

"var": zmienna przechwytywania lambda musi pochodzić z otaczającego zakresu funkcji

Zmienna przechwytywania lambda nie jest z otaczającego zakresu funkcji.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Usuń zmienną z listy przechwytywania wyrażenia lambda.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3480, ponieważ zmienna `global` nie jest z otaczającego zakresu funkcji:

```cpp
// C3480a.cpp

int global = 0;
int main()
{
   [&global] { global = 5; }(); // C3480
}
```

Poniższy przykład rozwiązuje C3480 przez usunięcie zmiennej `global` z listy przechwytywania wyrażenia lambda:

```cpp
// C3480b.cpp

int global = 0;
int main()
{
   [] { global = 5; }();
}
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)
