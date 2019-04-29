---
title: Błąd kompilatora C2734
ms.date: 11/04/2016
f1_keywords:
- C2734
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
ms.openlocfilehash: c20fcc7673c00ea7cfad32bdc3feae042f1f9086
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350770"
---
# <a name="compiler-error-c2734"></a>Błąd kompilatora C2734

'Identyfikator': obiekt const musi zostać zainicjowany, jeśli nie extern

Identyfikator jest zadeklarowany jako `const` , ale nie zainicjowane lub `extern`.

Poniższy przykład spowoduje wygenerowanie C2734:

```
// C2734.cpp
const int j;   // C2734
extern const int i;   // OK, declared as extern
```