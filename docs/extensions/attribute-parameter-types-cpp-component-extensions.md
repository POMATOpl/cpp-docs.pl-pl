---
description: Dowiedz się więcej na temat typów parametrów atrybutu (C++/CLI i C++/CX)
title: Typy parametrów atrybutu  (C++/CLI i C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- custom attributes, parameter types
ms.assetid: d9f127a3-7f08-456f-acc6-256805632712
ms.openlocfilehash: 7f2d5dd2def4e61d5b2b0406cc193bf818bc3d9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177097"
---
# <a name="attribute-parameter-types--ccli-and-ccx"></a>Typy parametrów atrybutu  (C++/CLI i C++/CX)

Wartości przesyłane do atrybutów muszą być znane kompilatorowi w czasie kompilacji.  Parametry atrybutu mogą być następujące:

- **`bool`**

- **`char`**, **`unsigned char`**

- **`short`**, **`unsigned short`**

- **`int`**, **`unsigned int`**

- **`long`**, **`unsigned long`**

- **`__int64`**, **niepodpisane __int64**

- **`float`**, **`double`**

- **`wchar_t`**

- **`char*`** lub `wchar_t*` lub `System::String*`

- `System::Type ^`

- `System::Object ^`

- **`enum`**

## <a name="example-attribute-parameter-types"></a>Przykład: typy parametrów atrybutów

### <a name="code"></a>Kod

```cpp
// attribute_parameter_types.cpp
// compile with: /clr /c
using namespace System;
ref struct AStruct {};

[AttributeUsage(AttributeTargets::ReturnValue)]
ref struct Attr : public Attribute {
   Attr(AStruct ^ i){}
   Attr(bool i){}
   Attr(){}
};

ref struct MyStruct {
   static AStruct ^ x = gcnew AStruct;
   [returnvalue:Attr(x)] int Test() { return 0; }   // C3104
   [returnvalue:Attr] int Test2() { return 0; }   // OK
   [returnvalue:Attr(true)] int Test3() { return 0; }   // OK
};
```

## <a name="example-unnamed-arguments-precede-named-arguments"></a>Przykład: argumenty nienazwane poprzedzające nazwane argumenty

### <a name="description"></a>Opis

Podczas określania atrybutów wszystkie argumenty nienazwane (pozycyjne) muszą poprzedzać nazwane argumenty.

### <a name="code"></a>Kod

```cpp
// extending_metadata_c.cpp
// compile with: /clr /c
using namespace System;
[AttributeUsage(AttributeTargets::Class)]
ref class MyAttr : public Attribute {
public:
   MyAttr() {}
   MyAttr(int i) {}
   property int Priority;
   property int Version;
};

[MyAttr]
ref class ClassA {};   // No arguments

[MyAttr(Priority = 1)]
ref class ClassB {};   // Named argument

[MyAttr(123)]
ref class ClassC {};   // Positional argument

[MyAttr(123, Version = 1)]
ref class ClassD {};   // Positional and named
```

## <a name="example-one-dimensional-array-attribute-parameter"></a>Przykład: jednowymiarowy parametr atrybutu tablicy

### <a name="description"></a>Opis

Parametry atrybutu mogą być jednowymiarowymi tablicami poprzednich typów.

### <a name="code"></a>Kod

```cpp
// extending_metadata_d.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::Class)]
public ref struct ABC : public Attribute {
   ABC(array<int>^){}
   array<double> ^ param;
};

[ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]
ref struct AStruct{};
```

## <a name="see-also"></a>Zobacz też

[Atrybuty zdefiniowane przez użytkownika](user-defined-attributes-cpp-component-extensions.md)
