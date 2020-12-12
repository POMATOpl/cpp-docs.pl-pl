---
description: 'Dowiedz się więcej o: błąd kompilatora C3179'
title: Błąd kompilatora C3179
ms.date: 11/04/2016
f1_keywords:
- C3179
helpviewer_keywords:
- C3179
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
ms.openlocfilehash: 5f4b573c822eff68d972517f9fac093071cf2a0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174159"
---
# <a name="compiler-error-c3179"></a>Błąd kompilatora C3179

nienazwany typ zarządzany lub WinRT jest niedozwolony

Wszystkie klasy CLR i WinRT muszą mieć nazwy.

Poniższy przykład generuje C3179 i pokazuje, jak to naprawić:

```cpp
// C3179a.cpp
// compile with: /clr /c
typedef value struct { // C3179
// try the following line instead
// typedef value struct MyStruct {
   int i;
} V;
```
