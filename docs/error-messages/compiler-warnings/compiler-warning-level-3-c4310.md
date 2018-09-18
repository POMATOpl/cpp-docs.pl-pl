---
title: Kompilator ostrzeżenie (poziom 3) C4310 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4310
dev_langs:
- C++
helpviewer_keywords:
- C4310
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 410db9aa1dee4c0a75b3e1df9d1b019cef736e34
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039455"
---
# <a name="compiler-warning-level-3-c4310"></a>Kompilator ostrzeżenie (poziom 3) C4310

Rzutowanie obcina stałą wartość

Wartość stała jest rzutowany na mniejszych typów. Kompilator wykonuje rzutowanie, w którym obcina danych. Poniższy przykład spowoduje wygenerowanie C4310:

```
// C4310.cpp
// compile with: /W4
int main() {
   long int a;
   a = (char) 128;   // C4310, use value 0-127 to resolve
}
```