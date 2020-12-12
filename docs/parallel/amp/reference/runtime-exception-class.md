---
description: Dowiedz się więcej na temat klasy runtime_exception
title: runtime_exception — Klasa
ms.date: 03/27/2019
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
ms.openlocfilehash: 8fa5750473ee5a9b84255313832bbcbbba406394
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329936"
---
# <a name="runtime_exception-class"></a>runtime_exception — Klasa

Typ podstawowy dla wyjątków w bibliotece C++ Accelerated Massive Parallelism (AMP).

### <a name="syntax"></a>Składnia

```cpp
class runtime_exception : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[Konstruktor runtime_exception](#ctor)|Inicjuje nowe wystąpienie klasy `runtime_exception`.|
|[~ runtime_exception destruktor](#dtor)|Niszczy `runtime_exception` obiekt.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[get_error_code](#get_error_code)|Zwraca kod błędu, który spowodował wyjątek.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[operator =](#operator_eq)|Kopiuje zawartość określonego `runtime_exception` obiektu do tego elementu.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`runtime_exception`

## <a name="requirements"></a>Wymagania

**Nagłówek:** amprt. h

**Przestrzeń nazw:** Współbieżności

## <a name="runtime_exception-constructor"></a><a name="ctor"></a> Konstruktor runtime_exception

Inicjuje nowe wystąpienie klasy.

### <a name="syntax"></a>Składnia

```cpp
runtime_exception(
    const char * _Message,
    HRESULT _Hresult ) throw();

explicit runtime_exception(
    HRESULT _Hresult ) throw();

runtime_exception(
    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opis błędu, który spowodował wyjątek.

*_Hresult*<br/>
WYNIK HRESULT błędu, który spowodował wyjątek.

*_Other*<br/>
`runtime_exception`Obiekt do skopiowania.

### <a name="return-value"></a>Wartość zwracana

Obiekt `runtime_exception`.

## <a name="runtime_exception-destructor"></a><a name="dtor"></a>  ~ runtime_exception destruktor

Niszczy obiekt.

### <a name="syntax"></a>Składnia

```cpp
virtual ~runtime_exception() throw();
```

## <a name="get_error_code"></a><a name="get_error_code"></a> get_error_code

Zwraca kod błędu, który spowodował wyjątek.

### <a name="syntax"></a>Składnia

```cpp
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Wartość zwracana

WYNIK HRESULT błędu, który spowodował wyjątek.

## <a name="operator"></a><a name="operator_eq"></a> operator =

Kopiuje zawartość określonego `runtime_exception` obiektu do tego elementu.

### <a name="syntax"></a>Składnia

```cpp
runtime_exception & operator= (    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Parametry

*_Other*<br/>
`runtime_exception`Obiekt do skopiowania.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do tego `runtime_exception` obiektu.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności (C++ AMP)](concurrency-namespace-cpp-amp.md)
