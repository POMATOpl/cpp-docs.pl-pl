---
description: 'Dowiedz się więcej o: &lt; ostream &gt; Typedefs'
title: '&lt;ostream &gt; Typedefs'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 886fb729f389fac161e4d154e00898b530d1d9f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193022"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream &gt; Typedefs

[ostream](#ostream)\
[wostream —](#wostream)

## <a name="ostream"></a><a name="ostream"></a> ostream

Tworzy typ z basic_ostream, który jest wyspecjalizowany **`char`** i `char_traits` wyspecjalizowany dla **`char`** .

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_ostream](../standard-library/basic-ostream-class.md), wyspecjalizowany dla elementów typu **`char`** z cechami domyślnymi znaków.

## <a name="wostream"></a><a name="wostream"></a> wostream —

Tworzy typ z basic_ostream, który jest wyspecjalizowany **`wchar_t`** i `char_traits` wyspecjalizowany dla **`wchar_t`** .

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_ostream](../standard-library/basic-ostream-class.md), wyspecjalizowany dla elementów typu **`wchar_t`** z cechami domyślnymi znaków.

## <a name="see-also"></a>Zobacz też

[\<ostream>](../standard-library/ostream.md)
