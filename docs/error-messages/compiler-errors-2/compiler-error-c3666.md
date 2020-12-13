---
description: 'Dowiedz się więcej o: błąd kompilatora C3666'
title: Błąd kompilatora C3666
ms.date: 11/04/2016
f1_keywords:
- C3666
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
ms.openlocfilehash: 245fd061a7a1ce7b9b3e25ae76e6b15ec9428145
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134267"
---
# <a name="compiler-error-c3666"></a>Błąd kompilatora C3666

"Konstruktor": specyfikator przesłonięcia "słowo kluczowe" jest niedozwolony w konstruktorze

Użyto specyfikatora przesłonięcia w konstruktorze, który jest niedozwolony. Aby uzyskać więcej informacji, zobacz [specyfikatory przesłonięć](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3666.

```cpp
// C3666.cpp
// compile with: /clr /c
ref struct R {
   R() new {}   // C3666
   R(int i) {}   // OK
};
```
