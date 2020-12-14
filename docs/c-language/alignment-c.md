---
title: Wyrównanie (C11)
description: Opisuje wyrównanie typu Microsoft Visual C
ms.date: 12/10/2020
helpviewer_keywords:
- _Alignof keyword [C]
- _Alignas keyword [C]
- memory, alignment
ms.openlocfilehash: 051987ae705f84d7d4972398f742143f14b53e2b
ms.sourcegitcommit: be469dd87453255b0e35e333712c8207b09b3dd4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/14/2020
ms.locfileid: "97440662"
---
# <a name="alignment-c11"></a>Wyrównanie (C11)

Jedną z funkcji niskiego poziomu języka C jest możliwość określania precyzyjnego wyrównania obiektów w pamięci w celu maksymalnego wykorzystania architektury sprzętu.

Procesor CPU odczytuje i zapisuje pamięć wydajniej, gdy dane są przechowywane w adresie, który jest wielokrotnością rozmiaru danych. Na przykład 4-bajtowa liczba całkowita jest używana bardziej wydajnie, jeśli jest przechowywana w adresie, który jest wielokrotnością 4. Gdy dane nie są wyrównane, procesor CPU wykonuje więcej zadań, aby uzyskać dostęp do danych.

Domyślnie kompilator wyrównuje dane na podstawie jego rozmiaru: **`char`** na granicy 1-bajtowej, **`short`** na granicy 2-bajtowej,, **`int`** **`long`** i **`float`** na granicy 4-bajtowej, **`double`** w granicach 8-bajtowych i tak dalej.

Ponadto poprzez wyrównywanie często używanych danych przy użyciu rozmiaru wiersza pamięci podręcznej procesora można poprawić wydajność pamięci podręcznej. Na przykład, jeśli zdefiniujesz strukturę o rozmiarze mniejszym niż 32 bajtów, możesz chcieć wyrównać 32-bajtowe wyrównanie, aby zapewnić wydajne buforowanie wystąpień struktury.

Zazwyczaj nie trzeba martwić się o wyrównanie. Kompilator ogólnie wyrównuje dane z naturalnych granic, które są oparte na procesorze docelowym i rozmiarze danych. Dane są wyrównane do 4-bajtowych granic na 32-bitowych procesorach i 8-bajtowych granicach na procesorach 64-bitowych. W niektórych przypadkach można jednak uzyskać ulepszenia wydajności lub oszczędności pamięci, określając niestandardowe wyrównanie struktur danych.

Użyj słowa kluczowego C11 **`_Alignof`** , aby uzyskać preferowane wyrównanie typu lub zmiennej, a **`_Alignas`** także określić niestandardowe wyrównanie dla zmiennej lub typu zdefiniowanego przez użytkownika.

Wygodne makra **`alignof`** i **`alignas`** zdefiniowane w programie `<stdalign.h>` mapują się bezpośrednio do **`_Alignof`** i **`_Alignas`** , odpowiednio. Te makra pasują do słów kluczowych używanych w języku C++. Użycie makr zamiast słów kluczowych języka C może być przydatne w przypadku przenoszenia kodu w przypadku współdzielenia kodu między tymi dwoma językami.

## <a name="alignas-and-_alignas-c11"></a>`alignas` i `_Alignas` (C11)

Użyj **`alignas`** lub **`_Alignas`** , aby określić niestandardowe wyrównanie dla zmiennej lub typu zdefiniowanego przez użytkownika. Można je stosować do struktury, Unii, wyliczenia lub zmiennej.

### <a name="alignas-syntax"></a>`alignas` obowiązuje

```c
alignas(type)
alignas(constant-expression)
_Alignas(type)
_Alignas(constant-expression)
```

### <a name="remarks"></a>Uwagi

`_Alignas` nie można użyć w deklaracji elementu typedef, bitowego-pola, funkcji, parametru funkcji lub obiektu zadeklarowanego za pomocą `register` specyfikatora.

Określ wyrównanie, które jest potęgą dwóch takich jak 1, 2, 4, 8, 16 i tak dalej. Nie używaj wartości mniejszej niż rozmiar typu.

