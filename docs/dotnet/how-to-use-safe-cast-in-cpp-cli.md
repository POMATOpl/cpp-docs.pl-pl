---
description: 'Dowiedz się więcej na temat: jak używać safe_cast w języku C++/CLI'
title: 'Instrukcje: Korzystanie z polecenia safe_cast w języku C++/interfejsie wiersza polecenia'
ms.date: 11/04/2016
helpviewer_keywords:
- safe_cast keyword [C++], upcasting
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
ms.openlocfilehash: f921371f97f967f9517121aaa163f79769781211
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145577"
---
# <a name="how-to-use-safe_cast-in-ccli"></a>Instrukcje: Korzystanie z polecenia safe_cast w języku C++/interfejsie wiersza polecenia

W tym artykule pokazano, jak używać safe_cast w aplikacjach C++/CLI. Aby uzyskać informacje na temat safe_cast w języku C++/CX, zobacz [safe_cast](../extensions/safe-cast-cpp-component-extensions.md).

## <a name="upcasting"></a>Rzutowanie

Rzutowanie jest rzutowane z typu pochodnego do jednej z jej klas podstawowych. To Rzutowanie jest bezpieczne i nie wymaga jawnego zapisu rzutowania. Poniższy przykład pokazuje, jak wykonać rzutowanie, z `safe_cast` i bez niego.

```cpp
// safe_upcast.cpp
// compile with: /clr
using namespace System;
interface class A {
   void Test();
};

ref struct B : public A {
   virtual void Test() {
      Console::WriteLine("in B::Test");
   }

   void Test2() {
      Console::WriteLine("in B::Test2");
   }
};

ref struct C : public B {
   virtual void Test() override {
      Console::WriteLine("in C::Test");
   };
};

int main() {
   C ^ c = gcnew C;

   // implicit upcast
   B ^ b = c;
   b->Test();
   b->Test2();

   // upcast with safe_cast
   b = nullptr;
   b = safe_cast<B^>(c);
   b->Test();
   b->Test2();
}
```

```Output
in C::Test
in B::Test2
in C::Test
in B::Test2
```

## <a name="downcasting"></a>Rzutowanie

Downcast to rzutowanie z klasy bazowej na klasę, która jest pochodną klasy bazowej.  Downcast jest bezpieczny tylko wtedy, gdy obiekt, który jest w trakcie wykonywania, faktycznie odnosi się do obiektu klasy pochodnej.  W przeciwieństwie do **`static_cast`** , `safe_cast` wykonuje dynamiczne sprawdzanie i zgłasza <xref:System.InvalidCastException> , jeśli konwersja nie powiedzie się.

```cpp
// safe_downcast.cpp
// compile with: /clr
using namespace System;

interface class A { void Test(); };

ref struct B : public A {
   virtual void Test() {
      Console::WriteLine("in B::Test()");
   }

   void Test2() {
      Console::WriteLine("in B::Test2()");
   }
};

ref struct C : public B {
   virtual void Test() override {
      Console::WriteLine("in C::Test()");
   }
};

interface class I {};

value struct V : public I {};

int main() {
   A^ a = gcnew C();
   a->Test();
   B^ b = safe_cast<B^>(a);
   b->Test();
   b->Test2();

   V v;
   I^ i = v;   // i boxes V
   V^ refv = safe_cast<V^>(i);

   Object^ o = gcnew B;
   A^ a2= safe_cast<A^>(o);
}
```

```Output
in C::Test()
in C::Test()
in B::Test2()
```

## <a name="safe_cast-with-user-defined-conversions"></a>safe_cast ze zdefiniowanymi przez użytkownika konwersjemi

Następny przykład pokazuje, jak można użyć `safe_cast` do wywołania konwersji zdefiniowanych przez użytkownika.

```cpp
// safe_cast_udc.cpp
// compile with: /clr
using namespace System;
value struct V;

ref struct R {
   int x;
   R() {
      x = 1;
   }

   R(int argx) {
      x = argx;
   }

   static operator R::V^(R^ r);
};

value struct V {
   int x;
   static operator R^(V& v) {
      Console::WriteLine("in operator R^(V& v)");
      R^ r = gcnew R();
      r->x = v.x;
      return r;
   }

   V(int argx) {
      x = argx;
   }
};

   R::operator V^(R^ r) {
      Console::WriteLine("in operator V^(R^ r)");
      return gcnew V(r->x);
   }

int main() {
   bool fReturnVal = false;
   V v(2);
   R^ r = safe_cast<R^>(v);   // should invoke UDC
   V^ v2 = safe_cast<V^>(r);   // should invoke UDC
}
```

