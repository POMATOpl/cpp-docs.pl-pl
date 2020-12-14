---
description: 'Dowiedz się więcej o: &lt; streambuf &gt; Typedefs'
title: '&lt;streambuf &gt; Typedefs'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: ae5394213143b05704d452e38eaae0b3581849cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221972"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf &gt; Typedefs

[streambuf](#streambuf)\
[wstreambuf —](#wstreambuf)

## <a name="streambuf"></a><a name="streambuf"></a> streambuf

Specjalizacja `basic_streambuf` , która używa **`char`** jako parametrów szablonu.

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_streambuf](../standard-library/basic-streambuf-class.md), wyspecjalizowany dla elementów typu **`char`** z cechami domyślnymi znaków.

## <a name="wstreambuf"></a><a name="wstreambuf"></a> wstreambuf —

Specjalizacja `basic_streambuf` , która używa **`wchar_t`** jako parametrów szablonu.

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Uwagi

Typ jest synonimem dla szablonu klasy [basic_streambuf](../standard-library/basic-streambuf-class.md), wyspecjalizowany dla elementów typu **`wchar_t`** z cechami domyślnymi znaków.

## <a name="see-also"></a>Zobacz też

[\<streambuf>](../standard-library/streambuf.md)
