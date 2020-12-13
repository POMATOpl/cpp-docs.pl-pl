---
description: 'Dowiedz się więcej o: błąd kompilatora C2111'
title: Błąd kompilatora C2111
ms.date: 11/04/2016
f1_keywords:
- C2111
helpviewer_keywords:
- C2111
ms.assetid: 38fd42ec-1480-4a44-aaca-ae4593ed5f50
ms.openlocfilehash: 604e793d787ceabd761d76146108df4b687c1e3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341259"
---
# <a name="compiler-error-c2111"></a>Błąd kompilatora C2111

' + ': Dodawanie wskaźników wymaga całkowitego operandu

Podjęto próbę dodania niecałkowitej wartości do wskaźnika przy użyciu operatora plus ( `+` ).

Poniższy przykład generuje C2111:

```cpp
// C2111.cpp
int main() {
   int *a = 0, *pa = 0, b = 0;
   double d = 0.00;

   a = pa + d;   // C2111
   a = pa + b;   // OK
}
```
