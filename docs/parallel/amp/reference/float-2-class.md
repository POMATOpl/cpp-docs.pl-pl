---
description: Dowiedz się więcej na temat klasy float_2
title: float_2 — Klasa
ms.date: 11/04/2016
f1_keywords:
- amp_short_vectors/Concurrency::graphics::float_2::yx
- amp_short_vectors/Concurrency::graphics::float_2::operator-=
- amp_short_vectors/Concurrency::graphics::float_2::operator++
- amp_short_vectors/Concurrency::graphics::float_2::operator-
- amp_short_vectors/Concurrency::graphics::float_2::r
- amp_short_vectors/Concurrency::graphics::float_2::get_yx
- amp_short_vectors/Concurrency::graphics::float_2::get_xy
- amp_short_vectors/Concurrency::graphics::float_2::operator/=
- amp_short_vectors/Concurrency::graphics::float_2::set_yx
- amp_short_vectors/Concurrency::graphics::float_2::x
- amp_short_vectors/Concurrency::graphics::float_2::get_y
- amp_short_vectors/Concurrency::graphics::float_2::operator+=
- amp_short_vectors/Concurrency::graphics::float_2::gr
- amp_short_vectors/Concurrency::graphics::float_2::operator=
- amp_short_vectors/Concurrency::graphics::float_2::set_x
- amp_short_vectors/Concurrency::graphics::float_2::operator--
- amp_short_vectors/Concurrency::graphics::float_2::get_x
- amp_short_vectors/Concurrency::graphics::float_2::operator*=
- amp_short_vectors/Concurrency::graphics::float_2::rg
- amp_short_vectors/Concurrency::graphics::float_2::set_xy
- amp_short_vectors/Concurrency::graphics::float_2::xy
- amp_short_vectors/Concurrency::graphics::float_2
- amp_short_vectors/Concurrency::graphics::float_2::set_y
- amp_short_vectors/Concurrency::graphics::float_2::y
- amp_short_vectors/Concurrency::graphics::float_2::g
ms.assetid: b3ebd48e-f8c8-4f00-a640-357f702f0cae
ms.openlocfilehash: a0d350c9742da6c11a5bf982a1638a1fc0921eb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325853"
---
# <a name="float_2-class"></a>float_2 — Klasa

Reprezentuje krótki wektor dwóch zmiennoprzecinkowych.

## <a name="syntax"></a>Składnia

```cpp
class float_2;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor float_2](#ctor)|Przeciążone. Konstruktor domyślny, inicjuje wszystkie elementy z wartością 0.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|float_2:: get_x||
|float_2:: get_xy||
|float_2:: get_y||
|float_2:: get_yx||
|float_2:: ref_g||
|float_2:: ref_r||
|float_2:: ref_x||
|float_2:: ref_y||
|float_2:: set_x||
|float_2:: set_xy||
|float_2:: set_y||
|float_2:: set_yx||

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|float_2:: operator-||
|float_2:: operator--||
|float_2:: operator * =||
|float_2:: operator/=||
|float_2:: operator + +||
|float_2:: operator + =||
|float_2:: operator =||
|float_2:: operator-=||

### <a name="public-constants"></a>Stałe publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Stała rozmiaru](#float_2__size)||

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|float_2:: g||
|float_2:: GR||
|float_2:: r||
|float_2:: RG||
|float_2:: x||
|float_2:: XY||
|float_2:: y||
|float_2:: yx||

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`float_2`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amp_short_vectors. h

**Przestrzeń nazw:** Concurrency:: Graphics

## <a name="float_2"></a><a name="ctor"></a> float_2

Konstruktor domyślny, inicjuje wszystkie elementy z wartością 0.

```cpp
float_2() restrict(amp,
    cpu);

float_2(
    float _V0,
    float _V1) restrict(amp,
    cpu);

float_2(
    float _V) restrict(amp,
    cpu);

float_2(
    const float_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const uint_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const int_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const norm_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const double_2& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parametry

*_V0*<br/>
Wartość, aby zainicjować element 0.

*_V1*<br/>
Wartość do zainicjowania elementu 1.

*_V*<br/>
Wartość dla inicjalizacji.

*_Other*<br/>
Obiekt używany do inicjowania.

## <a name="size"></a><a name="float_2__size"></a> zmienia

```cpp
static const int size = 2;
```

## <a name="see-also"></a>Zobacz też

[Concurrency::graphics — Przestrzeń nazw](concurrency-graphics-namespace.md)
