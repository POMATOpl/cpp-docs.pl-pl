---
description: 'Dowiedz się więcej na temat: Klasa ICollectionOnSTLImpl'
title: Klasa ICollectionOnSTLImpl
ms.date: 11/04/2016
f1_keywords:
- ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl
- ATLCOM/ATL::ICollectionOnSTLImpl::get__NewEnum
- ATLCOM/ATL::ICollectionOnSTLImpl::getcount
- ATLCOM/ATL::ICollectionOnSTLImpl::get_Item
- ATLCOM/ATL::ICollectionOnSTLImpl::m_coll
helpviewer_keywords:
- ICollectionOnSTLImpl class
ms.assetid: 683c88b0-0d97-4779-a762-e493334ba7f9
ms.openlocfilehash: 089fc0fbd8f410d740646e2a653b076d32448647
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139610"
---
# <a name="icollectiononstlimpl-class"></a>Klasa ICollectionOnSTLImpl

Ta klasa udostępnia metody używane przez klasę kolekcji.

## <a name="syntax"></a>Składnia

```
template <class T, class CollType, class ItemType, class CopyItem, class EnumType>
class ICollectionOnSTLImpl : public T
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Interfejs kolekcji COM.

*CollType*<br/>
Klasa kontenera standardowej biblioteki języka C++.

*ItemType*<br/>
Typ elementu uwidocznionego przez interfejs kontenera.

*CopyItem*<br/>
[Klasa zasad kopiowania](../../atl/atl-copy-policy-classes.md).

*EnumType*<br/>
Klasa modułu wyliczającego zgodną z [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md).

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[ICollectionOnSTLImpl:: get__NewEnum](#newenum)|Zwraca obiekt modułu wyliczającego dla kolekcji.|
|[ICollectionOnSTLImpl:: GetCount](#get_count)|Zwraca liczbę elementów w kolekcji.|
|[ICollectionOnSTLImpl:: get_Item](#get_item)|Zwraca żądany element z kolekcji.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[ICollectionOnSTLImpl:: m_coll](#m_coll)|Kolekcja.|

## <a name="remarks"></a>Uwagi

Ta klasa zawiera implementację trzech metod interfejsu kolekcji: [GetCount](#get_count), [get_Item](#get_item)i [get__NewEnum](#newenum).

Aby użyć tej klasy:

- Zdefiniuj (lub pożycz) interfejs kolekcji, który ma zostać wdrożony.

- Utwórz klasę z specjalizacji `ICollectionOnSTLImpl` opartej na tym interfejsie kolekcji.

- Użyj klasy pochodnej, aby zaimplementować wszelkie metody z interfejsu kolekcji, które nie są obsługiwane przez program `ICollectionOnSTLImpl` .

> [!NOTE]
> Jeśli interfejs kolekcji jest interfejsem podwójnym, należy poprowadzić klasę z [IDispatchImpl](../../atl/reference/idispatchimpl-class.md), przekazując `ICollectionOnSTLImpl` specjalizację jako pierwszy parametr szablonu, jeśli chcesz, aby ATL zaimplementował implementacje `IDispatch` metod.

- Dodaj elementy do elementu członkowskiego [m_coll](#m_coll) , aby wypełnić kolekcję.

Aby uzyskać więcej informacji i przykładów, zobacz [Kolekcje ATL i moduły wyliczające](../../atl/atl-collections-and-enumerators.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`T`

`ICollectionOnSTLImpl`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="icollectiononstlimplgetcount"></a><a name="get_count"></a> ICollectionOnSTLImpl:: GetCount

Ta metoda zwraca liczbę elementów w kolekcji.

```
STDMETHOD(getcount)(long* pcount);
```

### <a name="parameters"></a>Parametry

*pcount*<br/>
określoną Liczba elementów w kolekcji.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

## <a name="icollectiononstlimplget_item"></a><a name="get_item"></a> ICollectionOnSTLImpl:: get_Item

Ta metoda zwraca określony element z kolekcji.

```
STDMETHOD(get_Item)(long Index, ItemType* pvar);
```

### <a name="parameters"></a>Parametry

*Indeks*<br/>
podczas Indeks elementu w kolekcji, który jest oparty na 1.

*pvar*<br/>
określoną Element odpowiadający *indeksowi*.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

### <a name="remarks"></a>Uwagi

Element jest uzyskiwany przez skopiowanie danych w określonej pozycji w [m_coll](#m_coll) przy użyciu metody copy [klasy zasad kopiowania](../../atl/atl-copy-policy-classes.md) przekazaną jako argument szablonu w `ICollectionOnSTLImpl` specjalizacji.

## <a name="icollectiononstlimplget__newenum"></a><a name="newenum"></a> ICollectionOnSTLImpl:: get__NewEnum

Zwraca obiekt modułu wyliczającego dla kolekcji.

```
STDMETHOD(get__NewEnum)(IUnknown** ppUnk);
```

### <a name="parameters"></a>Parametry

*ppUnk*<br/>
określoną Wskaźnik **IUnknown** nowo utworzonego obiektu modułu wyliczającego.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

### <a name="remarks"></a>Uwagi

Nowo utworzony moduł wyliczający zachowuje iterator w oryginalnej kolekcji, `m_coll` , (w związku z czym nie jest wykonywana żadna kopia) i przechowuje odwołanie com do obiektu kolekcja, aby upewnić się, że kolekcja pozostaje aktywna, gdy istnieją zaległe Numeratory.

## <a name="icollectiononstlimplm_coll"></a><a name="m_coll"></a> ICollectionOnSTLImpl:: m_coll

Ten element członkowski zawiera elementy reprezentowane przez kolekcję.

```
CollType m_coll;
```

## <a name="see-also"></a>Zobacz też

[Przykład ATLCollections](../../overview/visual-cpp-samples.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
