---
description: 'Dowiedz się więcej o: błąd kompilatora C2157'
title: Błąd kompilatora C2157
ms.date: 11/04/2016
f1_keywords:
- C2157
helpviewer_keywords:
- C2157
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
ms.openlocfilehash: 4d8619d3d27bd9a1cb0c5323d9fdbf462b043ecf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181321"
---
# <a name="compiler-error-c2157"></a>Błąd kompilatora C2157

"Function": musi być zadeklarowana przed użyciem w liście pragma

Nazwa funkcji nie jest zadeklarowana przed odwołaniem na liście funkcji dla [alloc_text](../../preprocessor/alloc-text.md) pragma.

Poniższy przykład generuje C2157:

```cpp
// C2157.cpp
// compile with: /c
#pragma alloc_text( "func", func)   // C2157

// OK
extern "C" void func();
#pragma alloc_text( "func", func)
```
