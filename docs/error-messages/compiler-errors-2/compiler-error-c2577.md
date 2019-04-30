---
title: Błąd kompilatora C2577
ms.date: 11/04/2016
f1_keywords:
- C2577
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
ms.openlocfilehash: 4406aa90b26bc517308132ae9cccd003d44a9aad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408462"
---
# <a name="compiler-error-c2577"></a>Błąd kompilatora C2577

"członek": destruktor/finalizator nie może posiadać typu zwracanego

Destruktora lub finalizatora nie może zwracać wartość `void` lub dowolnego innego typu. Usuń `return` instrukcji z definicji destruktora.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C2577.

```
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