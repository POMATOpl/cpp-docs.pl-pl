---
description: 'Dowiedz się więcej o: błąd kompilatora C2283'
title: Błąd kompilatora C2283
ms.date: 11/04/2016
f1_keywords:
- C2283
helpviewer_keywords:
- C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
ms.openlocfilehash: dab8688623962051759f9f4be84f5831b58a700f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294980"
---
# <a name="compiler-error-c2283"></a>Błąd kompilatora C2283

"Identyfikator": czysty specyfikator lub abstrakcyjny specyfikator override nie jest dozwolony dla nienazwanej struktury

Funkcja członkowska nienazwanej klasy lub struktury jest zadeklarowana za pomocą czystego specyfikatora, co jest niedozwolone.

Poniższy przykład generuje C2283:

```cpp
// C2283.cpp
// compile with: /c
struct {
   virtual void func() = 0;   // C2283
};
struct T {
   virtual void func() = 0;   // OK
};
```
