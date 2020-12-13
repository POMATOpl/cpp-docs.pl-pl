---
description: 'Dowiedz się więcej na temat: Klasa IPropertyPage2Impl'
title: Klasa IPropertyPage2Impl
ms.date: 11/04/2016
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
ms.openlocfilehash: 8311746b03c4c680a040c0873ee58f936044dd9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139285"
---
# <a name="ipropertypage2impl-class"></a>Klasa IPropertyPage2Impl

Ta klasa implementuje `IUnknown` i dziedziczy domyślną implementację [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa, która pochodzi od `IPropertyPage2Impl` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[IPropertyPage2Impl::EditProperty](#editproperty)|Określa, która kontrolka właściwości będzie otrzymywać fokus po aktywowaniu strony właściwości. Implementacja ATL zwraca E_NOTIMPL.|

## <a name="remarks"></a>Uwagi

Interfejs [IPropertyPage2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2) rozszerza [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) przez dodanie `EditProperty` metody. Ta metoda umożliwia klientowi wybranie konkretnej właściwości w obiekcie strony właściwości.

Klasa `IPropertyPage2Impl` po prostu zwraca E_NOTIMPL dla elementu `IPropertyPage2::EditProperty` . Jednak dziedziczy domyślną implementację [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) i implementuje `IUnknown` przez wysyłanie informacji do urządzenia zrzutu w kompilacjach debugowania.

Podczas tworzenia strony właściwości Klasa jest zwykle wyprowadzana z `IPropertyPageImpl` . Aby zapewnić dodatkową pomoc techniczną `IPropertyPage2` , zmodyfikuj definicję klasy i Zastąp `EditProperty` metodę.

 [Samouczki dotyczące biblioteki](../../atl/active-template-library-atl-tutorial.md)ATL, [Tworzenie projektu ATL](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`IPropertyPage`

[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlctl. h

## <a name="ipropertypage2impleditproperty"></a><a name="editproperty"></a> IPropertyPage2Impl::EditProperty

Określa, która kontrolka właściwości będzie otrzymywać fokus po aktywowaniu strony właściwości.

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca E_NOTIMPL.

### <a name="remarks"></a>Uwagi

Zobacz [IPropertyPage2:: EditProperty](/windows/win32/api/ocidl/nf-ocidl-ipropertypage2-editproperty) w Windows SDK.

## <a name="see-also"></a>Zobacz też

[Klasa IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Klasa ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
