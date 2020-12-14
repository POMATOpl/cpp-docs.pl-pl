---
description: 'Dowiedz się więcej o: błąd kompilatora C2791'
title: Błąd kompilatora C2791
ms.date: 11/04/2016
f1_keywords:
- C2791
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
ms.openlocfilehash: 0f5bd93c1c6ee32399da793147a18e9225b5fcb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297775"
---
# <a name="compiler-error-c2791"></a>Błąd kompilatora C2791

niedozwolone użycie elementu "Super": "Class" nie ma żadnych klas bazowych

Słowo kluczowe [Super](../../cpp/super.md) zostało użyte w kontekście funkcji składowej klasy, która nie ma żadnych klas bazowych.

Poniższy przykład generuje C2791:

```cpp
// C2791.cpp
struct D {
   void mf() {
      __super::mf();   // C2791
   }
};
```
