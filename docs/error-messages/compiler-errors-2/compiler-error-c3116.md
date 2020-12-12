---
description: 'Dowiedz się więcej o: błąd kompilatora C3116'
title: Błąd kompilatora C3116
ms.date: 11/04/2016
f1_keywords:
- C3116
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
ms.openlocfilehash: ea11d851c4348725c48e408ffdd0ed6de4393e6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115940"
---
# <a name="compiler-error-c3116"></a>Błąd kompilatora C3116

"specyfikator magazynu": nieprawidłowa Klasa magazynu dla metody interfejsu

Użyto **`typedef`** , **`register`** , lub **`static`** jako klasy magazynu dla metody interfejsu. Te klasy magazynu są niedozwolone w składowych interfejsu.

Poniższy przykład generuje C3116:

```cpp
// C3116.cpp
__interface ImyInterface
{
   static void myFunc();   // C3116
};
```
