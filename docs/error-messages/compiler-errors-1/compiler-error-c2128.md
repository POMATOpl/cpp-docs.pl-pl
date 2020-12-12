---
description: 'Dowiedz się więcej o: błąd kompilatora C2128'
title: Błąd kompilatora C2128
ms.date: 11/04/2016
f1_keywords:
- c2128
helpviewer_keywords:
- C2128
ms.assetid: 08cbf734-75b3-49f2-9026-9b319947612d
ms.openlocfilehash: fd72ffd45206a885d56b3d2f1821240279f06e21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323171"
---
# <a name="compiler-error-c2128"></a>Błąd kompilatora C2128

"Function": alloc_text/same_seg ma zastosowanie tylko do funkcji z powiązaniem C

`#pragma alloc_text` może być używany tylko z funkcjami zadeklarowanymi w celu posiadania powiązania w języku C.

Poniższy przykład generuje C2128:

```cpp
// C2128.cpp
// compile with: /c

// Delete the following line to resolve.
void func();
// #pragma alloc_text("my segment", func)   // C2128

extern "C" {
void func();
}

#pragma alloc_text("my segment", func)
void func() {}
```
