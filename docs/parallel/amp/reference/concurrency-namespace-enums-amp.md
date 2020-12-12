---
description: 'Dowiedz się więcej na temat: wyliczenia przestrzeni nazw współbieżności (AMP)'
title: Wyliczenia przestrzeni nazw współbieżności (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
ms.openlocfilehash: 60f4b325de47a600ee5a28f30ecc4a06fc2082a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284905"
---
# <a name="concurrency-namespace-enums-amp"></a>Wyliczenia przestrzeni nazw współbieżności (AMP)

[access_type, Wyliczenie](#access_type)\
[queuing_mode, Wyliczenie](#queuing_mode)

## <a name="access_type-enumeration"></a><a name="access_type"></a> access_type, Wyliczenie

Typ wyliczeniowy używany do określenia różnych typów dostępu do danych.

```cpp
enum access_type;
```

### <a name="values"></a>Wartości

|Nazwa|Opis|
|----------|-----------------|
|`access_type_auto`|Automatycznie wybieraj najlepsze `access_type` dla akceleratora.|
|`access_type_none`|Personel. Alokacja jest dostępna tylko dla akceleratora, a nie na PROCESORze.|
|`access_type_read`|Udostępniać. Przydział jest dostępny na akceleratorze i można go odczytać na PROCESORze.|
|`access_type_read_write`|Udostępniać. Alokacja jest dostępna w akceleratorze i jest zapisywalna na PROCESORze.|
|`access_type_write`|Udostępniać. Przydział jest dostępny na akceleratorze i można go odczytać i zapisać na procesorze CPU.|

## <a name="queuing_mode-enumeration"></a><a name="queuing_mode"></a> queuing_mode, Wyliczenie

Określa tryby kolejkowania, które są obsługiwane w akceleratorze.

```cpp
enum queuing_mode;
```

### <a name="values"></a>Wartości

|Nazwa|Opis|
|----------|-----------------|
|`queuing_mode_immediate`|Tryb kolejkowania, który określa, że wszystkie polecenia, na przykład [funkcja parallel_for_each (C++ amp)](concurrency-namespace-functions-amp.md#parallel_for_each), są wysyłane do odpowiedniego urządzenia akceleratora zaraz po powrocie do obiektu wywołującego.|
|`queuing_mode_automatic`|Tryb kolejkowania, który określa, że polecenia są umieszczane w kolejce poleceń, która odpowiada obiektowi [accelerator_view](accelerator-view-class.md) . Polecenia są wysyłane do urządzenia, gdy zostanie wywołane [accelerator_view:: Flush](accelerator-view-class.md#flush) .|

## <a name="see-also"></a>Zobacz też

[Przestrzeń nazw współbieżności (C++ AMP)](concurrency-namespace-cpp-amp.md)
