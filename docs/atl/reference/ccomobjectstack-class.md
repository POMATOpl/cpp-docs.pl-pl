---
description: 'Dowiedz się więcej na temat: Klasa CComObjectStack'
title: Klasa CComObjectStack
ms.date: 11/04/2016
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
ms.openlocfilehash: 5713601a765ad9ff1c32992d1f9c517dd86affca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142418"
---
# <a name="ccomobjectstack-class"></a>Klasa CComObjectStack

Ta klasa tworzy tymczasowy obiekt COM i udostępnia go z implementacją szkieletową `IUnknown` .

## <a name="syntax"></a>Składnia

```
template <class  Base>
class CComObjectStack : public Base
```

#### <a name="parameters"></a>Parametry

*Opiera*<br/>
Klasa, pochodząca z [klasy CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) lub [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), a także z dowolnego innego interfejsu, który ma być obsługiwany w obiekcie.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|Konstruktor.|
|[CComObjectStack:: ~ CComObjectStack](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComObjectStack:: AddRef](#addref)|Zwraca wartość zero. W trybie debugowania wywołania `_ASSERTE` .|
|[CComObjectStack:: QueryInterface](#queryinterface)|Zwraca E_NOINTERFACE. W trybie debugowania wywołania `_ASSERTE` .|
|[CComObjectStack:: Release](#release)|Zwraca wartość zero. W trybie debugowania wywołania `_ASSERTE` . ~|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CComObjectStack:: m_hResFinalConstruct](#m_hresfinalconstruct)|Zawiera wartość HRESULT zwracaną podczas konstruowania `CComObjectStack` obiektu.|

## <a name="remarks"></a>Uwagi

`CComObjectStack` służy do tworzenia tymczasowego obiektu COM i zapewniania obiektowi implementacji szkieletowej `IUnknown` . Zazwyczaj obiekt jest używany jako zmienna lokalna w ramach jednej funkcji (jest to wypchnięcie na stos). Ponieważ obiekt jest niszczony po zakończeniu działania funkcji, zliczanie odwołań nie jest wykonywane w celu zwiększenia wydajności.

Poniższy przykład pokazuje, jak utworzyć obiekt COM używany wewnątrz funkcji:

[!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]

Obiekt tymczasowy `Tempobj` jest wypychany do stosu i automatycznie znika po zakończeniu działania funkcji.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`Base`

`CComObjectStack`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="ccomobjectstackaddref"></a><a name="addref"></a> CComObjectStack:: AddRef

Zwraca wartość zero.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość zero.

### <a name="remarks"></a>Uwagi

W trybie debugowania wywołania `_ASSERTE` .

## <a name="ccomobjectstackccomobjectstack"></a><a name="ccomobjectstack"></a> CComObjectStack::CComObjectStack

Konstruktor.

```
CComObjectStack(void* = NULL);
```

### <a name="remarks"></a>Uwagi

Wywołuje `FinalConstruct` , a następnie ustawia [m_hResFinalConstruct](#m_hresfinalconstruct) na wartość HRESULT zwracaną przez `FinalConstruct` . Jeśli klasa bazowa nie pochodzi od [klasy CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), należy podać własną `FinalConstruct` metodę. Destruktor wywołuje `FinalRelease` .

## <a name="ccomobjectstackccomobjectstack"></a><a name="dtor"></a> CComObjectStack:: ~ CComObjectStack

Destruktor.

```
CComObjectStack();
```

### <a name="remarks"></a>Uwagi

Zwalnia wszystkie przydzieloną zasoby i wywołuje [FinalRelease](ccomobjectrootex-class.md#finalrelease).

## <a name="ccomobjectstackm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a> CComObjectStack:: m_hResFinalConstruct

Zawiera wartość HRESULT zwracaną z wywołania `FinalConstruct` podczas konstruowania `CComObjectStack` obiektu.

```
HRESULT    m_hResFinalConstruct;
```

## <a name="ccomobjectstackqueryinterface"></a><a name="queryinterface"></a> CComObjectStack:: QueryInterface

Zwraca E_NOINTERFACE.

```
HRESULT    QueryInterface(REFIID, void**);
```

### <a name="return-value"></a>Wartość zwracana

Zwraca E_NOINTERFACE.

### <a name="remarks"></a>Uwagi

W trybie debugowania wywołania `_ASSERTE` .

## <a name="ccomobjectstackrelease"></a><a name="release"></a> CComObjectStack:: Release

Zwraca wartość zero.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość zero.

### <a name="remarks"></a>Uwagi

W trybie debugowania wywołania `_ASSERTE` .

## <a name="see-also"></a>Zobacz też

[Klasa CComAggObject](../../atl/reference/ccomaggobject-class.md)<br/>
[Klasa CComObject](../../atl/reference/ccomobject-class.md)<br/>
[Klasa CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
