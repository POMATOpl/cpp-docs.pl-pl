---
description: 'Dowiedz się więcej na temat: char_traits &lt; char16_t &gt; struktury'
title: '&lt;struktura char16_t &gt; char_traits'
ms.date: 11/04/2016
f1_keywords:
- char_traits<char16_t>
- iosfwd/std::char_traits<char16_t>
helpviewer_keywords:
- char_traits<char16_t> class
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
ms.openlocfilehash: 2ad725b514d6804edfdea6d4ba72c2cfd44c4f21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325265"
---
# <a name="char_traitsltchar16_tgt-struct"></a>&lt;struktura char16_t &gt; char_traits

Struktura, która jest specjalizacją struktury szablonu **char_traits \<CharType>** do elementu typu **`char16_t`** .

## <a name="syntax"></a>Składnia

```cpp
template <>
struct char_traits<char16_t>;
```

## <a name="remarks"></a>Uwagi

Specjalizacja umożliwia strukturze korzystanie z funkcji bibliotek, które manipulują obiektami typu **`char16_t`** .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<string>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[\<string>](../standard-library/string.md)\
[Struktura char_traits](../standard-library/char-traits-struct.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
