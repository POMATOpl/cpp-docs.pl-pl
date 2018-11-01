---
title: Błąd kompilatora C3233
ms.date: 11/04/2016
f1_keywords:
- C3233
helpviewer_keywords:
- C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
ms.openlocfilehash: 4a0cf849f7b87bd8d61b0ef087cf91d15669d719
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439523"
---
# <a name="compiler-error-c3233"></a>Błąd kompilatora C3233

"type": parametr typu generycznego już ograniczony

Nie jest prawidłowy w celu ograniczenia parametru ogólnego w więcej niż jednym `where` klauzuli.

Poniższy przykład spowoduje wygenerowanie C3233:

```
// C3233.cpp
// compile with: /clr /LD

interface struct C {};
interface struct D {};

generic <class T>
where T : C
where T : D
ref class E {};   // C3233
```