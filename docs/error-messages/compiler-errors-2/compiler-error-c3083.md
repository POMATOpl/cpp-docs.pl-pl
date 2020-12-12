---
description: 'Dowiedz się więcej o: błąd kompilatora C3083'
title: Błąd kompilatora C3083
ms.date: 11/04/2016
f1_keywords:
- C3083
helpviewer_keywords:
- C3083
ms.assetid: 05ff791d-52bb-41eb-9511-3ef89d7f4710
ms.openlocfilehash: 76740dfc9f95fd06cafc580acd2ab2a6b705d8ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320144"
---
# <a name="compiler-error-c3083"></a>Błąd kompilatora C3083

"Function": symbol po lewej stronie "::" musi być typem

Funkcja została wywołana nieprawidłowo.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3083.

```cpp
// C3083.cpp
// compile with: /c
struct N {
   ~N();
};

struct N1 {
   ~N1();
};

N::N::~N() {}   // C3083
N1::~N1() {}   // OK
```
