---
description: 'Dowiedz się więcej na temat: Klasa IPerPropertyBrowsingImpl'
title: Klasa IPerPropertyBrowsingImpl
ms.date: 11/04/2016
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
ms.openlocfilehash: eba17c0011343f50f586b13086dc76229f08ba3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139350"
---
# <a name="iperpropertybrowsingimpl-class"></a>Klasa IPerPropertyBrowsingImpl

Ta klasa implementuje `IUnknown` i umożliwia klientowi dostęp do informacji na stronach właściwości obiektu.

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa, która pochodzi od `IPerPropertyBrowsingImpl` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|Pobiera ciąg opisujący daną właściwość.|
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|Pobiera tablicę ciągów odpowiadającą wartościom, które mogą być akceptowane przez daną właściwość.|
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Pobiera wariant zawierający wartość właściwości identyfikowanej przez dany identyfikator DISPID. Identyfikator DISPID jest skojarzony z nazwą ciągu pobieraną z `GetPredefinedStrings` . Implementacja ATL zwraca E_NOTIMPL.|
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|Pobiera identyfikator CLSID strony właściwości skojarzonej z daną właściwością.|

## <a name="remarks"></a>Uwagi

Interfejs [IPerPropertyBrowsing](/windows/win32/api/ocidl/nn-ocidl-iperpropertybrowsing) umożliwia klientowi dostęp do informacji na stronach właściwości obiektu. Klasa `IPerPropertyBrowsingImpl` zapewnia domyślną implementację tego interfejsu i implementuje `IUnknown` przez wysyłanie informacji do urządzenia zrzutu w kompilacjach debugowania.

> [!NOTE]
> Jeśli używasz programu Microsoft Access jako aplikacji kontenera, musisz utworzyć klasę z `IPerPropertyBrowsingImpl` . W przeciwnym razie program Access nie załaduje formantu.

 [Samouczki dotyczące biblioteki](../../atl/active-template-library-atl-tutorial.md)ATL, [Tworzenie projektu ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IPerPropertyBrowsing`

`IPerPropertyBrowsingImpl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlctl. h

## <a name="iperpropertybrowsingimplgetdisplaystring"></a><a name="getdisplaystring"></a> IPerPropertyBrowsingImpl::GetDisplayString

Pobiera ciąg opisujący daną właściwość.

```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```

### <a name="remarks"></a>Uwagi

Zobacz [IPerPropertyBrowsing:: GetDisplayString](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getdisplaystring) w Windows SDK.

## <a name="iperpropertybrowsingimplgetpredefinedstrings"></a><a name="getpredefinedstrings"></a> IPerPropertyBrowsingImpl::GetPredefinedStrings

Wypełnia każdą tablicę zerowymi elementami.

```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```

### <a name="return-value"></a>Wartość zwracana

Implementacja biblioteki ATL [GetPredefinedValue](#getpredefinedvalue) zwraca E_NOTIMPL.

### <a name="remarks"></a>Uwagi

Zobacz [IPerPropertyBrowsing:: GetPredefinedStrings](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedstrings) w Windows SDK.

## <a name="iperpropertybrowsingimplgetpredefinedvalue"></a><a name="getpredefinedvalue"></a> IPerPropertyBrowsingImpl::GetPredefinedValue

Pobiera wariant zawierający wartość właściwości identyfikowanej przez dany identyfikator DISPID. Identyfikator DISPID jest skojarzony z nazwą ciągu pobieraną z `GetPredefinedStrings` .

```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca E_NOTIMPL.

### <a name="remarks"></a>Uwagi

Implementacja [GetPredefinedStrings](#getpredefinedstrings) biblioteki ATL nie pobiera odpowiednich ciągów.

Zobacz [IPerPropertyBrowsing:: GetPredefinedValue](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-getpredefinedvalue) w Windows SDK.

## <a name="iperpropertybrowsingimplmappropertytopage"></a><a name="mappropertytopage"></a> IPerPropertyBrowsingImpl::MapPropertyToPage

Pobiera identyfikator CLSID strony właściwości skojarzonej z określoną właściwością.

```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```

### <a name="remarks"></a>Uwagi

ATL używa mapy właściwości obiektu, aby uzyskać te informacje.

Zobacz [IPerPropertyBrowsing:: MapPropertyToPage](/windows/win32/api/ocidl/nf-ocidl-iperpropertybrowsing-mappropertytopage) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Klasa IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)<br/>
[Klasa ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
