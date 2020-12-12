---
description: Dowiedz się więcej na temat klasy regex_error
title: regex_error — Klasa
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
ms.openlocfilehash: a6e2ace44c7463cbe43d000d3dabb9cf9f7d6676
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250507"
---
# <a name="regex_error-class"></a>regex_error — Klasa

Zgłasza nieprawidłowy obiekt basic_regex.

## <a name="syntax"></a>Składnia

```cpp
class regex_error
: public std::runtime_error
```

## <a name="remarks"></a>Uwagi

Klasa opisuje obiekt wyjątku zgłoszony, aby zgłosić błąd w konstrukcji lub użyciu `basic_regex` obiektu.

### <a name="constructors"></a>Konstruktory

|Konstruktor|Opis|
|-|-|
|[regex_error](#regex_error)|Konstruuje obiekt.|

### <a name="member-functions"></a>Funkcje członkowskie

|Funkcja członkowska|Opis|
|-|-|
|[kodu](#code)|Zwraca kod błędu.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<regex>

**Przestrzeń nazw:** std

## <a name="example"></a>Przykład

```cpp
// std__regex__regex_error.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex_error paren(std::regex_constants::error_paren);

    try
        {
        std::regex rx("(a");
        }
    catch (const std::regex_error& rerr)
        {
        std::cout << "regex error: "
            << (rerr.code() == paren.code() ? "unbalanced parentheses" : "")
            << std::endl;
        }
    catch (...)
        {
        std::cout << "unknown exception" << std::endl;
        }

    return (0);
    }
```

```Output
regex error: unbalanced parentheses
```

## <a name="regex_errorcode"></a><a name="code"></a> regex_error:: Code

Zwraca kod błędu.

```cpp
regex_constants::error_code code() const;
```

### <a name="remarks"></a>Uwagi

Funkcja członkowska zwraca wartość, która została przeniesiona do konstruktora obiektu.

## <a name="regex_errorregex_error"></a><a name="regex_error"></a> regex_error:: regex_error

Konstruuje obiekt.

```cpp
regex_error(regex_constants::error_code error);
```

### <a name="parameters"></a>Parametry

*Porn*\
Kod błędu.

### <a name="remarks"></a>Uwagi

Konstruktor konstruuje obiekt, który zawiera *błąd* wartości.

## <a name="see-also"></a>Zobacz też

[\<regex>](../standard-library/regex.md)\
[Klasa regex_constants](../standard-library/regex-constants-class.md)\
[\<regex> obowiązki](../standard-library/regex-functions.md)\
[Klasa regex_iterator](../standard-library/regex-iterator-class.md)\
[\<regex> zainteresowanych](../standard-library/regex-operators.md)\
[Klasa regex_token_iterator](../standard-library/regex-token-iterator-class.md)\
[Klasa regex_traits](../standard-library/regex-traits-class.md)\
[\<regex> definicje typów](../standard-library/regex-typedefs.md)
