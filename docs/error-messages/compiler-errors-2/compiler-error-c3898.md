---
title: Błąd kompilatora C3898
ms.date: 11/04/2016
f1_keywords:
- C3898
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
ms.openlocfilehash: e7d1ce25e13e1b601c4abc85e71db484f7b3f822
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221032"
---
# <a name="compiler-error-c3898"></a>Błąd kompilatora C3898

"var": typy składowe danych mogą być tylko składowymi typów zarządzanych

Element członkowski danych [initonly](../../dotnet/initonly-cpp-cli.md) został zadeklarowany w klasie natywnej.  **`initonly`** Element członkowski danych może być zadeklarowany tylko w klasie CLR.

Poniższy przykład generuje C3898:

```cpp
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

Możliwe rozwiązanie:

```cpp
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```
