---
description: 'Dowiedz się więcej o: błąd kompilatora C3183'
title: Błąd kompilatora C3183
ms.date: 11/04/2016
f1_keywords:
- C3183
helpviewer_keywords:
- C3183
ms.assetid: dbd0f020-c739-43c9-947e-9ce21537331b
ms.openlocfilehash: 1a2b761af05ec9285e4222a874e1641466106c9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174107"
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
