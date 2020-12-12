---
description: 'Dowiedz się więcej na temat: Klasa CComFakeCriticalSection'
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
ms.openlocfilehash: 7280a47daa7464b24246ca8baa0aa7f5eaefa87a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152064"
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

`CComFakeCriticalSection` odzwierciedla metody Znalezione w [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Jednakże nie `CComFakeCriticalSection` zawiera sekcji krytycznej; w związku z tym jej metody nic nie rób.

Zwykle używasz `CComFakeCriticalSection` za pomocą **`typedef`** nazwy `AutoCriticalSection` lub `CriticalSection` . W przypadku używania [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) lub [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), oba te **`typedef`** odwołania do nazw `CComFakeCriticalSection` . W przypadku korzystania z [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), odwołują się one do [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) i `CComCriticalSection` , odpowiednio.

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcore. h

## <a name="ccomfakecriticalsectioninit"></a><a name="init"></a> CComFakeCriticalSection:: init

Nic nie dotyczy, ponieważ nie ma sekcji krytycznej.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

## <a name="ccomfakecriticalsectionlock"></a><a name="lock"></a> CComFakeCriticalSection:: Lock

Nic nie dotyczy, ponieważ nie ma sekcji krytycznej.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

## <a name="ccomfakecriticalsectionterm"></a><a name="term"></a> CComFakeCriticalSection:: Term

Nic nie dotyczy, ponieważ nie ma sekcji krytycznej.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

## <a name="ccomfakecriticalsectionunlock"></a><a name="unlock"></a> CComFakeCriticalSection:: Unlock

Nic nie dotyczy, ponieważ nie ma sekcji krytycznej.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
