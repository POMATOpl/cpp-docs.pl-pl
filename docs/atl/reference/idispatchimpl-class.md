---
description: 'Dowiedz się więcej na temat: Klasa IDispatchImpl'
title: Klasa IDispatchImpl
ms.date: 11/04/2016
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
ms.openlocfilehash: 709b703bf610776191b2587d11a0c5be651c4938
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139558"
---
# <a name="idispatchimpl-class"></a>Klasa IDispatchImpl

Zapewnia implementację domyślną dla `IDispatch` części podwójnego interfejsu.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template<class T,
        const IID* piid= &__uuidof(T),
        const GUID* plibid = &CAtlModule::m_libid,
        WORD wMajor = 1,
        WORD wMinor = 0,
        class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IDispatchImpl : public T
```

#### <a name="parameters"></a>Parametry

*T*<br/>
podczas Interfejs podwójny.

*piid*<br/>
podczas Wskaźnik do IID elementu *T*.

*plibid*<br/>
podczas Wskaźnik do identyfikatora LIBID biblioteki typów, który zawiera informacje o interfejsie. Domyślnie jest przenoszona biblioteka typów na poziomie serwera.

*wMajor*<br/>
podczas Główna wersja biblioteki typów. Wartość domyślna to 1.

*wMinor*<br/>
podczas Wersja pomocnicza biblioteki typów. Wartość domyślna to 0.

*tihclass*<br/>
podczas Klasa używana do zarządzania informacjami o typie dla *T*. Wartością domyślną jest `CComTypeInfoHolder` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IDispatchImpl::IDispatchImpl](#idispatchimpl)|Konstruktor. Wywołuje dla `AddRef` zmiennej chronionej składowej, która zarządza informacjami o typie dla podwójnego interfejsu. Destruktor wywołuje `Release` .|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IDispatchImpl:: GetIDsOfNames](#getidsofnames)|Zestaw nazw jest mapowany na odpowiedni zestaw identyfikatorów wysyłania.|
|[IDispatchImpl::](#gettypeinfo)|Pobiera informacje o typie dla podwójnego interfejsu.|
|[IDispatchImpl::GetTypeInfoCount](#gettypeinfocount)|Określa, czy dostępne są informacje o typie dla podwójnego interfejsu.|
|[IDispatchImpl:: Invoke](#invoke)|Zapewnia dostęp do metod i właściwości udostępnianych przez podwójny interfejs.|

## <a name="remarks"></a>Uwagi

`IDispatchImpl` udostępnia implementację domyślną dla `IDispatch` części każdego podwójnego interfejsu w obiekcie. Podwójny interfejs pochodzi z `IDispatch` i używa tylko typów zgodnych z automatyzacją. Podobnie jak w przypadku dispinterface, podwójny interfejs obsługuje wczesne powiązania i późne wiązanie. jednak podwójny interfejs obsługuje również powiązanie tablic wirtualnych.

W poniższym przykładzie przedstawiono typową implementację programu `IDispatchImpl` .

[!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]

Domyślnie `IDispatchImpl` Klasa wyszukuje informacje o typie dla *T* w rejestrze. Aby zaimplementować niezarejestrowany interfejs, można użyć `IDispatchImpl` klasy bez uzyskiwania dostępu do rejestru przy użyciu wstępnie zdefiniowanego numeru wersji. Jeśli utworzysz `IDispatchImpl` obiekt, który ma 0xFFFF jako wartość dla *WMajor* i 0xFFFF jako wartość dla *wMinor*, `IDispatchImpl` Klasa pobiera bibliotekę typów z pliku dll zamiast z rejestru.

`IDispatchImpl` zawiera statyczną składową typu `CComTypeInfoHolder` , która zarządza informacjami o typie dla podwójnego interfejsu. Jeśli masz wiele obiektów, które implementują ten sam podwójny interfejs, używane jest tylko jedno wystąpienie `CComTypeInfoHolder` .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`T`

`IDispatchImpl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="idispatchimplgetidsofnames"></a><a name="getidsofnames"></a> IDispatchImpl:: GetIDsOfNames

Zestaw nazw jest mapowany na odpowiedni zestaw identyfikatorów wysyłania.

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>Uwagi

Zobacz [IDispatch:: GetIDsOfNames](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames) w Windows SDK.

## <a name="idispatchimplgettypeinfo"></a><a name="gettypeinfo"></a> IDispatchImpl::

Pobiera informacje o typie dla podwójnego interfejsu.

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Uwagi

Zobacz [IDispatch::](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo) w Windows SDK.

## <a name="idispatchimplgettypeinfocount"></a><a name="gettypeinfocount"></a> IDispatchImpl::GetTypeInfoCount

Określa, czy dostępne są informacje o typie dla podwójnego interfejsu.

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>Uwagi

Zobacz `IDispatch::GetTypeInfoCount` w Windows SDK.

## <a name="idispatchimplidispatchimpl"></a><a name="idispatchimpl"></a> IDispatchImpl::IDispatchImpl

Konstruktor. Wywołuje dla `AddRef` zmiennej chronionej składowej, która zarządza informacjami o typie dla podwójnego interfejsu. Destruktor wywołuje `Release` .

```
IDispatchImpl();
```

## <a name="idispatchimplinvoke"></a><a name="invoke"></a> IDispatchImpl:: Invoke

Zapewnia dostęp do metod i właściwości udostępnianych przez podwójny interfejs.

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* pexcepinfo,
    UINT* puArgErr);
```

### <a name="remarks"></a>Uwagi

Zobacz [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
