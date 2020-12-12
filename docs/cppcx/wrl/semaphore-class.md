---
description: Dowiedz się więcej o klasie semaforów
title: Semaphore — Klasa
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Semaphore class
- Microsoft::WRL::Wrappers::Semaphore::Lock method
- Microsoft::WRL::Wrappers::Semaphore::operator= operator
- Microsoft::WRL::Wrappers::Semaphore::Semaphore, constructor
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
ms.openlocfilehash: 0cf99ff0a0e5263b3ed924ec5ac69b7edb0bd1f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186236"
---
# <a name="semaphore-class"></a>Semaphore — Klasa

Reprezentuje obiekt synchronizacji, który kontroluje zasób udostępniony, który może obsługiwać ograniczoną liczbę użytkowników.

## <a name="syntax"></a>Składnia

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

Nazwa       | Opis
---------- | ------------------------------------------------------
`SyncLock` | Synonim klasy, która obsługuje blokady synchroniczne.

### <a name="public-constructors"></a>Konstruktory publiczne

Nazwa                               | Opis
---------------------------------- | ----------------------------------------------------
[Semafor:: semafor](#semaphore) | Inicjuje nowe wystąpienie klasy `Semaphore`.

### <a name="public-methods"></a>Metody publiczne

Nazwa                     | Opis
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[Semafor:: Lock](#lock) | Czeka, aż bieżący obiekt lub obiekt skojarzony z określonym dojściem jest w stanie sygnalizacji lub upłynie określony interwał limitu czasu.

### <a name="public-operators"></a>Operatory publiczne

Nazwa                                     | Opis
---------------------------------------- | ---------------------------------------------------------------------------------------
[Semafor:: operator =](#operator-assign) | Przenosi określone dojście z `Semaphore` obiektu do bieżącego `Semaphore` obiektu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`Semaphore`

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki

## <a name="semaphorelock"></a><a name="lock"></a> Semafor:: Lock

Czeka, aż bieżący obiekt lub `Semaphore` obiekt skojarzony z określonym dojściem jest w stanie sygnalizacji lub upłynie określony interwał limitu czasu.

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>Parametry

*milisekundy*<br/>
Interwał limitu czasu (w milisekundach). Wartość domyślna to NIESKOŃCZONość, która czeka na czas nieokreślony.

*h*<br/>
Dojście do `Semaphore` obiektu.

### <a name="return-value"></a>Wartość zwracana

Polecenie `Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`

## <a name="semaphoreoperator"></a><a name="operator-assign"></a> Semafor:: operator =

Przenosi określone dojście z `Semaphore` obiektu do bieżącego `Semaphore` obiektu.

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Parametry

*h*<br/>
Rvalue — odwołanie do `Semaphore` obiektu.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do bieżącego `Semaphore` obiektu.

## <a name="semaphoresemaphore"></a><a name="semaphore"></a> Semafor:: semafor

Inicjuje nowe wystąpienie klasy `Semaphore`.

```cpp
explicit Semaphore(
   HANDLE h
);

WRL_NOTHROW Semaphore(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Parametry

*h*<br/>
Uchwyt lub rvalue odwołanie do `Semaphore` obiektu.
