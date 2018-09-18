---
title: Błąd kompilatora C3662 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3662
dev_langs:
- C++
helpviewer_keywords:
- C3662
ms.assetid: 61bd3e41-a86b-42c0-be89-d992d3906ff1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d04705d588e22c22e607bc6e1010eeec0d9c3f41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053469"
---
# <a name="compiler-error-c3662"></a>Błąd kompilatora C3662

"członek": specyfikator przesłonięcia "specyfikatora" dozwolone tylko dla funkcji składowych zarządzanych lub klasach WinRT

Specyfikator przesłonięcia została użyta w składowej typu natywnego, co jest niedozwolone.

Aby uzyskać więcej informacji, zobacz [jawne zastępowanie](../../windows/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3662.

```
// C3662.cpp
// compile with: /clr /c
struct S {
   virtual void f();
};

struct S1 : S {
   virtual void f() new;   // C3662
};

ref struct T {
   virtual void f();
};

ref struct T1 : T {
   virtual void f() new;   // OK
};
```