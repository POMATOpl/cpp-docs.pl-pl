---
description: Dowiedz się więcej na temat klasy affinity_partitioner
title: affinity_partitioner — Klasa
ms.date: 11/04/2016
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
ms.openlocfilehash: 44aa693d5007507e33f062a673713d1ddbda3172
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172326"
---
# <a name="affinity_partitioner-class"></a>affinity_partitioner — Klasa

`affinity_partitioner`Klasa jest podobna do `static_partitioner` klasy, ale zwiększa koligację pamięci podręcznej przez wybór zakresu mapowania na wątki robocze. Może znacząco poprawić wydajność, gdy pętla jest ponownie wykonywana nad tym samym zestawem danych, a dane pasują do pamięci podręcznej. Należy zauważyć, że ten sam `affinity_partitioner` obiekt musi być używany z kolejnymi iteracjami pętli równoległej, która jest wykonywana w określonym zestawie danych, aby można było skorzystać z lokalizacji danych.

## <a name="syntax"></a>Składnia

```cpp
class affinity_partitioner;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[affinity_partitioner](#ctor)|Konstruuje `affinity_partitioner` obiekt.|
|[~ affinity_partitioner destruktor](#dtor)|Niszczy `affinity_partitioner` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`affinity_partitioner`

## <a name="requirements"></a>Wymagania

**Nagłówek:** PPL. h

**Przestrzeń nazw:** współbieżność

## <a name="affinity_partitioner"></a><a name="dtor"></a> ~ affinity_partitioner

Niszczy `affinity_partitioner` obiekt.

```cpp
~affinity_partitioner();
```

## <a name="affinity_partitioner"></a><a name="ctor"></a> affinity_partitioner

Konstruuje `affinity_partitioner` obiekt.

```cpp
affinity_partitioner();
```

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
