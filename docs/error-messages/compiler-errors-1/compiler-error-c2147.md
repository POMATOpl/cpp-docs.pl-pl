---
title: Błąd kompilatora C2147 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2147
dev_langs:
- C++
helpviewer_keywords:
- C2147
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 786d47e23986962575567b8afdc2eefd5aac5be6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082433"
---
# <a name="compiler-error-c2147"></a>Błąd kompilatora C2147

Błąd składniowy: 'Identyfikator' to nowe słowo kluczowe

Użyto identyfikatora, który teraz jest zastrzeżonym słowem kluczowym w języku.

Poniższy przykład spowoduje wygenerowanie C2147:

```
// C2147.cpp
// compile with: /clr
int main() {
   int gcnew = 0;   // C2147
   int i = 0;   // OK
}
```