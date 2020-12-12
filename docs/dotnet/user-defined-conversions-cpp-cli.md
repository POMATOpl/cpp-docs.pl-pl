---
description: 'Dowiedz się więcej o: konwersje User-Defined (C++/CLI)'
title: Konwersje zdefiniowane przez użytkownika (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined conversions [C++]
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
ms.openlocfilehash: 0b07ab3201bfd379a17922f020486d0b17a59558
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204267"
---
# <a name="user-defined-conversions-ccli"></a>Konwersje zdefiniowane przez użytkownika (C++/CLI)

W tej sekcji omówiono konwersje zdefiniowane przez użytkownika (UDC), gdy jeden z typów w konwersji jest odwołaniem lub wystąpieniem typu wartości lub typu odwołania.

## <a name="implicit-and-explicit-conversions"></a>Konwersje niejawne i jawne

Zdefiniowana przez użytkownika konwersja może być niejawna lub jawna.  Element UDC powinien być niejawny, jeśli konwersja nie powoduje utraty informacji. W przeciwnym razie należy zdefiniować jawne UDC.

Konstruktor klasy natywnej może służyć do konwersji typu odwołania lub wartości na klasę natywną.

Aby uzyskać więcej informacji na temat konwersji, zobacz [przepakowywanie](../extensions/boxing-cpp-component-extensions.md) i [standardowe konwersje](../cpp/standard-conversions.md).

```cpp
// mcpp_User_Defined_Conversions.cpp
// compile with: /clr
#include "stdio.h"
ref class R;
class N;

value class V {
   static operator V(R^) {
      return V();
   }
};

ref class R {
public:
   static operator N(R^);
   static operator V(R^) {
      System::Console::WriteLine("in R::operator N");
      return V();
   }
};

class N {
public:
   N(R^) {
      printf("in N::N\n");
   }
};

R::operator N(R^) {
   System::Console::WriteLine("in R::operator N");
   return N(nullptr);
}

int main() {
   // Direct initialization:
   R ^r2;
   N n2(r2);   // direct initialization, calls constructor
   static_cast<N>(r2);   // also direct initialization

   R ^r3;
   // ambiguous V::operator V(R^) and R::operator V(R^)
   // static_cast<V>(r3);
}
```

**Dane wyjściowe**

```Output
in N::N
in N::N
```

## <a name="convert-from-operators"></a>Konwersja z operatorów

Operatory Convert-from tworzą obiekt klasy, w której operator jest zdefiniowany na podstawie obiektu innej klasy.

Standard C++ nie obsługuje operatorów Convert-from; w tym celu w standardzie C++ są stosowane konstruktory. Jednak w przypadku używania typów CLR Visual C++ zapewnia obsługę składni dla wywoływania operatorów Convert-from.

Aby dobrze współdziałać z innymi językami zgodnymi ze specyfikacją CLS, warto otoczyć każdy zdefiniowany przez użytkownika Konstruktor jednoargumentowy dla danej klasy z odpowiednim operatorem konwersji.

Operatory konwersji z:

- Muszą być zdefiniowane jako funkcje statyczne.

- Może być niejawny (w przypadku konwersji, które nie tracą precyzji, takiej jak Short-to-int) lub Explicit, w przypadku utraty dokładności.

- Zwraca obiekt klasy zawierającej.

- Ma typ "od" jako jedyny typ parametru.

Poniższy przykład pokazuje niejawny i jawny operator "Convert-from", konwersja zdefiniowana przez użytkownika (UDC).

```cpp
// clr_udc_convert_from.cpp
// compile with: /clr
value struct MyDouble {
   double d;

   MyDouble(int i) {
      d = static_cast<double>(i);
      System::Console::WriteLine("in constructor");
   }

   // Wrap the constructor with a convert-from operator.
   // implicit UDC because conversion cannot lose precision
   static operator MyDouble (int i) {
      System::Console::WriteLine("in operator");
      // call the constructor
      MyDouble d(i);
      return d;
   }

   // an explicit user-defined conversion operator
   static explicit operator signed short int (MyDouble) {
      return 1;
   }
};

int main() {
   int i = 10;
   MyDouble md = i;
   System::Console::WriteLine(md.d);

   // using explicit user-defined conversion operator requires a cast
   unsigned short int j = static_cast<unsigned short int>(md);
   System::Console::WriteLine(j);
}
```

**Dane wyjściowe**

```Output
in operator
in constructor
10
1
```

## <a name="convert-to-operators"></a>Operatory konwersji do

Operatory Konwertuj-do konwertują obiekt klasy, w której operator jest zdefiniowany dla innego obiektu. Poniższy przykład pokazuje niejawny operator konwersji zdefiniowany przez użytkownika:

```cpp
// clr_udc_convert_to.cpp
// compile with: /clr
using namespace System;
value struct MyInt {
   Int32 i;

   // convert MyInt to String^
   static operator String^ ( MyInt val ) {
      return val.i.ToString();
   }

   MyInt(int _i) : i(_i) {}
};

int main() {
   MyInt mi(10);
   String ^s = mi;
   Console::WriteLine(s);
}
```

**Dane wyjściowe**

```Output
10
```

Zdefiniowany przez użytkownika Operator konwersji na konwersję jest odpowiedni dla konwersji, które w jakiś sposób mogą utracić dane. Aby wywołać jawny Operator konwersji, należy użyć rzutowania.

```cpp
// clr_udc_convert_to_2.cpp
// compile with: /clr
value struct MyDouble {
   double d;
   // convert MyDouble to Int32
   static explicit operator System::Int32 ( MyDouble val ) {
      return (int)val.d;
   }
};

int main() {
   MyDouble d;
   d.d = 10.3;
   System::Console::WriteLine(d.d);
   int i = 0;
   i = static_cast<int>(d);
   System::Console::WriteLine(i);
}
```

**Dane wyjściowe**

```Output
10.3
10
```

## <a name="to-convert-generic-classes"></a>Aby skonwertować klasy ogólne

Klasy generycznej można przekonwertować na T.

```cpp
// clr_udc_generics.cpp
// compile with: /clr
generic<class T>
public value struct V {
   T mem;
   static operator T(V v) {
      return v.mem;
   }

   void f(T t) {
      mem = t;
   }
};

int main() {
   V<int> v;
   v.f(42);
   int i = v;
   i += v;
   System::Console::WriteLine(i == (42 * 2) );
}
```

**Dane wyjściowe**

```Output
True
```

Konstruktor konwersji przyjmuje typ i używa go do utworzenia obiektu.  Konstruktor konwertowany jest wywoływany tylko z bezpośrednią inicjalizacją; rzutowania nie wywoła konwersji konstruktorów. Domyślnie konwersja konstruktorów jest jawna dla typów CLR.

```cpp
// clr_udc_converting_constructors.cpp
// compile with: /clr
public ref struct R {
   int m;
   char c;

   R(int i) : m(i) { }
   R(char j) : c(j) { }
};

public value struct V {
   R^ ptr;
   int m;

   V(R^ r) : ptr(r) { }
   V(int i) : m(i) { }
};

int main() {
   R^ r = gcnew R(5);

   System::Console::WriteLine( V(5).m);
   System::Console::WriteLine( V(r).ptr);
}
```

**Dane wyjściowe**

```Output
5
R
```

W tym przykładzie kodu niejawna funkcja konwersji statycznej jest taka sama jak jawny Konstruktor konwersji.

```
public value struct V {
   int m;
   V(int i) : m(i) {}
   static operator V(int i) {
      V v(i*100);
      return v;
   }
};

public ref struct R {
   int m;
   R(int i) : m(i) {}
   static operator R^(int i) {
      return gcnew R(i*100);
   }
};

int main() {
   V v(13);   // explicit
   R^ r = gcnew R(12);   // explicit

   System::Console::WriteLine(v.m);
   System::Console::WriteLine(r->m);

   // explicit ctor can't be called here: not ambiguous
   v = 5;
   r = 20;

   System::Console::WriteLine(v.m);
   System::Console::WriteLine(r->m);
}
```

**Dane wyjściowe**

```Output
13
12
500
2000
```

## <a name="see-also"></a>Zobacz też

[Klasy i struktury](../extensions/classes-and-structs-cpp-component-extensions.md)
