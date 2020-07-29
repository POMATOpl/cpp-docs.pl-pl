---
title: '&lt;streambuf &gt; Typedefs'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 3c5dbefba8e2106c6e3e678002bce26fffd26a62
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215624"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf &gt; Typedefs

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf —](#wstreambuf)|

## <a name="streambuf"></a><a name="streambuf"></a>streambuf

Specjalizacja `basic_streambuf` , która używa **`char`** jako parametrów szablonu.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_streambuf](../standard-library/basic-streambuf-class.md), wyspecjalizowany dla elementów typu **`char`** z cechami domyślnymi znaków.

## <a name="wstreambuf"></a><a name="wstreambuf"></a>wstreambuf —

Specjalizacja `basic_streambuf` , która używa **`wchar_t`** jako parametrów szablonu.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_streambuf](../standard-library/basic-streambuf-class.md), wyspecjalizowany dla elementów typu **`wchar_t`** z cechami domyślnymi znaków.

## <a name="see-also"></a>Zobacz także

[\<streambuf>](../standard-library/streambuf.md)
