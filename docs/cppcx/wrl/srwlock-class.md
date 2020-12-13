---
description: 'Dowiedz się więcej na temat: Klasa SRWLock'
title: SRWLock — Klasa
ms.date: 09/25/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock_
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::~SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
helpviewer_keywords:
- Microsoft::WRL::Wrappers::SRWLock class
- Microsoft::WRL::Wrappers::SRWLock::LockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::LockShared method
- Microsoft::WRL::Wrappers::SRWLock::SRWLock, constructor
- Microsoft::WRL::Wrappers::SRWLock::SRWLock_ data member
- Microsoft::WRL::Wrappers::SRWLock::~SRWLock, destructor
- Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::TryLockShared method
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
ms.openlocfilehash: 10bc3dc700f90d5154ece1546cdf3ec464ea6e56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135190"
---
# <a name="srwlock-class"></a>SRWLock — Klasa

Przedstawia cienkią blokadę czytnika/składnika zapisywania.

## <a name="syntax"></a>Składnia

```cpp
class SRWLock;
```

## <a name="remarks"></a>Uwagi

Slim blokada czytnika/składnika zapisywania jest używana do synchronizowania dostępu między wątkami a obiektem lub zasobem. Aby uzyskać więcej informacji, zobacz [funkcje synchronizacji](/windows/win32/Sync/synchronization-functions).

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

Nazwa                | Opis
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | Synonim dla `SRWLock` obiektu, który jest uzyskiwany w trybie wyłączności.
`SyncLockShared`    | Synonim dla `SRWLock` obiektu, który jest uzyskiwany w trybie udostępnionym.

### <a name="public-constructors"></a>Konstruktory publiczne

Nazwa                                     | Opis
---------------------------------------- | --------------------------------------------------
[SRWLock:: SRWLock](#srwlock-constructor) | Inicjuje nowe wystąpienie klasy `SRWLock`.
[SRWLock:: ~ SRWLock](#tilde-srwlock)      | Umożliwia odinicjowanie wystąpienia `SRWLock` klasy.

### <a name="public-methods"></a>Metody publiczne

Nazwa                                           | Opis
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock:: LockExclusive —](#lockexclusive)       | Uzyskuje `SRWLock` obiekt w trybie wyłączności.
[SRWLock:: LockShared —](#lockshared)             | Uzyskuje `SRWLock` obiekt w trybie udostępnionym.
[SRWLock:: TryLockExclusive —](#trylockexclusive) | Próbuje uzyskać `SRWLock` obiekt w trybie wyłączności dla bieżącego lub określonego `SRWLock` obiektu.
[SRWLock:: TryLockShared —](#trylockshared)       | Próbuje uzyskać `SRWLock` obiekt w trybie udostępnionym dla bieżącego lub określonego `SRWLock` obiektu.

### <a name="protected-data-member"></a>Składowa chronionych danych

Nazwa                                      | Opis
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock:: SRWLock_](#srwlock-data-member) | Zawiera podstawową zmienną blokowania dla bieżącego `SRWLock` obiektu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`SRWLock`

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki

## <a name="srwlocksrwlock"></a><a name="tilde-srwlock"></a> SRWLock:: ~ SRWLock

Umożliwia odinicjowanie wystąpienia `SRWLock` klasy.

```cpp
~SRWLock();
```

## <a name="srwlocklockexclusive"></a><a name="lockexclusive"></a> SRWLock:: LockExclusive —

Uzyskuje `SRWLock` obiekt w trybie wyłączności.

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametry

*skręt*<br/>
Wskaźnik do `SRWLock` obiektu.

### <a name="return-value"></a>Wartość zwracana

`SRWLock`Obiekt w trybie wyłączności.

## <a name="srwlocklockshared"></a><a name="lockshared"></a> SRWLock:: LockShared —

Uzyskuje `SRWLock` obiekt w trybie udostępnionym.

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametry

*skręt*<br/>
Wskaźnik do `SRWLock` obiektu.

### <a name="return-value"></a>Wartość zwracana

`SRWLock`Obiekt w trybie udostępnionym.

## <a name="srwlocksrwlock"></a><a name="srwlock-constructor"></a> SRWLock:: SRWLock

Inicjuje nowe wystąpienie klasy `SRWLock`.

```cpp
SRWLock();
```

## <a name="srwlocksrwlock_"></a><a name="srwlock-data-member"></a> SRWLock:: SRWLock_

Zawiera podstawową zmienną blokowania dla bieżącego `SRWLock` obiektu.

```cpp
SRWLOCK SRWLock_;
```

## <a name="srwlocktrylockexclusive"></a><a name="trylockexclusive"></a> SRWLock:: TryLockExclusive —

Próbuje uzyskać `SRWLock` obiekt w trybie wyłączności dla bieżącego lub określonego `SRWLock` obiektu. Jeśli wywołanie powiedzie się, wątek wywołujący przejmuje własność blokady.

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametry

*skręt*<br/>
Wskaźnik do `SRWLock` obiektu.

### <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, `SRWLock` obiekt w trybie wyłączności i wątek wywołujący przejmują prawo własności blokady. W przeciwnym razie `SRWLock` obiekt, którego stan jest nieprawidłowy.

## <a name="srwlocktrylockshared"></a><a name="trylockshared"></a> SRWLock:: TryLockShared —

Próbuje uzyskać `SRWLock` obiekt w trybie udostępnionym dla bieżącego lub określonego `SRWLock` obiektu.

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parametry

*skręt*<br/>
Wskaźnik do `SRWLock` obiektu.

### <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, `SRWLock` obiekt w trybie współdzielonym i wątek wywołujący przejmują prawo własności blokady. W przeciwnym razie `SRWLock` obiekt, którego stan jest nieprawidłowy.
