---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4945'
title: Ostrzeżenie kompilatora (poziom 1) C4945
ms.date: 11/04/2016
f1_keywords:
- C4945
helpviewer_keywords:
- C4945
ms.assetid: 6d2079ea-dc59-4611-bc68-9a22c06f7587
ms.openlocfilehash: df05b0882b672f22428e9ddef0b195043cca7d2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327992"
---
# <a name="compiler-warning-level-1-c4945"></a>Ostrzeżenie kompilatora (poziom 1) C4945

"symbol": nie można zaimportować symbolu z "Assembly2": ponieważ "symbol" został już zaimportowany z innego zestawu "assembly1"

Symbol został zaimportowany z przywoływanego zestawu, ale ten symbol został już zaimportowany z innego zestawu, do którego się odwołuje. Nie należy odwoływać się do jednego z zestawów lub uzyskać zmiany nazwy symbolu w jednym z zestawów.

Poniższe przykłady generują C4945.

```csharp
// C4945a.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

a następnie

```csharp
// C4945b.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

a następnie

```cpp
// C4945c.cpp
// compile with: /clr /LD /W1
#using "C4945a.dll"
#using "C4945b.dll"   // C4945
```
