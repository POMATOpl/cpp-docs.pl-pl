---
description: Dowiedz się więcej o strukturze SRWLockExclusiveTraits
title: SRWLockExclusiveTraits — Struktura
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock method
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
ms.openlocfilehash: 135d4f866d1ca32ee9170ef9844cb0bf8d38c29a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186210"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits — Struktura

Opisuje typowe cechy `SRWLock` klasy w trybie blokady wyłącznej.

## <a name="syntax"></a>Składnia

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

Nazwa   | Opis
------ | --------------------------------------------------------------------------
`Type` | Synonim dla wskaźnika do klasy [SRWLOCK](srwlock-class.md) .

### <a name="public-methods"></a>Metody publiczne

Nazwa                                                        | Opis
----------------------------------------------------------- | --------------------------------------------------------------------
[SRWLockExclusiveTraits:: GetInvalidValue —](#getinvalidvalue) | Pobiera `SRWLockExclusiveTraits` obiekt, który jest zawsze nieprawidłowy.
[SRWLockExclusiveTraits:: Unlock](#unlock)                   | Zwalnia kontrolę wykluczającą określonego `SRWLock` obiektu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`SRWLockExclusiveTraits`

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki:: HandleTraits

## <a name="srwlockexclusivetraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> SRWLockExclusiveTraits:: GetInvalidValue —

Pobiera `SRWLockExclusiveTraits` obiekt, który jest zawsze nieprawidłowy.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Wartość zwracana

Pusty `SRWLockExclusiveTraits` obiekt.

## <a name="srwlockexclusivetraitsunlock"></a><a name="unlock"></a> SRWLockExclusiveTraits:: Unlock

Zwalnia kontrolę wykluczającą określonego `SRWLock` obiektu.

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Parametry

*SRWLock*<br/>
Dojście do `SRWLock` obiektu.
