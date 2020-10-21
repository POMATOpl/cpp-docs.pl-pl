---
title: Literal (C++/CLI)
description: Literal słowo kluczowe jest kontekstowego słowa kluczowego Microsoft C++/CLI dla stałej czasu kompilacji.
ms.date: 10/20/2020
ms.topic: reference
f1_keywords:
- literal
- literal_cpp
helpviewer_keywords:
- literal keyword [C++]
ms.openlocfilehash: 2d71a535252ba51f89407670b474a34b407eaffc
ms.sourcegitcommit: 59b7c18703d1ffd66827db0e2eeece490d3d8789
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2020
ms.locfileid: "92337216"
---
# <a name="literal-ccli"></a>`literal` (C++/CLI)

Zmienna (element członkowski danych) oznaczona jako **`literal`** w **`/clr`** kompilacji to stała czasu kompilacji. Jest to natywny odpowiednik zmiennej języka C# [`const`](/dotnet/csharp/language-reference/keywords/const) .

## <a name="all-platforms"></a>Wszystkie platformy

### <a name="remarks"></a>Uwagi

(Nie ma żadnych uwag dla tej funkcji języka, które mają zastosowanie do wszystkich środowisk uruchomieniowych).

## <a name="windows-runtime"></a>Środowisko wykonawcze systemu Windows

### <a name="remarks"></a>Uwagi

(Nie ma żadnych uwag dla tej funkcji języka, które mają zastosowanie tylko do środowisko wykonawcze systemu Windows).

## <a name="common-language-runtime"></a>środowiska uruchomieniowe w trakcie wykonania

## <a name="remarks"></a>Uwagi

Element członkowski danych oznaczony jako **`literal`** musi być zainicjowany, gdy jest zadeklarowany. I, wartość musi być stałą typu całkowitego, wyliczeniem lub ciągiem. Konwersja z typu wyrażenia inicjującego na typ **`literal`** elementu członkowskiego danych nie może wymagać konwersji zdefiniowanej przez użytkownika.

Nie przydzielono pamięci dla **`literal`** pola w czasie wykonywania; kompilator wstawia tylko jego wartość w metadanych dla klasy. **`literal`** Wartość jest traktowana jako stała czasu kompilacji. Najbliższy odpowiednik w standardzie C++ to **`constexpr`** , ale element członkowski danych nie może znajdować się **`constexpr`** w/CLI. C++

Zmienna oznaczona jako **`literal`** inna niż jedna oznaczona **`static const`** . **`static const`** Składowa danych nie jest dostępna w metadanych do innych kompilatorów. Aby uzyskać więcej informacji, zobacz [`static`](../cpp/storage-classes-cpp.md) i [`const`](../cpp/const-cpp.md) .

**`literal`** jest kontekstowym słowem kluczowym. Aby uzyskać więcej informacji, zobacz [kontekstowe słowa kluczowe](context-sensitive-keywords-cpp-component-extensions.md).

## <a name="examples"></a>Przykłady

Ten przykład pokazuje, że **`literal`** zmienna implikuje **`static`** .

```cpp
// mcppv2_literal.cpp
// compile with: /clr
ref struct X {
   literal int i = 4;
};

int main() {
   int value = X::i;
}
```

Poniższy przykład pokazuje efekt **`literal`** w metadanych:

```cpp
// mcppv2_literal2.cpp
// compile with: /clr /LD
public ref struct A {
   literal int lit = 0;
   static const int sc = 1;
};
```

Zwróć uwagę na różnice w metadanych dla `sc` i `lit` : `modopt` dyrektywa jest stosowana do `sc` , co oznacza, że może być ignorowana przez inne kompilatory.

```MSIL
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x00000001)
```

```MSIL
.field public static literal int32 lit = int32(0x00000000)
```

Poniższy przykład, utworzony w języku C#, odwołuje się do metadanych utworzonych w poprzednim przykładzie i przedstawia efekt **`literal`** i **`static const`** zmienne:

```csharp
// mcppv2_literal3.cs
// compile with: /reference:mcppv2_literal2.dll
// A C# program
class B {
   public static void Main() {
      // OK
      System.Console.WriteLine(A.lit);
      System.Console.WriteLine(A.sc);

      // C# does not enforce C++ const
      A.sc = 9;
      System.Console.WriteLine(A.sc);

      // C# enforces const for a literal
      A.lit = 9;   // CS0131

      // you can assign a C++ literal variable to a C# const variable
      const int i = A.lit;
      System.Console.WriteLine(i);

      // but you cannot assign a C++ static const variable
      // to a C# const variable
      const int j = A.sc;   // CS0133
      System.Console.WriteLine(j);
   }
}
```

## <a name="requirements"></a>Wymagania

Opcja kompilatora: `/clr`

## <a name="see-also"></a>Zobacz też

[Rozszerzenia składników dla platform .NET i platformy UWP](component-extensions-for-runtime-platforms.md)
