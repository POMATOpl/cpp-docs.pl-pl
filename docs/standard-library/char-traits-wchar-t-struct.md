---
description: 'Dowiedz się więcej na temat: char_traits &lt; wchar_t &gt; struktury'
title: '&lt;struktura wchar_t &gt; char_traits'
ms.date: 11/04/2016
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
ms.openlocfilehash: 0276f4b50cb0039d0bec49b1b3eb2a0b3b2463aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325225"
---
# <a name="char_traitsltwchar_tgt-struct"></a>&lt;struktura wchar_t &gt; char_traits

Klasa, która jest specjalizacją struktury szablonu **char_traits \<CharType>** do elementu typu **`wchar_t`** .

## <a name="syntax"></a>Składnia

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>Uwagi

Specjalizacja umożliwia strukturze korzystanie z funkcji bibliotek, które manipulują obiektami tego typu **`wchar_t`** .

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<string>

**Przestrzeń nazw:** std

## <a name="see-also"></a>Zobacz też

[Struktura char_traits](../standard-library/char-traits-struct.md)\
[Bezpieczeństwo wątku w standardowej bibliotece języka C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
