---
description: Dowiedz się więcej na temat klasy simple_partitioner
title: simple_partitioner — Klasa
ms.date: 11/04/2016
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
ms.openlocfilehash: 76dcac6d7fc2dce5b69d0a9dbefaf01420f8bcde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188693"
---
# <a name="simple_partitioner-class"></a>simple_partitioner — Klasa

`simple_partitioner`Klasa reprezentuje statyczne partycjonowanie zakresu powtarzanego przez `parallel_for` . Program Partitioner dzieli zakres na fragmenty w taki sposób, że każdy fragment ma co najmniej liczbę iteracji określoną przez rozmiar fragmentu.

## <a name="syntax"></a>Składnia

```cpp
class simple_partitioner;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[simple_partitioner](#ctor)|Konstruuje `simple_partitioner` obiekt.|
|[~ simple_partitioner destruktor](#dtor)|Niszczy `simple_partitioner` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`simple_partitioner`

## <a name="requirements"></a>Wymagania

**Nagłówek:** PPL. h

**Przestrzeń nazw:** współbieżność

## <a name="simple_partitioner"></a><a name="dtor"></a> ~ simple_partitioner

Niszczy `simple_partitioner` obiekt.

```cpp
~simple_partitioner();
```

## <a name="simple_partitioner"></a><a name="ctor"></a> simple_partitioner

Konstruuje `simple_partitioner` obiekt.

```cpp
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>Parametry

*_Chunk_size*<br/>
Minimalny rozmiar partycji.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
