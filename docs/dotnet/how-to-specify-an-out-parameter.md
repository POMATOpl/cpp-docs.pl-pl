---
description: 'Dowiedz się więcej na temat: jak określić parametr out'
title: 'Instrukcje: Określanie parametru wyjściowego'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
ms.openlocfilehash: b43930557b4bdfd22bf902a6d9adf95eb8ba4d01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286341"
---
# <a name="how-to-specify-an-out-parameter"></a>Instrukcje: Określanie parametru wyjściowego

Ten przykład pokazuje, jak określić, że parametr funkcji jest `out` parametrem i jak wywołać tę funkcję z programu w języku C#.

`out`Parametr jest określony w języku C++ przy użyciu <xref:System.Runtime.InteropServices.OutAttribute> .

## <a name="example"></a>Przykład

Pierwsza część tego przykładu tworzy bibliotekę DLL języka C++. Definiuje typ, który zawiera funkcję z `out` parametrem.

```cpp
// cpp_out_param.cpp
// compile with: /LD /clr
using namespace System;
public value struct TestStruct {
   static void Test([Runtime::InteropServices::Out] String^ %s) {
      s = "a string";
   }
};
```

Ten plik źródłowy jest klientem języka C#, który korzysta ze składnika C++ utworzonego w poprzednim przykładzie.

```csharp
// cpp_out_param_2.cs
// compile with: /reference:cpp_out_param.dll
using System;
class TestClass {
   public static void Main() {
      String t;
      TestStruct.Test(out t);
      System.Console.WriteLine(t);
   }
}
```

```Output
a string
```

## <a name="see-also"></a>Zobacz też

[Korzystanie z międzyoperacyjności języka C++ (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
