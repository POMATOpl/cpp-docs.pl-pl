---
description: 'Dowiedz się więcej o: błąd kompilatora C2394'
title: Błąd kompilatora C2394
ms.date: 11/04/2016
f1_keywords:
- C2394
helpviewer_keywords:
- C2394
ms.assetid: 653fa9a0-29b3-48aa-bc01-82f98f717a2b
ms.openlocfilehash: 116ab480c5a72c18bfa551e582fb797d3c216d6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194871"
---
# <a name="compiler-error-c2394"></a>Błąd kompilatora C2394

"your_type:: operator'op" ": środowisko CLR lub WinRToperator jest nieprawidłowe. Co najmniej jeden parametr musi mieć następujące typy: "t ^", "^%", "^&", gdzie T = "your_type"

Operator w środowisko wykonawcze systemu Windows lub typie zarządzanym nie ma co najmniej jednego parametru, którego typ jest taki sam jak typ zwracanej wartości operatora.

Poniższy przykład generuje C2394:

```cpp
// C2394.cpp
// compile with: /clr /c
ref struct Y {
   static Y^ operator -(int i, char c);   // C2394

   // OK
   static Y^ operator -(Y^ hY, char c);
   // or
   static Y^ operator -(int i, Y^& rhY);
};
```
