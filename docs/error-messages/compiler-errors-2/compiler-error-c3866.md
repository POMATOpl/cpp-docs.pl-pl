---
description: 'Dowiedz się więcej o: błąd kompilatora C3866'
title: Błąd kompilatora C3866
ms.date: 11/04/2016
f1_keywords:
- C3866
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
ms.openlocfilehash: fceb8ed41a3cbfc287f4c1115cd0502ce8506925
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222869"
---
# <a name="compiler-error-c3866"></a>Błąd kompilatora C3866

Brak listy argumentów wywołania funkcji

Wewnątrz niestatycznej funkcji członkowskiej, destruktor lub wywołanie finalizatora nie miało listy argumentów.

Poniższy przykład generuje C3866:

```cpp
// C3866.cpp
// compile with: /c
class C {
   ~C();
   void f() {
      this->~C;   // C3866
      this->~C();   // OK
   }
};
```
