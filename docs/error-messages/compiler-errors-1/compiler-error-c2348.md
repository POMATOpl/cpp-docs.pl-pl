---
title: Błąd kompilatora C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: 379bcc7f37ff8942e4e45c6a6188438400937875
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526444"
---
# <a name="compiler-error-c2348"></a>Błąd kompilatora C2348

'Nazwa typu': nie jest agregacji stylu C, nie można wyeksportować w osadzonym IDL

Aby umieścić `struct` w pliku .idl, o [wyeksportować](../../windows/export.md) atrybutu `struct` musi zawierać tylko dane.

Poniższy przykład spowoduje wygenerowanie C2348:

```
// C2348.cpp
// C2348 error expected
[ module(name="SimpleMidlTest") ];

[export]
struct Point {
   // Delete the following two lines to resolve.
   Point() : m_i(0), m_j(0) {}
   Point(int i, int j) : m_i(i), m_j(j) {}

   int m_i;
   int m_j;
};
```