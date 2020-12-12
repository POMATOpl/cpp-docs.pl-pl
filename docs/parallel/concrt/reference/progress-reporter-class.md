---
description: Dowiedz się więcej na temat klasy progress_reporter
title: progress_reporter — Klasa
ms.date: 11/04/2016
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
ms.openlocfilehash: 40ae3dba0c804381478d8c32da4425b20a9825d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169362"
---
# <a name="progress_reporter-class"></a>progress_reporter — Klasa

Klasa raportów postępu umożliwia raportowanie powiadomień o postępie określonego typu. Każdy obiekt progress_reporter jest powiązany z określoną akcją asynchroniczną lub operacją.

## <a name="syntax"></a>Składnia

```cpp
template<typename _ProgressType>
class progress_reporter;
```

### <a name="parameters"></a>Parametry

*_ProgressType*<br/>
Typ ładunku każdej powiadomienia o postępie raportowany przez raport postępu.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[progress_reporter](#ctor)||

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[report (raport)](#report)|Wysyła raport postępu do akcji asynchronicznej lub operacji, do której jest powiązany ten raport postępu.|

## <a name="remarks"></a>Uwagi

Ten typ jest dostępny tylko dla aplikacji środowisko wykonawcze systemu Windows.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`progress_reporter`

## <a name="requirements"></a>Wymagania

**Nagłówek:** ppltasks. h

**Przestrzeń nazw:** współbieżność

## <a name="progress_reporter"></a><a name="ctor"></a> progress_reporter

```cpp
progress_reporter();
```

## <a name="report"></a><a name="report"></a> Raport

Wysyła raport postępu do akcji asynchronicznej lub operacji, do której jest powiązany ten raport postępu.

```cpp
void report(const _ProgressType& val) const;
```

### <a name="parameters"></a>Parametry

*użyte*<br/>
Ładunek do zgłoszenia w ramach powiadomienia o postępie.

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności](concurrency-namespace.md)
