---
description: 'Dowiedz się więcej na temat słów kluczowych: Context-Sensitive (C++/CLI i C++/CX)'
title: Kontekstowe słowa kluczowe  (C++/CLI i C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- internal_CPP
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
ms.openlocfilehash: 7c005b1a6149f010b9729db5459fa3951bc50521
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176863"
---
# <a name="context-sensitive-keywords--ccli-and-ccx"></a>Kontekstowe słowa kluczowe  (C++/CLI i C++/CX)

*Kontekstowe słowa kluczowe* są elementami języka, które są rozpoznawane tylko w określonych kontekstach. Poza określonym kontekstem, kontekstowe słowo kluczowe może być symbolem zdefiniowanym przez użytkownika.

## <a name="all-runtimes"></a>Wszystkie środowiska wykonawcze

### <a name="remarks"></a>Uwagi

Poniżej znajduje się lista kontekstowych słów kluczowych:

- [streszczeń](abstract-cpp-component-extensions.md)

- [Wierz](delegate-cpp-component-extensions.md)

- [wydarzen](event-cpp-component-extensions.md)

- [finally](../dotnet/finally.md)

- [for each, in](../dotnet/for-each-in.md)

- [initonly](../dotnet/initonly-cpp-cli.md)

- `internal`

- [wpisać](literal-cpp-component-extensions.md)

- [override](override-cpp-component-extensions.md)

- [wartość](property-cpp-component-extensions.md)

- [sealed](sealed-cpp-component-extensions.md)

- `where` (część [rodzajów](generics-cpp-component-extensions.md))

Na potrzeby czytelności można ograniczyć użycie słów kluczowych kontekstowych jako symboli zdefiniowanych przez użytkownika.

## <a name="windows-runtime"></a>Środowisko wykonawcze systemu Windows

### <a name="remarks"></a>Uwagi

(Nie ma żadnych uwag specyficznych dla platformy dla tej funkcji).

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/ZW`

## <a name="common-language-runtime"></a>środowiska uruchomieniowe w trakcie wykonania

### <a name="remarks"></a>Uwagi

(Nie ma żadnych uwag specyficznych dla platformy dla tej funkcji).

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/clr`

### <a name="examples"></a>Przykłady

Poniższy przykład kodu pokazuje, że w odpowiednim kontekście **`property`** słowo kluczowe kontekstowe może służyć do definiowania właściwości i zmiennej.

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

[Rozszerzenia składników dla platform .NET i platformy UWP](component-extensions-for-runtime-platforms.md)
