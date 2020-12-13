---
description: 'Dowiedz się więcej o: 4. Zmienne środowiskowe'
title: 4. Zmienne środowiskowe
ms.date: 01/16/2019
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: 47c0d557497a387f89c13c88c414aae9eb9377ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342533"
---
# <a name="4-environment-variables"></a>4. zmienne środowiskowe

W tym rozdziale opisano zmienne środowiskowe interfejsu API OpenMP C i C++ (lub podobne mechanizmy specyficzne dla platformy) kontrolujące wykonywanie kodu równoległego.  Nazwy zmiennych środowiskowych muszą być pisane wielką literą. Wartości przypisanych do nich nie uwzględniają wielkości liter i mogą zawierać odstępy wiodące i końcowe.  Modyfikacje wartości po rozpoczęciu pracy programu zostały zignorowane.

Zmienne środowiskowe są następujące:

- [OMP_SCHEDULE](#41-omp_schedule) ustawia typ harmonogramu czasu wykonywania i rozmiar fragmentu.
- [OMP_NUM_THREADS](#42-omp_num_threads) ustawia liczbę wątków, które mają być używane podczas wykonywania.
- [OMP_DYNAMIC](#43-omp_dynamic) włącza lub wyłącza dynamiczne dopasowanie liczby wątków.
- [OMP_NESTED](#44-omp_nested) włącza lub wyłącza zagnieżdżoną równoległość.

W przykładach w tym rozdziale przedstawiono tylko te zmienne, które można ustawić w środowiskach powłoki C Shell (CSH). W środowiskach powłoki Korna i systemu DOS działania są podobne:

csh:  
`setenv OMP_SCHEDULE "dynamic"`

ksh:  
`export OMP_SCHEDULE="dynamic"`

ZADAŃ  
`set OMP_SCHEDULE="dynamic"`

## <a name="41-omp_schedule"></a><a name="41-omp_schedule"></a> 4,1 OMP_SCHEDULE

`OMP_SCHEDULE` dotyczy tylko `for` `parallel for` dyrektyw, które mają typ harmonogramu `runtime` . Typ harmonogramu i rozmiar fragmentu dla wszystkich takich pętli można ustawić w czasie wykonywania. Ustaw tę zmienną środowiskową na dowolny rozpoznany typ harmonogramu i opcjonalne *chunk_size*.

Dla `for` dyrektywy i, `parallel for` które mają typ harmonogramu inny niż `runtime` , `OMP_SCHEDULE` jest ignorowany. Wartością domyślną dla tej zmiennej środowiskowej jest zdefiniowana implementacja. Jeśli opcjonalny *chunk_size* jest ustawiony, wartość musi być dodatnia. Jeśli *chunk_size* nie jest ustawiona, zostanie przyjęta wartość 1, z wyjątkiem sytuacji, gdy harmonogram jest `static` . W przypadku `static` harmonogramu domyślny rozmiar fragmentu jest ustawiany na przestrzeń iteracji pętli podzieloną przez liczbę wątków zastosowanych do pętli.

Przykład:

```csh
setenv OMP_SCHEDULE "guided,4"
setenv OMP_SCHEDULE "dynamic"
```

### <a name="cross-references"></a>Odsyłacze

- [dla](2-directives.md#241-for-construct) dyrektywy
- [Parallel dla](2-directives.md#251-parallel-for-construct) dyrektywy

## <a name="42-omp_num_threads"></a><a name="42-omp_num_threads"></a> 4,2 OMP_NUM_THREADS

`OMP_NUM_THREADS`Zmienna środowiskowa ustawia domyślną liczbę wątków do użycia podczas wykonywania. `OMP_NUM_THREADS` jest ignorowany, jeśli ten numer zostanie jawnie zmieniony przez wywołanie `omp_set_num_threads` procedury biblioteki. Jest on również ignorowany, jeśli w dyrektywie występuje jawna `num_threads` klauzula `parallel` .

Wartość `OMP_NUM_THREADS` zmiennej środowiskowej musi być dodatnią liczbą całkowitą. Jego wpływ zależy od tego, czy włączone jest dynamiczne dopasowanie liczby wątków. Aby uzyskać kompleksowy zestaw reguł dotyczących interakcji między `OMP_NUM_THREADS` zmienną środowiskową a dynamicznym dopasowaniem wątków, zobacz [sekcję 2,3](2-directives.md#23-parallel-construct).

Liczba wątków do użycia jest definiowana przez implementację, jeśli:

- `OMP_NUM_THREADS`zmienna środowiskowa nie jest określona,
- określona wartość nie jest dodatnią liczbą całkowitą.
- wartość jest większa niż maksymalna liczba wątków obsługiwanych przez system.

Przykład:

```csh
setenv OMP_NUM_THREADS 16
```

### <a name="cross-references"></a>Odsyłacze

- klauzula [num_threads](2-directives.md#23-parallel-construct)
- Funkcja [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function)
- Funkcja [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function)

## <a name="43-omp_dynamic"></a><a name="43-omp_dynamic"></a> 4,3 OMP_DYNAMIC

`OMP_DYNAMIC`Zmienna środowiskowa włącza lub wyłącza dynamiczne dopasowanie liczby wątków dostępnych do wykonywania regionów równoległych. `OMP_DYNAMIC` jest ignorowany, gdy dynamiczne dopasowanie jest jawnie włączone lub wyłączone przez wywołanie `omp_set_dynamic` procedury biblioteki. Wartość musi być `TRUE` lub `FALSE` .

Jeśli `OMP_DYNAMIC` jest ustawiona na `TRUE` , liczba wątków używanych do wykonywania regionów równoległych może być dostosowywana przez środowisko uruchomieniowe, aby najlepiej wykorzystać zasoby systemowe.  Jeśli `OMP_DYNAMIC` jest ustawiona na `FALSE` , dynamiczne dopasowanie jest wyłączone. Domyślnym warunkiem jest zdefiniowana implementacja.

Przykład:

```csh
setenv OMP_DYNAMIC TRUE
```

### <a name="cross-references"></a>Odsyłacze

- [Równoległe regiony](2-directives.md#23-parallel-construct)
- Funkcja [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function)

## <a name="44-omp_nested"></a><a name="44-omp_nested"></a> 4,4 OMP_NESTED

`OMP_NESTED`Zmienna środowiskowa włącza lub wyłącza zagnieżdżoną równoległość, chyba że zagnieżdżona równoległość jest włączona lub wyłączona przez wywołanie `omp_set_nested` procedury biblioteki. Jeśli `OMP_NESTED` jest ustawiona na `TRUE` , zagnieżdżona równoległość jest włączona. Jeśli `OMP_NESTED` jest ustawiona na `FALSE` , zagnieżdżona równoległość jest wyłączona. Wartość domyślna to `FALSE`.

Przykład:

```csh
setenv OMP_NESTED TRUE
```

### <a name="cross-reference"></a>Odwołanie krzyżowe

- Funkcja [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function)
