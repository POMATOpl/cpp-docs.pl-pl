---
description: Dowiedz się więcej na temat klasy scheduler_not_attached
title: scheduler_not_attached — Klasa
ms.date: 11/04/2016
f1_keywords:
- scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached::scheduler_not_attached
helpviewer_keywords:
- scheduler_not_attached class
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
ms.openlocfilehash: 1d412ffecea288d4ecad1d0c2949e7444adfd913
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188862"
---
# <a name="scheduler_not_attached-class"></a>scheduler_not_attached — Klasa

Ta klasa opisuje wyjątek zgłoszony podczas wykonywania operacji, który wymaga dołączenia harmonogramu do bieżącego kontekstu, a jeden nie jest.

## <a name="syntax"></a>Składnia

```cpp
class scheduler_not_attached : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[scheduler_not_attached](#ctor)|Przeciążone. Konstruuje `scheduler_not_attached` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`scheduler_not_attached`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="scheduler_not_attached"></a><a name="ctor"></a> scheduler_not_attached

Konstruuje `scheduler_not_attached` obiekt.

```cpp
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Scheduler — Klasa](scheduler-class.md)
