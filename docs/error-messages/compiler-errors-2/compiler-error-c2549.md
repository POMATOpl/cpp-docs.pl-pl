---
title: Błąd kompilatora C2549 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2549
dev_langs:
- C++
helpviewer_keywords:
- C2549
ms.assetid: 29310094-54a3-4605-bc6d-a312a68daf5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e32baf420a0bba66966b418b05642c6bcf96f180
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054566"
---
# <a name="compiler-error-c2549"></a>Błąd kompilatora C2549

konwersja zdefiniowana przez użytkownika nie może określić zwracanego typu

Poniższy przykład spowoduje wygenerowanie C2549:

```
// C2549.cpp
// compile with: /c
class X {
public:
   int operator int() { return value; }   // C2549

   // try the following line instead
   // operator int() { return value; }
private:
   int value;
};
```