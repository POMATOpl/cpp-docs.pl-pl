---
description: 'Dowiedz się więcej o: błąd kompilatora C3490'
title: Błąd kompilatora C3490
ms.date: 11/04/2016
f1_keywords:
- C3490
helpviewer_keywords:
- C3490
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
ms.openlocfilehash: 03896872fd0c683e3011aa7edbacb6a0a01ceaef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113366"
---
# <a name="compiler-error-c3490"></a>Błąd kompilatora C3490

nie można zmodyfikować elementu "var", ponieważ jest on dostępny za pomocą obiektu const

Wyrażenie lambda zadeklarowane w **`const`** metodzie nie może modyfikować niemodyfikowalnych danych elementu członkowskiego.

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Usuń **`const`** modyfikator z deklaracji metody.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3490, ponieważ modyfikuje zmienną członkowską `_i` w **`const`** metodzie:

```cpp
// C3490a.cpp
// compile with: /c

class C
{
   void f() const
   {
      auto x = [=]() { _i = 20; }; // C3490
   }

   int _i;
};
```

Poniższy przykład rozwiązuje C3490 przez usunięcie **`const`** modyfikatora z deklaracji metody:

```cpp
// C3490b.cpp
// compile with: /c

class C
{
   void f()
   {
      auto x = [=]() { _i = 20; };
   }

   int _i;
};
```

## <a name="see-also"></a>Zobacz też

[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)
