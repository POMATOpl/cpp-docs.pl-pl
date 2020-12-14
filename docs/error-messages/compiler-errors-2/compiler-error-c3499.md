---
description: 'Dowiedz się więcej o: błąd kompilatora C3499'
title: Błąd kompilatora C3499
ms.date: 11/04/2016
f1_keywords:
- C3499
helpviewer_keywords:
- C3499
ms.assetid: 6717de5c-ae0f-4024-bdf2-b5598009e7b6
ms.openlocfilehash: e4e572be1b5e39ccec6bf1ca64eaf62a3e44ef28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315481"
---
# <a name="compiler-error-c3499"></a>Błąd kompilatora C3499

lambda, która została określona jako zwracająca typ void nie może zwracać wartości

Kompilator generuje ten błąd, gdy wyrażenie lambda, które określa **`void`** jako zwracany typ zwraca wartość, lub gdy wyrażenie lambda zawiera więcej niż jedną instrukcję i zwraca wartość, ale nie określa jego typu zwracanego.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Nie zwracaj wartości z wyrażenia lambda lub

- Podaj zwracany typ wyrażenia lambda lub

- Połącz instrukcje tworzące treść wyrażenia lambda w pojedynczej instrukcji.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3499, ponieważ treść wyrażenia lambda zawiera wiele instrukcji i zwraca wartość, ale wyrażenie lambda nie określa zwracanego typu:

```cpp
// C3499a.cpp

int main()
{
   [](int x) { int n = x * 2; return n; } (5); // C3499
}
```

Poniższy przykład przedstawia dwa możliwe rozwiązania do C3499. Pierwsze rozwiązanie zapewnia zwracany typ wyrażenia lambda. Druga rozdzielczość łączy instrukcje, które tworzą treść wyrażenia lambda w pojedynczej instrukcji.

```cpp
// C3499b.cpp

int main()
{
   // Possible resolution 1:
   // Provide the return type of the lambda expression.
   [](int x) -> int { int n = x * 2; return n; } (5);

   // Possible resolution 2:
   // Combine the statements that make up the body of
   // the lambda expression into a single statement.
   [](int x) { return x * 2; } (5);
}
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)
