---
title: Błąd kompilatora C3745 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3745
dev_langs:
- C++
helpviewer_keywords:
- C3745
ms.assetid: 1e64aec5-7e53-47e5-bc7d-3905230cfc66
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa8393a1ac85c21df9299dcfeeb553ca145d5dac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025116"
---
# <a name="compiler-error-c3745"></a>Błąd kompilatora C3745

'Funkcja': tylko zdarzenie może być "raised"

Tylko funkcji zdefiniowanej przy użyciu [__event](../../cpp/event.md) — słowo kluczowe może być przekazywany do [__raise](../../cpp/raise.md) — słowo kluczowe.

Poniższy przykład spowoduje wygenerowanie C3745:

```
// C3745.cpp
struct E {
   __event void func();
   void func(int) {
   }

   void func2() {
   }

   void bar() {
      __raise func();
      __raise func(1);   // C3745
      __raise func2();   // C3745
   }
};

int main() {
   E e;
   __raise e.func();
   __raise e.func(1);   // C3745
   __raise e.func2();   // C3745
}
```