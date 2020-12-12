---
description: 'Dowiedz się więcej na temat: Klasa CComObjectGlobal'
title: Klasa CComObjectGlobal
ms.date: 11/04/2016
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
ms.openlocfilehash: 0f79acb0fdbb43f9456e08f26875d45eec9904c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151986"
---
# <a name="ccomobjectglobal-class"></a>Klasa CComObjectGlobal

Ta klasa zarządza liczbą odwołań w module zawierającym `Base` obiekt.

## <a name="syntax"></a>Składnia

```
template<class Base>
class CComObjectGlobal : public Base
```

#### <a name="parameters"></a>Parametry

*Opiera*<br/>
Klasa, pochodząca z [klasy CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) lub [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), a także z dowolnego innego interfejsu, który ma być obsługiwany w obiekcie.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|Konstruktor.|
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComObjectGlobal:: AddRef](#addref)|Implementuje globalną `AddRef` .|
|[CComObjectGlobal:: QueryInterface](#queryinterface)|Implementuje globalną `QueryInterface` .|
|[CComObjectGlobal:: Release](#release)|Implementuje globalną `Release` .|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CComObjectGlobal:: m_hResFinalConstruct](#m_hresfinalconstruct)|Zawiera wartość HRESULT zwracaną podczas konstruowania `CComObjectGlobal` obiektu.|

## <a name="remarks"></a>Uwagi

`CComObjectGlobal` zarządza liczbą odwołań w module zawierającym `Base` obiekt. `CComObjectGlobal` zapewnia, że obiekt nie zostanie usunięty, o ile moduł nie zostanie opublikowany. Obiekt zostanie usunięty tylko wtedy, gdy liczba odwołań dla całego modułu przejdzie do zera.

Na przykład przy użyciu `CComObjectGlobal` , fabryka klasy może przechowywać wspólny obiekt globalny, który jest współużytkowany przez wszystkich jego klientów.

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`Base`

`CComObjectGlobal`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="ccomobjectglobaladdref"></a><a name="addref"></a> CComObjectGlobal:: AddRef

Zwiększa liczbę odwołań obiektu o 1.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Wartość zwracana

Wartość, która może być przydatna w przypadku diagnostyki i testowania.

### <a name="remarks"></a>Uwagi

Domyślnie `AddRef` wywołania `_Module::Lock` , gdzie `_Module` to globalne wystąpienie elementu [CComModule](../../atl/reference/ccommodule-class.md) lub klasy pochodzącej od niej.

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="ccomobjectglobal"></a> CComObjectGlobal::CComObjectGlobal

Konstruktor. Wywołania `FinalConstruct` , a następnie ustawia [m_hResFinalConstruct](#m_hresfinalconstruct) do `HRESULT` zwracanego przez `FinalConstruct` .

```
CComObjectGlobal(void* = NULL));
```

### <a name="remarks"></a>Uwagi

Jeśli klasa bazowa nie pochodzi od [klasy CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), należy podać własną `FinalConstruct` metodę. Destruktor wywołuje `FinalRelease` .

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="dtor"></a> CComObjectGlobal:: ~ CComObjectGlobal

Destruktor.

```
CComObjectGlobal();
```

### <a name="remarks"></a>Uwagi

Zwalnia wszystkie przydzieloną zasoby i wywołuje [FinalRelease](ccomobjectrootex-class.md#finalrelease).

## <a name="ccomobjectglobalm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a> CComObjectGlobal:: m_hResFinalConstruct

Zawiera wynik HRESULT z wywołania `FinalConstruct` podczas konstruowania `CComObjectGlobal` obiektu.

```
HRESULT m_hResFinalConstruct;
```

## <a name="ccomobjectglobalqueryinterface"></a><a name="queryinterface"></a> CComObjectGlobal:: QueryInterface

Pobiera wskaźnik do żądanego wskaźnika interfejsu.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametry

*IID*<br/>
podczas Identyfikator GUID żądanego interfejsu.

*ppvObject*<br/>
określoną Wskaźnik do wskaźnika interfejsu identyfikowanego przez identyfikator IID lub wartość NULL, jeśli nie można odnaleźć interfejsu.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

### <a name="remarks"></a>Uwagi

`QueryInterface` obsługuje tylko interfejsy w tabeli mapy COM.

## <a name="ccomobjectglobalrelease"></a><a name="release"></a> CComObjectGlobal:: Release

Zmniejsza liczbę odwołań obiektu o 1.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Wartość zwracana

W kompilacjach debugowania `Release` zwraca wartość, która może być przydatna w przypadku diagnostyki i testowania. W kompilacjach niedebugowanych `Release` zawsze zwraca wartość 0.

### <a name="remarks"></a>Uwagi

Domyślnie `Release` wywołania `_Module::Unlock` , gdzie `_Module` to globalne wystąpienie elementu [CComModule](../../atl/reference/ccommodule-class.md) lub klasy pochodzącej od niej.

## <a name="see-also"></a>Zobacz też

[Klasa CComObjectStack](../../atl/reference/ccomobjectstack-class.md)<br/>
[Klasa CComAggObject](../../atl/reference/ccomaggobject-class.md)<br/>
[Klasa CComObject](../../atl/reference/ccomobject-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
