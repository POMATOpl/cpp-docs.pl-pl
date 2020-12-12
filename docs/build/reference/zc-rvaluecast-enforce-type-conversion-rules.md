---
description: 'Dowiedz się więcej na temat:/Zc: rvalueCast (Wymuś reguły konwersji typów)'
title: /Zc:rvalueCast (Wymuszanie zasad konwersji typów)
ms.date: 02/18/2020
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
ms.openlocfilehash: f9739f16b12e5e0335f17bb5a56ed1e4aa265e9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269149"
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (Wymuszanie zasad konwersji typów)

Gdy **`/Zc:rvalueCast`** opcja jest określona, kompilator prawidłowo identyfikuje typ referencyjny rvalue jako wynik operacji Cast. Jego zachowanie jest zgodne ze standardem C++ 11. Jeśli opcja nie jest określona, zachowanie kompilatora jest takie samo jak w programie Visual Studio 2012.

## <a name="syntax"></a>Składnia

> **`/Zc:rvalueCast`**\
> **`/Zc:rvalueCast-`**

## <a name="remarks"></a>Uwagi

Jeśli **`/Zc:rvalueCast`** jest określony, kompilator postępuje zgodnie z sekcją 5,4 standardu c++ 11 i traktuje tylko wyrażenia rzutowania, które powodują typy niereferencyjne i wyrażenia rzutowania, które powodują odwołania rvalue do typów niebędących funkcjami jako typy rvalue. Domyślnie, lub jeśli **`/Zc:rvalueCast-`** jest określony, kompilator jest niezgodny i traktuje wszystkie wyrażenia rzutowania, które powodują odwołania rvalue jako rvalues. W celu uzyskania zgodności i wyeliminowania błędów związanych z użyciem rzutowania zalecamy korzystanie z programu **`/Zc:rvalueCast`** .

Domyślnie program **`/Zc:rvalueCast`** jest wyłączony ( **`/Zc:rvalueCast-`** ). Opcja kompilatora [/permissive-](permissive-standards-conformance.md) niejawnie ustawia tę opcję, ale można ją zastąpić przy użyciu **`/Zc:rvalueCast-`** .

Użyj, **`/Zc:rvalueCast`** Jeśli Przekaż wyrażenie rzutowania jako argument do funkcji, która przyjmuje typ referencyjny rvalue. Zachowanie domyślne powoduje błąd kompilatora [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) , gdy kompilator niepoprawnie Określa typ wyrażenia Cast. Ten przykład pokazuje błąd kompilatora w prawidłowym kodzie, gdy **`/Zc:rvalueCast`** nie jest określony:

```cpp
// Test of /Zc:rvalueCast
// compile by using:
// cl /c /Zc:rvalueCast- make_thing.cpp
// cl /c /Zc:rvalueCast make_thing.cpp

#include <utility>

template <typename T>
struct Thing {
   // Construct a Thing by using two rvalue reference parameters
   Thing(T&& t1, T&& t2)
      : thing1(t1), thing2(t2) {}

   T& thing1;
   T& thing2;
};

// Create a Thing, using move semantics if possible
template <typename T>
Thing<T> make_thing(T&& t1, T&& t2)
{
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));
}

struct Test1 {
   long a;
   long b;

   Thing<long> test() {
      // Use identity casts to create rvalues as arguments
      return make_thing(static_cast<long>(a), static_cast<long>(b));
   }
};
```

Domyślne zachowanie kompilatora może nie zgłaszać błędów C2102 w razie potrzeby. W tym przykładzie kompilator nie zgłasza błędu, jeśli adres rvalue utworzonego przez rzutowanie tożsamości jest tworzony, gdy **`/Zc:rvalueCast`** jest nieokreślony:

```cpp
int main() {
   int a = 1;
   int *p = &a;   // Okay, take address of lvalue
                  // Identity cast creates rvalue from lvalue;
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value
}
```

Aby uzyskać więcej informacji na temat problemów ze zgodnością w Visual C++, zobacz [niestandardowe zachowanie](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz   >  stronę właściwości konfiguracja języka **C/C++**  >   .

1. Ustaw właściwość **Wymuszaj reguły konwersji typu** na **`/Zc:rvalueCast`** lub **`/Zc:rvalueCast-`** . Wybierz **przycisk OK** lub **Zastosuj** , aby zapisać zmiany.

## <a name="see-also"></a>Zobacz też

[/Zc (Zgodność)](zc-conformance.md)
