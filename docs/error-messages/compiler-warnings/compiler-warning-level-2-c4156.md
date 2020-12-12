---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 2) C4156'
title: Ostrzeżenie kompilatora (poziom 2) C4156
ms.date: 11/04/2016
f1_keywords:
- C4156
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
ms.openlocfilehash: 243652ec191e315d7ad06a571c78a1dedce0f032
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326494"
---
# <a name="compiler-warning-level-2-c4156"></a>Ostrzeżenie kompilatora (poziom 2) C4156

usunięcie wyrażenia tablicowego bez użycia formularza tablicy "Delete"; zastąpiono formularz tablicy

Forma nietablicowa **`delete`** nie może usunąć tablicy. Kompilator tłumaczony **`delete`** na formularz tablicowy.

To ostrzeżenie występuje tylko w ramach rozszerzeń Microsoft (/ze).

## <a name="example"></a>Przykład

```cpp
// C4156.cpp
// compile with: /W2
int main()
{
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];
   delete array; // C4156, changed by compiler to "delete [] array;"
}
```
