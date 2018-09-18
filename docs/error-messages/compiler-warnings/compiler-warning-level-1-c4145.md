---
title: Kompilator ostrzeżenie (poziom 1) C4145 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4145
dev_langs:
- C++
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65d041b9fdb7fb4b01abfadf5010444b0e406220
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100692"
---
# <a name="compiler-warning-level-1-c4145"></a>Kompilator ostrzeżenie (poziom 1) C4145

"wyrażenie1": wyrażenie relacyjne jako wyrażenie przełącznik; możliwa pomyłka z "wyrażenie2"

A `switch` instrukcja używa wyrażenie relacyjne jako wyrażenie jego kontroli, co skutkuje wartość logiczną parametru **przypadek** instrukcji. Czy chodziło Ci o *wyrażenie2*?

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C4145:

```
// C4145.cpp
// compile with: /W1
int main() {
   int i = 0;
   switch(i == 1) {   // C4145, use i instead of i == 1 to resolve
      case 1:
         break;
      default:
         break;
   }
}
```