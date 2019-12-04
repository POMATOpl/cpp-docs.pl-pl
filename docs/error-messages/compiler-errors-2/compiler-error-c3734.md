---
title: Błąd kompilatora C3734
ms.date: 11/04/2016
f1_keywords:
- C3734
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
ms.openlocfilehash: 381bb59dae523c05cdc67e33ba9d326e247abc7d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752863"
---
# <a name="compiler-error-c3734"></a>Błąd kompilatora C3734

"Class": Klasa Managed lub WinRT nie może być klasą coclass

Atrybut [coclass](../../windows/coclass.md) nie może być używany z klasami zarządzanymi ani WinRT.

Poniższy przykład generuje C3734 i pokazuje, jak to naprawić:

```cpp
// C3734.cpp
// compile with: /clr /c
[module(name="x")];

[coclass]
ref class CMyClass {   // C3734 remove the ref keyword to resolve
};
```
