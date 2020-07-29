---
title: Klasa CComFakeCriticalSection
ms.date: 11/04/2016
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
ms.openlocfilehash: 5ada0fbed705af34391709653dbd3638fed32bf7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226584"
---
# <a name="ccomfakecriticalsection-class"></a>Klasa CComFakeCriticalSection

Ta klasa zawiera te same metody co [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) , ale nie udostępnia sekcji krytycznej.

## <a name="syntax"></a>Składnia

```
class CComFakeCriticalSection
```

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComFakeCriticalSection:: init](#init)|Nic nie dotyczy, ponieważ nie ma sekcji krytycznej.|
|[CComFakeCriticalSection:: Lock](#lock)|Nic nie dotyczy, ponieważ nie ma sekcji krytycznej.|
|[CComFakeCriticalSection:: Term](#term)|Nic nie dotyczy, ponieważ nie ma sekcji krytycznej.|
|[CComFakeCriticalSection:: Unlock](#unlock)|Nic nie dotyczy, ponieważ nie ma sekcji krytycznej.|

## <a name="remarks"></a>Uwagi

`CComFakeCriticalSection`odzwierciedla metody Znalezione w [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Jednakże nie `CComFakeCriticalSection` zawiera sekcji krytycznej; w związku z tym jej metody nic nie rób.

Zwykle używasz `CComFakeCriticalSection` za pomocą **`typedef`** nazwy `AutoCriticalSection` lub `CriticalSection` . W przypadku używania [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) lub [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), oba te **`typedef`** odwołania do nazw `CComFakeCriticalSection` . W przypadku korzystania z [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), odwołują się one do [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) i `CComCriticalSection` , odpowiednio.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcore. h

## <a name="ccomfakecriticalsectioninit"></a><a name="init"></a>CComFakeCriticalSection:: init

Nic nie dotyczy, ponieważ nie ma sekcji krytycznej.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

## <a name="ccomfakecriticalsectionlock"></a><a name="lock"></a>CComFakeCriticalSection:: Lock

Nic nie dotyczy, ponieważ nie ma sekcji krytycznej.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

## <a name="ccomfakecriticalsectionterm"></a><a name="term"></a>CComFakeCriticalSection:: Term

Nic nie dotyczy, ponieważ nie ma sekcji krytycznej.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

## <a name="ccomfakecriticalsectionunlock"></a><a name="unlock"></a>CComFakeCriticalSection:: Unlock

Nic nie dotyczy, ponieważ nie ma sekcji krytycznej.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

## <a name="see-also"></a>Zobacz także

[Przegląd klas](../../atl/atl-class-overview.md)
