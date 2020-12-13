---
description: 'Dowiedz się więcej o języku: opakowanie (C++/CLI i C++/CX)'
title: Konwersja boxing  (C++/CLI i C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- boxing, C++
ms.assetid: b5fd2c98-c578-4f83-8257-6dd663478665
ms.openlocfilehash: b3bdc87d9dea2a5a70344ee032655712af221d59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333752"
---
# <a name="boxing--ccli-and-ccx"></a>Konwersja boxing  (C++/CLI i C++/CX)

Konwersja typów wartości do obiektów jest nazywana *opakowaniem*, a Konwersja obiektów na typy wartości jest nazywana *rozpakowywaniem*.

## <a name="all-runtimes"></a>Wszystkie środowiska wykonawcze

(Nie ma żadnych uwag dla tej funkcji języka, które mają zastosowanie do wszystkich środowisk uruchomieniowych).

## <a name="windows-runtime"></a>Środowisko wykonawcze systemu Windows

C++/CX obsługuje składnię skróconą dla typów wartości opakowania i rozpakowywanie typów odwołań. Typ wartości jest opakowany, gdy jest przypisany do zmiennej typu `Object` . `Object`Zmienna jest oddzielona, gdy jest przypisana do zmiennej typu wartości, a nieopakowany typ jest określony w nawiasach, czyli gdy zmienna obiektu jest rzutowana na typ wartości.

```cpp
  Platform::Object^
  object_variable  = value_variable;
value_variable = (value_type) object_variable;
```

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/ZW`

### <a name="examples"></a>Przykłady

Poniższe przykładowe kody i oddzielą pola `DateTime` wartości. Najpierw przykład uzyskuje `DateTime` wartość reprezentującą bieżącą datę i godzinę, a następnie przypisuje ją do `DateTime` zmiennej. Następnie `DateTime` jest opakowany przez przypisanie go do `Object` zmiennej. Na koniec, opakowana wartość jest niezaopakowana, przypisując ją do innej `DateTime` zmiennej.

Aby przetestować przykład, należy utworzyć `BlankApplication` projekt, zastąpić `BlankPage::OnNavigatedTo()` metodę, a następnie określić punkty przerwania w nawiasie zamykającym i przypisanie do zmiennej `str1` . Gdy przykład osiągnie nawias zamykający, należy zapoznać się z tematem `str1` .

```cpp
void BlankPage::OnNavigatedTo(NavigationEventArgs^ e)
{
    using namespace Windows::Globalization::DateTimeFormatting;

    Windows::Foundation::DateTime dt, dtAnother;
    Platform::Object^ obj1;

    Windows::Globalization::Calendar^ c =
        ref new Windows::Globalization::Calendar;
    c->SetToNow();
    dt = c->GetDateTime();
    auto dtf = ref new DateTimeFormatter(
                           YearFormat::Full,
                           MonthFormat::Numeric,
                           DayFormat::Default,
                           DayOfWeekFormat::None);
    String^ str1 = dtf->Format(dt);
    OutputDebugString(str1->Data());
    OutputDebugString(L"\r\n");

    // Box the value type and assign to a reference type.
    obj1 = dt;
    // Unbox the reference type and assign to a value type.
    dtAnother = (Windows::Foundation::DateTime) obj1;

    // Format the DateTime for display.
    String^ str2 = dtf->Format(dtAnother);
    OutputDebugString(str2->Data());
}
```

Aby uzyskać więcej informacji, zobacz [opakowanie (C++/CX)](../cppcx/boxing-c-cx.md).

## <a name="common-language-runtime"></a>środowiska uruchomieniowe w trakcie wykonania

Pola kompilatora mają typ wartości <xref:System.Object> . Jest to możliwe z powodu konwersji zdefiniowanej przez kompilator na konwersję typów wartości na <xref:System.Object> .

Pakowanie i rozpakowywanie Włącz typy wartości, które mają być traktowane jako obiekty. Typy wartości, w tym typy struktury i typy wbudowane, takie jak int, można przekonwertować na typ i z tego typu <xref:System.Object> .

Aby uzyskać więcej informacji, zobacz:

- [Jak jawnie zażądać opakowania](../dotnet/how-to-explicitly-request-boxing.md)

- [Instrukcje: użycie gcnew do tworzenia typów wartości i użycie niejawnego opakowania](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)

- [Instrukcje: Rozpakowywanie](../dotnet/how-to-unbox.md)

- [Konwersje standardowe i niejawny opakowanie](../dotnet/standard-conversions-and-implicit-boxing.md)

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/clr`

### <a name="examples"></a>Przykłady

Poniższy przykład pokazuje, jak działa niejawny opakowanie.

```cpp
// vcmcppv2_explicit_boxing2.cpp
// compile with: /clr
using namespace System;

ref class A {
public:
   void func(System::Object^ o){Console::WriteLine("in A");}
};

value class V {};

interface struct IFace {
   void func();
};

value class V1 : public IFace {
public:
   virtual void func() {
      Console::WriteLine("Interface function");
   }
};

value struct V2 {
   // conversion operator to System::Object
   static operator System::Object^(V2 v2) {
      Console::WriteLine("operator System::Object^");
      return (V2^)v2;
   }
};

void func1(System::Object^){Console::WriteLine("in void func1(System::Object^)");}
void func1(V2^){Console::WriteLine("in func1(V2^)");}

void func2(System::ValueType^){Console::WriteLine("in func2(System::ValueType^)");}
void func2(System::Object^){Console::WriteLine("in func2(System::Object^)");}

int main() {
   // example 1 simple implicit boxing
   Int32^ bi = 1;
   Console::WriteLine(bi);

   // example 2 calling a member with implicit boxing
   Int32 n = 10;
   Console::WriteLine("xx = {0}", n.ToString());

   // example 3 implicit boxing for function calls
   A^ a = gcnew A;
   a->func(n);

   // example 4 implicit boxing for WriteLine function call
   V v;
   Console::WriteLine("Class {0} passed using implicit boxing", v);
   Console::WriteLine("Class {0} passed with forced boxing", (V^)(v));   // force boxing

   // example 5 casting to a base with implicit boxing
   V1 v1;
   IFace ^ iface = v1;
   iface->func();

   // example 6 user-defined conversion preferred over implicit boxing for function-call parameter matching
   V2 v2;
   func1(v2);   // user defined conversion from V2 to System::Object preferred over implicit boxing
                // Will call void func1(System::Object^);

   func2(v2);   // OK: Calls "static V2::operator System::Object^(V2 v2)"
   func2((V2^)v2);   // Using explicit boxing: calls func2(System::ValueType^)
}
```

```Output
1

xx = 10

in A

Class V passed using implicit boxing

Class V passed with forced boxing

Interface function

in func1(V2^)

in func2(System::ValueType^)

in func2(System::ValueType^)
```

## <a name="see-also"></a>Zobacz też

[Rozszerzenia składników dla platform .NET i platformy UWP](component-extensions-for-runtime-platforms.md)
