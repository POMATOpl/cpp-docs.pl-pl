---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4668'
title: Ostrzeżenie kompilatora (poziom 4) C4668
ms.date: 11/04/2016
f1_keywords:
- C4668
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
ms.openlocfilehash: 559043027bf9fab38470223ea7735ca70297aabf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134059"
---
# <a name="compiler-warning-level-4-c4668"></a>Ostrzeżenie kompilatora (poziom 4) C4668

'symbol' nie jest zdefiniowany jako makro preprocesora, zastępowanie przez '0' dla 'dyrektywy'

Symbol, który nie został zdefiniowany, został użyty z dyrektywą preprocesora. Symbol zostanie obliczony na wartość false. Aby zdefiniować symbol, można użyć [dyrektywy #define](../../preprocessor/hash-define-directive-c-cpp.md) lub [/d](../../build/reference/d-preprocessor-definitions.md) kompilatora.

To ostrzeżenie jest domyślnie wyłączone. Aby uzyskać więcej informacji [, zobacz ostrzeżenia kompilatora, które są domyślnie wyłączone](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C4668:

```cpp
// C4668.cpp
// compile with: /W4
#include <stdio.h>

#pragma warning (default : 4668)   // turn warning on

int main()
{
    #if q   // C4668, q is not defined
        printf_s("defined");
    #else
        printf_s("undefined");
    #endif
}
```
