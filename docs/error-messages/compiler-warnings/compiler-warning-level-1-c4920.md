---
title: Kompilator ostrzeżenie (poziom 1) C4920 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4920
dev_langs:
- C++
helpviewer_keywords:
- C4920
ms.assetid: 1e501f2e-93c1-4d27-a4fa-54fc86271ae7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4873fcb1e5bb6d712e44b86d6f60589d6c8ddf4d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091741"
---
# <a name="compiler-warning-level-1-c4920"></a>Kompilator ostrzeżenie (poziom 1) C4920

Członek elementu członkowskiego wyliczenia typu wyliczeniowego = wartość już występuje w typie wyliczeniowym wyliczenia jako elementu członkowskiego = wartość

Jeśli .tlb, który jest przekazywany do #import ma ten sam symbolu, zdefiniowanego w co najmniej dwóch typów wyliczeniowych, to ostrzeżenie wskazuje, że kolejne identyczne symbole są ignorowane i będzie komentarzami w pliku .tlh.

Zakładając, że .tlb, który zawiera:

```
library MyLib
{
    typedef enum {
        enumMember = 512
    } AProblem;

    typedef enum {
        enumMember = 1024
    } BProblem;
};
```

Poniższe przykłady generuje C4920,

```
// C4920.cpp
// compile with: /W1
#import "t4920.tlb"   // C4920

int main() {
}
```