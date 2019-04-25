---
title: Compiler Error C2860
ms.date: 11/04/2016
f1_keywords:
- C2860
helpviewer_keywords:
- C2860
ms.assetid: ccc83553-90ed-4e94-b5e9-38b58ae38e31
ms.openlocfilehash: 7d468fb2a71ce23bcd527cb02663dd5f7b7eecad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302868"
---
# <a name="compiler-error-c2860"></a>Compiler Error C2860

"void" nie może być typem argumentu, z wyjątkiem "(void)"

Typ `void` nie można używać jako typu argumentu z innymi argumentami.

Poniższy przykład spowoduje wygenerowanie C2860:

```
// C2860.cpp
// compile with: /c
void profunc1(void, int i);   // C2860
void func10(void);   // OK
```