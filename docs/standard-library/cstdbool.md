---
description: 'Dowiedz się więcej na temat: &lt; cstdbool&gt;'
title: '&lt;cstdbool&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdbool>
- cstdbool
helpviewer_keywords:
- cstdbool header
ms.assetid: 44ccb8b2-d808-4715-8097-58ba09ab33ed
ms.openlocfilehash: 0711c05ff136f90a701ff707976a172d2bcb1315
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324738"
---
# <a name="ltcstdboolgt"></a>&lt;cstdbool&gt;

Zawiera nagłówek standardowej biblioteki C \<stdbool.h> i dodaje skojarzone nazwy do `std` przestrzeni nazw.

> [!NOTE]
> Ponieważ \<stdbool.h> nagłówek definiuje makra, które są słowami kluczowymi w języku C++, w tym nie ma żadnego wpływu. \<stdbool.h>Nagłówek jest przestarzały w języku C++. \<cstdbool>Nagłówek jest przestarzały w języku c++ 17 i został usunięty z wersji Standard c++ 20.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<cstdbool>

**Przestrzeń nazw:** std

## <a name="remarks"></a>Uwagi

Dołączenie tego nagłówka zapewnia, że nazwy zadeklarowane za pomocą zewnętrznego powiązania w nagłówku standardowej biblioteki C są deklarowane w `std` przestrzeni nazw.

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](cpp-standard-library-header-files.md)\
[Omówienie standardowej biblioteki języka C++](cpp-standard-library-overview.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](thread-safety-in-the-cpp-standard-library.md)
