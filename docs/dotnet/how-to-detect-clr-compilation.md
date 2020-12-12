---
description: 'Dowiedz się więcej na temat: Jak wykryć kompilację/CLR'
title: 'Instrukcje: Wykrywanie kompilacji CLR'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, detecting /clr
- /clr compiler option [C++], detecting use of
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
ms.openlocfilehash: 25cd241a08f79bcae629c05fb3c7982a387120ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175719"
---
# <a name="how-to-detect-clr-compilation"></a>Porady: wykrywanie kompilacji /clr

Użyj `_MANAGED` makra lub, `_M_CEE` Aby sprawdzić, czy moduł został skompilowany z **/CLR**. Aby uzyskać więcej informacji, zobacz [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../build/reference/clr-common-language-runtime-compilation.md).

Aby uzyskać więcej informacji na temat makr, zobacz [wstępnie zdefiniowane makra](../preprocessor/predefined-macros.md).

## <a name="example"></a>Przykład

```cpp
// detect_CLR_compilation.cpp
// compile with: /clr
#include <stdio.h>

int main() {
   #if (_MANAGED == 1) || (_M_CEE == 1)
      printf_s("compiling with /clr\n");
   #else
      printf_s("compiling without /clr\n");
   #endif
}
```

## <a name="see-also"></a>Zobacz także

[Korzystanie z międzyoperacyjności języka C++ (niejawne PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
