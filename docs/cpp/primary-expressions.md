---
title: Wyrażenia podstawowe
description: Wyrażenia podstawowe w języku programowania C++.
ms.date: 10/02/2020
helpviewer_keywords:
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
ms.openlocfilehash: 4c52992071453bc189a3078db9592b02dfb8ba9b
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765318"
---
# <a name="primary-expressions"></a>Wyrażenia podstawowe

Wyrażenia podstawowe są blokami konstrukcyjnymi bardziej złożonych wyrażeń. Mogą to być literały, nazwy i nazwy kwalifikowane przez operator rozpoznawania zakresu ( `::` ). Wyrażenie podstawowe może mieć jedną z następujących form:

*`primary-expression`*\
&emsp;*`literal`*\
&emsp;**`this`**\
&emsp;*`name`*\
&emsp;**`::`** *`name`* **`(`** *`expression`* **`)`**

A *`literal`* to stałe wyrażenie podstawowe. Jego typ zależy od postaci jego specyfikacji. Aby uzyskać pełne informacje na temat określania literałów, zobacz [literały](../cpp/numeric-boolean-and-pointer-literals-cpp.md) .

**`this`** Słowo kluczowe jest wskaźnikiem do obiektu klasy. Jest on dostępny w niestatycznych funkcjach składowych. Wskazuje na wystąpienie klasy, dla której wywołano funkcję. **`this`** Nie można użyć słowa kluczowego poza treścią funkcji składowej klasy.

Typ **`this`** wskaźnika to `type * const` (gdzie `type` to nazwa klasy) w funkcjach, które nie modyfikują **`this`** wskaźnika. Poniższy przykład przedstawia deklaracje funkcji składowych i typy **`this`** :

```cpp
// expre_Primary_Expressions.cpp
// compile with: /LD
class Example
{
public:
    void Func();          //  * const this
    void Func() const;    //  const * const this
    void Func() volatile; //  volatile * const this
};
```

Aby uzyskać więcej informacji na temat modyfikowania typu **`this`** wskaźnika, zobacz [ `this` wskaźnik](this-pointer.md).

Operator rozpoznawania zakresu ( **`::`** ), po którym następuje nazwa, jest wyrażeniem podstawowym.  Nazwy te muszą być nazwami w zakresie globalnym, a nie nazwami elementów członkowskich. Typ wyrażenia jest określany przez deklarację nazwy. Jest to wartość l (czyli, która może pojawić się po lewej stronie wyrażenia przypisania), jeśli nazwa deklarująca jest wartością l. Operator rozpoznawania zakresu umożliwia odwoływanie się do globalnej nazwy, nawet jeśli ta nazwa jest ukryta w bieżącym zakresie. Zobacz [zakres](../cpp/scope-visual-cpp.md) , aby zapoznać się z przykładem użycia operatora rozpoznawania zakresu.

Wyrażenie ujęte w nawiasy jest wyrażeniem podstawowym. Jego typ i wartość są identyczne z typem i wartością wyrażenia nieujętego w nawiasy. Jest to wartość l, jeśli wyrażenie nieujęte w nawiasy jest wartością l.

Przykłady wyrażeń podstawowych:

```cpp
100 // literal
'c' // literal
this // in a member function, a pointer to the class instance
::func // a global function
::operator + // a global operator function
::A::B // a global qualified name
( i + 1 ) // a parenthesized expression
```

Te przykłady są uznawane za *nazwy*, a jako wyrażenia podstawowe w różnych formach:

```cpp
MyClass // an identifier
MyClass::f // a qualified name
operator = // an operator function name
operator char* // a conversion operator function name
~MyClass // a destructor name
A::B   // a qualified name
A<int> // a template id
```

## <a name="see-also"></a>Zobacz też

[Typy wyrażeń](../cpp/types-of-expressions.md)
