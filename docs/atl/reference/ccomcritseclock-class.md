---
description: 'Dowiedz się więcej na temat: Klasa CComCritSecLock'
title: Klasa CComCritSecLock
ms.date: 11/04/2016
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
ms.openlocfilehash: 7cad44f062fe75418da1f948c5f180283142779b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152103"
---
# <a name="ccomcritseclock-class"></a>Klasa CComCritSecLock

Ta klasa zapewnia metody blokowania i odblokowywania obiektu sekcji krytycznej.

## <a name="syntax"></a>Składnia

```
template<class TLock> class CComCritSecLock
```

#### <a name="parameters"></a>Parametry

*TLock*<br/>
Obiekt, który ma być zablokowany i odblokowany.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComCritSecLock::CComCritSecLock](#ctor)|Konstruktor.|
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComCritSecLock:: Lock](#lock)|Wywołaj tę metodę, aby zablokować obiekt sekcji krytycznej.|
|[CComCritSecLock:: Unlock](#unlock)|Wywołaj tę metodę, aby odblokować obiekt sekcji krytycznej.|

## <a name="remarks"></a>Uwagi

Ta klasa umożliwia blokowanie i odblokowywanie obiektów w bezpieczniejszy sposób niż z klasą [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) lub [klasą CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md).

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlbase. h

## <a name="ccomcritseclockccomcritseclock"></a><a name="ctor"></a> CComCritSecLock::CComCritSecLock

Konstruktor.

```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```

### <a name="parameters"></a>Parametry

*Rejestr*<br/>
Obiekt sekcji krytycznej.

*bInitialLock*<br/>
Początkowy stan blokady: **`true`** oznacza zablokowany.

### <a name="remarks"></a>Uwagi

Inicjuje obiekt sekcji krytycznej.

## <a name="ccomcritseclockccomcritseclock"></a><a name="dtor"></a> CComCritSecLock:: ~ CComCritSecLock

Destruktor.

```
~CComCritSecLock() throw();
```

### <a name="remarks"></a>Uwagi

Odblokowuje obiekt sekcji krytycznej.

## <a name="ccomcritseclocklock"></a><a name="lock"></a> CComCritSecLock:: Lock

Wywołaj tę metodę, aby zablokować obiekt sekcji krytycznej.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK, jeśli obiekt został pomyślnie zablokowany, lub błąd HRESULT w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Jeśli obiekt jest już zablokowany, wystąpi błąd potwierdzenia w kompilacjach debugowania.

## <a name="ccomcritseclockunlock"></a><a name="unlock"></a> CComCritSecLock:: Unlock

Wywołaj tę metodę, aby odblokować obiekt sekcji krytycznej.

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>Uwagi

Jeśli obiekt jest już odblokowany, wystąpi błąd potwierdzenia w kompilacjach debugowania.

## <a name="see-also"></a>Zobacz też

[Klasa CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Klasa CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)
