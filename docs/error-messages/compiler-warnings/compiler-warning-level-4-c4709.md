---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4709'
title: Ostrzeżenie kompilatora (poziom 4) C4709
ms.date: 11/04/2016
f1_keywords:
- C4709
helpviewer_keywords:
- C4709
ms.assetid: 8abfdd45-8c70-4c27-b0fb-ca0c3f0fccf9
ms.openlocfilehash: 3138b8d95fd05cac113166ee9de9e7979f08223d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136230"
---
# <a name="compiler-warning-level-4-c4709"></a>Ostrzeżenie kompilatora (poziom 4) C4709

operator przecinka wewnątrz wyrażenia indeksu tablicy

Gdy przecinek występuje w wyrażeniu indeksu tablicy, kompilator używa wartości po ostatnim przecinku.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4709:

```cpp
// C4709.cpp
// compile with: /W4
#include <stdio.h>

int main()
{
    int arr[2][2];
    arr[0][0] = 10;
    arr[0][1] = 11;

    // Prints 10, not 11
    printf_s("\n%d",arr[0][1,0]);   // C4709
}
```
