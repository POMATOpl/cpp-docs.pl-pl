---
title: Błąd kompilatora C2006 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2006
dev_langs:
- C++
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9468be17584a54047563bace2b35f5cb4888b41
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031213"
---
# <a name="compiler-error-c2006"></a>Błąd kompilatora C2006

"dyrektywa" Oczekiwano nazwy pliku, znaleziono "token"

Dyrektywy, takie jak [#include](../../preprocessor/hash-include-directive-c-cpp.md) lub [#import](../../preprocessor/hash-import-directive-cpp.md) wymagają nazwy pliku. Aby naprawić błąd, upewnij się, *tokenu* jest prawidłową nazwą pliku. Ponadto umieść nazwę pliku w podwójne cudzysłowy lub nawiasy.

Poniższy przykład spowoduje wygenerowanie C2006:

```
// C2006.cpp
#include stdio.h   // C2006
```

Możliwe rozwiązanie:

```
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```