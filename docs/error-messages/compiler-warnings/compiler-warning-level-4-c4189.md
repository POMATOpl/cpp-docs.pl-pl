---
title: Kompilator ostrzeżenie (poziom 4) C4189 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4189
dev_langs:
- C++
helpviewer_keywords:
- C4189
ms.assetid: 7ad9242c-228e-4054-8244-5e914b618ef3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f02e718edf732284c2bf6ab3158082b6ec545eba
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115908"
---
# <a name="compiler-warning-level-4-c4189"></a>Kompilator ostrzeżenie (poziom 4) C4189

'Identyfikator': lokalna zmienna jest zainicjowana, ale nie odwołuje się

Zmienna jest zadeklarowana i zainicjowana, ale nie używane.

Poniższy przykład spowoduje wygenerowanie C4189:

```
// C4189.cpp
// compile with: /W4
int main() {
   int a = 1;   // C4189, remove declaration to resolve
}
```