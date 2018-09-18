---
title: Błąd kompilatora C2733 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2733
dev_langs:
- C++
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42749c26f4a8a474f3dac076b80a1bfe71e89d58
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110448"
---
# <a name="compiler-error-c2733"></a>Błąd kompilatora C2733

drugie powiązanie C przeciążonej funkcji "function" niedozwolone

Więcej niż jeden przeciążonej funkcji jest zadeklarowany z powiązaniem C. Korzystając z powiązaniem C, tylko jeden formularz określonej funkcji może być zewnętrzne. Ponieważ przeciążone funkcje mają taką samą nazwę niedekorowanego, nie można używać z programów C.

Poniższy przykład spowoduje wygenerowanie C2733:

```
// C2733.cpp
extern "C" {
   void F1(int);
}

extern "C" {
   void F1();   // C2733
   // try the following line instead
   // void F2();
}
```