---
description: Dowiedz się więcej o strukturze SRWLockSharedTraits
title: SRWLockSharedTraits — Struktura
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock method
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
ms.openlocfilehash: 2cdfbd584adeffc9dedd8504d9183d6c5d4c1a95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135125"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits — Struktura

Opisuje typowe cechy `SRWLock` klasy w trybie blokady udostępnionej.

## <a name="syntax"></a>Składnia

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

Nazwa   | Opis
------ | --------------------------------------------------------------------------
`Type` | Synonim dla wskaźnika do klasy [SRWLOCK](srwlock-class.md) .

### <a name="public-methods"></a>Metody publiczne

Nazwa                                                     | Opis
-------------------------------------------------------- | -----------------------------------------------------------------
[SRWLockSharedTraits:: GetInvalidValue —](#getinvalidvalue) | Pobiera `SRWLockSharedTraits` obiekt, który jest zawsze nieprawidłowy.
[SRWLockSharedTraits:: Unlock](#unlock)                   | Zwalnia kontrolę wykluczającą określonego `SRWLock` obiektu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`SRWLockSharedTraits`

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki:: HandleTraits

## <a name="srwlocksharedtraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> SRWLockSharedTraits:: GetInvalidValue —

Pobiera `SRWLockSharedTraits` obiekt, który jest zawsze nieprawidłowy.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Wartość zwracana

Dojście do `SRWLockSharedTraits` obiektu.

## <a name="srwlocksharedtraitsunlock"></a><a name="unlock"></a> SRWLockSharedTraits:: Unlock

Zwalnia kontrolę wykluczającą określonego `SRWLock` obiektu.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Parametry

*SRWLock*<br/>
Dojście do `SRWLock` obiektu.
