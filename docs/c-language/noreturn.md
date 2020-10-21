---
title: _Noreturn słowo kluczowe i noreturn makro (C11)
description: Opisuje `_Noreturn` słowo kluczowe i `noreturn` makro.
ms.date: 10/19/2020
f1_keywords:
- _Noreturn_c
- noreturn
helpviewer_keywords:
- keywords [C]
ms.openlocfilehash: 68448d8b8c999c92fb240100c25048fa94a559b9
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274691"
---
# <a name="_noreturn-keyword-and-noreturn-macro-c11"></a>`_Noreturn` słowo kluczowe i `noreturn` makro (C11)

`_Noreturn`Słowo kluczowe zostało wprowadzone w C11. Informuje kompilator, że funkcja, która jest stosowana, nie zwraca do obiektu wywołującego. Kompilator wie, że kod następujący po wywołaniu `_Noreturn` funkcji jest nieosiągalny. Przykład funkcji, która nie zwraca wartości, jest [przerywana](../c-runtime-library/reference/abort.md). Jeśli istnieje możliwość, aby przepływ sterowania był zwracany do obiektu wywołującego, funkcja nie może mieć `_Noreturn` atrybutu.

Słowo kluczowe jest zwykle używane przez wygodne makro, które znajduje się `noreturn` w <stdnoreturn. h>, które mapuje do `_Noreturn` słowa kluczowego.

Główną zaletą korzystania z programu `_Noreturn` (lub równoważnego `noreturn` ) jest zamiar funkcji jasnej w kodzie dla przyszłych czytelników i wykrywania niecelowo nieosiągalnego kodu.

Funkcja oznaczona jako `noreturn` nie powinna zawierać zwracanego typu, ponieważ nie zwraca wartości do obiektu wywołującego. Powinna ona mieć wartość `void`.

## <a name="example-using-noreturn-macro-and-_noreturn-keyword"></a>Przykład użycia `noreturn` makra i `_Noreturn ` słowa kluczowego

Poniższy przykład demonstruje `_Noreturn` słowo kluczowe i równoważne `noreturn` makro.

Funkcja IntelliSense może wygenerować błąd fałszywe, `E0065` w przypadku użycia makra `noreturn` , które można zignorować. Nie uniemożliwia to uruchomienia przykładu.

```C
// Compile with Warning Level4 (/W4) and /std:c11
#include <stdio.h>
#include <stdlib.h>
#include <stdnoreturn.h>

noreturn void fatal_error(void)
{
    exit(3);
}

_Noreturn void not_coming_back(void)
{
    puts("There's no coming back");
    fatal_error();
    return; // warning C4645 - function declared with noreturn has a return statement
}

void done(void)
{
    puts("We'll never get here");
}

int main(void)
{
    not_coming_back();
    done(); // warning c4702 - unreachable code

    return 0;
}
```

## <a name="requirements"></a>Wymagania

|Makro|Wymagany nagłówek|
|-------------|---------------------|
|**`noreturn`**|\<stdnoreturn.h>|

## <a name="see-also"></a>Zobacz też

[/STD (Określ wersję standardową języka)](../build/reference/std-specify-language-standard-version.md)\
[/W4 (Określ poziom ostrzeżeń)](../build/reference/compiler-option-warning-level.md)\
[Ostrzeżenie C4702](../error-messages\compiler-warnings\compiler-warning-level-4-c4702.md)\
[__declspec (noreturn)](../cpp/noreturn.md)
