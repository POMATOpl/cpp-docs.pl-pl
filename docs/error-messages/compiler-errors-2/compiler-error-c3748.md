---
title: Błąd kompilatora C3748
ms.date: 11/04/2016
f1_keywords:
- C3748
helpviewer_keywords:
- C3748
ms.assetid: 6fe71a0a-dd93-4ce6-9729-b9616360cf34
ms.openlocfilehash: ef1c446f9feb3d40add62513a31fc81a382b98e1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226846"
---
# <a name="compiler-error-c3748"></a>Błąd kompilatora C3748

"interface": zarządzane interfejsy nie mogą wyzwalać zdarzeń

[__Event](../../cpp/event.md) — słowo kluczowe nie może występować wewnątrz interfejsu.

Poniższy przykład spowoduje wygenerowanie C3748:

```
// C3748.cpp
__interface I {
// try the following line instead
// struct I {
   __event void f();   // C3748
};

int main() {
}
```