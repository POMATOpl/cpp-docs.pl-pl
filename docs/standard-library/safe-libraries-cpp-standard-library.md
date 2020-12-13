---
description: 'Dowiedz się więcej na temat: bezpieczne biblioteki: standardowa biblioteka C++'
title: 'Bezpieczne biblioteki: Standardowa biblioteka C++'
ms.date: 11/04/2016
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
ms.openlocfilehash: 7027031054bf9ef7c2a157d6162539bc3801dec4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148892"
---
# <a name="safe-libraries-c-standard-library"></a>Bezpieczne biblioteki: Standardowa biblioteka C++

Do bibliotek dostarczanych z programem Microsoft C++, w tym standardowej biblioteki języka C++, wprowadzono kilka ulepszeń, które zwiększają ich bezpieczeństwo.

Kilka metod w standardowej bibliotece języka C++ została zidentyfikowana jako potencjalnie niebezpieczna, ponieważ mogą one prowadzić do przepełnienia buforu lub innej wady kodu. Korzystanie z tych metod jest niezalecane, a nowe, bardziej bezpieczne metody zostały utworzone w celu ich zastąpienia. Wszystkie te nowe metody kończą się `_s` .

Wprowadzono również kilka ulepszeń, które zwiększają bezpieczeństwo iteratorów i algorytmów. Aby uzyskać więcej informacji, zobacz [sprawdzone Iteratory](../standard-library/checked-iterators.md), [Obsługa iteratora debugowania](../standard-library/debug-iterator-support.md) i [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Uwagi

W poniższej tabeli wymieniono metody standardowej biblioteki języka C++, które są potencjalnie niebezpieczne, a także ich bezpieczniejszy odpowiednik:

|Potencjalnie niebezpieczna Metoda|Bezpieczniejszy odpowiednik|
|-------------------------------|----------------------|
|[kopiowane](../standard-library/basic-string-class.md#copy)|[basic_string:: _Copy_s](../standard-library/basic-string-class.md#copy_s)|
|[kopiowane](../standard-library/char-traits-struct.md#copy)|[char_traits:: _Copy_s](../standard-library/char-traits-struct.md#copy_s)|

W przypadku wywołania jednej z potencjalnie niebezpiecznych metod powyżej lub w przypadku nieprawidłowego użycia iteratorów kompilator generuje [Ostrzeżenie kompilatora (poziom 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Aby uzyskać informacje na temat sposobu wyłączania tych ostrzeżeń, zobacz [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

## <a name="in-this-section"></a>W tej sekcji

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)

[_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)

[Sprawdzone Iteratory](../standard-library/checked-iterators.md)

[Obsługa iteratora debugowania](../standard-library/debug-iterator-support.md)

## <a name="see-also"></a>Zobacz też

[Omówienie standardowej biblioteki języka C++](../standard-library/cpp-standard-library-overview.md)
