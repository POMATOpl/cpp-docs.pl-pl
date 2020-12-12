---
description: Dowiedz się więcej na temat klasy tiled_extent
title: tiled_extent — Klasa
ms.date: 11/04/2016
f1_keywords:
- tiled_extent
- AMP/tiled_extent
- AMP/Concurrency::tiled_extent::tiled_extent
- AMP/Concurrency::tiled_extent::get_tile_extent
- AMP/Concurrency::tiled_extent::pad
- AMP/Concurrency::tiled_extent::truncate
- AMP/Concurrency::tiled_extent::tile_dim0
- AMP/Concurrency::tiled_extent::tile_dim1
- AMP/Concurrency::tiled_extent::tile_dim2
- AMP/Concurrency::tiled_extent::tile_extent
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
ms.openlocfilehash: ca5b5c630152263ca49adf5c201ee0b892a192c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163876"
---
# <a name="tiled_extent-class"></a>tiled_extent — Klasa

`tiled_extent`Obiekt to `extent` obiekt od jednego do trzech wymiarów, dzielący przestrzeń na jeden, dwa lub trzy.

## <a name="syntax"></a>Składnia

```cpp
template <
    int _Dim0,
    int _Dim1,
    int _Dim2
>
class tiled_extent : public Concurrency::extent<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;

template <
    int _Dim0
>
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;
```

### <a name="parameters"></a>Parametry

*_Dim0*<br/>
Długość najbardziej znaczącego wymiaru.

*_Dim1*<br/>
Długość następnego do najbardziej znaczącego wymiaru.

*_Dim2*<br/>
Długość najmniej znaczącego wymiaru.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor tiled_extent](#ctor)|Inicjuje nowe wystąpienie klasy `tiled_extent`.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[get_tile_extent](#get_tile_extent)|Zwraca `extent` obiekt, który przechwytuje wartości `tiled_extent` argumentów szablonu `_Dim0` , `_Dim1` i `_Dim2` .|
|[konsolę](#pad)|Zwraca nowy `tiled_extent` obiekt z dopasowanymi zakresami, tak aby był równy podzielenia przez wymiary kafelków.|
|[obciąć](#truncate)|Zwraca nowy `tiled_extent` obiekt z przypiętymi zakresami ustawionymi w dół, aby był równy podzielenia przez wymiary kafelków.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[operator =](#operator_eq)|Kopiuje zawartość określonego `tiled_index` obiektu do tego elementu.|

### <a name="public-constants"></a>Stałe publiczne

|Nazwa|Opis|
|----------|-----------------|
|[tile_dim0 stała](#tile_dim0)|Przechowuje długość najbardziej znaczącego wymiaru.|
|[tile_dim1 stała](#tile_dim1)|Przechowuje Długość następnego do najbardziej znaczącego wymiaru.|
|[tile_dim2 stała](#tile_dim2)|Przechowuje długość najmniej znaczącego wymiaru.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[tile_extent](#tile_extent)|Pobiera `extent` obiekt, który przechwytuje wartości `tiled_extent` argumentów szablonu `_Dim0` , `_Dim1` i `_Dim2` .|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`extent`

`tiled_extent`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amp. h

**Przestrzeń nazw:** Współbieżności

## <a name="tiled_extent-constructor"></a><a name="ctor"></a> Konstruktor tiled_extent

Inicjuje nowe wystąpienie klasy `tiled_extent`.

### <a name="syntax"></a>Składnia

```cpp
tiled_extent();

tiled_extent(
    const Concurrency::extent<rank>& _Other );

tiled_extent(
    const tiled_extent& _Other );
```

### <a name="parameters"></a>Parametry

*_Other*<br/>
`extent`Obiekt lub `tiled_extent` do skopiowania.

## <a name="get_tile_extent"></a><a name="get_tile_extent"></a> get_tile_extent

Zwraca `extent` obiekt, który przechwytuje wartości `tiled_extent` argumentów szablonu `_Dim0` , `_Dim1` i `_Dim2` .

### <a name="syntax"></a>Składnia

```cpp
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>Wartość zwracana

`extent`Obiekt, który przechwytuje wymiary tego `tiled_extent` wystąpienia.

## <a name="pad"></a><a name="pad"></a> konsola

Zwraca nowy `tiled_extent` obiekt z dopasowanymi zakresami, tak aby był równy podzielenia przez wymiary kafelków.

### <a name="syntax"></a>Składnia

```cpp
tiled_extent pad() const;
```

### <a name="return-value"></a>Wartość zwracana

Nowy `tiled_extent` obiekt według wartości.

## <a name="truncate"></a><a name="truncate"></a> Obetnij

Zwraca nowy `tiled_extent` obiekt z przypiętymi zakresami ustawionymi w dół, aby był równy podzielenia przez wymiary kafelków.

### <a name="syntax"></a>Składnia

```cpp
tiled_extent truncate() const;
```

### <a name="return-value"></a>Wartość zwracana

Zwraca nowy `tiled_extent` obiekt z przypiętymi zakresami ustawionymi w dół, aby był równy podzielenia przez wymiary kafelków.

## <a name="operator"></a><a name="operator_eq"></a> operator =

Kopiuje zawartość określonego `tiled_index` obiektu do tego elementu.

### <a name="syntax"></a>Składnia

```cpp
tiled_extent&  operator= (
    const tiled_extent& _Other ) restrict (amp, cpu);
```

### <a name="parameters"></a>Parametry

*_Other*<br/>
`tiled_index`Obiekt, z którego mają zostać skopiowane.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do tego `tiled_index` wystąpienia.

## <a name="tile_dim0"></a><a name="tile_dim0"></a> tile_dim0

Przechowuje długość najbardziej znaczącego wymiaru.

### <a name="syntax"></a>Składnia

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a><a name="tile_dim1"></a> tile_dim1

Przechowuje Długość następnego do najbardziej znaczącego wymiaru.

### <a name="syntax"></a>Składnia

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a><a name="tile_dim2"></a> tile_dim2

Przechowuje długość najmniej znaczącego wymiaru.

### <a name="syntax"></a>Składnia

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_extent"></a><a name="tile_extent"></a> tile_extent

Pobiera `extent` obiekt, który przechwytuje wartości `tiled_extent` argumentów szablonu `_Dim0` , `_Dim1` i `_Dim2` .

### <a name="syntax"></a>Składnia

```cpp
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;
```

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności (C++ AMP)](concurrency-namespace-cpp-amp.md)
