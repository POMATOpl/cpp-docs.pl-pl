---
description: 'Dowiedz się więcej na temat: &lt; CLocale&gt;'
title: '&lt;clocale&gt;'
ms.date: 11/04/2016
f1_keywords:
- <clocale>
helpviewer_keywords:
- clocale header
ms.assetid: 5bde3e01-cf67-4f1f-a383-447ec814d00e
ms.openlocfilehash: 3a1efb972d33ccb5b28fac6d77803aa6de2e08c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325117"
---
# <a name="ltclocalegt"></a>&lt;clocale&gt;

Zawiera nagłówek standardowej biblioteki C \<locale.h> i dodaje skojarzone nazwy do `std` przestrzeni nazw.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<clocale>

**Przestrzeń nazw:** std

## <a name="remarks"></a>Uwagi

Dołączenie tego nagłówka zapewnia, że nazwy zadeklarowane za pomocą zewnętrznego powiązania w nagłówku standardowej biblioteki C są deklarowane w `std` przestrzeni nazw.

## <a name="constants"></a>Stałe

```cpp
#define NULL see below
#define LC_ALL see below
#define LC_COLLATE see below
#define LC_CTYPE see below
#define LC_MONETARY see below
#define LC_NUMERIC see below
#define LC_TIME see below
```

## <a name="structures"></a>Struktury

```cpp
struct lconv;
```

## <a name="functions"></a>Funkcje

```cpp
char* setlocale(int category, const char* locale);
lconv* localeconv();
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[Omówienie standardowej biblioteki języka C++](../standard-library/cpp-standard-library-overview.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
