---
description: 'Dowiedz się więcej na temat: Klasa ISpecifyPropertyPagesImpl'
title: Klasa ISpecifyPropertyPagesImpl
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
ms.openlocfilehash: 528fafa0473a4aa803e1c1d17a24b2d27584c33a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158052"
---
# <a name="ispecifypropertypagesimpl-class"></a>Klasa ISpecifyPropertyPagesImpl

Ta klasa implementuje `IUnknown` i udostępnia domyślną implementację interfejsu [ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) .

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa, która pochodzi od `ISpecifyPropertyPagesImpl` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[ISpecifyPropertyPagesImpl:: GetPages](#getpages)|Wypełnia zliczoną tablicę wartości UUID. Każdy identyfikator UUID odpowiada identyfikatorowi CLSID jednej ze stron właściwości, które mogą być wyświetlane w arkuszu właściwości obiektu.|

## <a name="remarks"></a>Uwagi

Interfejs [ISpecifyPropertyPages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) umożliwia klientowi uzyskanie listy identyfikatorów CLSID dla stron właściwości obsługiwanych przez obiekt. Klasa `ISpecifyPropertyPagesImpl` zapewnia domyślną implementację tego interfejsu i implementuje `IUnknown` przez wysyłanie informacji do urządzenia zrzutu w kompilacjach debugowania.

> [!NOTE]
> Nie ujawniaj `ISpecifyPropertyPages` interfejsu, jeśli obiekt nie obsługuje stron właściwości.

 [Samouczki dotyczące biblioteki](../../atl/active-template-library-atl-tutorial.md)ATL, [Tworzenie projektu ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="ispecifypropertypagesimplgetpages"></a><a name="getpages"></a> ISpecifyPropertyPagesImpl:: GetPages

Wypełnia tablicę w strukturze [CAUUID](/windows/win32/api/ocidl/ns-ocidl-cauuid) z identyfikatorami CLSID dla stron właściwości, które mogą być wyświetlane w arkuszu właściwości obiektu.

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>Uwagi

ATL używa mapy właściwości obiektu, aby pobrać każdy identyfikator CLSID.

Zobacz [ISpecifyPropertyPages:: GetPages](/windows/win32/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Klasa IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)<br/>
[Klasa IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
