---
description: Dowiedz się więcej na temat klasy static_partitioner
title: static_partitioner — Klasa
ms.date: 11/04/2016
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
ms.openlocfilehash: f75d2e620a66e0ed347d39d429f59e3e2715369a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188498"
---
# <a name="static_partitioner-class"></a>static_partitioner — Klasa

`static_partitioner`Klasa reprezentuje statyczne partycjonowanie zakresu powtarzanego przez `parallel_for` . Partycja dzieli zakres na tyle fragmentów, ile jest dostępnych dla pracowników w źródłowym harmonogramie.

## <a name="syntax"></a>Składnia

```cpp
class static_partitioner;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[static_partitioner](#ctor)|Konstruuje `static_partitioner` obiekt.|
|[~ static_partitioner destruktor](#dtor)|Niszczy `static_partitioner` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`static_partitioner`

## <a name="requirements"></a>Wymagania

**Nagłówek:** PPL. h

**Przestrzeń nazw:** współbieżność

## <a name="static_partitioner"></a><a name="dtor"></a> ~ static_partitioner

Niszczy `static_partitioner` obiekt.

```cpp
~static_partitioner();
```

## <a name="static_partitioner"></a><a name="ctor"></a> static_partitioner

Konstruuje `static_partitioner` obiekt.

```cpp
static_partitioner();
```

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
