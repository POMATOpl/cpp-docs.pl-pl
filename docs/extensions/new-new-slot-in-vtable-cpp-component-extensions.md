---
description: 'Dowiedz się więcej na temat: New (nowe miejsce w tabeli metod wirtualnych) (C++/CLI i C++/CX)'
title: new (nowe gniazdo w vtable)  (C++/CLI i C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
ms.openlocfilehash: ccc6adbd29eca82b44d34b981803a88332a8784a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257681"
---
# <a name="new-new-slot-in-vtable--ccli-and-ccx"></a>new (nowe gniazdo w vtable)  (C++/CLI i C++/CX)

**`new`** Słowo kluczowe wskazuje, że wirtualny element członkowski otrzyma nowe miejsce w tabeli metod wirtualnych.

## <a name="all-runtimes"></a>Wszystkie środowiska wykonawcze

(Nie ma żadnych uwag dla tej funkcji języka, które mają zastosowanie do wszystkich środowisk uruchomieniowych).

## <a name="windows-runtime"></a>Środowisko wykonawcze systemu Windows

Nieobsługiwane w środowisko wykonawcze systemu Windows.

## <a name="common-language-runtime"></a>środowiska uruchomieniowe w trakcie wykonania

### <a name="remarks"></a>Uwagi

W `/clr` kompilacji wskazuje, **`new`** że wirtualny element członkowski będzie miał nowe miejsce w tabeli metod wirtualnych, że funkcja nie przesłania metody klasy bazowej.

**`new`** powoduje, że modyfikator NewSlot ma zostać dodany do IL dla funkcji.  Aby uzyskać więcej informacji na temat NewSlot, zobacz:

- <xref:System.Reflection.MethodInfo.GetBaseDefinition?displayProperty=nameWithType>

- <xref:System.Reflection.MethodAttributes?displayProperty=nameWithType>

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/clr`

### <a name="examples"></a>Przykłady

Poniższy przykład pokazuje efekt **`new`** .

```cpp
// newslot.cpp
// compile with: /clr
ref class C {
public:
   virtual void f() {
      System::Console::WriteLine("C::f() called");
   }

   virtual void g() {
      System::Console::WriteLine("C::g() called");
   }
};

ref class D : public C {
public:
   virtual void f() new {
      System::Console::WriteLine("D::f() called");
   }

   virtual void g() override {
      System::Console::WriteLine("D::g() called");
   }
};

ref class E : public D {
public:
   virtual void f() override {
      System::Console::WriteLine("E::f() called");
   }
};

int main() {
   D^ d = gcnew D;
   C^ c = gcnew D;

   c->f();   // calls C::f
   d->f();   // calls D::f

   c->g();   // calls D::g
   d->g();   // calls D::g

   D ^ e = gcnew E;
   e->f();   // calls E::f
}
```

```Output
C::f() called

D::f() called

D::g() called

D::g() called

E::f() called
```

## <a name="see-also"></a>Zobacz też

[Rozszerzenia składników dla platform .NET i platformy UWP](component-extensions-for-runtime-platforms.md)<br/>
[Specyfikatory przesłonięcia](override-specifiers-cpp-component-extensions.md)
