---
description: 'Dowiedz się więcej na temat: Klasa CComContainedObject'
title: Klasa CComContainedObject
ms.date: 11/04/2016
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
ms.openlocfilehash: 9c0993d5ce71a557b71939f60a7019d3c062bac3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152207"
---
# <a name="ccomcontainedobject-class"></a>Klasa CComContainedObject

Ta klasa implementuje [interfejs IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) przez delegowanie do obiektu właściciela `IUnknown` .

> [!IMPORTANT]
> Tej klasy i jej elementów członkowskich nie można używać w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

## <a name="syntax"></a>Składnia

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>Parametry

*Opiera*<br/>
Klasa, która pochodzi od [klasy CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) lub [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|Konstruktor. Inicjuje wskaźnik elementu członkowskiego do obiektu właściciela `IUnknown` .|
|[CComContainedObject:: ~ CComContainedObject](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComContainedObject:: AddRef](#addref)|Zwiększa liczbę odwołań do obiektu właściciela.|
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|Pobiera obiekt Owner `IUnknown` .|
|[CComContainedObject:: QueryInterface](#queryinterface)|Pobiera wskaźnik do interfejsu żądanego w obiekcie Owner.|
|[CComContainedObject:: Release](#release)|Zmniejsza liczbę odwołań do obiektu właściciela.|

## <a name="remarks"></a>Uwagi

Użycie ATL `CComContainedObject` w klasach [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md)i [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md). `CComContainedObject` implementuje [interfejs IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) przez delegowanie do obiektu właściciela `IUnknown` . (Właściciel jest obiektem zewnętrznym agregacji lub obiektem, dla którego tworzony jest interfejs odrywający). `CComContainedObject` wywołania `CComObjectRootEx` `OuterQueryInterface` , `OuterAddRef` , i `OuterRelease` , wszystkie Odziedziczone przez `Base` .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`Base`

`CComContainedObject`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="ccomcontainedobjectaddref"></a><a name="addref"></a> CComContainedObject:: AddRef

Zwiększa liczbę odwołań do obiektu właściciela.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Wartość zwracana

Wartość, która może być przydatna w przypadku diagnostyki lub testowania.

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="ccomcontainedobject"></a> CComContainedObject::CComContainedObject

Konstruktor.

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>Parametry

*wa*<br/>
podczas Obiekt Owner `IUnknown` .

### <a name="remarks"></a>Uwagi

Ustawia `m_pOuterUnknown` wskaźnik elementu członkowskiego (Dziedziczony przez `Base` klasę) na *WB*.

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="dtor"></a> CComContainedObject:: ~ CComContainedObject

Destruktor.

```
~CComContainedObject();
```

### <a name="remarks"></a>Uwagi

Zwalnia wszystkie przydzieloną zasoby.

## <a name="ccomcontainedobjectgetcontrollingunknown"></a><a name="getcontrollingunknown"></a> CComContainedObject::GetControllingUnknown

Zwraca `m_pOuterUnknown` wskaźnik elementu członkowskiego (Dziedziczony przez klasę *bazową* ), który zawiera obiekt Owner `IUnknown` .

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>Wartość zwracana

Obiekt Owner `IUnknown` .

### <a name="remarks"></a>Uwagi

Ta metoda może być wirtualna `Base` , jeśli deklaruje makro [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) .

## <a name="ccomcontainedobjectqueryinterface"></a><a name="queryinterface"></a> CComContainedObject:: QueryInterface

Pobiera wskaźnik do interfejsu żądanego w obiekcie Owner.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>Parametry

*IID*<br/>
podczas Identyfikator żądanego interfejsu.

*ppvObject*<br/>
określoną Wskaźnik do wskaźnika interfejsu identyfikowanego przez *Identyfikator IID*. Jeśli obiekt nie obsługuje tego interfejsu, *ppvObject* ma wartość null.

*miesięcznie*<br/>
określoną Wskaźnik do wskaźnika interfejsu identyfikowanego przez typ `Q` . Jeśli obiekt nie obsługuje tego *interfejsu, ma* USTAWIONĄ wartość null.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

## <a name="ccomcontainedobjectrelease"></a><a name="release"></a> CComContainedObject:: Release

Zmniejsza liczbę odwołań do obiektu właściciela.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Wartość zwracana

W kompilacjach debugowania `Release` zwraca wartość, która może być przydatna w przypadku diagnostyki lub testowania. W kompilacjach niedebugowanych `Release` zawsze zwraca wartość 0.

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
