---
title: Błąd kompilatora C2794
ms.date: 11/04/2016
f1_keywords:
- C2794
helpviewer_keywords:
- C2794
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
ms.openlocfilehash: 1e9d3ee84b72dc9a4f83337f79f38c0237e0b505
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360141"
---
# <a name="compiler-error-c2794"></a>Błąd kompilatora C2794

'Funkcja': nie jest elementem Członkowskim wszelkie bezpośredniej lub pośredniej klasy bazowej "class"

Próbowano użyć [super](../../cpp/super.md) wywołanie funkcji nieistniejącego elementu członkowskiego.

Poniższy przykład spowoduje wygenerowanie C2794

```
// C2794.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::f();  // C2794
   }
};
```