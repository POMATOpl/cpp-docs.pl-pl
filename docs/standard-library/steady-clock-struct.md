---
description: Dowiedz się więcej na temat struktury steady_clock
title: steady_clock — struktura
ms.date: 05/22/2018
f1_keywords:
- chrono/std::chrono::steady_clock
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
ms.openlocfilehash: 066a98f4eba6670e640e9fcc9b79eb017859a3d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169076"
---
# <a name="steady_clock-struct"></a>steady_clock — struktura

Reprezentuje *stały* zegar.

## <a name="syntax"></a>Składnia

```cpp
struct steady_clock;
```

## <a name="remarks"></a>Uwagi

W systemie Windows `steady_clock` zawija `QueryPerformanceCounter` funkcję.

Zegar jest *monotoniczny* , jeśli wartość zwracana przez pierwsze wywołanie `now` jest zawsze mniejsza lub równa wartości zwracanej przez kolejne wywołanie do `now` . Zegar jest *stabilny* , jeśli jest *monotoniczny* , a czas między taktami zegara jest stały.

`high_resolution_clock` jest elementem TypeDef dla elementu `steady_clock` .

### <a name="public-typedefs"></a>Publiczne definicje typów

|Nazwa|Opis|
|----------|-----------------|
|`steady_clock::duration`|Synonim dla `nanoseconds` , zdefiniowany w \<chrono> .|
|`steady_clock::period`|Synonim dla `nano` , zdefiniowany w \<ratio> .|
|`steady_clock::rep`|Synonim dla **`long long`** typu, który jest używany do reprezentowania liczby taktów zegara w zawartym utworzeniu wystąpienia `duration` .|
|`steady_clock::time_point`|Synonim dla `chrono::time_point<steady_clock>` .|

## <a name="public-functions"></a>Funkcje publiczne

|Funkcja|Opis|
|--------------|-----------------|
|`now`|Zwraca bieżący czas jako `time_point` wartość.|

## <a name="public-constants"></a>Stałe publiczne

|Nazwa|Opis|
|----------|-----------------|
|`steady_clock::is_steady`|Zawiera **`true`** . `steady_clock`Jest *stała*.|

## <a name="requirements"></a>Wymagania

**Nagłówek:**\<chrono>

**Przestrzeń nazw:** std:: Chrono

## <a name="see-also"></a>Zobacz też

- [Dokumentacja plików nagłówkowych](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [system_clock — Struktura](../standard-library/system-clock-structure.md)
