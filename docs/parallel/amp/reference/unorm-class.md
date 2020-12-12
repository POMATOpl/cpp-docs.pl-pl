---
description: 'Dowiedz się więcej na temat: Klasa unorm'
title: unorm — Klasa
ms.date: 11/04/2016
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
ms.openlocfilehash: 947660d046ea41025e70aa4e6521e3c8f34c0a94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314531"
---
# <a name="unorm-class"></a>unorm — Klasa

Przedstawia numer unorm. Każdy element jest liczbą zmiennoprzecinkową z zakresu [0.0 f, 1.0 f].

## <a name="syntax"></a>Składnia

```cpp
class unorm;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor unorm](#ctor)|Przeciążone. Konstruktor domyślny. Zainicjuj do 0.0 f.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|unorm:: operator--||
|unorm:: operator float|Operator konwersji. Przekonwertuj liczbę unorm na wartość zmiennoprzecinkową.|
|unorm:: operator * =||
|unorm:: operator/=||
|unorm:: operator + +||
|unorm:: operator + =||
|unorm:: operator =||
|unorm:: operator-=||

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`unorm`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amp_short_vectors. h

**Przestrzeń nazw:** Concurrency:: Graphics

## <a name="unorm"></a><a name="ctor"></a> unorm

Konstruktor domyślny. Zainicjuj do 0.0 f.

```cpp
unorm(
    void) restrict(amp,
    cpu);

explicit unorm(
    float _V) restrict(amp,
    cpu);

explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

explicit unorm(
    int _V) restrict(amp,
    cpu);

explicit unorm(
    double _V) restrict(amp,
    cpu);

unorm(
    const unorm& _Other) restrict(amp,
    cpu);

inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parametry

*_V*<br/>
Wartość używana do inicjowania.

*_Other*<br/>
Obiekt normy używany do inicjowania.

## <a name="see-also"></a>Zobacz też

[Concurrency::graphics — Przestrzeń nazw](concurrency-graphics-namespace.md)
