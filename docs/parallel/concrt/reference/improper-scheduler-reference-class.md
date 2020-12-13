---
description: Dowiedz się więcej na temat klasy improper_scheduler_reference
title: improper_scheduler_reference — Klasa
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference::improper_scheduler_reference
helpviewer_keywords:
- improper_scheduler_reference class
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
ms.openlocfilehash: 4857418e14908b2d085d52249236d6395284b98a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334596"
---
# <a name="improper_scheduler_reference-class"></a>improper_scheduler_reference — Klasa

Ta klasa opisuje wyjątek zgłoszony `Reference` , gdy metoda jest wywoływana w obiekcie, `Scheduler` który jest zamykany, z kontekstu, który nie jest częścią tego harmonogramu.

## <a name="syntax"></a>Składnia

```cpp
class improper_scheduler_reference : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[improper_scheduler_reference](#ctor)|Przeciążone. Konstruuje `improper_scheduler_reference` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`improper_scheduler_reference`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="improper_scheduler_reference"></a><a name="ctor"></a> improper_scheduler_reference

Konstruuje `improper_scheduler_reference` obiekt.

```cpp
explicit _CRTIMP improper_scheduler_reference(_In_z_ const char* _Message) throw();

improper_scheduler_reference() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Scheduler — Klasa](scheduler-class.md)
