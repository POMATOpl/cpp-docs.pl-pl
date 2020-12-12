---
description: 'Dowiedz się więcej na temat: _SECURE_SCL'
title: _SECURE_SCL
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
ms.openlocfilehash: 1a0e32ada449709a60eb601138ce0bb8b7ae9123
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197104"
---
# <a name="_secure_scl"></a>_SECURE_SCL

Zastępujący przez [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), to makro określa, czy są włączone [Iteratory sprawdzane](../standard-library/checked-iterators.md) . Domyślnie zaznaczone Iteratory są włączane w kompilacjach debugowania i wyłączone w kompilacjach detalicznych.

> [!IMPORTANT]
> Bezpośrednie użycie makra _SECURE_SCL jest przestarzałe. Zamiast tego należy użyć _ITERATOR_DEBUG_LEVEL, aby kontrolować zaznaczone ustawienia iteratora. Aby uzyskać więcej informacji, zobacz [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Uwagi

Gdy wybrane Iteratory są włączone, niebezpieczne użycie iteratora powoduje błąd w czasie wykonywania, a program zostaje przerwany. Aby włączyć sprawdzone Iteratory, ustaw _ITERATOR_DEBUG_LEVEL na 1 lub 2. Jest to równoznaczne z ustawieniem _SECURE_SCL równym 1 lub włączonym:

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

Aby wyłączyć sprawdzone Iteratory, ustaw wartość _ITERATOR_DEBUG_LEVEL na 0. Jest to równoznaczne z ustawieniem _SECURE_SCL równym 0 lub wyłączone:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

Aby uzyskać informacje na temat sposobu wyłączania ostrzeżeń dotyczących sprawdzonych iteratorów, zobacz [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

## <a name="see-also"></a>Zobacz też

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[Sprawdzone Iteratory](../standard-library/checked-iterators.md)\
[Obsługa iteratora debugowania](../standard-library/debug-iterator-support.md)\
[Bezpieczne biblioteki: standardowa biblioteka C++](../standard-library/safe-libraries-cpp-standard-library.md)
