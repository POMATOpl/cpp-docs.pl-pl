---
description: 'Dowiedz się więcej o: błąd kompilatora C2344'
title: Błąd kompilatora C2344
ms.date: 11/04/2016
f1_keywords:
- C2344
helpviewer_keywords:
- C2344
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
ms.openlocfilehash: 1ad4f1808f407a9f654f5bbf3a022c2dc7b0b3ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234764"
---
# <a name="compiler-error-c2344"></a>Błąd kompilatora C2344

align (#): wyrównanie musi być potęgą liczby dwa

Przy użyciu słowa kluczowego [align](../../cpp/align-cpp.md) , przekazana wartość musi być potęgą liczby dwa.

Na przykład poniższy kod generuje C2344, ponieważ 3 nie jest potęgą dwóch:

```cpp
// C2344.cpp
// compile with: /c
__declspec(align(3)) int a;   // C2344
__declspec(align(4)) int b;   // OK
```
