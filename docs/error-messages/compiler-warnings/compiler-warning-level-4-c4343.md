---
title: Kompilator ostrzeżenie (poziom 4) C4343
ms.date: 11/04/2016
f1_keywords:
- C4343
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
ms.openlocfilehash: c8f0bb514a3da932500f986e50a20af0947827c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403990"
---
# <a name="compiler-warning-level-4-c4343"></a>Kompilator ostrzeżenie (poziom 4) C4343

\#pragma optimize("g",off) przesłania opcję /Og

To ostrzeżenie, tylko prawidłowe w kompilatorze rodziny procesorów Itanium (IPF) informuje, że pragma [zoptymalizować](../../preprocessor/optimize.md) overrode [/Og](../../build/reference/og-global-optimizations.md) — opcja kompilatora.

Poniższy przykład spowoduje wygenerowanie C4343:

```
// C4343.cpp
// compile with: /Og /W4 /LD
// processor: IPF
#pragma optimize ("g", off)   // C4343
```