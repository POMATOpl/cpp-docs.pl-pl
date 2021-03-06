---
description: 'Dowiedz się więcej na temat: Klasa IProvideClassInfo2Impl'
title: Klasa IProvideClassInfo2Impl
ms.date: 11/04/2016
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
ms.openlocfilehash: 9c3422c98ebd857231f492efb77d51a0a49acb76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139260"
---
# <a name="iprovideclassinfo2impl-class"></a>Klasa IProvideClassInfo2Impl

Ta klasa zawiera domyślną implementację metod [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) i [IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) .

## <a name="syntax"></a>Składnia

```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```

#### <a name="parameters"></a>Parametry

*pcoclsid*<br/>
Wskaźnik do identyfikatora klasy coclass.

*psrcid*<br/>
Wskaźnik do identyfikatora dla domyślnego dispinterface wychodzącego klasy coclass.

*plibid*<br/>
Wskaźnik do identyfikatora LIBID biblioteki typów, który zawiera informacje o interfejsie. Domyślnie jest przenoszona biblioteka typów na poziomie serwera.

*wMajor*<br/>
Główna wersja biblioteki typów. Wartość domyślna to 1.

*wMinor*<br/>
Wersja pomocnicza biblioteki typów. Wartość domyślna to 0.

*tihclass*<br/>
Klasa używana do zarządzania informacjami o typie klasy coclass. Wartość domyślna to `CComTypeInfoHolder`.

## <a name="members"></a>Elementy członkowskie

### <a name="constructors"></a>Konstruktory

|Nazwa|Opis|
|----------|-----------------|
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|Konstruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|Pobiera `ITypeInfo` wskaźnik do informacji o typie klasy coclass.|
|[IProvideClassInfo2Impl:: GetGuid](#getguid)|Pobiera identyfikator GUID dispinterface wychodzącego obiektu.|

### <a name="protected-data-members"></a>Chronione elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[IProvideClassInfo2Impl:: _tih](#_tih)|Zarządza informacjami o typie dla klasy coclass.|

## <a name="remarks"></a>Uwagi

Interfejs [IProvideClassInfo2](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo2) rozszerza [IProvideClassInfo](/windows/win32/api/ocidl/nn-ocidl-iprovideclassinfo) przez dodanie `GetGUID` metody. Ta metoda umożliwia klientowi pobranie identyfikatora IID interfejsu wychodzącego obiektu dla jego domyślnego zestawu zdarzeń. Klasa `IProvideClassInfo2Impl` zawiera domyślną implementację `IProvideClassInfo` `IProvideClassInfo2` metod i.

`IProvideClassInfo2Impl` zawiera statyczną składową typu `CComTypeInfoHolder` , która zarządza informacjami o typie dla klasy coclass.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IProvideClassInfo2`

`IProvideClassInfo2Impl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="iprovideclassinfo2implgetclassinfo"></a><a name="getclassinfo"></a> IProvideClassInfo2Impl::GetClassInfo

Pobiera `ITypeInfo` wskaźnik do informacji o typie klasy coclass.

```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```

### <a name="remarks"></a>Uwagi

Zobacz [IProvideClassInfo:: GetClassInfo](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo-getclassinfo) w Windows SDK.

## <a name="iprovideclassinfo2implgetguid"></a><a name="getguid"></a> IProvideClassInfo2Impl:: GetGuid

Pobiera identyfikator GUID dispinterface wychodzącego obiektu.

```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```

### <a name="remarks"></a>Uwagi

Zobacz [IProvideClassInfo2:: GetGuid](/windows/win32/api/ocidl/nf-ocidl-iprovideclassinfo2-getguid) w Windows SDK.

## <a name="iprovideclassinfo2impliprovideclassinfo2impl"></a><a name="iprovideclassinfo2impl"></a> IProvideClassInfo2Impl::IProvideClassInfo2Impl

Konstruktor.

```
IProvideClassInfo2Impl();
```

### <a name="remarks"></a>Uwagi

Wywołania `AddRef` elementu członkowskiego [_tih](#_tih) . Destruktor wywołuje `Release` .

## <a name="iprovideclassinfo2impl_tih"></a><a name="_tih"></a> IProvideClassInfo2Impl:: _tih

Ten statyczny element członkowski danych jest wystąpieniem parametru szablonu klasy *tihclass*, który domyślnie jest `CComTypeInfoHolder` .

```
static  tihclass
    _tih;
```

### <a name="remarks"></a>Uwagi

`_tih` zarządza informacjami o typie dla klasy coclass.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
