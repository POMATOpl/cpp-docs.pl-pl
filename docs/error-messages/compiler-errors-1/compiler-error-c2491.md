---
title: Błąd kompilatora C2491 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2491
dev_langs:
- C++
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40e6adfc369cd79f4c08c9099f5bc7db2b2281d8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110994"
---
# <a name="compiler-error-c2491"></a>Błąd kompilatora C2491

'Identyfikator': definicja dllimport funkcja nie jest dozwolona

Dane statyczne elementy członkowskie danych i funkcje, które mogą być deklarowane jako `dllimport`s, ale nie zdefiniowano jako `dllimport`s.

Aby rozwiązać ten problem, Usuń `__declspec(dllimport)` specyfikator w definicji funkcji.

Poniższy przykład spowoduje wygenerowanie C2491:

```
// C2491.cpp
// compile with: /c
// function definition
void __declspec(dllimport) funcB() {}   // C2491

// function declaration
void __declspec(dllimport) funcB();   // OK
```