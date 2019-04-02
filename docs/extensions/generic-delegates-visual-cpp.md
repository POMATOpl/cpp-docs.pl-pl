---
title: Delegaty ogólne (C + +/ CLI)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- generic delegates
- delegates, generic [C++]
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
ms.openlocfilehash: 1152656156a2f1002167fd83762f2d9a33342c49
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787263"
---
# <a name="generic-delegates-ccli"></a>Delegaty ogólne (C + +/ CLI)

Można używać parametrów typu ogólnego, przy użyciu delegatów. Aby uzyskać więcej informacji na temat obiektów delegowanych, zobacz [delegowania (C + +/ CLI i C + +/ CX)](delegate-cpp-component-extensions.md).

## <a name="syntax"></a>Składnia

```cpp
[attributes]
generic < [class | typename] type-parameter-identifiers>
[type-parameter-constraints-clauses]
[accessibility-modifiers] delegate result-type identifier
([formal-parameters]);
```

### <a name="parameters"></a>Parametry

*Atrybuty*<br/>
(Opcjonalnie) Dodatkowe informacje deklaratywnego. Aby uzyskać więcej informacji o atrybuty i klasy atrybutów Zobacz atrybutów.

*Typ — parametr-identyfikatory*<br/>
Rozdzielana przecinkami lista identyfikatorów dla parametrów typu.

*type-parameter-constraints-clauses*<br/>
Ma postać określone w [ograniczenia dotyczące parametrów typu ogólnego (C + +/ CLI)](constraints-on-generic-type-parameters-cpp-cli.md)

*accessibility-modifiers*<br/>
(Opcjonalnie) Modyfikatory dostępności (np. **publicznych**, **prywatnej**).

*result-type*<br/>
Zwracany typ delegata.

*Identyfikator*<br/>
Nazwa obiektu delegowanego.

*parametrów formalnych*<br/>
(Opcjonalnie) Lista parametrów delegata.

## <a name="example"></a>Przykład

Parametry typu delegata są określone w punkcie, w którym tworzony jest obiekt delegowany. Delegat i skojarzona metoda musi mieć taki sam podpis. Oto przykład deklaracja delegata ogólnego.

```cpp
// generics_generic_delegate1.cpp
// compile with: /clr /c
generic <class ItemType>
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);
```

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, że

- Nie można użyć tego samego obiektu delegowanego z różnymi typami skonstruowany. Utwórz delegata różnych obiektów dla różnych typów.

- Delegat ogólny może być skojarzony z metody rodzajowej.

- Po wywołaniu metody ogólnej bez określania argumentów typu kompilator próbuje wywnioskować argumentów typu na wywołanie.

```cpp
// generics_generic_delegate2.cpp
// compile with: /clr
generic <class ItemType>
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);

generic <class ItemType>
ref struct MyGenClass {
   ItemType MyMethod(ItemType i, ItemType % j) {
      return ItemType();
   }
};

ref struct MyClass {
   generic <class ItemType>
   static ItemType MyStaticMethod(ItemType i, ItemType % j) {
      return ItemType();
   }
};

int main() {
   MyGenClass<int> ^ myObj1 = gcnew MyGenClass<int>();
   MyGenClass<double> ^ myObj2 = gcnew MyGenClass<double>();
   GenDelegate<int>^ myDelegate1 =
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);

   GenDelegate<double>^ myDelegate2 =
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);

   GenDelegate<int>^ myDelegate =
      gcnew GenDelegate<int>(&MyClass::MyStaticMethod<int>);
}
```

## <a name="example"></a>Przykład

Poniższy przykład deklaruje Delegat ogólny `GenDelegate<ItemType>`, a następnie tworzy wystąpienie przez skojarzenie jej z metodą `MyMethod` używającą parametrów typu `ItemType`. Dwa wystąpienia delegata (całkowitą i wartość o podwójnej precyzji) są tworzone i wywołana.

```cpp
// generics_generic_delegate.cpp
// compile with: /clr
using namespace System;

// declare generic delegate
generic <typename ItemType>
delegate ItemType GenDelegate (ItemType p1, ItemType% p2);

// Declare a generic class:
generic <typename ItemType>
ref class MyGenClass {
public:
   ItemType MyMethod(ItemType p1, ItemType% p2) {
      p2 = p1;
      return p1;
    }
};

int main() {
   int i = 0, j = 0;
   double m = 0.0, n = 0.0;

   MyGenClass<int>^ myObj1 = gcnew MyGenClass<int>();
   MyGenClass<double>^ myObj2 = gcnew MyGenClass<double>();

   // Instantiate a delegate using int.
   GenDelegate<int>^ MyDelegate1 =
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);

   // Invoke the integer delegate using MyMethod.
   i = MyDelegate1(123, j);

   Console::WriteLine(
      "Invoking the integer delegate: i = {0}, j = {1}", i, j);

   // Instantiate a delegate using double.
   GenDelegate<double>^ MyDelegate2 =
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);

   // Invoke the integer delegate using MyMethod.
   m = MyDelegate2(0.123, n);

   Console::WriteLine(
      "Invoking the double delegate: m = {0}, n = {1}", m, n);
}
```

```Output
Invoking the integer delegate: i = 123, j = 123
Invoking the double delegate: m = 0.123, n = 0.123
```

## <a name="see-also"></a>Zobacz też

[Typy ogólne](generics-cpp-component-extensions.md)