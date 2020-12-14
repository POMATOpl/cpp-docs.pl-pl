---
description: 'Dowiedz się więcej o: błąd kompilatora C3409'
title: Błąd kompilatora C3409
ms.date: 11/06/2018
f1_keywords:
- C3409
helpviewer_keywords:
- C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
ms.openlocfilehash: 6d3ba602ab9f98526d2ddd6538e424b7879c7017
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316261"
---
# <a name="compiler-error-c3409"></a>Błąd kompilatora C3409

> pusty blok atrybutu jest niedozwolony

## <a name="remarks"></a>Uwagi

Nawiasy kwadratowe zostały zinterpretowane przez kompilator jako blok [atrybutu](../../windows/attributes/attributes-alphabetical-reference.md) , ale nie znaleziono żadnych atrybutów.

Kompilator może generować ten błąd w przypadku używania nawiasów kwadratowych jako części definicji wyrażenia lambda. Ten błąd występuje, gdy kompilator nie może określić, czy nawiasy kwadratowe są częścią definicji wyrażenia lambda lub bloku atrybutu. Aby uzyskać więcej informacji na temat wyrażeń lambda, zobacz [lambda Expressions](../../cpp/lambda-expressions-in-cpp.md).

### <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Jeśli nawiasy kwadratowe są częścią bloku atrybutu:

   1. Podaj jeden lub więcej atrybutów w bloku atrybutu.

   1. Usuń blok atrybutu.

1. Jeśli nawiasy kwadratowe są częścią wyrażenia lambda, upewnij się, że wyrażenie lambda jest zgodne z prawidłowymi regułami składni.

   Aby uzyskać więcej informacji na temat składni wyrażenia lambda, zobacz [składnia wyrażenia lambda](../../cpp/lambda-expression-syntax.md).

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C3409.

```cpp
// C3409.cpp
// compile with: /c
#include <windows.h>
[]   // C3409
class a {};

// OK
[object, uuid("00000000-0000-0000-0000-000000000000")]
__interface x {};

[coclass, uuid("00000000-0000-0000-0000-000000000001")]
class b : public x {};
```

Poniższy przykład generuje C3409, ponieważ wyrażenie lambda używa **`mutable`** specyfikacji, ale nie dostarcza listy parametrów. Kompilator nie może określić, czy nawiasy kwadratowe są częścią definicji wyrażenia lambda lub bloku atrybutu.

```cpp
// C3409b.cpp

int main()
{
   [] mutable {}();
}
```

## <a name="see-also"></a>Zobacz też

[przypisane](../../windows/attributes/attributes-alphabetical-reference.md)<br/>
[Wyrażenia lambda](../../cpp/lambda-expressions-in-cpp.md)<br/>
[Składnia wyrażenia lambda](../../cpp/lambda-expression-syntax.md)
