---
description: Dowiedz się więcej na temat klasy nested_scheduler_missing_detach
title: nested_scheduler_missing_detach — Klasa
ms.date: 11/04/2016
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
ms.openlocfilehash: 3d1232b8f9b807835f5b4b1e19c6049d049f12f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202109"
---
# <a name="nested_scheduler_missing_detach-class"></a>nested_scheduler_missing_detach — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy środowisko uruchomieniowe współbieżności wykryje, że pozostało wywołanie `CurrentScheduler::Detach` metody w kontekście dołączonym do drugiego harmonogramu przy użyciu `Attach` metody `Scheduler` obiektu.

## <a name="syntax"></a>Składnia

```cpp
class nested_scheduler_missing_detach : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[nested_scheduler_missing_detach](#ctor)|Przeciążone. Konstruuje `nested_scheduler_missing_detach` obiekt.|

## <a name="remarks"></a>Uwagi

Ten wyjątek jest zgłaszany tylko w przypadku zagnieżdżania jednego harmonogramu w innym przez wywołanie `Attach` metody `Scheduler` obiektu w kontekście, który jest już własnością lub dołączony do innego harmonogramu. Środowisko uruchomieniowe współbieżności zgłasza ten wyjątek odpowiednio Uzgodnij, gdy może wykryć scenariusz jako pomoc w celu zlokalizowania problemu. Nie każde wystąpienie zaniedbania wywołania `CurrentScheduler::Detach` metody jest gwarantowane wygenerowanie tego wyjątku.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`nested_scheduler_missing_detach`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="nested_scheduler_missing_detach"></a><a name="ctor"></a> nested_scheduler_missing_detach

Konstruuje `nested_scheduler_missing_detach` obiekt.

```cpp
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Scheduler — Klasa](scheduler-class.md)
