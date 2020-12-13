---
description: 'Dowiedz się więcej na temat: Klasa CComAggObject'
title: Klasa CComAggObject
ms.date: 11/04/2016
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
ms.openlocfilehash: 84af79678221ae74a151a4821039ff1d7a743cc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152363"
---
# <a name="ccomaggobject-class"></a>Klasa CComAggObject

Ta klasa implementuje interfejs [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) dla obiektu agregowanego. Według definicji, zagregowany obiekt jest zawarty w obiekcie zewnętrznym. `CComAggObject`Klasa jest podobna do [klasy CComObject](../../atl/reference/ccomobject-class.md), z tą różnicą, że ujawnia interfejs, który jest bezpośrednio dostępny dla klientów zewnętrznych.

## <a name="syntax"></a>Składnia

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>Parametry

*przechowywany*<br/>
Klasa, pochodząca z [klasy CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) lub [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), a także z innych interfejsów, które mają być obsługiwane w obiekcie.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComAggObject:: CComAggObject](#ccomaggobject)|Konstruktor.|
|[CComAggObject:: ~ CComAggObject](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComAggObject:: AddRef](#addref)|Zwiększa liczbę odwołań do zagregowanego obiektu.|
|[CComAggObject:: CreateInstance](#createinstance)|Ta funkcja statyczna pozwala utworzyć nowy obiekt **<CComAggObject** `contained` **>** bez narzutu na [wywołanie](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)funkcji.|
|[CComAggObject:: FinalConstruct](#finalconstruct)|Wykonuje ostateczną inicjalizację `m_contained` .|
|[CComAggObject:: FinalRelease](#finalrelease)|Wykonuje ostateczne zniszczenie `m_contained` .|
|[CComAggObject:: QueryInterface](#queryinterface)|Pobiera wskaźnik do żądanego interfejsu.|
|[CComAggObject:: Release](#release)|Zmniejsza liczbę odwołań do zagregowanego obiektu.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CComAggObject:: m_contained](#m_contained)|Deleguje `IUnknown` wywołania nieznane zewnętrzne.|

## <a name="remarks"></a>Uwagi

`CComAggObject` implementuje [interfejs IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) dla zagregowanego obiektu. `CComAggObject` ma własny `IUnknown` interfejs, oddziel się od interfejsu zewnętrznego obiektu `IUnknown` i utrzymuje swój własny licznik odwołań.

Aby uzyskać więcej informacji na temat agregacji, zapoznaj się z artykułem [podstawy obiektów ATL com](../../atl/fundamentals-of-atl-com-objects.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="ccomaggobjectaddref"></a><a name="addref"></a> CComAggObject:: AddRef

Zwiększa liczbę odwołań do zagregowanego obiektu.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Wartość zwracana

Wartość, która może być przydatna w przypadku diagnostyki lub testowania.

## <a name="ccomaggobjectccomaggobject"></a><a name="ccomaggobject"></a> CComAggObject:: CComAggObject

Konstruktor.

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>Parametry

*wa*<br/>
podczas Nieznana zewnętrzna.

### <a name="remarks"></a>Uwagi

Inicjuje `CComContainedObject` element członkowski, [m_contained](#m_contained)i zwiększa liczbę blokad modułu.

Destruktor zmniejsza liczbę blokad modułu.

## <a name="ccomaggobjectccomaggobject"></a><a name="dtor"></a> CComAggObject:: ~ CComAggObject

Destruktor.

```
~CComAggObject();
```

### <a name="remarks"></a>Uwagi

Zwalnia wszystkie przydzieloną zasoby, wywołuje [FinalRelease](#finalrelease)i zmniejsza liczbę blokad modułu.

## <a name="ccomaggobjectcreateinstance"></a><a name="createinstance"></a> CComAggObject:: CreateInstance

Ta funkcja statyczna pozwala utworzyć nowy obiekt **<CComAggObject** `contained` **>** bez narzutu na [wywołanie](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)funkcji.

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>Parametry

*miesięcznie*<br/>
określoną Wskaźnik do **CComAggObject \<**<em> zawiera </em>**> * * wskaźnik. Jeśli `CreateInstance` to się nie powiedzie, *PP* ma ustawioną wartość null.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

### <a name="remarks"></a>Uwagi

Zwrócony obiekt ma liczbę odwołań równą zero, więc Wywołaj `AddRef` natychmiast, a następnie użyj, `Release` Aby zwolnić odwołanie na wskaźniku obiektu po zakończeniu.

Jeśli nie potrzebujesz bezpośredniego dostępu do obiektu, ale nadal chcesz utworzyć nowy obiekt bez nakładu pracy `CoCreateInstance` , zamiast tego użyj [CComCoClass:: CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) .

## <a name="ccomaggobjectfinalconstruct"></a><a name="finalconstruct"></a> CComAggObject:: FinalConstruct

Wywoływana podczas końcowych etapów konstruowania obiektu, ta metoda wykonuje wszelkie końcowe inicjalizacje elementu członkowskiego [m_contained](#m_contained) .

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

## <a name="ccomaggobjectfinalrelease"></a><a name="finalrelease"></a> CComAggObject:: FinalRelease

Wywoływana podczas niszczenia obiektu, ta metoda zwalnia składową [m_contained](#m_contained) .

```cpp
void FinalRelease();
```

## <a name="ccomaggobjectm_contained"></a><a name="m_contained"></a> CComAggObject:: m_contained

Obiekt [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) pochodzący od klasy.

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>Parametry

*przechowywany*<br/>
podczas Klasa, pochodząca z [klasy CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) lub [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), a także z innych interfejsów, które mają być obsługiwane w obiekcie.

### <a name="remarks"></a>Uwagi

Wszystkie `IUnknown` wywołania przez `m_contained` są delegowane do nieznanego zewnętrznego.

## <a name="ccomaggobjectqueryinterface"></a><a name="queryinterface"></a> CComAggObject:: QueryInterface

Pobiera wskaźnik do żądanego interfejsu.

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

### <a name="remarks"></a>Uwagi

Jeśli żądany interfejs to `IUnknown` , `QueryInterface` zwraca wskaźnik do własnego obiektu zagregowanego `IUnknown` i zwiększa liczbę odwołań. W przeciwnym razie ta metoda wysyła zapytanie do interfejsu za pomocą `CComContainedObject` elementu członkowskiego, [m_contained](#m_contained).

## <a name="ccomaggobjectrelease"></a><a name="release"></a> CComAggObject:: Release

Zmniejsza liczbę odwołań do zagregowanego obiektu.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Wartość zwracana

W kompilacjach debugowania `Release` zwraca wartość, która może być przydatna w przypadku diagnostyki lub testowania. W kompilacjach niedebugowanych `Release` zawsze zwraca wartość 0.

## <a name="see-also"></a>Zobacz też

[Klasa CComObject](../../atl/reference/ccomobject-class.md)<br/>
[Klasa CComPolyObject](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
