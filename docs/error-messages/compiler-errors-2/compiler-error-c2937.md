---
title: Błąd kompilatora C2937 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2937
dev_langs:
- C++
helpviewer_keywords:
- C2937
ms.assetid: 95671ca3-79f7-4b56-a5f2-a92296da1629
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccb13a7cf95e1f63bd10b3901a3c2157a7fe29bf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061808"
---
# <a name="compiler-error-c2937"></a>Błąd kompilatora C2937

"class": typ klasy identyfikator ponownie definiowana jako globalne — typedef

Generyczny lub szablonu klasy nie można użyć jako globalne `typedef`.

Poniższy przykład spowoduje wygenerowanie C2937:

```
// C2937.cpp
// compile with: /c
template<class T>
struct TC { };
typedef int TC<int>;   // C2937
typedef TC<int> c;   // OK
```

C2937 może również wystąpić, gdy za pomocą typów ogólnych:

```
// C2937b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };
typedef int GC<int>;   // C2937
typedef GC<int> xx;   // OK
```