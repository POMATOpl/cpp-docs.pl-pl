---
description: 'Dowiedz się więcej o: błąd kompilatora C2533'
title: Błąd kompilatora C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: 46f9a18d80bcf75d916a6cf5387dc7145f1f1629
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258125"
---
# <a name="compiler-error-c2533"></a>Błąd kompilatora C2533

"Identyfikator": konstruktory nie mogą być typem zwracanym

Konstruktor nie może mieć zwracanego typu (nawet **`void`** typu zwracanego).

Typowym źródłem tego błędu jest brak średnika między końcem definicji klasy a pierwszą implementacją konstruktora. Kompilator widzi klasę jako definicję zwracanego typu dla funkcji konstruktora i generuje C2533.

Poniższy przykład generuje C2533 i pokazuje, jak go naprawić:

```cpp
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```
