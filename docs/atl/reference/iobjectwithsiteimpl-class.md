---
description: 'Dowiedz się więcej na temat: Klasa IObjectWithSiteImpl'
title: Klasa IObjectWithSiteImpl
ms.date: 11/04/2016
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
ms.openlocfilehash: 100a4d16bea63d573fe4fb00bc37e656a7c2c483
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158299"
---
# <a name="iobjectwithsiteimpl-class"></a>Klasa IObjectWithSiteImpl

Ta klasa udostępnia metody umożliwiające obiektowi komunikowanie się z jego lokacją.

## <a name="syntax"></a>Składnia

```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa, która pochodzi od `IObjectWithSiteImpl` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IObjectWithSiteImpl:: GetSite](#getsite)|Wysyła zapytanie do witryny pod kątem wskaźnika interfejsu.|
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Udostępnia obiekt ze `IUnknown` wskaźnikiem lokacji.|
|[IObjectWithSiteImpl:: SetSite](#setsite)|Udostępnia obiekt ze `IUnknown` wskaźnikiem lokacji.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[IObjectWithSiteImpl:: m_spUnkSite](#m_spunksite)|Zarządza `IUnknown` wskaźnikiem witryny.|

## <a name="remarks"></a>Uwagi

Interfejs [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) umożliwia obiektowi komunikowanie się z jego lokacją. Klasa `IObjectWithSiteImpl` zapewnia domyślną implementację tego interfejsu i implementuje `IUnknown` przez wysyłanie informacji do urządzenia zrzutu w kompilacjach debugowania.

`IObjectWithSiteImpl` określa dwie metody. Klient najpierw wywołuje `SetSite` , przekazując `IUnknown` wskaźnik lokacji. Ten wskaźnik jest przechowywany w obiekcie i można go później pobrać za pomocą wywołania do `GetSite` .

Zazwyczaj Klasa pochodzi od, `IObjectWithSiteImpl` gdy tworzysz obiekt, który nie jest formantem. W przypadku formantów należy utworzyć klasę z [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), która udostępnia również wskaźnik lokacji. Nie należy dziedziczyć klasy z obu `IObjectWithSiteImpl` i `IOleObjectImpl` .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IObjectWithSite`

`IObjectWithSiteImpl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="iobjectwithsiteimplgetsite"></a><a name="getsite"></a> IObjectWithSiteImpl:: GetSite

Wysyła zapytanie do witryny pod kątem wskaźnika do interfejsu identyfikowanego przez `riid` .

```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```

### <a name="remarks"></a>Uwagi

Jeśli witryna obsługuje ten interfejs, wskaźnik jest zwracany przez `ppvSite` . W przeciwnym razie `ppvSite` jest ustawiona na wartość null.

Zobacz [IObjectWithSite:: GetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-getsite) w Windows SDK.

## <a name="iobjectwithsiteimplm_spunksite"></a><a name="m_spunksite"></a> IObjectWithSiteImpl:: m_spUnkSite

Zarządza `IUnknown` wskaźnikiem witryny.

```
CComPtr<IUnknown> m_spUnkSite;
```

### <a name="remarks"></a>Uwagi

`m_spUnkSite` Początkowo otrzymuje ten wskaźnik przez wywołanie metody [SetSite](#setsite).

## <a name="iobjectwithsiteimplsetchildsite"></a><a name="setchildsite"></a> IObjectWithSiteImpl::SetChildSite

Udostępnia obiekt ze `IUnknown` wskaźnikiem lokacji.

```
HRESULT SetChildSite(IUnknown* pUnkSite);
```

### <a name="parameters"></a>Parametry

*pUnkSite*<br/>
podczas Wskaźnik na `IUnknown` wskaźnik interfejsu lokacji zarządzającej tym obiektem. Jeśli wartość jest równa NULL, obiekt powinien wywołać `IUnknown::Release` wszystkie istniejące lokacje, w których obiekt nie wie już swojej lokacji.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK.

## <a name="iobjectwithsiteimplsetsite"></a><a name="setsite"></a> IObjectWithSiteImpl:: SetSite

Udostępnia obiekt ze `IUnknown` wskaźnikiem lokacji.

```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```

### <a name="remarks"></a>Uwagi

Zobacz [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
