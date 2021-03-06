---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4930'
title: Ostrzeżenie kompilatora (poziom 1) C4930
ms.date: 11/04/2016
f1_keywords:
- C4930
helpviewer_keywords:
- C4930
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
ms.openlocfilehash: 9111b87ee2b281c7781e7115330634daefb14cc4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328066"
---
# <a name="compiler-warning-level-1-c4930"></a>Ostrzeżenie kompilatora (poziom 1) C4930

"prototyp": funkcja prototypowa nie została wywołana (czy definicja zmiennej była zamierzona?)

Kompilator wykrył nieużywany prototyp funkcji. Jeśli prototyp został zamierzony jako deklaracja zmiennej, Usuń nawiasy otwierające/zamykające.

Poniższy przykład generuje C4930:

```cpp
// C4930.cpp
// compile with: /W1
class Lock {
public:
   int i;
};

void f() {
   Lock theLock();   // C4930
   // try the following line instead
   // Lock theLock;
}

int main() {
}
```

C4930 może również wystąpić, gdy kompilator nie może rozróżnić deklaracji prototypu funkcji i wywołania funkcji.

Poniższy przykład generuje C4930:

```cpp
// C4930b.cpp
// compile with: /EHsc /W1

class BooleanException
{
   bool _result;

public:
   BooleanException(bool result)
      : _result(result)
   {
   }

   bool GetResult() const
   {
      return _result;
   }
};

template<class T = BooleanException>
class IfFailedThrow
{
public:
   IfFailedThrow(bool result)
   {
      if (!result)
      {
         throw T(result);
      }
   }
};

class MyClass
{
public:
   bool MyFunc()
   {
      try
      {
         IfFailedThrow<>(MyMethod()); // C4930

         // try one of the following lines instead
         // IfFailedThrow<> ift(MyMethod());
         // IfFailedThrow<>(this->MyMethod());
         // IfFailedThrow<>((*this).MyMethod());

         return true;
      }
      catch (BooleanException e)
      {
         return e.GetResult();
      }
   }

private:
   bool MyMethod()
   {
      return true;
   }
};

int main()
{
   MyClass myClass;
   myClass.MyFunc();
}
```

W powyższym przykładzie wynik metody, która przyjmuje zero argumentów jest przenoszona jako argument do konstruktora nienazwanej zmiennej klasy lokalnej. Wywołanie można rozróżnić przy użyciu nazwy zmiennej lokalnej lub prefiksu wywołania metody z wystąpieniem obiektu wraz z odpowiednim operatorem do składowej.