```Output
in operator R^(V& v
in operator V^(R^ r)
```

## <a name="safe_cast-and-boxing-operations"></a>safe_cast i pakowanie operacji

### <a name="boxing"></a>Boxing

Opakowanie jest zdefiniowane jako konwersja, zdefiniowana przez użytkownika.  W związku z tym można użyć `safe_cast` do pola wartości na stercie CLR.

Poniższy przykład pokazuje opakowanie z prostymi i zdefiniowanymi przez użytkownika typami wartości.  `safe_cast`Ramki typu wartość zmienna, która znajduje się na stosie macierzystym, dzięki czemu może być przypisana do zmiennej na stosie zebranych elementów bezużytecznych.

```cpp
// safe_cast_boxing.cpp
// compile with: /clr
using namespace System;

interface struct I {};

value struct V : public I {
   int m_x;

   V(int i) : m_x(i) {}
};

int main() {
   // box a value type
   V v(100);
   I^ i = safe_cast<I^>(v);

   int x = 100;
   V^ refv = safe_cast<V^>(v);
   int^ refi = safe_cast<int^>(x);
}
```

Następny przykład pokazuje, że opakowanie ma priorytet nad konwersją zdefiniowaną przez użytkownika w `safe_cast` operacji.

```cpp
// safe_cast_boxing_2.cpp
// compile with: /clr
static bool fRetval = true;

interface struct I {};
value struct V : public I {
   int x;

   V(int argx) {
      x = argx;
   }

   static operator I^(V v) {
      fRetval = false;
      I^ pi = v;
      return pi;
   }
};

ref struct R {
   R() {}
   R(V^ pv) {}
};

int main() {
   V v(10);
   I^ pv = safe_cast<I^>(v);   // boxing will occur, not UDC "operator I^"
}
```

### <a name="unboxing"></a>Rozpakowywanie

Rozpakowywanie jest zdefiniowane jako iniekcja zdefiniowana przez użytkownika przez kompilator.  W związku z tym, można użyć `safe_cast` do Unbox wartości na stercie CLR.

Rozpakowywanie jest konwersją zdefiniowaną przez użytkownika, ale w przeciwieństwie do opakowania, rozpakowywanie musi być jawne — to znaczy, że musi być wykonywane przez **`static_cast`** Rzutowanie w stylu C lub `safe_cast` nie można wykonać odpakowania niejawnie.

```cpp
// safe_cast_unboxing.cpp
// compile with: /clr
int main() {
   System::Object ^ o = 42;
   int x = safe_cast<int>(o);
}
```

Poniższy przykład pokazuje rozpakowywanie z typami wartości i typami pierwotnymi.

```cpp
// safe_cast_unboxing_2.cpp
// compile with: /clr
using namespace System;

interface struct I {};

value struct VI : public I {};

void test1() {
   Object^ o = 5;
   int x = safe_cast<Int32>(o);
}

value struct V {
   int x;
   String^ s;
};

void test2() {
   V localv;
   Object^ o = localv;
   V unboxv = safe_cast<V>(o);
}

void test3() {
   V localv;
   V^ o2 = localv;
   V unboxv2 = safe_cast<V>(o2);
}

void test4() {
   I^ refi = VI();
   VI vi  = safe_cast<VI>(refi);
}

int main() {
   test1();
   test2();
   test3();
   test4();
}
```

## <a name="safe_cast-and-generic-types"></a>safe_cast i typy ogólne

Następny przykład pokazuje, jak można użyć `safe_cast` do wykonywania downcast z typem ogólnym.

```cpp
// safe_cast_generic_types.cpp
// compile with: /clr
interface struct I {};

generic<class T> where T:I
ref struct Base {
   T t;
   void test1() {}
};

generic<class T> where T:I
ref struct Derived:public Base <T> {};

ref struct R:public I {};

typedef Base<R^> GBase_R;
typedef Derived<R^> GDerived_R;

int main() {
   GBase_R^ br = gcnew GDerived_R();
   GDerived_R^ dr = safe_cast<GDerived_R^>(br);
}
```

## <a name="see-also"></a>Zobacz też

[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)
