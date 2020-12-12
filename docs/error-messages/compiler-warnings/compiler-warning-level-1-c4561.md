---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4561'
title: Ostrzeżenie kompilatora (poziom 1) C4561
ms.date: 11/04/2016
f1_keywords:
- C4561
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
ms.openlocfilehash: fc94879039f72bba0734240bc26d152965d6b650
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337286"
---
# <a name="compiler-warning-level-1-c4561"></a>Ostrzeżenie kompilatora (poziom 1) C4561

element "__fastcall" jest niezgodny z opcją "/CLR": konwertowanie na " \_ _stdcall"

Nie można używać konwencji wywoływania funkcji [__fastcall](../../cpp/fastcall.md) z opcją kompilatora [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) . Kompilator ignoruje wywołania do **`__fastcall`** . Aby usunąć to ostrzeżenie, Usuń wywołania **`__fastcall`** lub Kompiluj bez **/CLR**.

Poniższy przykład generuje C4561:

```cpp
// C4561.cpp
// compile with: /clr /W1 /c
// processor: x86
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve
```
