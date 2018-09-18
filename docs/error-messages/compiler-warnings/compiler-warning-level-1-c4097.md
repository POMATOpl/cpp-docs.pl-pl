---
title: Kompilator ostrzeżenie (poziom 1) C4097 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4097
dev_langs:
- C++
helpviewer_keywords:
- C4097
ms.assetid: 2525be51-fac2-43b2-b57c-3bbf1a2268f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93202696c06a38682da95947ac068b2d90e177ec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062686"
---
# <a name="compiler-warning-level-1-c4097"></a>Kompilator ostrzeżenie (poziom 1) C4097

Oczekiwano wartości parametru pragma "Restore" lub "off"

Dyrektywa pragma została przekazana nieprawidłowa wartość.

Poniższy przykład spowoduje wygenerowanie C4097:

```
// C4097.cpp
// compile with: /W1
#pragma runtime_checks("",test)   // C4097
// try the following line instead
// #pragma runtime_checks("",off)

int main() {
}
```