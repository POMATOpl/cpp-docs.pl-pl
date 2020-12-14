---
description: 'Dowiedz się więcej o: błąd kompilatora C2316'
title: Błąd kompilatora C2316
ms.date: 07/08/2019
f1_keywords:
- C2316
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
ms.openlocfilehash: 0e2f528b3f13964a971b88fca110980947bd7d11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282201"
---
# <a name="compiler-error-c2316"></a>Błąd kompilatora C2316

> "*class_type*": nie można przechwycić, ponieważ destruktor i/lub Konstruktor kopiujący są niedostępne lub zostały usunięte

Wyjątek został przechwycony przez wartość lub przez odwołanie, ale Konstruktor kopiujący, operator przypisania lub oba były niedostępne.

## <a name="remarks"></a>Uwagi

Zmiany zgodności w programie Visual Studio 2015 zostały wykonane z powodu nieprawidłowych instrukcji przechwytywania wyjątków MFC pochodzących od `CException` . Ze względu `CException` na to, że ma Dziedziczony prywatny Konstruktor kopiujący, Klasa i jej pochodne nie są możliwe do kopiowania i nie mogą być przesyłane przez wartość, co oznacza, że nie mogą być przechwytywane przez wartość. Instrukcje catch, które przechwytują wyjątki MFC według wartości, wcześniej doprowadziły do nieprzechwyconych wyjątków w czasie wykonywania. Teraz kompilator prawidłowo identyfikuje tę sytuację i zgłasza błąd C2316. Aby rozwiązać ten problem, zalecamy korzystanie z makr TRY/CATCH MFC zamiast pisania własnych programów obsługi wyjątków. Jeśli nie jest to odpowiednie dla kodu, należy przechwycić wyjątki MFC przez odwołanie.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2316 i przedstawia sposób jego rozwiązania:

```cpp
// C2316.cpp
// compile with: /EHsc
#include <stdio.h>

struct B
{
public:
    B() {}
    // Delete the following line to resolve.
private:
    // copy constructor
    B(const B&) {}
};

void f(const B&)
{
}

int main()
{
    try
    {
        B aB;
        f(aB);
    }
    catch (B b)    // C2316
    {
        printf_s("Caught an exception!\n");
    }
}
```
