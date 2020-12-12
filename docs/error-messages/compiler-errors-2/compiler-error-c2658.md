---
description: 'Dowiedz się więcej o: błąd kompilatora C2658'
title: Błąd kompilatora C2658
ms.date: 11/04/2016
f1_keywords:
- C2658
helpviewer_keywords:
- C2658
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
ms.openlocfilehash: 6f86bb2147d13a0192cb7272e3ac2f3f580b1493
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286049"
---
# <a name="compiler-error-c2658"></a>Błąd kompilatora C2658

"member": Ponowna Definicja w anonimowej strukturze/Unii

Dwie anonimowe struktury lub Unii zawierają deklaracje składowych o tym samym identyfikatorze, ale z różnymi typami. W obszarze [/za](../../build/reference/za-ze-disable-language-extensions.md)zostanie również wyświetlony ten błąd dla elementów członkowskich o takim samym identyfikatorze i typie.

Poniższy przykład generuje C2658:

```cpp
// C2658.cpp
// compile with: /c
struct X {
   union { // can be struct too
      int i;
   };
   union {
      int i;   // Under /Za, C2658
      // int i not needed here because it is defined in the first union
   };
};

struct Z {
   union {
      char *i;
   };

   union {
      void *i;   // C2658 redefinition of 'i'
      // try the following line instead
      // void *ii;
   };
};
```
