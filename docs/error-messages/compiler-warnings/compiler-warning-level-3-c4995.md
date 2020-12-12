---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 3) C4995'
title: Ostrzeżenie kompilatora (poziom 3) C4995
ms.date: 11/04/2016
f1_keywords:
- C4995
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
ms.openlocfilehash: bb63802edf523fb0816bc6aeec289839b99b1110
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332054"
---
# <a name="compiler-warning-level-3-c4995"></a>Ostrzeżenie kompilatora (poziom 3) C4995

"Function": nazwa została oznaczona jako przestarzała #pragma

Kompilator napotkał funkcję, która została oznaczona za pomocą dyrektywy pragma jako [przestarzałą](../../preprocessor/deprecated-c-cpp.md). Przyszła wersja prawdopodobnie nie będzie obsługiwała tej funkcji. To ostrzeżenie można wyłączyć za pomocą dyrektywy pragma [Warning](../../preprocessor/warning.md) (przykład poniżej).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4995:

```cpp
// C4995.cpp
// compile with: /W3
#include <stdio.h>

// #pragma warning(disable : 4995)
void func1(void)
{
    printf("\nIn func1");
}

int main()
{
    func1();
    #pragma deprecated(func1)
    func1();   // C4995
}
```
