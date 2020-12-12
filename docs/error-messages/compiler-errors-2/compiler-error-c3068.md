---
description: 'Dowiedz się więcej o: błąd kompilatora C3068'
title: Błąd kompilatora C3068
ms.date: 11/04/2016
f1_keywords:
- C3068
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
ms.openlocfilehash: a73c525f017a3d571600e31d4c9ea875d0b25662
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281677"
---
# <a name="compiler-error-c3068"></a>Błąd kompilatora C3068

"Function": funkcja "owies" nie może zawierać obiektów, które wymagałyby odwinięcia w przypadku wystąpienia wyjątku C++

Kompilator nie może wykonać odwinięcia stosu dla funkcji [owies](../../cpp/naked-cpp.md) , która wywołała wyjątek, ponieważ został utworzony obiekt tymczasowy w funkcji i obsłudze wyjątków C++ ([/EHsc](../../build/reference/eh-exception-handling-model.md)).

Aby rozwiązać ten problem, należy wykonać co najmniej jedną z następujących czynności:

- Nie Kompiluj z/EHsc.

- Nie zaznaczaj funkcji jako `naked` .

- Nie należy tworzyć obiektu tymczasowego w funkcji.

Jeśli funkcja tworzy obiekt tymczasowy na stosie, jeśli funkcja zgłasza wyjątek, a jeśli obsługa wyjątków C++ jest włączona, kompilator wyczyści stos, jeśli zostanie zgłoszony wyjątek.

Gdy wyjątek jest zgłaszany, kod wygenerowany przez kompilator, nazywany prologiem i epilogu, które nie są obecne w funkcji owies, jest wykonywany dla funkcji.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3068:

```cpp
// C3068.cpp
// compile with: /EHsc
// processor: x86
class A {
public:
   A(){}
   ~A(){}
};

void b(A){}

__declspec(naked) void c() {
   b(A());   // C3068
};
```