Struktury i związki mają wyrównanie równe największemu wyrównaniu każdego elementu członkowskiego. Bajty uzupełniania są dodawane w strukturach, aby upewnić się, że są spełnione wymagania dotyczące wyrównania poszczególnych elementów członkowskich.

Jeśli **`alignas`**  w deklaracji występuje wiele specyfikatorów (na przykład struktury z kilkoma elementami członkowskimi, które mają różne **`alignas`** specyfikatory), wyrównanie struktury będzie takie jak największa.

### <a name="alignas-example"></a>`alignas` przyklad

W tym przykładzie jest stosowane wygodne makro, **`alignof`** ponieważ jest ono przenośne w języku C++. Zachowanie jest takie samo, jeśli używasz `_Alignof` .

```c
// Compile with /std:c11

#include <stdio.h>
#include <stdalign.h>

typedef struct 
{
    int value; // aligns on a 4-byte boundary. There will be 28 bytes of padding between value and alignas
    alignas(32) char alignedMemory[32]; // assuming a 32 byte friendly cache alignment
} cacheFriendly; // this struct will be 32-byte aligned because alignedMemory is 32-byte alligned and is the largest alignment specified in the struct

int main()
{
    printf("sizeof(cacheFriendly): %d\n", sizeof(cacheFriendly)); // 4 bytes for int value + 32 bytes for alignedMemory[] + padding to ensure  alignment
    printf("alignof(cacheFriendly): %d\n", alignof(cacheFriendly)); // 32 because alignedMemory[] is aligned on a 32-byte boundary

    /* output
        sizeof(cacheFriendly): 64
        alignof(cacheFriendly): 32
    */
}
```

## <a name="alignof-and-_alignof-c11"></a>`alignof` i `_Alignof` (C11)

`_Alignof` zwraca wyrównanie w bajtach określonego typu. Zwraca wartość typu `size_t` .

### <a name="alignof-syntax"></a>`alignof` obowiązuje

```cpp
alignof(type)
_Alignof(type)
```

### <a name="alignof-example"></a>`alignof` przyklad

W tym przykładzie jest stosowane wygodne makro, **`alignof`** ponieważ jest ono przenośne w języku C++. Zachowanie jest takie samo, jeśli używasz `_Alignof` .

```c
// Compile with /std:c11

#include <stdalign.h>
#include <stdio.h>

int main()
{
    size_t alignment = alignof(short);
    printf("alignof(short) = %d\n", alignment); // 2
    printf("alignof(int) = %d\n", alignof(int)); // 4
    printf("alignof(long) = %d\n", alignof(long)); // 4
    printf("alignof(float) = %d\n", alignof(float)); // 4
    printf("alignof(double) = %d\n", alignof(double)); // 8

    typedef struct
    {
        int a;
        double b;
    } test;

    printf("alignof(test) = %d\n", alignof(test)); // 8 because that is the alignment of the largest element in the structure

    /* output
        
       alignof(short) = 2
       alignof(int) = 4
       alignof(long) = 4
       alignof(float) = 4
       alignof(double) = 8
       alignof(test) = 8
    */
}
```

## <a name="requirements"></a>Wymagania

wymagana jest wartość [std: c++ 11](../build/reference/std-specify-language-standard-version.md) lub nowsza.

Windows SDK w wersji 10.0.20201.0 lub nowszej. Ta wersja jest obecnie kompilacją programu testowego, którą można pobrać z [wersji zapoznawczej programu Windows Preview](https://www.microsoft.com/software-download/windowsinsiderpreviewSDK). Aby uzyskać instrukcje dotyczące instalowania i używania tego zestawu SDK, zobacz [C11 i C17: wprowadzenie](https://devblogs.microsoft.com/cppblog/c11-and-c17-standard-support-arriving-in-msvc/#c11-and-c17-getting-started) .

## <a name="see-also"></a>Zobacz także

[`/std` (Określ wersję standardową języka)](../build/reference/std-specify-language-standard-version.md)\
[C++ `alignof` i `alignas`](../cpp/alignment-cpp-declarations.md#alignof-and-alignas)\
[Obsługa wyrównania danych przez kompilator](../cpp/alignment-cpp-declarations.md#compiler-handling-of-data-alignment)