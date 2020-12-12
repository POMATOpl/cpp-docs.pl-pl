---
description: Dowiedz się więcej na temat klasy operation_timed_out
title: operation_timed_out — Klasa
ms.date: 11/04/2016
f1_keywords:
- operation_timed_out
- CONCRT/concurrency::operation_timed_out
- CONCRT/concurrency::operation_timed_out::operation_timed_out
helpviewer_keywords:
- operation_timed_out class
ms.assetid: 963efe1d-a6e0-477c-9a70-d93d8412c897
ms.openlocfilehash: 476dfc2d7f29b2769c076ff525f3d0eb1e20a8f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236558"
---
# <a name="operation_timed_out-class"></a>operation_timed_out — Klasa

Ta klasa opisuje wyjątek zgłoszony, gdy upłynął limit czasu operacji.

## <a name="syntax"></a>Składnia

```cpp
class operation_timed_out : public std::exception;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[operation_timed_out](#ctor)|Przeciążone. Konstruuje `operation_timed_out` obiekt.|

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`exception`

`operation_timed_out`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ConcRT. h

**Przestrzeń nazw:** współbieżność

## <a name="operation_timed_out"></a><a name="ctor"></a> operation_timed_out

Konstruuje `operation_timed_out` obiekt.

```cpp
explicit _CRTIMP operation_timed_out(_In_z_ const char* _Message) throw();

operation_timed_out() throw();
```

### <a name="parameters"></a>Parametry

*_Message*<br/>
Opisowy komunikat o błędzie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
