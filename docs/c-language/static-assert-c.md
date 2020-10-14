---
title: _Static_assert słowo kluczowe i makro static_assert (C11)
description: Opisuje słowo kluczowe C11 _Static_assert i makro static_assert C11.
ms.date: 10/13/2020
f1_keywords:
- static_assert_c
- _Static_assert
helpviewer_keywords:
- assertions [C], _Static_assert, static_assert
ms.openlocfilehash: dbe49b1dcbb8dd4e0d9df678f4456bc605e01c3f
ms.sourcegitcommit: 651348f8cd92ab0d52f09e9225a7eb41562559db
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "92061020"
---
# <a name="_static_assert-keyword-and-static_assert-macro-c11"></a>_Static_assert słowo kluczowe i makro static_assert (C11)

Testuje potwierdzenie w czasie kompilacji. Jeśli określone wyrażenie stałe ma wartość **`false`** , kompilator Wyświetla określony komunikat i kompilacja kończy się niepowodzeniem z powodu błędu C2338; w przeciwnym razie nie ma żadnego wpływu. Nowość w C11.

**`_Static_assert`** jest słowem kluczowym wprowadzonym w C11.
**`static_assert`** jest makrem wprowadzonym w C11, który jest mapowany do **`_Static_assert`** słowa kluczowego.

## <a name="syntax"></a>Składnia

```C
_Static_assert(constant-expression, string-literal);
static_assert(constant-expression, string-literal);
```

### <a name="parameters"></a>Parametry

*wyrażenie stałe*\
Wyrażenie stałej całkowitej, które może być oceniane w czasie kompilacji. Jeśli wyrażenie ma wartość zero (false), wyświetla parametr *literału ciągu* , a kompilacja kończy się niepowodzeniem z powodu błędu. Jeśli wyrażenie ma wartość różną od zera (true), nie ma żadnego wpływu.

*literał ciągu*\
Komunikat wyświetlany, gdy *stałe wyrażenie* ma wartość zero (false). Komunikat musi zostać utworzony przy użyciu [podstawowego zestawu znaków](../c-language/ascii-character-set.md) kompilatora. Znaki nie mogą być znakami [wielobajtowymi lub szerokimi](../c-language/multibyte-and-wide-characters.md).

## <a name="remarks"></a>Uwagi

**`_Static_assert`** Słowo kluczowe i **`static_assert`** makro testuje potwierdzenie oprogramowania w czasie kompilacji. Mogą one być używane w zakresie globalnym lub funkcji.

Natomiast [makro Assert i _ASSERT i funkcje _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) testują potwierdzenie oprogramowania w czasie wykonywania i wiążą się z kosztem środowiska uruchomieniowego.

**Zachowanie specyficzne dla firmy Microsoft**

W języku C, gdy nie dołączysz `<assert.h>` , kompilator Microsoft Visual C/C++ traktuje się **`static_assert`** jako słowo kluczowe, które mapuje na **`_Static_assert`** . Użycie **`static_assert`** jest preferowane, ponieważ ten sam kod będzie działał zarówno w języku C, jak i C++.

## <a name="example-of-a-compile-time-assert"></a>Przykład potwierdzeń czasu kompilacji

W poniższym przykładzie **`static_assert`** i **`_Static_assert`** są używane do sprawdzania, ile elementów znajduje się w wyliczeniu i że liczby całkowite są 32 bitów.

```C
// requires /std:c11 or higher
#include <assert.h>

enum Items
{
    A,
    B,
    C,
    LENGTH
};

int main()
{
    // _Static_assert is a C11 keyword
    _Static_assert(LENGTH == 3, "Expected Items enum to have three elements");

    // Preferred: static_assert maps to _Static_Assert and is compatible with C++
    static_assert(sizeof(int) == 4, "Expecting 32 bit integers"); 

    return 0;
}
```

## <a name="requirements"></a>Wymagania

|Makro|Wymagany nagłówek|
|-------------|---------------------|
|**`static_assert`**|\<assert.h>|

## <a name="see-also"></a>Zobacz też

[_STATIC_ASSERT makro](../c-runtime-library/reference/static-assert-macro.md)\
[potwierdzj makro i _ASSERT i funkcje _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) 
 [/STD (Określ wersję standardową języka)](../build/reference/std-specify-language-standard-version.md)