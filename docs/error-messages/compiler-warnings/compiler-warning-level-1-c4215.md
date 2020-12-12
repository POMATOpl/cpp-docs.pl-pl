---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4215'
title: Ostrzeżenie kompilatora (poziom 1) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: 4d2e4d170b31c483f216fa85369c05ada38c30d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266562"
---
# <a name="compiler-warning-level-1-c4215"></a>Ostrzeżenie kompilatora (poziom 1) C4215

użyto niestandardowego rozszerzenia: Long float

Domyślne rozszerzenia Microsoft (/ze) traktują **długie dane zmiennoprzecinkowe** jako **`double`** . Zgodność ANSI ([/za](../../build/reference/za-ze-disable-language-extensions.md)) nie jest zgodna z programem. Służy **`double`** do zachowania zgodności.

Poniższy przykład generuje C4215:

```cpp
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```
