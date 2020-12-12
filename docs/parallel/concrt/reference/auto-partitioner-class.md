---
description: Dowiedz się więcej na temat klasy auto_partitioner
title: auto_partitioner — Klasa
ms.date: 11/04/2016
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
ms.openlocfilehash: d8e099c7a3132ce89f81df65d7e18a5c6c673697
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172261"
---
# <a name="auto_partitioner-class"></a>auto_partitioner — Klasa

`auto_partitioner`Klasa reprezentuje metodę domyślną `parallel_for` `parallel_for_each` i `parallel_transform` służy do partycjonowania zakresu, w którym się powtarza. Ta metoda partycjonowania wykorzystuje funkcję kradzieży zakresu na potrzeby równoważenia obciążenia, a także anulowania dla iteracji.

## <a name="syntax"></a>Składnia

```cpp
class auto_partitioner;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[auto_partitioner](#ctor)|Konstruuje `auto_partitioner` obiekt.|
|[~ auto_partitioner destruktor](#dtor)|Niszczy `auto_partitioner` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`auto_partitioner`

## <a name="requirements"></a>Wymagania

**Nagłówek:** PPL. h

**Przestrzeń nazw:** współbieżność

## <a name="auto_partitioner"></a><a name="dtor"></a> ~ auto_partitioner

Niszczy `auto_partitioner` obiekt.

```cpp
~auto_partitioner();
```

## <a name="auto_partitioner"></a><a name="ctor"></a> auto_partitioner

Konstruuje `auto_partitioner` obiekt.

```cpp
auto_partitioner();
```

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
