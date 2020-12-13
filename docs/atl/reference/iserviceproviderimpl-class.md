---
description: 'Dowiedz się więcej na temat: Klasa IServiceProviderImpl'
title: Klasa IServiceProviderImpl
ms.date: 11/04/2016
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
ms.openlocfilehash: 0cd9fab784fe8bffe420123129aa51c80c187890
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139155"
---
# <a name="iserviceproviderimpl-class"></a>Klasa IServiceProviderImpl

Ta klasa udostępnia domyślną implementację `IServiceProvider` interfejsu.

## <a name="syntax"></a>Składnia

```
template <class T>
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa, która pochodzi od `IServiceProviderImpl` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IServiceProviderImpl::QueryService](#queryservice)|Tworzy lub uzyskuje dostęp do określonej usługi i zwraca wskaźnik interfejsu do określonego interfejsu dla usługi.|

## <a name="remarks"></a>Uwagi

`IServiceProvider`Interfejs lokalizuje usługę określoną przez jego identyfikator GUID i zwraca wskaźnik interfejsu dla żądanego interfejsu w usłudze. Klasa `IServiceProviderImpl` udostępnia domyślną implementację tego interfejsu.

`IServiceProviderImpl` Określa jedną metodę: [QueryService](#queryservice), która tworzy lub uzyskuje dostęp do określonej usługi i zwraca wskaźnik interfejsu do określonego interfejsu dla usługi.

`IServiceProviderImpl` używa mapy usługi, zaczynając od [BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) i kończąc z [END_SERVICE_MAP](service-map-macros.md#end_service_map).

Mapa usługi zawiera dwa wpisy: [SERVICE_ENTRY](service-map-macros.md#service_entry), która wskazuje określony identyfikator usługi (SID) obsługiwany przez obiekt i [SERVICE_ENTRY_CHAIN](service-map-macros.md#service_entry_chain), który wywołuje `QueryService` łańcuch do innego obiektu.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IServiceProvider`

`IServiceProviderImpl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="iserviceproviderimplqueryservice"></a><a name="queryservice"></a> IServiceProviderImpl::QueryService

Tworzy lub uzyskuje dostęp do określonej usługi i zwraca wskaźnik interfejsu do określonego interfejsu dla usługi.

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>Parametry

*guidService*<br/>
podczas Wskaźnik do identyfikatora usługi (SID).

*riid*<br/>
podczas Identyfikator interfejsu, do którego obiekt wywołujący ma uzyskać dostęp.

*ppvObj*<br/>
określoną Pośredni wskaźnik do żądanego interfejsu.

### <a name="return-value"></a>Wartość zwracana

Zwrócona wartość HRESULT ma jedną z następujących wartości:

|Wartość zwracana|Znaczenie|
|------------------|-------------|
|S_OK|Usługa została pomyślnie utworzona lub pobrana.|
|E_INVALIDARG|Co najmniej jeden z argumentów jest nieprawidłowy.|
|E_OUTOFMEMORY|Brak wystarczającej ilości pamięci do utworzenia usługi.|
|E_UNEXPECTED|Wystąpił nieznany błąd.|
|E_NOINTERFACE|Żądany interfejs nie jest częścią tej usługi lub usługa jest nieznana.|

### <a name="remarks"></a>Uwagi

`QueryService` zwraca pośredni wskaźnik do żądanego interfejsu w określonej usłudze. Obiekt wywołujący jest odpowiedzialny za zwolnienie tego wskaźnika, gdy nie jest już wymagany.

Po wywołaniu należy `QueryService` przekazać zarówno identyfikator usługi (*guidService*), jak i identyfikator interfejsu (*riid*). *GuidService* określa usługę, do której chcesz uzyskać dostęp, a *riid* identyfikuje interfejs, który jest częścią usługi. W powrocie otrzymujesz pośredni wskaźnik do interfejsu.

Obiekt, który implementuje interfejs, może również zaimplementować interfejsy, które są częścią innych usług. Rozważ następujące źródła:

- Niektóre z tych interfejsów mogą być opcjonalne. Nie wszystkie interfejsy zdefiniowane w opisie usługi muszą być obecne w każdej implementacji usługi lub na każdym zwracanym obiekcie.

- W przeciwieństwie do wywołania `QueryInterface` , przekazywanie innego identyfikatora usługi nie musi oznaczać, że jest zwracany inny obiekt Component Object Model (com).

- Zwrócony obiekt może mieć dodatkowe interfejsy, które nie są częścią definicji usługi.

Dwie różne usługi, takie jak SID_SMyService i SID_SYourService, mogą określić użycie tego samego interfejsu, nawet jeśli implementacja interfejsu może nie zawierać żadnych wspólnych wartości między obiema usługami. To działa, ponieważ wywołanie metody `QueryService` (SID_SMyService, IID_IDispatch) może zwrócić inny obiekt niż `QueryService` (SID_SYourService, IID_IDispatch). Nie przyjmuje się tożsamości obiektu po określeniu innego identyfikatora usługi.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
