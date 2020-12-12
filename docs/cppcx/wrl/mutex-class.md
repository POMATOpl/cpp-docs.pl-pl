---
description: Dowiedz się więcej o klasie mutex
title: Mutex — Klasa
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Mutex class
- Microsoft::WRL::Wrappers::Mutex::Lock method
- Microsoft::WRL::Wrappers::Mutex::Mutex, constructor
- Microsoft::WRL::Wrappers::Mutex::operator= operator
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
ms.openlocfilehash: f69c14014a2283fe56ef8e7f705bebe5a5f6dc9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330846"
---
# <a name="mutex-class"></a>Mutex — Klasa

Reprezentuje obiekt synchronizacji, który kontroluje wyłącznie zasób udostępniony.

## <a name="syntax"></a>Składnia

```cpp
class Mutex : public HandleT<HandleTraits::MutexTraits>;
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-typedefs"></a>Publiczne definicje typów

Nazwa       | Opis
---------- | ------------------------------------------------------
`SyncLock` | Synonim klasy, która obsługuje blokady synchroniczne.

### <a name="public-constructor"></a>Konstruktor publiczny

Nazwa                   | Opis
---------------------- | ------------------------------------------------
[Mutex:: mutex](#mutex) | Inicjuje nowe wystąpienie klasy `Mutex`.

### <a name="public-members"></a>Publiczne składowe

Nazwa                 | Opis
-------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------
[Mutex:: Lock](#lock) | Czeka, aż bieżący obiekt lub `Mutex` obiekt skojarzony z określonym dojściem zwolni element mutex lub upłynie określony interwał limitu czasu.

### <a name="public-operator"></a>Operator publiczny

Nazwa                                 | Opis
------------------------------------ | ---------------------------------------------------------------------------
[Mutex:: operator =](#operator-assign) | Przypisuje (przenosi) określony `Mutex` obiekt do bieżącego `Mutex` obiektu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`Mutex`

## <a name="requirements"></a>Wymagania

**Nagłówek:** corewrappers. h

**Przestrzeń nazw:** Microsoft:: WRL:: otoki

## <a name="mutexlock"></a><a name="lock"></a> Mutex:: Lock

Czeka, aż bieżący obiekt lub `Mutex` obiekt skojarzony z określonym dojściem zwolni element mutex lub upłynie określony interwał limitu czasu.

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
Uchwyt `Mutex` obiektu.

### <a name="return-value"></a>Wartość zwracana

## <a name="mutexmutex"></a><a name="mutex"></a> Mutex:: mutex

Inicjuje nowe wystąpienie klasy `Mutex`.

```cpp
explicit Mutex(
   HANDLE h
);

Mutex(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Parametry

*h*<br/>
Dojście lub odwołanie rvalue do dojścia do `Mutex` obiektu.

### <a name="remarks"></a>Uwagi

Pierwszy Konstruktor inicjuje `Mutex` obiekt z określonego dojścia. Drugi Konstruktor inicjuje `Mutex` obiekt z określonego dojścia, a następnie przenosi własność elementu mutex do bieżącego `Mutex` obiektu.

## <a name="mutexoperator"></a><a name="operator-assign"></a> Mutex:: operator =

Przypisuje (przenosi) określony `Mutex` obiekt do bieżącego `Mutex` obiektu.

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Parametry

*h*<br/>
Rvalue odwołanie do `Mutex` obiektu.

### <a name="return-value"></a>Wartość zwracana

Odwołanie do bieżącego `Mutex` obiektu.

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz sekcję **przenoszenie semantyki** [rvalue Reference deklarator:  &&](../../cpp/rvalue-reference-declarator-amp-amp.md).
