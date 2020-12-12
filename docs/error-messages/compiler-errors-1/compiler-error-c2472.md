---
description: 'Dowiedz się więcej o: błąd kompilatora C2472'
title: Błąd kompilatora C2472
ms.date: 11/04/2016
f1_keywords:
- C2472
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
ms.openlocfilehash: a1d4d668c1e7151771a2df85e888384c6c3ea028
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164500"
---
# <a name="compiler-error-c2472"></a>Błąd kompilatora C2472

> nie można wygenerować *funkcji "Function*" w zarządzanym kodzie: "*Message*"; Kompiluj z/CLR, aby wygenerować mieszany obraz

## <a name="remarks"></a>Uwagi

Ten błąd występuje, gdy typy nieobsługiwane przez kod zarządzany są używane w środowisku środowiska uruchomieniowego języka wspólnego (CLR). Skompiluj z **/CLR** , aby rozwiązać ten problem.

**/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i nieobsługiwane w programie Visual Studio 2017.

## <a name="example"></a>Przykład

Poniższy przykład generuje C2472.

```cpp
// C2472.cpp
// compile with: /clr:pure
// C2472 expected

#include <cstdlib>

int main()
{
   int * __ptr32 p32;
   int * __ptr64 p64;

   p32 = (int * __ptr32)malloc(4);
   p64 = p32;
}
```

## <a name="see-also"></a>Zobacz też

- [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md)
