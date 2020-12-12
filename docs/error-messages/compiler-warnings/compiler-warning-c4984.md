---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4984'
title: Ostrzeżenie kompilatora C4984
ms.date: 08/19/2019
f1_keywords:
- C4984
helpviewer_keywords:
- C4984
ms.openlocfilehash: 5a6708a1063baf8fa4b5feece65eabd93df7bbeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326003"
---
# <a name="compiler-warning-c4984"></a>Ostrzeżenie kompilatora C4984

> "If constexpr" jest rozszerzeniem języka C++ 17

## <a name="remarks"></a>Uwagi

Kompilator znalazł `if constexpr` wyrażenie w kodzie skompilowane przy użyciu domyślnego standardu c++ 14. To wyrażenie jest określone począwszy od standardu C++ 17. Jeśli jest wymagana zgodność z językiem C++ 11 lub C++ 14, to wyrażenie nie jest przenośne.

C4984 jest domyślnie wystawiany jako błąd, ale jest suppressible. Aby włączyć to wyrażenie, kompilując kod jako C++ 17, użyj [/std: c++ 17 lub/std: C + + Najnowsza](../../build/reference/std-specify-language-standard-version.md). Aby użyć `if constexpr` wyrażenia w kodzie skompilowanym dla języka c++ 14 jako rozszerzenia Microsoft, można pominąć, wyłączyć lub zmienić poziom ostrzeżeń komunikatu o błędzie. Można użyć [/wd4984](../../build/reference/compiler-option-warning-level.md) , aby wyłączyć C4984, lub __/w__*N*__4984__ , aby włączyć ją jako poziom *N* ostrzeżenie, a nie błąd. Lub Użyj [ostrzeżenia #pragma (Pomiń: 4984)](../../preprocessor/warning.md) przed wierszem, który powoduje ostrzeżenie w pliku źródłowym.

To ostrzeżenie jest dostępne począwszy od programu Visual Studio 2017 w wersji 15,3. Aby uzyskać informacje na temat sposobu wyłączania ostrzeżeń wprowadzonych w określonej wersji kompilatora lub nowszych, zobacz [ostrzeżenia kompilatora według wersji kompilatora](compiler-warnings-by-compiler-version.md).

## <a name="example"></a>Przykład

Ten przykład generuje C4984 i pokazuje sposoby jego rozwiązania:

```cpp
// C4984.cpp
// compile with: cl /EHsc C4984.cpp
#include <iostream>

int main()
{
    constexpr bool compile_time = true;
    // Uncomment the following line or use /std:c++17 to fix
    // #pragma warning(suppress:4984)
    if constexpr (compile_time)
    {
        std::cout << "compile_time is true";
    }
    else
    {
        std::cout << "compile_time is false";
    }
}
```
