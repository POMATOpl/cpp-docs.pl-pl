---
title: Błąd kompilatora C3183
ms.date: 11/04/2016
f1_keywords:
- C3183
helpviewer_keywords:
- C3183
ms.assetid: dbd0f020-c739-43c9-947e-9ce21537331b
ms.openlocfilehash: ff48c9a084049efe5520e39a269be5c2abcd40a6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761650"
---
# <a name="compiler-error-c3183"></a>Błąd kompilatora C3183

nie można zdefiniować nienazwanej klasy, struktury lub związku w obrębie typu zarządzanego lub typu WinRT

Typ osadzony w typie zarządzanym lub WinRT musi mieć nazwę.

Poniższy przykład generuje C3183:

```cpp
// C3183a.cpp
// compile with: /clr /c
ref class Test
{
   ref class
   {  // C3183, delete class or name it
      int a;
      int b;
   };
};
```
