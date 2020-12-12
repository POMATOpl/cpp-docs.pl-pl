---
description: Dowiedz się więcej na temat klasy uninitialized_object
title: uninitialized_object — Klasa
ms.date: 03/27/2019
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
ms.openlocfilehash: 4929de9e865492c9fb468f5fac336f67fb307efb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326393"
---
# <a name="uninitialized_object-class"></a>uninitialized_object — Klasa

Wyjątek, który jest generowany, gdy jest używany Niezainicjowany obiekt.

## <a name="syntax"></a>Składnia

```cpp
class uninitialized_object : public runtime_exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor uninitialized_object](#uninitialized_object)|Inicjuje nowe wystąpienie klasy `uninitialized_object`.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`runtime_exception`

`uninitialized_object`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amprt. h

**Przestrzeń nazw:** Współbieżności

## <a name="uninitialized_object"></a><a name="uninitialized_object"></a> uninitialized_object

Tworzy nowe wystąpienie `uninitialized_object` wyjątku.

### <a name="syntax"></a>Składnia

```cpp
explicit uninitialized_object(
    const char * _Message ) throw();

uninitialized_object() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opis błędu.

### <a name="return-value"></a>Wartość zwracana

`uninitialized_object`Obiekt wyjątku.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności (C++ AMP)](concurrency-namespace-cpp-amp.md)
