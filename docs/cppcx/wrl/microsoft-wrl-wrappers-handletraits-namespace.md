---
description: 'Dowiedz się więcej o: Microsoft:: WRL:: otoki:: HandleTraits, przestrzeń nazw'
title: Microsoft::WRL::Wrappers::HandleTraits — Przestrzeń nazw
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: 4bbc970a6d3445e8acda752be1a2030ee99759a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178059"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits — Przestrzeń nazw

Opisuje charakterystykę typowych typów zasobów opartych na obsłudze.

## <a name="syntax"></a>Składnia

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>Elementy członkowskie

### <a name="structures"></a>Struktury

|Nazwa|Opis|
|----------|-----------------|
|[CriticalSectionTraits — Struktura](criticalsectiontraits-structure.md)|Wyspecjalizowano `CriticalSection` obiekt do obsługi nieprawidłowej sekcji krytycznej lub funkcji w celu wydania sekcji krytycznej.|
|[EventTraits — Struktura](eventtraits-structure.md)|Definiuje charakterystykę `Event` dojścia do klasy.|
|[FileHandleTraits, struktura](filehandletraits-structure.md)|Definiuje charakterystykę dojścia do pliku.|
|[HANDLENullTraits, struktura](handlenulltraits-structure.md)|Definiuje typowe cechy niezainicjowanego dojścia.|
|[HANDLETraits — Struktura](handletraits-structure.md)|Definiuje typowe cechy dojścia.|
|[MutexTraits — Struktura](mutextraits-structure.md)|Definiuje typowe cechy klasy [mutex](mutex-class.md) .|
|[SemaphoreTraits, struktura](semaphoretraits-structure.md)|Definiuje typowe cechy obiektu semafora.|
|[SRWLockExclusiveTraits, struktura](srwlockexclusivetraits-structure.md)|Opisuje typowe cechy `SRWLock` klasy w trybie blokady wyłącznej.|
|[SRWLockSharedTraits — Struktura](srwlocksharedtraits-structure.md)|Opisuje typowe cechy `SRWLock` klasy w trybie blokady udostępnionej.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki

## <a name="see-also"></a>Zobacz też

[Microsoft:: WRL:: Otoke — przestrzeń nazw](microsoft-wrl-wrappers-namespace.md)
