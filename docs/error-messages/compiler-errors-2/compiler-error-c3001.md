---
title: Błąd kompilatora C3001 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3001
dev_langs:
- C++
helpviewer_keywords:
- C3001
ms.assetid: d0e03478-1b44-47e5-8f5b-70415fa1f8bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4cfa4dbd157a76422cfc86f20b72af5b84c15c0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051467"
---
# <a name="compiler-error-c3001"></a>Błąd kompilatora C3001

"error_text": Oczekiwano nazwy dyrektywy OpenMP

`omp` Pragma musi następować dyrektywy.

Poniższy przykład spowoduje wygenerowanie C3001:

```
// C3001.c
// compile with: /openmp
int main()
{
   #pragma omp   // C3001 missing token
}
```