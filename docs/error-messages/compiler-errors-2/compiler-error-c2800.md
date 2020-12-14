---
description: 'Dowiedz się więcej o: błąd kompilatora C2800'
title: Błąd kompilatora C2800
ms.date: 11/04/2016
f1_keywords:
- C2800
helpviewer_keywords:
- C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
ms.openlocfilehash: 7adcb8e24bd7b3f3941260a9cceaa5157334ae8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297508"
---
# <a name="compiler-error-c2800"></a>Błąd kompilatora C2800

nie można obciążać operatora "operator"

Następujące operatory nie mogą być przeciążone: dostęp do składowej klasy ( `.` ), wskaźnik do elementu członkowskiego ( `.*` ), rozpoznawanie zakresu ( `::` ), wyrażenie warunkowe ( `? :` ) i **`sizeof`** .

Poniższy przykład generuje C2800:

```cpp
// C2800.cpp
// compile with: /c
class C {
   operator:: ();   // C2800
};
```
