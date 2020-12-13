---
description: 'Dowiedz się więcej o: błąd kompilatora C2395'
title: Błąd kompilatora C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: 86b6123646ca91945a861e9b9822076877421ac8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145473"
---
# <a name="compiler-error-c2395"></a>Błąd kompilatora C2395

"your_type:: operator'op" ": nieprawidłowy operator CLR lub WinRT. Co najmniej jeden parametr musi mieć następujące typy: "t", "t%", "&", "^", "^%", "^&", gdzie T = "your_type"

Operator w środowisko wykonawcze systemu Windows lub typie zarządzanym nie ma co najmniej jednego parametru, którego typ jest taki sam jak typ zwracanej wartości operatora.

Poniższy przykład generuje C2395 i pokazuje, jak to naprawić:

```cpp
// C2395.cpp
// compile with: /clr /c
value struct V {
   static V operator *(int i, char c);   // C2395

   // OK
   static V operator *(V v, char c);
   // or
   static V operator *(int i, V& rv);
};
```
