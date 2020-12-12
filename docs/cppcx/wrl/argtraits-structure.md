---
description: Dowiedz się więcej o strukturze ArgTraits
title: ArgTraits — Struktura
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
- event/Microsoft::WRL::Details::ArgTraits::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraits structure
- Microsoft::WRL::Details::ArgTraits::args constant
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
ms.openlocfilehash: b44cd1ff8d5aa4355385629cc08321dfe353e24c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175914"
---
# <a name="argtraits-structure"></a>ArgTraits — Struktura

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template<typename TMemberFunction>
struct ArgTraits;

template<typename TDelegateInterface>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;

template<typename TDelegateInterface, typename TArg1>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;

template<typename TDelegateInterface, typename TArg1, typename TArg2>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8,
    typename TArg9
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;
```

### <a name="parameters"></a>Parametry

*TMemberFunction*<br/>
Parametr TypeName struktury ArgTraits, który nie jest zgodny z żadną `Invoke` sygnaturą metody.

*TDelegateInterface*<br/>
Interfejs delegata.

*TArg1*<br/>
Typ pierwszego argumentu `Invoke` metody.

*TArg2*<br/>
Typ drugiego argumentu `Invoke` metody.

*TArg3*<br/>
Typ trzeciego argumentu `Invoke` metody.

*TArg4*<br/>
Typ czwartego argumentu `Invoke` metody.

*TArg5*<br/>
Typ piątego argumentu `Invoke` metody.

*TArg6*<br/>
Typ szóstego argumentu `Invoke` metody.

*TArg7*<br/>
Typ siódmego argumentu `Invoke` metody.

*TArg8*<br/>
Typ ósmego argumentu `Invoke` metody.

*TArg9*<br/>
Typ dziewiątego argumentu `Invoke` metody.

## <a name="remarks"></a>Uwagi

`ArgTraits`Struktura deklaruje określony interfejs delegata i anonimową funkcję członkowską, która ma określoną liczbę parametrów.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

Nazwa       | Opis
---------- | ----------------------
`Arg1Type` | Element typedef dla TArg1.
`Arg2Type` | Element typedef dla TArg2.
`Arg3Type` | Element typedef dla TArg3.
`Arg4Type` | Element typedef dla TArg4.
`Arg5Type` | Element typedef dla TArg5.
`Arg6Type` | Element typedef dla TArg6.
`Arg7Type` | Element typedef dla TArg7.
`Arg8Type` | Element typedef dla TArg8.
`Arg9Type` | Element typedef dla TArg9.

### <a name="public-constants"></a>Stałe publiczne

Nazwa                     | Opis
------------------------ | ---------------------------------------------------------------------------------------
[ArgTraits:: args](#args) | Przechowuje liczbę parametrów `Invoke` metody interfejsu delegata.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`ArgTraits`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Event. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="argtraitsargs"></a><a name="args"></a> ArgTraits:: args

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
static const int args = -1;
```

### <a name="remarks"></a>Uwagi

Przechowuje liczbę parametrów `Invoke` metody interfejsu delegata. Gdy `args` jest równe-1, nie może istnieć dopasowanie `Invoke` sygnatury metody.
