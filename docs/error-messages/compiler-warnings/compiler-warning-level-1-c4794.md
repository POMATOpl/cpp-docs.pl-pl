---
title: Kompilator ostrzeżenie (poziom 1) C4794 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4794
dev_langs:
- C++
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c6e6b8aedacc71291afc2a34a6a11d7b19a126b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027404"
---
# <a name="compiler-warning-level-1-c4794"></a>Kompilator ostrzeżenie (poziom 1) C4794

segment zmiennej lokalny magazyn wątków 'Zmienna' zmieniony z "Nazwa sekcji" na ".tls$"

Użyte [#pragma data_seg](../../preprocessor/data-seg.md) umieścić zmiennej tls w sekcji nie uruchamia się za pomocą .tls$.

.Tls$*x* sekcji będzie istnieć w pliku obiektu gdzie [__declspec(thread)](../../cpp/thread.md) zmienne są zdefiniowane. Sekcja .tls w pliku EXE lub DLL spowoduje w tych sekcjach.

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C4794:

```
// C4794.cpp
// compile with: /W1 /c
#pragma data_seg(".someseg")
__declspec(thread) int i;   // C4794

// OK
#pragma data_seg(".tls$9")
__declspec(thread) int j;
```