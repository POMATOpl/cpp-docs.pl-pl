---
description: Dowiedz się więcej na temat klasy invalid_compute_domain
title: invalid_compute_domain — Klasa
ms.date: 11/04/2016
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
helpviewer_keywords:
- invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
ms.openlocfilehash: 7598180a12cacabcdb308c3924c84eb17ec90ed7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330001"
---
# <a name="invalid_compute_domain-class"></a>invalid_compute_domain — Klasa

Wyjątek, który jest generowany, gdy środowisko uruchomieniowe nie może uruchomić jądra przy użyciu domeny obliczeniowej określonej w lokacji wywołania [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) .

## <a name="syntax"></a>Składnia

```cpp
class invalid_compute_domain : public runtime_exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor invalid_compute_domain](#ctor)|Inicjuje nowe wystąpienie klasy `invalid_compute_domain`.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`runtime_exception`

`invalid_compute_domain`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amprt. h

**Przestrzeń nazw:** Współbieżności

## <a name="invalid_compute_domain"></a><a name="ctor"></a> invalid_compute_domain

Inicjuje nowe wystąpienie klasy.

### <a name="syntax"></a>Składnia

```cpp
explicit invalid_compute_domain(
    const char * _Message ) throw();

invalid_compute_domain() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opis błędu.

### <a name="return-value"></a>Wartość zwracana

Wystąpienie `invalid_compute_domain` klasy

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności (C++ AMP)](concurrency-namespace-cpp-amp.md)
