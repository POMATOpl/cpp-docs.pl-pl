---
description: 'Dowiedz się więcej na temat: bool (C++)'
title: bool (C++)
ms.date: 11/04/2016
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
ms.openlocfilehash: ea3af17260f21d3724f05b8bbad54091b23203e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229590"
---
# <a name="bool-c"></a>bool (C++)

To słowo kluczowe jest typu wbudowanego. Zmienna tego typu może mieć wartości [`true`](../cpp/true-cpp.md) i [`false`](../cpp/false-cpp.md) . Wyrażenia warunkowe mają typ **`bool`** i dlatego mają wartości typu **`bool`** . Na przykład `i != 0` ma teraz **`true`** lub **`false`** w zależności od wartości `i` .

**Program Visual Studio 2017 w wersji 15,3 lub nowszej** (dostępny w [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)): argument operacji "przyrostka" przyrostkowego lub zmniejszania prefiksu nie może być typu **`bool`** . Innymi słowy, w przypadku zmiennej `b` typu **`bool`** , wyrażenia te nie są już dozwolone:

```cpp
    b++;
    ++b;
    b--;
    --b;
```

Wartości **`true`** i **`false`** mają następującą relację:

```cpp
!false == true
!true == false
```

W poniższej instrukcji:

```cpp
if (condexpr1) statement1;
```

Jeśli `condexpr1` jest **`true`** , `statement1` jest zawsze wykonywane; Jeśli `condexpr1` jest **`false`** , `statement1` nigdy nie jest wykonywane.

Gdy operator przyrostka lub prefiks **`++`** jest stosowany do zmiennej typu **`bool`** , zmienna jest ustawiana na **`true`** .

**Program Visual Studio 2017 w wersji 15,3 i nowszej**: `operator++` dla **`bool`** został usunięty z języka i nie jest już obsługiwany.

Nie można zastosować przyrostka lub operatora prefiksu **`--`** do zmiennej tego typu.

**`bool`** Typ uczestniczy w domyślnych promocjach całkowitych. Wartość r typu **`bool`** może zostać przekonwertowana na wartość r typu **`int`** , przy **`false`** czym staje się zerowa i **`true`** staje się jedną. Jako typ odrębny, **`bool`** uczestniczy w rozwiązywaniu przeciążenia.

## <a name="see-also"></a>Zobacz też

[Słowa kluczowe](../cpp/keywords-cpp.md)<br/>
[Typy wbudowane](../cpp/fundamental-types-cpp.md)
