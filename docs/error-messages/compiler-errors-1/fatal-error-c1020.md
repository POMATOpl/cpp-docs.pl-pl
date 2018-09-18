---
title: Błąd krytyczny C1020 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1020
dev_langs:
- C++
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ab0da342e575c0af452ec70d1759fe34188db9a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066872"
---
# <a name="fatal-error-c1020"></a>Błąd krytyczny C1020

Nieoczekiwany #endif

`#endif` Dyrektywy nie ma odpowiadającego `#if`, `#ifdef`, lub `#ifndef` dyrektywy. Można się, że każdy `#endif` ma pasujące dyrektywy.

Poniższy przykład spowoduje wygenerowanie C1020:

```
// C1020.cpp
#endif     // C1020
```

Możliwe rozwiązanie:

```
// C1020b.cpp
// compile with: /c
#if 1
#endif
```