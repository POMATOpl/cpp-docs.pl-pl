---
title: Błąd kompilatora C2809 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2809
dev_langs:
- C++
helpviewer_keywords:
- C2809
ms.assetid: ce796b8e-1a8c-4074-995d-1ad09afd0e93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6503f395a795056d0952c7a55f2c69300501313e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018877"
---
# <a name="compiler-error-c2809"></a>Błąd kompilatora C2809

"operator operator" nie ma formalnych parametrów

Operator nie ma wymaganych parametrów.

Poniższy przykład spowoduje wygenerowanie C2809:

```
// C2809.cpp
// compile with: /c
class A{};
int operator+ ();   // C2809
int operator+ (A);   // OK
```