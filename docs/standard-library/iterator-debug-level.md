---
description: 'Dowiedz się więcej na temat: _ITERATOR_DEBUG_LEVEL'
title: _ITERATOR_DEBUG_LEVEL
ms.date: 11/04/2016
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
ms.openlocfilehash: 769b7f3a8eecd3c994ee82b67385f080f0945f33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306641"
---
# <a name="_iterator_debug_level"></a>_ITERATOR_DEBUG_LEVEL

Makro _ITERATOR_DEBUG_LEVEL kontroluje, czy są włączone [sprawdzone Iteratory](../standard-library/checked-iterators.md) i [obsługujące Iteratory debugowania](../standard-library/debug-iterator-support.md) . To makro zastępuje i łączy funkcjonalność starszych _SECURE_SCL i _HAS_ITERATOR_DEBUGGING makr.

## <a name="macro-values"></a>Wartości makr

Poniższa tabela zawiera podsumowanie możliwych wartości dla makra _ITERATOR_DEBUG_LEVEL.

|Tryb kompilacji|Wartość makra|Opis|
|----------------------|----------------|-----------------|
|**Debugowanie**|||
||0|Wyłącza sprawdzone Iteratory i wyłącza debugowanie iteratora.|
||1|Włącza sprawdzone Iteratory i wyłącza debugowanie iteratora.|
||2 (wartość domyślna)|Włącza debugowanie iteratora; sprawdzone Iteratory nie są istotne.|
|**Wersja**|||
||0 (wartość domyślna)|Wyłącza sprawdzone Iteratory.|
||1|Włącza sprawdzone Iteratory; Debugowanie iteratora nie jest istotne.|

W trybie wydania kompilator generuje błąd, jeśli określono _ITERATOR_DEBUG_LEVEL jako 2.

## <a name="remarks"></a>Uwagi

Makro _ITERATOR_DEBUG_LEVEL kontroluje, czy są włączone [Iteratory sprawdzane](../standard-library/checked-iterators.md) , i w trybie debugowania, czy jest włączona [Obsługa iteratora debugowania](../standard-library/debug-iterator-support.md) . Jeśli _ITERATOR_DEBUG_LEVEL jest zdefiniowany jako 1 lub 2, sprawdzane Iteratory zapewniają, że granice kontenerów nie są zastępowane. Jeśli _ITERATOR_DEBUG_LEVEL ma wartość 0, Iteratory nie są sprawdzane. Gdy _ITERATOR_DEBUG_LEVEL jest zdefiniowany jako 1, wszelkie niebezpieczne użycie iteratora powoduje błąd w czasie wykonywania, a program zostaje zakończony. Gdy _ITERATOR_DEBUG_LEVEL jest zdefiniowany jako 2, niebezpieczne użycie iteratora powoduje wyświetlenie okna dialogowego błędu w czasie wykonywania, które umożliwia przerwanie w debugerze.

Ponieważ makro _ITERATOR_DEBUG_LEVEL obsługuje podobną funkcjonalność do makr _SECURE_SCL i _HAS_ITERATOR_DEBUGGING, można nie określać, które wartości makr i makr mają być używane w określonej sytuacji. Aby uniknąć nieporozumień, zalecamy użycie tylko makra _ITERATOR_DEBUG_LEVEL. W tej tabeli opisano odpowiednik wartości makra _ITERATOR_DEBUG_LEVEL, która ma być używana dla różnych wartości _SECURE_SCL i _HAS_ITERATOR_DEBUGGING w istniejącym kodzie.

|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0 (wydanie domyślne)|0 (wyłączone)|0 (wyłączone)|
|1|1 (włączone)|0 (wyłączone)|
|2 (Debuguj domyślnie)|(nie dotyczy)|1 (włączone w trybie debugowania)|

Aby uzyskać informacje na temat sposobu wyłączania ostrzeżeń dotyczących sprawdzonych iteratorów, zobacz [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

### <a name="example"></a>Przykład

Aby określić wartość dla makra _ITERATOR_DEBUG_LEVEL, należy użyć [/d](../build/reference/d-preprocessor-definitions.md) kompilatora, aby zdefiniować go w wierszu polecenia lub użyć `#define` przed dołączeniem nagłówków standardowej biblioteki C++ do plików źródłowych. Na przykład w wierszu polecenia, aby skompilować *przykład. cpp* w trybie debugowania i korzystać z obsługi iteratora debugowania, można określić definicję makra _ITERATOR_DEBUG_LEVEL:

`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`

W pliku źródłowym należy określić makro przed nagłówki biblioteki standardowej, które definiują Iteratory.

```cpp
// sample.cpp

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>

// ...
```

## <a name="see-also"></a>Zobacz też

[Sprawdzone Iteratory](../standard-library/checked-iterators.md)\
[Obsługa iteratora debugowania](../standard-library/debug-iterator-support.md)\
[Bezpieczne biblioteki: standardowa biblioteka C++](../standard-library/safe-libraries-cpp-standard-library.md)
