---
title: Kompilator ostrzeżenie (poziom 1) C4632 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4632
dev_langs:
- C++
helpviewer_keywords:
- C4632
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84a8e078afe7164f1a3877f15c0b2741c6c848b8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086411"
---
# <a name="compiler-warning-level-1-c4632"></a>Kompilator ostrzeżenie (poziom 1) C4632

Komentarz dokumentu XML: pliku — odmowa dostępu: Przyczyna

Ścieżka do pliku .xdc (`file`) nie jest prawidłowa, a nie pliku .xdc utworzone.

Poniższy przykład spowoduje wygenerowanie C4632:

```
// C4632.cpp
// compile with: /clr /docv:\\falsedir /LD /W1
// C4632 expected

/// Text for class MyClass.
public ref class MyClass {};
```