---
description: 'Dowiedz się więcej o: _com_ptr_t operatory relacyjne'
title: _com_ptr_t — Operatory relacyjne
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::operator>
- _com_ptr_t::operator>=
- _com_ptr_t::operator<=
- _com_ptr_t::operator==
- _com_ptr_t::operator!=
- _com_ptr_t::operator<
helpviewer_keywords:
- '>= operator [C++], comparing specific objects'
- '!= operator'
- operator > [C++], pointers
- operator>= [C++], pointers
- operator < [C++], pointers
- operator!= [C++], relational operators
- < operator [C++], comparing specific objects
- operator== [C++], pointers
- operator == [C++], pointers
- <= operator [C++], with specific objects
- relational operators [C++], _com_ptr_t class
- operator >= [C++], pointers
- operator != [C++], relational operators
- operator <= [C++], pointers
- '> operator [C++], comparing specific objects'
- operator<= [C++], pointers
- operator< [C++], pointers
- == operator [C++], with specific Visual C++ objects
ms.assetid: 5ae4028c-33ee-485d-bbda-88d2604d6d4b
ms.openlocfilehash: 6c2b4bb3b3f7ca604874a4f2dad1caff58e70735
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135437"
---
# <a name="_com_ptr_t-relational-operators"></a>_com_ptr_t — Operatory relacyjne

**Specyficzne dla firmy Microsoft**

Porównaj obiekt inteligentnego wskaźnika z innym wskaźnikiem inteligentnym, nieprzetworzonym wskaźnikiem interfejsu lub wartością NULL.

## <a name="syntax"></a>Składnia

```
template<typename _OtherIID>
bool operator==( const _com_ptr_t<_OtherIID>& p );

template<typename _OtherIID>
bool operator==( _com_ptr_t<_OtherIID>& p );

template<typename _InterfaceType>
bool operator==( _InterfaceType* p );

template<>
bool operator==( Interface* p );

template<>
bool operator==( const _com_ptr_t& p ) throw();

template<>
bool operator==( _com_ptr_t& p ) throw();

bool operator==( Int null );

template<typename _OtherIID>
bool operator!=( const _com_ptr_t<_OtherIID>& p );

template<typename _OtherIID>
bool operator!=( _com_ptr_t<_OtherIID>& p );

template<typename _InterfaceType>
bool operator!=( _InterfaceType* p );

bool operator!=( Int null );

template<typename _OtherIID>
bool operator<( const _com_ptr_t<_OtherIID>& p );

template<typename _OtherIID>
bool operator<( _com_ptr_t<_OtherIID>& p );

template<typename _InterfaceType>
bool operator<( _InterfaceType* p );

template<typename _OtherIID>
bool operator>( const _com_ptr_t<_OtherIID>& p );

template<typename _OtherIID>
bool operator>(_com_ptr_t< _OtherIID>& p );

template<typename _InterfaceType>
bool operator>( _InterfaceType* p );

template<typename _OtherIID>
bool operator<=( const _com_ptr_t<_OtherIID>& p );

template<typename _OtherIID>
bool operator<=( _com_ptr_t<_OtherIID>& p );

template<typename _InterfaceType>
bool operator<=( _InterfaceType* p );

template<typename _OtherIID>
bool operator>=( const _com_ptr_t<_OtherIID>& p );

template<typename _OtherIID>
bool operator>=( _com_ptr_t<_OtherIID>& p );

template<typename _InterfaceType>
bool operator>=( _InterfaceType* p );
```

## <a name="remarks"></a>Uwagi

Porównuje obiekt inteligentnego wskaźnika do innego wskaźnika inteligentnego, wskaźnika interfejsu Raw lub wartości NULL. Oprócz testów wskaźnika o wartości NULL te operatory najpierw wykonują zapytania względem obu wskaźników dla `IUnknown` i porównują wyniki.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Klasa _com_ptr_t](../cpp/com-ptr-t-class.md)
