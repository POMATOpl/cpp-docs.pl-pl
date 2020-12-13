---
description: 'Dowiedz się więcej o: błąd kompilatora C2457'
title: Błąd kompilatora C2457
ms.date: 11/04/2016
f1_keywords:
- C2457
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
ms.openlocfilehash: 1fea5192b97e280a38f674a67b0bf739041ffe97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332364"
---
# <a name="compiler-error-c2457"></a>Błąd kompilatora C2457

> "*makro*": wstępnie zdefiniowane makro nie może występować poza treścią funkcji

Podjęto próbę użycia wstępnie zdefiniowanego makra, takiego jak [&#95;&#95;funkcji&#95;&#95;](../../preprocessor/predefined-macros.md), w obszarze globalnym.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2457, a także wyświetla poprawne użycie:

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```
