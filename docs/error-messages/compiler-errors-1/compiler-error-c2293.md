---
title: Błąd kompilatora C2293 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2293
dev_langs:
- C++
helpviewer_keywords:
- C2293
ms.assetid: 17e7b4e2-368b-4dd7-a01b-d82be60f8e56
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c5a24be3c51f17d12712b950babe5e723f1633c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031174"
---
# <a name="compiler-error-c2293"></a>Błąd kompilatora C2293

'Identyfikator': niedozwolony zmiennej składowej jako specyfikatora __based

Specyfikatory dla `__based` modyfikator musi być niebędących wskaźników.

Poniższy przykład spowoduje wygenerowanie C2293:

```
// C2293.cpp
// compile with: /c
class A {
   static int *i;
   void __based(i) *bp;   // C2293
   void *bp2;   // OK
};
```