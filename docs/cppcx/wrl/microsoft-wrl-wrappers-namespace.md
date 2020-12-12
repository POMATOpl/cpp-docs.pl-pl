---
description: 'Dowiedz się więcej o: Microsoft:: WRL:: otoki — przestrzeń nazw'
title: Microsoft::WRL::Wrappers — Przestrzeń nazw
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
ms.openlocfilehash: 603fa14b0e43f481b1afe56d98e355d328f284fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209402"
---
# <a name="microsoftwrlwrappers-namespace"></a>Microsoft::WRL::Wrappers — Przestrzeń nazw

Definiuje typy otoki inicjującej pozyskiwanie zasobów (RAII), które upraszczają zarządzanie obiektami, ciągami i uchwytami.

## <a name="syntax"></a>Składnia

```cpp
namespace Microsoft::WRL::Wrappers;
```

## <a name="members"></a>Elementy członkowskie

### <a name="typedefs"></a>Typedefs

|Nazwa|Opis|
|----------|-----------------|
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|

### <a name="classes"></a>Klasy

|Nazwa|Opis|
|----------|-----------------|
|[Klasa CriticalSection](criticalsection-class.md)|Reprezentuje obiekt sekcji krytycznej.|
|[Event — Klasa (WRL)](event-class-wrl.md)|Reprezentuje zdarzenie.|
|[Obsługa klasy](handlet-class.md)|Reprezentuje dojście do obiektu.|
|[Klasa HString](hstring-class.md)|Zapewnia obsługę manipulowania dojściami HSTRING.|
|[Klasa HStringReference](hstringreference-class.md)|Reprezentuje element HSTRING, który jest tworzony na podstawie istniejącego ciągu.|
|[Mutex — Klasa](mutex-class.md)|Reprezentuje obiekt synchronizacji, który kontroluje wyłącznie zasób udostępniony.|
|[Klasa RoInitializeWrapper](roinitializewrapper-class.md)|Inicjuje środowisko wykonawcze systemu Windows.|
|[Klasa semaforów](semaphore-class.md)|Reprezentuje obiekt synchronizacji, który kontroluje zasób udostępniony, który może obsługiwać ograniczoną liczbę użytkowników.|
|[Klasa SRWLock](srwlock-class.md)|Przedstawia cienkią blokadę czytnika/składnika zapisywania.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL, przestrzeń nazw](microsoft-wrl-namespace.md)
