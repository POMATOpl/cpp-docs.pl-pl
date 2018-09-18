---
title: Błąd kompilatora C2531 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2531
dev_langs:
- C++
helpviewer_keywords:
- C2531
ms.assetid: c49afe15-55f8-4dc8-ac01-bf653622a7db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05af2bd4f1dc3403f5ecbb3254564292698624aa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045097"
---
# <a name="compiler-error-c2531"></a>Błąd kompilatora C2531

'Identyfikator': odwołanie do nieco pola jest niedozwolony

Odwołania do pola bitowe nie są dozwolone.

Poniższy przykład spowoduje wygenerowanie C2531:

```
// C2531.cpp
// compile with: /c
class P {
   int &b1 : 10;   // C2531
   int b2 : 10;   // OK
};
```