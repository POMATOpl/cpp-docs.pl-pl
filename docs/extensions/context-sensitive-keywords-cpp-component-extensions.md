---
title: Kontekstowe słowa kluczowe (C + +/ CLI i C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- internal_CPP
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
ms.openlocfilehash: 488a047a51547eff09b519afc453138b2e386e73
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787251"
---
# <a name="context-sensitive-keywords--ccli-and-ccx"></a>Kontekstowe słowa kluczowe (C + +/ CLI i C + +/ CX)

*Kontekstowe słowa kluczowe* są elementami języka, które są rozpoznawane tylko w określonych kontekstach. Poza określonym kontekstem kontekstowe słowo kluczowe może być symbolem zdefiniowanych przez użytkownika.

## <a name="all-runtimes"></a>Wszystkie środowiska wykonawcze

### <a name="remarks"></a>Uwagi

Oto lista kontekstowych słów kluczowych:

- [abstract](abstract-cpp-component-extensions.md)

- [delegate](delegate-cpp-component-extensions.md)

- [event](event-cpp-component-extensions.md)

- [finally](../dotnet/finally.md)

- [for each, in](../dotnet/for-each-in.md)

- [initonly](../dotnet/initonly-cpp-cli.md)

- `internal`

- [literał](literal-cpp-component-extensions.md)

- [override](override-cpp-component-extensions.md)

- [właściwość](property-cpp-component-extensions.md)

- [sealed](sealed-cpp-component-extensions.md)

- `where` (część [ogólne](generics-cpp-component-extensions.md))

Dla potrzeb czytelności warto ograniczyć korzystanie z kontekstowych słów kluczowych jako symboli zdefiniowanych przez użytkownika.

## <a name="windows-runtime"></a>Środowisko wykonawcze systemu Windows

### <a name="remarks"></a>Uwagi

(Nie ma żadnych uwag specyficznych dla platformy, dla tej funkcji).

### <a name="requirements"></a>Wymagania

— Opcja kompilatora: `/ZW`

## <a name="common-language-runtime"></a>środowiska uruchomieniowe w trakcie wykonania

### <a name="remarks"></a>Uwagi

(Nie ma żadnych uwag specyficznych dla platformy, dla tej funkcji).

### <a name="requirements"></a>Wymagania

— Opcja kompilatora: `/clr`

### <a name="examples"></a>Przykłady

Poniższy przykład kodu pokazuje, że w odpowiedniego kontekstu **właściwość** kontekstowe słowo kluczowe może służyć do definiowania właściwości i zmiennej.

```cpp
// context_sensitive_keywords.cpp
// compile with: /clr
public ref class C {
   int MyInt;
public:
   C() : MyInt(99) {}

   property int Property_Block {   // context-sensitive keyword
      int get() { return MyInt; }
   }
};

int main() {
   int property = 0;               // variable name
   C ^ MyC = gcnew C();
   property = MyC->Property_Block;
   System::Console::WriteLine(++property);
}
```

```Output
100
```

## <a name="see-also"></a>Zobacz też

[Rozszerzenia składników dla platformy .NET i platformy uniwersalnej systemu Windows](component-extensions-for-runtime-platforms.md)