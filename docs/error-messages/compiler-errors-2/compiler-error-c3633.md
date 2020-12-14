---
description: 'Dowiedz się więcej o: błąd kompilatora C3633'
title: Błąd kompilatora C3633
ms.date: 11/04/2016
f1_keywords:
- C3633
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
ms.openlocfilehash: caf89e2297bb4e9d62be76699b153f013095fa34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239262"
---
# <a name="compiler-error-c3633"></a>Błąd kompilatora C3633

nie można zdefiniować elementu "member" jako składowej typu zarządzanego "

Elementy członkowskie danych klasy referencyjnej CLR nie mogą być typu innego niż C++.  Można utworzyć wystąpienie tylko typu natywnego POD w typie CLR.  Na przykład typ POD nie może zawierać konstruktora kopiującego ani operatora przypisania.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3633.

```cpp
// C3633.cpp
// compile with: /clr /c
#pragma warning( disable : 4368 )

class A1 {
public:
   A1() { II = 0; }
   int II;
};

ref class B {
public:
   A1 a1;   // C3633
   A1 * a2;   // OK
   B() : a2( new A1 ) {}
    ~B() { delete a2; }
};
```
