---
title: Błąd kompilatora C2479 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2479
dev_langs:
- C++
helpviewer_keywords:
- C2479
ms.assetid: c74c7869-e65b-4ca1-b6fa-eb39fed4458a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc7210a6ff2e57b2d5f96fc59daace974e6f1744
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045234"
---
# <a name="compiler-error-c2479"></a>Błąd kompilatora C2479

'Identyfikator': "ALLOCATE()" jest prawidłowy tylko dla elementów danych statycznego obszaru

`__declspec( allocate())` Statycznego tylko do danych można używać składni.

Poniższy przykład spowoduje wygenerowanie C2479:

```
// C2479.cpp
// compile with: /c
#pragma section("mycode", read)
static __declspec(allocate("mycode")) void DoNothing() {}   // C2479
__declspec(allocate("mycode"))  int i = 0;   // OK
```