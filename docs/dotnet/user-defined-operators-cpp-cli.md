---
title: Operatory zdefiniowane przez użytkownika (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined operators under /clr
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
ms.openlocfilehash: ee5aa122983a315e55884c643a9b7894f075e260
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008957"
---
# <a name="user-defined-operators-ccli"></a>Operatory zdefiniowane przez użytkownika (C++/CLI)

Operatory zdefiniowane przez użytkownika dla typów zarządzanych są dozwolone jako statyczne elementy członkowskie lub elementy członkowskie wystąpienia lub w zakresie globalnym. Jednak tylko operatory statyczne są dostępne za pomocą metadanych na klientach, które są zapisywane w języku innym niż Visual C++.

W typie referencyjnym jeden z parametrów statycznego operatora zdefiniowanego przez użytkownika musi mieć jedną z następujących wartości:

- Dojście ( `type` ^) do wystąpienia typu otaczającego.

- Pośredni typ odwołania ( `type` ^& lub typ ^%) do dojścia do wystąpienia typu otaczającego.

W typie wartości jeden z parametrów statycznego operatora zdefiniowanego przez użytkownika musi być jednym z następujących:

- Tego samego typu co typ wartości otaczającej.

- Pośredni typ wskaźnika ( `type` ^) do typu otaczającego.

- Pośredni typ odwołania ( `type` % lub `type`&) do typu otaczającego.

- Pośredniego typu odwołania ( `type` ^% lub `type` ^&) do dojścia.

Można zdefiniować następujące operatory:

|Operator|Formularze jednoargumentowe/binarne?|
|--------------|--------------------------|
|!|Jednoargumentowy|
|!=|Binarne|
|%|Binarne|
|&|Jednoargumentowy i binarny|
|&&|Binarne|
|*|Jednoargumentowy i binarny|
|+|Jednoargumentowy i binarny|
|++|Jednoargumentowy|
|,|Binarne|
|-|Jednoargumentowy i binarny|
|--|Jednoargumentowy|
|->|Jednoargumentowy|
|/|Binarne|
|<|Binarne|
|<<|Binarne|
|\<=|Binarne|
|=|Binarne|
|==|Binarne|
|>|Binarne|
|>=|Binarne|
|>>|Binarne|
|^|Binarne|
|fałsz|Jednoargumentowy|
|true|Jednoargumentowy|
|&#124;|Binarne|
|&#124;&#124;|Binarne|
|~|Jednoargumentowy|

## <a name="example-user-defined-operators"></a>Przykład: zdefiniowane przez użytkownika operatory

```cpp
// mcppv2_user-defined_operators.cpp
// compile with: /clr
using namespace System;
public ref struct X {
   X(int i) : m_i(i) {}
   X() {}

   int m_i;

   // static, binary, user-defined operator
   static X ^ operator + (X^ me, int i) {
      return (gcnew X(me -> m_i + i));
   }

   // instance, binary, user-defined operator
   X^ operator -( int i ) {
      return gcnew X(this->m_i - i);
   }

   // instance, unary, user-defined pre-increment operator
   X^ operator ++() {
      return gcnew X(this->m_i++);
   }

   // instance, unary, user-defined post-increment operator
   X^ operator ++(int i) {
      return gcnew X(this->m_i++);
   }

   // static, unary user-defined pre- and post-increment operator
   static X^ operator-- (X^ me) {
      return (gcnew X(me -> m_i - 1));
   }
};

int main() {
   X ^hX = gcnew X(-5);
   System::Console::WriteLine(hX -> m_i);

   hX = hX + 1;
   System::Console::WriteLine(hX -> m_i);

   hX = hX - (-1);
   System::Console::WriteLine(hX -> m_i);

   ++hX;
   System::Console::WriteLine(hX -> m_i);

   hX++;
   System::Console::WriteLine(hX -> m_i);

   hX--;
   System::Console::WriteLine(hX -> m_i);

   --hX;
   System::Console::WriteLine(hX -> m_i);
}
```

```Output
-5
-4
-3
-2
-1
-2
-3
```

## <a name="example-operator-synthesis"></a>Przykład: synteza operatora

Poniższy przykład demonstruje syntezę operatora, która jest dostępna tylko w przypadku użycia opcji **/CLR** do kompilowania. Synteza operatora tworzy formularz przypisania operatora binarnego, jeśli nie jest on zdefiniowany, gdzie lewa strona operatora przypisania ma typ CLR.

```cpp
// mcppv2_user-defined_operators_2.cpp
// compile with: /clr
ref struct A {
   A(int n) : m_n(n) {};
   static A^ operator + (A^ r1, A^ r2) {
      return gcnew A( r1->m_n + r2->m_n);
   };
   int m_n;
};

int main() {
   A^ a1 = gcnew A(10);
   A^ a2 = gcnew A(20);

   a1 += a2;   // a1 = a1 + a2   += not defined in source
   System::Console::WriteLine(a1->m_n);
}
```

```Output
30
```

## <a name="see-also"></a>Zobacz też

[Klasy i struktury](../extensions/classes-and-structs-cpp-component-extensions.md)
