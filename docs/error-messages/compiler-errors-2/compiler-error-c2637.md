---
description: 'Dowiedz się więcej o: błąd kompilatora C2637'
title: Błąd kompilatora C2637
ms.date: 11/04/2016
f1_keywords:
- C2637
helpviewer_keywords:
- C2637
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
ms.openlocfilehash: 1f42a732d5dfa3f7c94e0cc755bd1db00c8ff56b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208726"
---
# <a name="compiler-error-c2637"></a>Błąd kompilatora C2637

"Identyfikator": nie można modyfikować wskaźników do składowych danych

Wskaźnik do składowej danych nie może mieć konwencji wywoływania. Aby rozwiązać ten problem, Usuń konwencję wywoływania lub Zadeklaruj wskaźnik do funkcji składowej.

Poniższy przykład generuje C2637:

```cpp
// C2637.cpp
// compile with: /c
struct S {};
int __stdcall S::*pms1;   // C2637

// OK
int S::*pms2;
int (__stdcall S::*pms3)(...);
```
