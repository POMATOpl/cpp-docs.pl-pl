---
description: 'Dowiedz się więcej na temat: _HAS_ITERATOR_DEBUGGING'
title: _HAS_ITERATOR_DEBUGGING
ms.date: 11/04/2016
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
ms.openlocfilehash: ee1765739624fe7c6fccd41ff84f455d5f90cc42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231995"
---
# <a name="_has_iterator_debugging"></a>_HAS_ITERATOR_DEBUGGING

Zastępujący przez [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), to makro definiuje, czy funkcja debugowania iteratora jest włączona w kompilacji debugowania. Domyślnie debugowanie iteratora jest włączone w kompilacjach debugowania i wyłączone w kompilacjach detalicznych. Aby uzyskać więcej informacji, zobacz [Obsługa iteratora debugowania](../standard-library/debug-iterator-support.md).

> [!IMPORTANT]
> Bezpośrednie użycie makra _HAS_ITERATOR_DEBUGGING jest przestarzałe. Zamiast tego należy użyć _ITERATOR_DEBUG_LEVEL, aby kontrolować ustawienia debugowania iteratora. Aby uzyskać więcej informacji, zobacz [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Uwagi

Aby włączyć debugowanie iteratora w kompilacjach debugowania, ustaw _ITERATOR_DEBUG_LEVEL na 2. Jest to równoznaczne z ustawieniem _HAS_ITERATOR_DEBUGGING równym 1 lub włączonym:

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

Nie można ustawić wartości 2 dla _ITERATOR_DEBUG_LEVEL (i _HAS_ITERATOR_DEBUGGING nie można ustawić na 1) w kompilacjach detalicznych.

Aby wyłączyć Iteratory debugowania w kompilacjach debugowania, ustaw _ITERATOR_DEBUG_LEVEL na 0 lub 1. Jest to równoznaczne z ustawieniem _HAS_ITERATOR_DEBUGGING równym 0 lub wyłączone:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>Zobacz też

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[Obsługa iteratora debugowania](../standard-library/debug-iterator-support.md)\
[Sprawdzone Iteratory](../standard-library/checked-iterators.md)\
[Bezpieczne biblioteki: standardowa biblioteka C++](../standard-library/safe-libraries-cpp-standard-library.md)
