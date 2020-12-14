---
description: 'Dowiedz się więcej o: błąd kompilatora C3849'
title: Błąd kompilatora C3849
ms.date: 11/04/2016
f1_keywords:
- C3849
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
ms.openlocfilehash: 6dbe4656eea2691c1c77c1afa389be80ab76af18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255356"
---
# <a name="compiler-error-c3849"></a>Błąd kompilatora C3849

Wywołanie w stylu funkcji na wyrażeniu typu "Type" spowoduje utratę kwalifikatorów const i/lub volatile dla wszystkich dostępnych przeciążeń operatora liczbowego

Zmienna z określonym nietrwałym typem const może wywołać tylko funkcje członkowskie zdefiniowane z tymi samymi lub większymi nietrwałymi atrybutami const.

Aby naprawić ten błąd, podaj odpowiednią funkcję członkowską. Nie można wykonać konwersji na obiekt kwalifikowany const lub volatile, gdy konwersja powoduje utratę kwalifikacji. Można uzyskać kwalifikatory, ale nie można utracić kwalifikatorów w konwersji.

Następujące przykłady generują C3849:

```cpp
// C3849.cpp
void glbFunc3(int i, char c)
{
   i;
}
typedef void (* pFunc3)(int, char);

void glbFunc2(int i)
{
   i;
}

typedef void (* pFunc2)(int);

void glbFunc1()
{
}
typedef void (* pFunc1)();

struct S4
{
   operator ()(int i)
   {
      i;
   }

   operator pFunc1() const
   {
      return &glbFunc1;
   }

   operator pFunc2() volatile
   {
      return &glbFunc2;
   }

   operator pFunc3()
   {
      return &glbFunc3;
   }

   // operator pFunc1() const volatile
   // {
   //    return &glbFunc1;
   // }
};

int main()
{
   // Cannot call any of the 4 overloads of "operator ()(.....)" and
   // "operator pFunc()" because none is declared as "const volatile"
   const volatile S4 s4;  // can only call cv member functions of S4
   s4();   // C3849 to resolve, uncomment member function
}
```
