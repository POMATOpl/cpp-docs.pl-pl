---
description: 'Dowiedz się więcej na temat: Klasa ComPtrRefBase'
title: ComPtrRefBase — Klasa
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
- client/Microsoft::WRL::Details::ComPtrRefBase::ptr_
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRefBase class
- Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable** operator
- Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown** operator
- Microsoft::WRL::Details::ComPtrRefBase::ptr_ data member
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
ms.openlocfilehash: 4dce58e8292092084916c24153d543f2a45856fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273140"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase — Klasa

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

## <a name="syntax"></a>Składnia

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>Parametry

*T*<br/>
Typ [ComPtr \<T> ](comptr-class.md) lub typ pochodzący od niego, nie tylko interfejs reprezentowany przez `ComPtr` .

## <a name="remarks"></a>Uwagi

Reprezentuje klasę bazową dla klasy [ComPtrRef](comptrref-class.md) .

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

Nazwa            | Opis
--------------- | -------------------------------------------------
`InterfaceType` | Synonim dla typu parametru szablonu *T*.

### <a name="public-operators"></a>Operatory publiczne

Nazwa                                                                       | Opis
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[ComPtrRefBase:: operator IInspectable * *](#operator-iinspectable-star-star) | Rzutuje bieżący element członkowski danych [ptr_](#ptr) na wskaźnik do wskaźnika do `IInspectable` interfejsu.
[ComPtrRefBase:: operator IUnknown * *](#operator-iunknown-star-star)         | Rzutuje bieżący element członkowski danych [ptr_](#ptr) na wskaźnik do wskaźnika do `IUnknown` interfejsu.

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

Nazwa                        | Opis
--------------------------- | ----------------------------------------------------------------
[ComPtrRefBase::p tr_](#ptr) | Wskaźnik do typu określonego przez bieżący parametr szablonu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`ComPtrRefBase`

## <a name="requirements"></a>Wymagania

**Nagłówek:** Client. h

**Przestrzeń nazw:** Microsoft:: WRL::D etails

## <a name="comptrrefbaseoperator-iinspectable-operator"></a><a name="operator-iinspectable-star-star"></a>ComPtrRefBase:: operator — \* \* operator IInspectable

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>Uwagi

Rzutuje bieżący element członkowski danych [ptr_](#ptr) na wskaźnik do wskaźnika do `IInspectable` interfejsu.

Błąd jest emitowany, jeśli bieżący `ComPtrRefBase` nie pochodzi od `IInspectable` .

To Rzutowanie jest dostępne tylko wtedy, gdy `__WRL_CLASSIC_COM__` jest zdefiniowany.

## <a name="comptrrefbaseoperator-iunknown-operator"></a><a name="operator-iunknown-star-star"></a> ComPtrRefBase:: operator IUnknown * * — operator

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>Uwagi

Rzutuje bieżący element członkowski danych [ptr_](#ptr) na wskaźnik do wskaźnika do `IUnknown` interfejsu.

Błąd jest emitowany, jeśli bieżący `ComPtrRefBase` nie pochodzi od `IUnknown` .

## <a name="comptrrefbaseptr_"></a><a name="ptr"></a> ComPtrRefBase::p tr_

Obsługuje infrastrukturę WRL i nie jest przeznaczona do użycia bezpośrednio w kodzie.

```cpp
T* ptr_;
```

### <a name="remarks"></a>Uwagi

Wskaźnik do typu określonego przez bieżący parametr szablonu. `ptr_` jest chronionymi elementami członkowskimi danych.
