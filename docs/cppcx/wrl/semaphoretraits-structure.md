---
description: Dowiedz się więcej o strukturze SemaphoreTraits
title: SemaphoreTraits — Struktura
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock method
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
ms.openlocfilehash: 5779a30d22fd2d32e57f96f752bb52e2bf469cd8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135229"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits — Struktura

Definiuje typowe cechy `Semaphore` obiektu.

## <a name="syntax"></a>Składnia

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

Nazwa                               | Opis
---------------------------------- | --------------------------------------
[SemaphoreTraits:: Unlock](#unlock) | Zwalnia kontrolę nad zasobem udostępnionym.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki:: HandleTraits

## <a name="semaphoretraitsunlock"></a><a name="unlock"></a> SemaphoreTraits:: Unlock

Zwalnia kontrolę nad zasobem udostępnionym.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Parametry

*h*<br/>
Dojście do `Semaphore` obiektu.

### <a name="remarks"></a>Uwagi

Jeśli operacja odblokowywania nie powiedzie się, `Unlock()` emituje błąd, który wskazuje przyczynę niepowodzenia.
