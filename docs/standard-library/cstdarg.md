---
title: '&lt;cstdarg&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdarg>
helpviewer_keywords:
- cstdarg header
ms.assetid: 639b4ef7-8408-4640-9343-41631f0ab663
ms.openlocfilehash: f8d2d3b886cfa46905e8f17f1e13b51881b80191
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244487"
---
# <a name="ltcstdarggt"></a>&lt;cstdarg&gt;

Dołącza nagłówek biblioteki standardowe C \<stdarg.h > i dodaje skojarzone nazwy `std` przestrzeni nazw. Dołączenie tego pliku nagłówkowego gwarantuje również, że nazwy zadeklarowane za pomocą zewnętrznego powiązania w nagłówku biblioteki standardowe C są deklarowane w `std` przestrzeni nazw.

## <a name="syntax"></a>Składnia

```cpp
#include <cstdarg>
```

## <a name="namespace-and-macros"></a>Makra i Namespace

```cpp
namespace std {
    using va_list = see below;
}

#define va_arg(V, P)
#define va_copy(VDST, VSRC)
#define va_end(V)
#define va_start(V, P)
```

## <a name="see-also"></a>Zobacz także

[Odwołanie do plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)<br/>
[Standardowa biblioteka C++ — przegląd](../standard-library/cpp-standard-library-overview.md)<br/>
[Bezpieczeństwo wątku w standardowej bibliotece C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
