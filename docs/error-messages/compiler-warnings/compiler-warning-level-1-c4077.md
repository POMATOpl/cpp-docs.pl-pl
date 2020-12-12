---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4077'
title: Ostrzeżenie kompilatora (poziom 1) C4077
ms.date: 11/04/2016
f1_keywords:
- C4077
helpviewer_keywords:
- C4077
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
ms.openlocfilehash: 96e611db6d36dfa62d96561deb2f4c4d57638c72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208713"
---
# <a name="compiler-warning-level-1-c4077"></a>Ostrzeżenie kompilatora (poziom 1) C4077

nieznana opcja check_stack

Stara forma **check_stack** pragma jest używana z nieznanym argumentem. Argument musi być `+` , `-` ,, `(on)` lub być `(off)` pusty.

Kompilator ignoruje pragmę i pozostawia sprawdzanie stosu bez zmian.

## <a name="example"></a>Przykład

```cpp
// C4077.cpp
// compile with: /W1 /LD
#pragma check_stack yes // C4077
#pragma check_stack +    // Correct old form
#pragma check_stack (on) // Correct new form
```
