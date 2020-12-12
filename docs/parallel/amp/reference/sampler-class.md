---
description: Dowiedz się więcej o klasie próbnika
title: sampler — Klasa
ms.date: 06/28/2018
f1_keywords:
- sampler
- AMP_GRAPHICS/sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::get_address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::get_border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::get_filter_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::filter_mode
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
ms.openlocfilehash: 61292cccb9e28ca76dc4ecaa1aaca849d9219ffc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327624"
---
# <a name="sampler-class"></a>sampler — Klasa

Klasa próbnika agreguje informacje konfiguracyjne próbkowania, które mają być używane do próbkowania tekstury.

## <a name="syntax"></a>Składnia

```cpp
class sampler;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor próbnika](#ctor)|Przeciążone. Konstruuje wystąpienie próbnika.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[get_address_mode](#get_address_mode)|Zwraca `address_mode` skojarzoną z obiektem próbnika.|
|[get_border_color](#get_border_color)|Zwraca kolor obramowania skojarzony z obiektem próbnika.|
|[get_filter_mode](#get_filter_mode)|Zwraca `filter_mode` skojarzoną z obiektem próbnika.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[operator =](#operator_eq)|Przeciążone. Operator przypisania.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[address_mode](#address_mode)|Pobiera tryb adresu `sampler` obiektu.|
|[border_color](#border_color)|Pobiera kolor obramowania `sampler` obiektu.|
|[filter_mode](#filter_mode)|Pobiera tryb filtru `sampler` obiektu.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`sampler`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amp_graphics. h

**Przestrzeń nazw:** concurrency:: Graphics

## <a name="sampler"></a><a name="ctor"></a> próbnika

Tworzy wystąpienie [klasy próbnika](sampler-class.md).

```cpp
sampler() restrict(cpu);    // [1] default constructor

sampler(                    // [2] constructor
    filter_mode _Filter_mode) restrict(cpu);

sampler(                    // [3] constructor
    address_mode _Address_mode,
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

sampler(                    // [4] constructor
    filter_mode _Filter_mode,
    address_mode _Address_mode,
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

sampler(                    // [5] copy constructor
    const sampler& _Other) restrict(amp,
    cpu);

sampler(                    // [6] move constructor
    sampler&& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parametry

*_Filter_mode*<br/>
Tryb filtru, który ma być używany w próbkach.

*_Address_mode*<br/>
Tryb adresowania, który ma być używany podczas próbkowania dla wszystkich wymiarów.

*_Border_color*<br/>
Kolor obramowania, który ma być używany, jeśli tryb adresu jest address_border. Wartość domyślna to `float_4(0.0f, 0.0f, 0.0f, 0.0f)`.

*_Other*<br/>
[5] Skopiuj Konstruktor `sampler` obiektu, który ma zostać skopiowany do nowego `sampler` wystąpienia.

[6] Przenieś Konstruktor `sampler` obiekt, który ma zostać przeniesiony do nowego `sampler` wystąpienia.

## <a name="address_mode"></a><a name="address_mode"></a> address_mode

Pobiera tryb adresu `sampler` obiektu.

```cpp
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;
```

## <a name="border_color"></a><a name="border_color"></a> border_color

Pobiera kolor obramowania `sampler` obiektu.

```cpp
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;
```

## <a name="filter_mode"></a><a name="filter_mode"></a> filter_mode

Pobiera tryb filtru `sampler` obiektu.

```cpp
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;
```

## <a name="get_address_mode"></a><a name="get_address_mode"></a> get_address_mode

Zwraca tryb filtru, który jest skonfigurowany dla tego elementu `sampler` .

```cpp
Concurrency::graphics::address_mode get_address_mode() const __GPU;
```

### <a name="return-value"></a>Wartość zwracana

Tryb adresu skonfigurowany dla próbnika.

## <a name="get_border_color"></a><a name="get_border_color"></a> get_border_color

Zwraca kolor obramowania, który jest skonfigurowany dla tego elementu `sampler` .

```cpp
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```

### <a name="return-value"></a>Wartość zwracana

Float_4, który zawiera kolor obramowania.

## <a name="get_filter_mode"></a><a name="get_filter_mode"></a> get_filter_mode

Zwraca tryb filtru, który jest skonfigurowany dla tego elementu `sampler` .

```cpp
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```

### <a name="return-value"></a>Wartość zwracana

Tryb filtru, który jest skonfigurowany dla próbnika.

## <a name="operator"></a><a name="operator_eq"></a> operator =

Przypisuje wartość innego obiektu próbnika do istniejącego próbnika.

```cpp
sampler& operator= (    // [1] copy assignment operator
    const sampler& _Other) restrict(amp, cpu);

sampler& operator= (    // [2] move assignment operator
    sampler&& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>Parametry

*_Other*<br/>
[1] Kopiuj operator przypisania, `sampler` do którego ma zostać skopiowany obiekt `sampler` .

[2] Przenieś operator przypisania do `sampler` tego obiektu `sampler` .

### <a name="return-value"></a>Wartość zwracana

Odwołanie do tego wystąpienia próbnika.

## <a name="see-also"></a>Zobacz też

[Concurrency::graphics — Przestrzeń nazw](concurrency-graphics-namespace.md)
