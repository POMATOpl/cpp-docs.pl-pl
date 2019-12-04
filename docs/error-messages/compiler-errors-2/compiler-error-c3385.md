---
title: Błąd kompilatora C3385
ms.date: 11/04/2016
f1_keywords:
- C3385
helpviewer_keywords:
- C3385
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
ms.openlocfilehash: 18cdc09a209c072036154cd610684b94addfae49
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751862"
---
# <a name="compiler-error-c3385"></a>Błąd kompilatora C3385

"Class:: Function": funkcja, która ma niestandardowy atrybut DllImport nie może zwrócić wystąpienia klasy

Funkcja zdefiniowana jako będąca w pliku DLL określonego przy użyciu atrybutu `DllImport` nie może zwrócić wystąpienia klasy.

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
