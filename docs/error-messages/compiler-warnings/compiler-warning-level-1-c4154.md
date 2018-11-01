---
title: Kompilator ostrzeżenie (poziom 1) C4154
ms.date: 11/04/2016
f1_keywords:
- C4154
helpviewer_keywords:
- C4154
ms.assetid: 4511afeb-e893-4cc6-83b6-4c7a0477f76b
ms.openlocfilehash: 5d2d6316838e8f3ef4acdf60494a0450a5efbdbe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563553"
---
# <a name="compiler-warning-level-1-c4154"></a>Kompilator ostrzeżenie (poziom 1) C4154

Usunięcie wyrażenia tablicowego; dostarczono konwersji do wskaźnika

Nie można użyć `delete` w tablicy, dlatego kompilator konwertuje tablicy do wskaźnika.

## <a name="example"></a>Przykład

```
// C4154.cpp
// compile with: /c /W1
int main() {
   int array[ 10 ];
   delete array;   // C4154 can't delete stack object

   int *parray2 = new int [10];
   int (&array2)[10] = (int(&)[10]) parray2;
   delete [] array2;   // C4154

   // try the following line instead
   delete [] &array2;
}
```