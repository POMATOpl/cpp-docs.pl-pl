---
title: Ostrzeżenie kompilatora (poziom 1) C4154
ms.date: 11/04/2016
f1_keywords:
- C4154
helpviewer_keywords:
- C4154
ms.assetid: 4511afeb-e893-4cc6-83b6-4c7a0477f76b
ms.openlocfilehash: f09a15fd4c115a764f9bf738a00e1b977786397a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223307"
---
# <a name="compiler-warning-level-1-c4154"></a>Ostrzeżenie kompilatora (poziom 1) C4154

usunięcie wyrażenia tablicowego; przekazana konwersja do wskaźnika

Nie można użyć **`delete`** w tablicy, więc kompilator konwertuje tablicę na wskaźnik.

## <a name="example"></a>Przykład

```cpp
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
