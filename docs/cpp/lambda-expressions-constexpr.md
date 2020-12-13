---
description: Dowiedz się więcej na temat wyrażeń lambda w języku C++
title: wyrażenia lambda constexpr w języku C++
ms.date: 04/08/2019
helpviewer_keywords:
- lambda expressions [C++], constexpr
ms.assetid: b56346cd-fbff-475f-aeaa-ed2010c6d6f7
ms.openlocfilehash: 4ff4b3acf4289a74f8b7320620601e0e2284d356
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333933"
---
# <a name="constexpr-lambda-expressions-in-c"></a>wyrażenia lambda constexpr w języku C++

**Visual Studio 2017 w wersji 15,3 lub nowszej** (dostępny w [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)): wyrażenie lambda może być zadeklarowane jako **`constexpr`** lub używane w wyrażeniu stałym, gdy Inicjalizacja każdego elementu członkowskiego, który przechwytuje lub wprowadził, jest dozwolony w wyrażeniu stałym.

```cpp
    int y = 32;
    auto answer = [y]() constexpr
    {
        int x = 10;
        return y + x;
    };

    constexpr int Increment(int n)
    {
        return [n] { return n + 1; }();
    }
```

Wyrażenie lambda jest niejawnie, **`constexpr`** jeśli jego wynik spełnia wymagania **`constexpr`** funkcji:

```cpp
    auto answer = [](int n)
    {
        return 32 + n;
    };

    constexpr int response = answer(10);
```

Jeśli wyrażenie lambda jest niejawnie lub jawnie **`constexpr`** i zostanie przekonwertowane na wskaźnik funkcji, wynikiem funkcji jest również **`constexpr`** :

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja języka C++](../cpp/cpp-language-reference.md)<br/>
[Obiekty funkcji w standardowej bibliotece języka C++](../standard-library/function-objects-in-the-stl.md)<br/>
[Wywołanie funkcji](../cpp/function-call-cpp.md)<br/>
[for_each](../standard-library/algorithm-functions.md#for_each)
