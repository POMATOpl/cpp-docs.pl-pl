---
description: 'Dowiedz się więcej na temat: listy zmiennych argumentów (...) (C++/CLI)'
title: Listy zmiennych argumentów (...) (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- variable argument lists
- parameter arrays
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
ms.openlocfilehash: fec05a2ce397a0991a4bfd0a5aeb6a8b16d986ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176850"
---
# <a name="variable-argument-lists--ccli"></a>Listy zmiennych argumentów (...) (C++/CLI)

Ten przykład pokazuje, jak można użyć `...` składni w języku C++/CLI do implementowania funkcji, które mają zmienną liczbę argumentów.

> [!NOTE]
> Ten temat dotyczy języka C++/CLI. Aby uzyskać informacje o używaniu `...` języka ISO w standardzie C++, zobacz [wielokropek i szablony wariadyczne](../cpp/ellipses-and-variadic-templates.md) oraz wielokropek i argumenty domyślne w [wyrażeniach przyrostkowych](../cpp/postfix-expressions.md).

Parametr, który używa `...` musi być ostatnim parametrem na liście parametrów.

## <a name="example"></a>Przykład

### <a name="code"></a>Kod

```cpp
// mcppv2_paramarray.cpp
// compile with: /clr
using namespace System;
double average( ... array<Int32>^ arr ) {
   int i = arr->GetLength(0);
   double answer = 0.0;

   for (int j = 0 ; j < i ; j++)
      answer += arr[j];

   return answer / i;
}

int main() {
   Console::WriteLine("{0}", average( 1, 2, 3, 6 ));
}
```

```Output
3
```

## <a name="code-example"></a>Przykład kodu

Poniższy przykład pokazuje, jak wywołać w języku C# funkcję Visual C++, która przyjmuje zmienną liczbę argumentów.

```cpp
// mcppv2_paramarray2.cpp
// compile with: /clr:safe /LD
using namespace System;

public ref class C {
public:
   void f( ... array<String^>^ a ) {}
};
```

Funkcję `f` można wywołać z poziomu języka C# lub Visual Basic, na przykład, tak jakby była funkcją, która może przyjmować zmienną liczbę argumentów.

W języku C# argument, który jest przesyłany do `ParamArray` parametru może być wywoływany przez zmienną liczbę argumentów. Poniższy przykład kodu jest w języku C#.

```csharp
// mcppv2_paramarray3.cs
// compile with: /r:mcppv2_paramarray2.dll
// a C# program

public class X {
   public static void Main() {
      // Visual C# will generate a String array to match the
      // ParamArray attribute
      C myc = new C();
      myc.f("hello", "there", "world");
   }
}
```

Wywołanie `f` w Visual C++ może przekazać zainicjowaną tablicę lub tablicę o zmiennej długości.

```cpp
// mcpp_paramarray4.cpp
// compile with: /clr
using namespace System;

public ref class C {
public:
   void f( ... array<String^>^ a ) {}
};

int main() {
   C ^ myc = gcnew C();
   myc->f("hello", "world", "!!!");
}
```

## <a name="see-also"></a>Zobacz też

[Tablice](arrays-cpp-component-extensions.md)
