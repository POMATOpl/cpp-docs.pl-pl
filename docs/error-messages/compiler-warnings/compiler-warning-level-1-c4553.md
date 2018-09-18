---
title: Kompilator ostrzeżenie (poziom 1) C4553 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4553
dev_langs:
- C++
helpviewer_keywords:
- C4553
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 17c5887b550ea3181ac51d23ee24928502da1003
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096434"
---
# <a name="compiler-warning-level-1-c4553"></a>Kompilator ostrzeżenie (poziom 1) C4553

'operator': operator nie przynosi efektu; Czy chodziło 'operator'?

Jeśli Instrukcja wyrażenia operatora z efektem nie jako górnej części wyrażenia, prawdopodobnie jest błąd.

Poniższy przykład spowoduje wygenerowanie C4553:

```
// C4553.cpp
// compile with: /W1
int func()
{
   return 0;
}

int main()
{
   int i;
   i == func();   // C4553
   // try the following line instead
   // i = func();
}
```