---
title: Kompilator ostrzeżenie (poziom 1) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: a45cd6cf86eb8ab1edb33ad5e0df8374972c425e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386489"
---
# <a name="compiler-warning-level-1-c4215"></a>Kompilator ostrzeżenie (poziom 1) C4215

użyto niestandardowego rozszerzenia: long float

Traktuj domyślnych rozszerzeń firmy Microsoft (/Ze) **long float** jako **double**. Zgodność ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) nie jest. Użyj **double** zachować zgodność.

Poniższy przykład spowoduje wygenerowanie C4215:

```
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```