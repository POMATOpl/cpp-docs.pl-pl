---
description: 'Dowiedz się więcej o: błąd kompilatora C2801'
title: Błąd kompilatora C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: ca7e74f99b91b5a6699cdf3361ab64a89b7a7392
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297476"
---
# <a name="compiler-error-c2801"></a>Błąd kompilatora C2801

operator "operator" musi być niestatyczną składową

Następujące operatory mogą być przeciążone tylko jako niestatyczne elementy członkowskie:

- Wykorzystując `=`

- Dostęp do elementu członkowskiego klasy `->`

- Tworzenie indeksów dolnych `[]`

- Wywołanie funkcji `()`

Możliwe przyczyny C2801:

- Przeciążony operator nie jest klasą, strukturą ani składową Unii.

- Zadeklarowano przeciążony operator **`static`** .

- Poniższy przykład generuje C2801:

```cpp
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```
