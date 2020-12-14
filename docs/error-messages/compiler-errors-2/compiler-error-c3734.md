---
description: 'Dowiedz się więcej o: błąd kompilatora C3734'
title: Błąd kompilatora C3734
ms.date: 11/04/2016
f1_keywords:
- C3734
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
ms.openlocfilehash: f24c81c06a0e140f7970e8a6fc96d90aae3780f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245008"
---
# <a name="compiler-error-c3734"></a>Błąd kompilatora C3734

"Class": Klasa Managed lub WinRT nie może być klasą coclass

Atrybut [coclass](../../windows/attributes/coclass.md) nie może być używany z klasami zarządzanymi ani WinRT.

Poniższy przykład generuje C3734 i pokazuje, jak to naprawić:

```cpp
// C3734.cpp
// compile with: /clr /c
[module(name="x")];

[coclass]
ref class CMyClass {   // C3734 remove the ref keyword to resolve
};
```
