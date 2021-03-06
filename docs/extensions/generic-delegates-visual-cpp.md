---
description: 'Dowiedz się więcej o: delegatów ogólnych (C++/CLI)'
title: Delegaty ogólne (C++/CLI)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- generic delegates
- delegates, generic [C++]
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
ms.openlocfilehash: c3ce8f27d0a16d84774f3eeafbd5668384e3cf17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301753"
---
# <a name="generic-delegates-ccli"></a>Delegaty ogólne (C++/CLI)

Parametry typu ogólnego można użyć z delegatami. Aby uzyskać więcej informacji na temat delegatów, zobacz [Delegat (C++/CLI i c++/CX)](delegate-cpp-component-extensions.md).

## <a name="syntax"></a>Składnia

```cpp
[attributes]
generic < [class | typename] type-parameter-identifiers>
[type-parameter-constraints-clauses]
[accessibility-modifiers] delegate result-type identifier
([formal-parameters]);
```

### <a name="parameters"></a>Parametry

*Attributes*<br/>
Obowiązkowe Dodatkowe informacje deklaratywne. Aby uzyskać więcej informacji na temat atrybutów i klas atrybutów, zobacz atrybuty.

*identyfikatory parametrów typu*<br/>
Rozdzielana przecinkami lista identyfikatorów parametrów typu.

*ograniczenia parametrów typu-Parameter-klauzule*<br/>
Przyjmuje formularz określony w [ograniczeniach dla parametrów typu ogólnego (C++/CLI)](constraints-on-generic-type-parameters-cpp-cli.md)

*ułatwienia dostępu — Modyfikatory*<br/>
Obowiązkowe Modyfikatory dostępności (np. **`public`** **`private`** ).

*Typ wyniku*<br/>
Zwracany typ delegata.

*identyfikatora*<br/>
Nazwa delegata.

*parametry formalne*<br/>
Obowiązkowe Lista parametrów delegata.

## <a name="examples"></a>Przykłady

Parametry typu delegata są określone w punkcie, w którym jest tworzony obiekt delegowany. Obiekt delegowany i skojarzona z nim Metoda musi mieć taki sam podpis. Poniżej znajduje się przykład ogólnej deklaracji delegata.

```cpp
// generics_generic_delegate1.cpp
// compile with: /clr /c
generic <class ItemType>
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);
```

Poniższy przykład pokazuje, że

- Nie można użyć tego samego obiektu delegowanego z różnymi skonstruowanymi typami. Utwórz różne obiekty delegatów dla różnych typów.

- Delegat generyczny może być skojarzony z metodą rodzajową.

- Gdy metoda ogólna jest wywoływana bez określenia argumentów typu, kompilator próbuje wywnioskować argumenty typu dla wywołania.

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

Poniższy przykład deklaruje delegata ogólnego `GenDelegate<ItemType>` , a następnie tworzy wystąpienie go przez skojarzenie go z metodą `MyMethod` , która używa parametru typu `ItemType` . Tworzone i wywoływane są dwa wystąpienia delegata (liczba całkowita i podwójna).

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
