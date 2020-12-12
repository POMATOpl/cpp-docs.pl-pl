---
description: 'Dowiedz się więcej o: błąd kompilatora C3385'
title: Błąd kompilatora C3385
ms.date: 11/04/2016
f1_keywords:
- C3385
helpviewer_keywords:
- C3385
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
ms.openlocfilehash: d51659561deb21882532b772455cf1e3636684aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285568"
---
# <a name="compiler-error-c3385"></a>Błąd kompilatora C3385

"Class:: Function": funkcja, która ma niestandardowy atrybut DllImport nie może zwrócić wystąpienia klasy

Funkcja zdefiniowana jako będąca w pliku DLL określonego za pomocą `DllImport` atrybutu nie może zwracać wystąpienia klasy.

Poniższy przykład generuje C3385:

```cpp
// C3385.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

struct SomeStruct1 {};

public ref struct Wrap {
   [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ]
   static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385
};
```
