---
description: Dowiedz się więcej na temat klasy improper_scheduler_detach
title: improper_scheduler_detach — Klasa
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach::improper_scheduler_detach
helpviewer_keywords:
- improper_scheduler_detach class
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
ms.openlocfilehash: 62def23a4a3459c4cb8268b3b0f4df4a77025668
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334607"
---
# <a name="improper_scheduler_detach-class"></a>improper_scheduler_detach — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy `CurrentScheduler::Detach` Metoda jest wywoływana w kontekście, który nie został dołączony do żadnego harmonogramu przy użyciu `Attach` metody `Scheduler` obiektu.

## <a name="syntax"></a>Składnia

```cpp
class improper_scheduler_detach : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[improper_scheduler_detach](#ctor)|Przeciążone. Konstruuje `improper_scheduler_detach` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`improper_scheduler_detach`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="improper_scheduler_detach"></a><a name="ctor"></a> improper_scheduler_detach

Konstruuje `improper_scheduler_detach` obiekt.

```cpp
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Scheduler — Klasa](scheduler-class.md)
