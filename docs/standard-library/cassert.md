---
description: 'Dowiedz się więcej na temat: &lt; cassert&gt;'
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: e2b515fe492e6847c4d0cc5841dc43a2d879dd99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325359"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

Zawiera nagłówek standardowej biblioteki C \<assert.h> i dodaje skojarzone nazwy do `std` przestrzeni nazw. Dołączenie tego nagłówka zapewnia, że nazwy zadeklarowane za pomocą zewnętrznego powiązania w nagłówku standardowej biblioteki C są deklarowane w `std` przestrzeni nazw.

> [!NOTE]
> \<assert.h> nie definiuje **`static_assert`** makra.

## <a name="syntax"></a>Składnia

```cpp
#include <cassert>
```

## <a name="macros"></a>Makra

```cpp
#define assert(E)
```

### <a name="remarks"></a>Uwagi

`assert(E)` jest tylko stałą, jeśli NDEBUG jest zdefiniowany, gdzie jest zdefiniowana jako `assert` Ostatnia zdefiniowana lub ponownie zdefiniowana, lub wartość *E* konwertowana na bool jest równa **`true`** .

## <a name="see-also"></a>Zobacz też

[potwierdzj makro, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)\
[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[Omówienie standardowej biblioteki języka C++](../standard-library/cpp-standard-library-overview.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
