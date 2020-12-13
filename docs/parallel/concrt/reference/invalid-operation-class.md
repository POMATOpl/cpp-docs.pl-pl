---
description: Dowiedz się więcej na temat klasy invalid_operation
title: invalid_operation — Klasa
ms.date: 11/04/2016
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
ms.openlocfilehash: f3050d487f2c374f66f264b6e568fce5244d25ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334544"
---
# <a name="invalid_operation-class"></a>invalid_operation — Klasa

Ta klasa opisuje wyjątek zgłoszony w przypadku wykonania nieprawidłowej operacji, która nie jest dokładniej opisana przez inny typ wyjątku zgłoszony przez środowisko uruchomieniowe współbieżności.

## <a name="syntax"></a>Składnia

```cpp
class invalid_operation : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[invalid_operation](#ctor)|Przeciążone. Konstruuje `invalid_operation` obiekt.|

## <a name="remarks"></a>Uwagi

Różne metody, które zgłaszają ten wyjątek, będą na ogół udokumentowane pod kątem tego, jakie okoliczności ich wygenerują.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`invalid_operation`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="invalid_operation"></a><a name="ctor"></a> invalid_operation

Konstruuje `invalid_operation` obiekt.

```cpp
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
