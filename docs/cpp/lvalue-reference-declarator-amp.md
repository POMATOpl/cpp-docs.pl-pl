---
description: 'Dowiedz się więcej na temat: lvalue Reference deklarator: &amp;'
title: 'Deklarator odwołania lvalue: &amp;'
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- reference operator
- '& operator [C++], reference operator'
ms.assetid: edf0513d-3dcc-4663-b276-1269795dda51
ms.openlocfilehash: 99160f0eac10922e95b131d4246f898b3f59705e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312283"
---
# <a name="lvalue-reference-declarator-amp"></a>Deklarator odwołania lvalue: &amp;

Przechowuje adres obiektu, ale zachowuje się syntaktycznie jak obiekt.

## <a name="syntax"></a>Składnia

```
type-id & cast-expression
```

## <a name="remarks"></a>Uwagi

Odwołanie lvalue można traktować jako inną nazwę obiektu. Deklaracja odwołania lvalue składa się z opcjonalnej listy specyfikatorów, a następnie odwołania deklarator. Odwołanie musi być zainicjowane i nie można go zmienić.

Każdy obiekt, którego adres można przekonwertować na dany typ wskaźnika, można również przekonwertować na podobny typ odwołania. Na przykład każdy obiekt, którego adres można przekonwertować na typ, `char *` może być również konwertowany na typ `char &` .

Nie należy mylić deklaracji odwołań z użyciem [operatora address-of](../cpp/address-of-operator-amp.md). Gdy `&` *Identyfikator* jest poprzedzony typem, takim jak **`int`** lub **`char`** , *Identyfikator* jest zadeklarowany jako odwołanie do typu. Gdy `&` *Identyfikator* nie jest poprzedzony typem, użycie jest zgodne z operatorem address-of.

## <a name="example"></a>Przykład

Poniższy przykład demonstruje odwołanie deklarator przez zadeklarowanie `Person` obiektu i odwołania do tego obiektu. Ponieważ `rFriend` jest odwołaniem do `myFriend` , aktualizowanie każdej zmiennej zmienia ten sam obiekt.

```cpp
// reference_declarator.cpp
// compile with: /EHsc
// Demonstrates the reference declarator.
#include <iostream>
using namespace std;

struct Person
{
    char* Name;
    short Age;
};

int main()
{
   // Declare a Person object.
   Person myFriend;

   // Declare a reference to the Person object.
   Person& rFriend = myFriend;

   // Set the fields of the Person object.
   // Updating either variable changes the same object.
   myFriend.Name = "Bill";
   rFriend.Age = 40;

   // Print the fields of the Person object to the console.
   cout << rFriend.Name << " is " << myFriend.Age << endl;
}
```

```Output
Bill is 40
```

## <a name="see-also"></a>Zobacz też

[Materiały źródłowe](../cpp/references-cpp.md)<br/>
[Argumenty funkcji typu odwołania](../cpp/reference-type-function-arguments.md)<br/>
[Funkcja typu odwołania zwraca](../cpp/reference-type-function-returns.md)<br/>
[Odwołania do wskaźników](../cpp/references-to-pointers.md)
