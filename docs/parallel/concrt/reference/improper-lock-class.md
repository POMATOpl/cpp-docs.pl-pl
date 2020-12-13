---
description: Dowiedz się więcej na temat klasy improper_lock
title: improper_lock — Klasa
ms.date: 11/04/2016
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
ms.openlocfilehash: 8e29172ad171bbd3f95b3079840fb50b91dfe577
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334636"
---
# <a name="improper_lock-class"></a>improper_lock — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy blokada jest pobrana nieprawidłowo.

## <a name="syntax"></a>Składnia

```cpp
class improper_lock : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[improper_lock](#ctor)|Przeciążone. Konstruuje `improper_lock exception` .|

## <a name="remarks"></a>Uwagi

Zazwyczaj ten wyjątek jest zgłaszany, gdy podejmowana jest próba uzyskania blokady niewspółpracującej cyklicznie w tym samym kontekście.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`improper_lock`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="improper_lock"></a><a name="ctor"></a> improper_lock

Konstruuje `improper_lock exception` .

```cpp
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)<br/>
[Klasa critical_section](critical-section-class.md)<br/>
[Klasa reader_writer_lock](reader-writer-lock-class.md)
