---
title: _bstr_t — Operatory relacyjne
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator>
- _bstr_t::operator==
- _bstr_t::operator>=
- _bstr_t::operator!=
- _bstr_t::operator<
- _bstr_t::operator<=
- _bstr_t::operator!
helpviewer_keywords:
- '>= operator [C++], comparing specific objects'
- operator<= [C++], bstr
- '!= operator'
- operator == [C++], bstr
- operator!= [C++], relational operators
- < operator [C++], comparing specific objects
- relational operators [C++], _bstr_t class
- operator== [C++], bstr
- <= operator [C++], with specific objects
- operator <= [C++], bstr
- operator >= [C++], bstr
- operator != [C++], relational operators
- '> operator [C++], comparing specific objects'
- operator< [C++], bstr
- == operator [C++], with specific Visual C++ objects
- operator>= [C++], bstr
- operator < [C++], bstr
- operator > [C++], bstr
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
ms.openlocfilehash: f454c8bcfeb28ada8c07564e9bb562e18a537e45
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345158"
---
# <a name="bstrt-relational-operators"></a>_bstr_t — Operatory relacyjne

**Microsoft Specific**

Porównuje dwa `_bstr_t` obiektów.

## <a name="syntax"></a>Składnia

```
bool operator!( ) const throw( );
bool operator==(const _bstr_t& str) const throw( );
bool operator!=(const _bstr_t& str) const throw( );
bool operator<(const _bstr_t& str) const throw( );
bool operator>(const _bstr_t& str) const throw( );
bool operator<=(const _bstr_t& str) const throw( );
bool operator>=(const _bstr_t& str) const throw( );
```

## <a name="remarks"></a>Uwagi

Te operatory porównania dwóch `_bstr_t` leksykograficznie obiektów. Operatory zwraca wartość TRUE, jeśli mają porównania, w przeciwnym razie zwraca wartość FALSE.

**END specyficzny dla Microsoft**

## <a name="see-also"></a>Zobacz także

[_bstr_t, klasa](../cpp/bstr-t-class.md)