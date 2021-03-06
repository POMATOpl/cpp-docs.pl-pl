---
description: Dowiedz się więcej na temat klasy writeonly_texture_view
title: writeonly_texture_view — Klasa
ms.date: 11/04/2016
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
ms.openlocfilehash: 17e9ed49c5fb3c976343d8c3ad8690d7f41b166d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314524"
---
# <a name="writeonly_texture_view-class"></a>writeonly_texture_view — Klasa

Zapewnia dostęp do tekstury.

## <a name="syntax"></a>Składnia

```cpp
template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view;

template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;
```

### <a name="parameters"></a>Parametry

*value_type*<br/>
Typ elementów w tekstury.

*_Rank*<br/>
Ranga tekstury.

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`scalar_type`||
|`value_type`|Typ elementów w tekstury.|

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor writeonly_texture_view](#ctor)|Inicjuje nowe wystąpienie klasy `writeonly_texture_view`.|
|[~ writeonly_texture_view destruktor](#ctor)|Niszczy `writeonly_texture_view` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[zbiór](#set)|Ustawia wartość elementu w określonym indeksie.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[operator =](#operator_eq)|Kopiuje określony `writeonly_texture_view` obiekt do tego obiektu.|

### <a name="public-constants"></a>Stałe publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Stała rangi](#rank)|Pobiera rangę `writeonly_texture_view` obiektu.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`_Texture_base`

`writeonly_texture_view`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amp_graphics. h

**Przestrzeń nazw:** Concurrency:: Graphics

## <a name="writeonly_texture_view"></a><a name="dtor"></a> ~ writeonly_texture_view

Niszczy `writeonly_texture_view` obiekt.

```cpp
~writeonly_texture_view() restrict(amp,cpu);
```

## <a name="operator"></a><a name="operator_eq"></a> operator =

Kopiuje określony `writeonly_texture_view` obiekt do tego obiektu.

```cpp
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Other*<br/>
`writeonly_texture_view` obiekt do skopiowania.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do tego `writeonly_texture_view` obiektu.

## <a name="rank"></a><a name="rank"></a> stopni

Pobiera rangę `writeonly_texture_view` obiektu.

```cpp
static const int rank = _Rank;
```

## <a name="set"></a><a name="set"></a> zbiór

Ustawia wartość elementu w określonym indeksie.

```cpp
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>Parametry

*_Index*<br/>
Indeks elementu.

*wartość*<br/>
Nowa wartość elementu.

## <a name="writeonly_texture_view"></a><a name="ctor"></a> writeonly_texture_view

Inicjuje nowe wystąpienie klasy `writeonly_texture_view`.

```cpp
writeonly_texture_view(
    texture<value_type,
    _Rank>& _Src) restrict(amp);

writeonly_texture_view(
    const writeonly_texture_view<value_type,
    _Rank>& _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametry

*_Rank*<br/>
Ranga tekstury.

*value_type*<br/>
Typ elementów w tekstury.

*_Src*<br/>
Tekstura, która jest używana do tworzenia `writeonly_texture_view` .

## <a name="see-also"></a>Zobacz też

[Concurrency::graphics — Przestrzeń nazw](concurrency-graphics-namespace.md)
