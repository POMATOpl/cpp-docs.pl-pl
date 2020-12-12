---
description: 'Dowiedz się więcej o: błąd kompilatora C2577'
title: Błąd kompilatora C2577
ms.date: 11/04/2016
f1_keywords:
- C2577
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
ms.openlocfilehash: 9e54791070401f334a4dc0650ca2b1bcee5f32a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208856"
---
# <a name="compiler-error-c2577"></a>Błąd kompilatora C2577

"member": destruktor/finalizator nie może mieć zwracanego typu

Destruktor lub finalizator nie może zwracać wartości **`void`** ani żadnego innego typu. Usuń **`return`** instrukcję z definicji destruktora.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2577.

```cpp
// C2577.cpp
// compile with: /c
class A {
public:
   A() {}
   ~A(){
      return 0;   // C2577
   }
};
```
