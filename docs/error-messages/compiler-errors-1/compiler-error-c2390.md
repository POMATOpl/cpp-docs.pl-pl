---
description: 'Dowiedz się więcej o: błąd kompilatora C2390'
title: Błąd kompilatora C2390
ms.date: 11/04/2016
f1_keywords:
- C2390
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
ms.openlocfilehash: 91539cea6ed89c02734c08f068f3d6474283dfa9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337594"
---
# <a name="compiler-error-c2390"></a>Błąd kompilatora C2390

"Identyfikator": nieprawidłowa specyfikator klasy magazynu "

Klasa magazynu nie jest prawidłowa dla identyfikatora zakresu globalnego. Domyślna Klasa magazynu jest używana zamiast nieprawidłowej klasy.

Możliwe rozwiązania:

- Jeśli identyfikator jest funkcją, zadeklaruj ją z **`extern`** magazynem.

- Jeśli identyfikator jest parametrem formalnym lub zmienną lokalną, zadeklaruj go za pomocą automagazynu.

- Jeśli identyfikator jest zmienną globalną, zadeklaruj ją bez klasy magazynu (autostorage).

## <a name="example"></a>Przykład

- Poniższy przykład generuje C2390:

```cpp
// C2390.cpp
register int i;   // C2390

int main() {
   register int j;   // OK
}
```
