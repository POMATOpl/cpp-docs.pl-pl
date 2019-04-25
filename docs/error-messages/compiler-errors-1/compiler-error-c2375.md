---
title: Błąd kompilatora C2375
ms.date: 11/04/2016
f1_keywords:
- C2375
helpviewer_keywords:
- C2375
ms.assetid: 193c5e8b-1b20-4928-8a02-8c1cddaf2a26
ms.openlocfilehash: 162f1b13ea76a92db6fbef08124a1e46bc4e18a7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187685"
---
# <a name="compiler-error-c2375"></a>Błąd kompilatora C2375

'Funkcja': zmiana definicji; różne powiązania

Funkcja jest już zadeklarowana ze specyfikatorem różne powiązania.

Poniższy przykład spowoduje wygenerowanie C2375:

```
// C2375.cpp
// compile with: /Za /c
extern void func( void );
static void func( void );   // C2375
static void func2( void );   // OK
```