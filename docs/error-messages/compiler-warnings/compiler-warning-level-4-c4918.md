---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4918'
title: Ostrzeżenie kompilatora (poziom 4) C4918
ms.date: 11/04/2016
f1_keywords:
- C4918
helpviewer_keywords:
- C4918
ms.assetid: 1bcf6d35-3467-4aa8-b2ef-cb33f4e70238
ms.openlocfilehash: 268fbff753ff5ed0cc2d63df6ba8422cdf073662
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330443"
---
# <a name="compiler-warning-level-4-c4918"></a>Ostrzeżenie kompilatora (poziom 4) C4918

"Character": nieprawidłowy znak na liście optymalizacji pragma

Na liście optymalizacji instrukcji " [Optimize](../../preprocessor/optimize.md) pragma" znaleziono nieznany znak.

Na przykład następująca instrukcja generuje C4918:

```cpp
// C4918.cpp
// compile with: /W4
#pragma optimize("X", on) // C4918 expected
int main()
{
}
```
