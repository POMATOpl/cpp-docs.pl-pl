---
title: Błąd kompilatora C2496 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2496
dev_langs:
- C++
helpviewer_keywords:
- C2496
ms.assetid: 9a25237d-5bbb-4112-98f3-29cd99d3f89f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04e9e9a58c3ad64010aaffda2378f5b79cccbb67
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062907"
---
# <a name="compiler-error-c2496"></a>Błąd kompilatora C2496

'Identyfikator': "selectany" może być stosowany tylko do elementów danych za pomocą zewnętrznego powiązania

[Selectany](../../cpp/selectany.md) atrybut można stosować tylko do elementów danych globalnych i widoczny zewnętrznie.

Poniższy przykład spowoduje wygenerowanie C2496:

```
// C2496.cpp
// compile with: /c
__declspec(selectany) int x1 = 1;
const __declspec(selectany) int x2 = 2;   // C2496
static __declspec(selectany) int x6 = 6;   // C2496

extern const __declspec(selectany) int x3 = 3;

__declspec(selectany) int x4;

// dynamic initialization of x5
int f();
__declspec(selectany) int x5 = f();

extern const int x7;
// OK - redeclaration of x7 that is extern
const __declspec(selectany) int x7 = 7;
```