---
title: Wybór ogólny (C11)
description: Opisuje słowo kluczowe C11 _Generic używane w kompilatorze Microsoft Visual C
ms.date: 12/9/2020
helpviewer_keywords:
- _Generic keyword [C]
ms.openlocfilehash: de0e840c19186219d53800b9d008d7695b807bc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97349418"
---
# <a name="generic-selection-c11"></a>Wybór ogólny (C11)

Użyj **`_Generic`** słowa kluczowego, aby napisać kod, który wybiera wyrażenie w czasie kompilacji na podstawie typu argumentu. Jest to podobne do przeciążania w języku C++, gdzie typ argumentu wybiera funkcję do wywołania, z tą różnicą, że typ argumentu wybiera wyrażenie do obliczenia.

Na przykład wyrażenie `_Generic(42, int: "integer", char: "character", default: "unknown");` oblicza typ `42` i szuka pasującego typu, `int` na liście. Znajduje je i zwraca `"integer"` .

## <a name="syntax"></a>Składnia

*`generic-selection`*:\
&nbsp;&nbsp;&nbsp;&nbsp;**`_Generic`** **(** *`assignment-expression`, `assoc-list`* **)**

*`assoc-list`*:\
&nbsp;&nbsp;&nbsp;&nbsp;*`association`*\
&nbsp;&nbsp;&nbsp;&nbsp;*`assoc-list`, `association`*

*`association`*:\
&nbsp;&nbsp;&nbsp;&nbsp;*`type-name`* : *`assignment-expression`*\
&nbsp;&nbsp;&nbsp;&nbsp;**`default`** : *`assignment-expression`*

Pierwszy *`assignment-expression`* jest nazywany wyrażeniem sterującym. Typ wyrażenia kontrolnego jest określany w czasie kompilacji i dopasowywany do, *`assoc-list`* Aby znaleźć wyrażenie, które ma zostać obliczone i zwrócone. Wyrażenie sterujące nie jest oceniane. Na przykład `_Generic(intFunc(), int: "integer", default: "error");` nie powoduje wywołania w czasie wykonywania do `intFunc()` . 

Gdy typ wyrażenia kontrolnego jest określony, `const` ,  `volatile` , i `restrict` są usuwane przed dopasowaniem do *`assoc-list`* .

Wpisy w `assoc-list` nie wybrane nie są oceniane.

## <a name="constraints"></a>Ograniczenia

- *`assoc-list`* Nie można określić tego samego typu więcej niż raz.
- *`assoc-list`* Nie można określić typów, które są zgodne ze sobą, takich jak Wyliczenie i typ podstawowy tego wyliczenia.
- Jeśli zaznaczenie ogólne nie ma domyślnego, wyrażenie sterujące musi mieć tylko jedną zgodną nazwę typu na liście skojarzenie ogólne.

## <a name="example"></a>Przykład

Jednym ze sposobów korzystania z programu **`_Generic`** jest w makrze. Plik nagłówka <tgmath. h> używa **_Generic** do wywołania odpowiedniej funkcji matematycznej w zależności od typu argumentu. Na przykład makro `cos()` mapuje wywołanie z zmiennoprzecinkową do `cosf()` , podczas mapowania wywołania złożonego dwukrotnie na `ccos()` .

Poniższy przykład pokazuje, jak napisać makro, które identyfikuje typ argumentu, który jest przekazywany do niego. Tworzy, `"unknown"` Jeśli żaden wpis w nie *`assoc-list`* jest zgodny z wyrażeniem kontrolnym:

```C
// Compile with /std:c11

#include <stdio.h>

/* Get a type name string for the argument x */
#define TYPE_NAME(X) _Generic((X), \
      int: "int", \
      char: "char", \
      double: "double", \
      default: "unknown")

int main()
{
    printf("Type name: %s\n", TYPE_NAME(42.42));

    // The following would result in a compile error because 
    // 42.4 is a double, doesn't match anything in the list, 
    // and there is no default.
    // _Generic(42.4, int: "integer", char: "character"));
}

/* Output:
Type name: double
*/

```

## <a name="see-also"></a>Zobacz też

[`/std` (Określ wersję standardową języka)](../build/reference/std-specify-language-standard-version.md)\
[Funkcje matematyczne niezależne od typu](../c-runtime-library/tgmath.md)