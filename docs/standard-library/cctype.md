---
description: 'Dowiedz się więcej na temat: &lt; cctype&gt;'
title: '&lt;cctype&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cctype>
helpviewer_keywords:
- cctype header
ms.assetid: 3fd18bfd-c414-4def-bac1-c362e1fe8b71
ms.openlocfilehash: a66c0b0f253ce034becf1845bb42f0c204414c34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325345"
---
# <a name="ltcctypegt"></a>&lt;cctype&gt;

Zawiera nagłówek standardowej biblioteki C \<ctype.h> i dodaje skojarzone nazwy do `std` przestrzeni nazw.

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<cctype>

**Przestrzeń nazw:** std

## <a name="remarks"></a>Uwagi

Dołączenie tego nagłówka zapewnia, że nazwy zadeklarowane za pomocą zewnętrznego powiązania w nagłówku standardowej biblioteki C są deklarowane w `std` przestrzeni nazw.

## <a name="functions"></a>Funkcje

```cpp
int isalnum(int c);
int isalpha(int c);
int isblank(int c);
int iscntrl(int c);
int isdigit(int c);
int isgraph(int c);
int islower(int c);
int isprint(int c);
int ispunct(int c);
int isspace(int c);
int isupper(int c);
int isxdigit(int c);
int tolower(int c);
int toupper(int c);
```

## <a name="see-also"></a>Zobacz też

[Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)\
[Omówienie standardowej biblioteki języka C++](../standard-library/cpp-standard-library-overview.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
