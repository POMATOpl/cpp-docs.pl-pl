---
description: 'Dowiedz się więcej o: błąd kompilatora C3392'
title: Błąd kompilatora C3392
ms.date: 11/04/2016
f1_keywords:
- C3392
helpviewer_keywords:
- C3392
ms.assetid: e4757596-e2aa-4314-b01e-5c4bfd2110e9
ms.openlocfilehash: c64b49bee05079fd2d1b468d807af5b1fd89ba26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316339"
---
# <a name="compiler-error-c3392"></a>Błąd kompilatora C3392

"type_arg": nieprawidłowy typ argumentu dla parametru generycznego "param" generycznej "generic_type", musi mieć publiczny Konstruktor bez parametrów

Wystąpienie typu ogólnego zostało nieprawidłowo utworzone. Sprawdź definicję typu. Aby uzyskać więcej informacji, zobacz  [Ogólne](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład używa języka C# do tworzenia składnika, który zawiera typ ogólny, który ma pewne ograniczenia, które nie są obsługiwane podczas tworzenia typów ogólnych w C++/CLI. Aby uzyskać więcej informacji, zobacz [ograniczenia dotyczące parametrów typu](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```csharp
// C3392.cs
// Compile by using: csc /target:library C3392.cs
// a C# program
public class GR<C, V, N>
where C : class
where V : struct
where N : new() {}
```

Gdy dostępny jest składnik C3392.dll, Poniższy przykład generuje C3392.

```cpp
// C3392_b.cpp
// Compile by using: cl /clr C3392_b.cpp
#using <C3392.dll>

ref class R { R(int) {} };
ref class N { N() {} };

value class V {};

ref class N2 { public: N2() {} };
ref class R2 { public: R2() {} };

int main () {
   GR<R^, V, N^>^ gr1;   // C3392
   GR<R^, V, N2^>^ gr1a; // OK

   GR<R^, N^, N^>^ gr3;  // C3392
   GR<R^, V, N2^>^ gr3a; // OK

   GR<R^, V, R^>^ gr4;   // C3392
   GR<R^, V, R2^>^ gr4a; // OK
}
```
