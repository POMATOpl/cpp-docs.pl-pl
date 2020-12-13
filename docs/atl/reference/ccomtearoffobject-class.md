---
description: 'Dowiedz się więcej na temat: Klasa CComTearOffObject'
title: Klasa CComTearOffObject
ms.date: 11/04/2016
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
ms.openlocfilehash: b9fe9e7a790a004aec1de059415bd5f47572455b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142158"
---
# <a name="ccomtearoffobject-class"></a>Klasa CComTearOffObject

Ta klasa implementuje interfejs odrywający.

## <a name="syntax"></a>Składnia

```
template<class Base>
class CComTearOffObject : public Base
```

#### <a name="parameters"></a>Parametry

*Opiera*<br/>
Klasa odrywania, pochodna `CComTearOffObjectBase` i interfejsy, które mają być obsługiwane przez obiekt.

ATL implementuje interfejsy Odrywane w dwóch fazach — `CComTearOffObjectBase` metody obsługują liczbę odwołań i `QueryInterface` , podczas gdy `CComTearOffObject` implementuje [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown).

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|Konstruktor.|
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComTearOffObject:: AddRef](#addref)|Zwiększa liczbę odwołań dla `CComTearOffObject` obiektu.|
|[CComTearOffObject:: QueryInterface](#queryinterface)|Zwraca wskaźnik do żądanego interfejsu w klasie odrywanej lub klasie Owner.|
|[CComTearOffObject:: Release](#release)|Zmniejsza liczbę odwołań dla `CComTearOffObject` obiektu i niszczy go.|

### <a name="ccomtearoffobjectbase-methods"></a>Metody CComTearOffObjectBase

|Funkcja|Opis|
|-|-|
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|Konstruktor.|

### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOffObjectBase elementy członkowskie danych

|Element członkowski danych|Opis|
|-|-|
|[m_pOwner](#m_powner)|Wskaźnik do elementu `CComObject` pochodnego od klasy Owner.|

## <a name="remarks"></a>Uwagi

`CComTearOffObject` implementuje interfejs odrywany jako oddzielny obiekt, którego wystąpienie jest tworzone tylko wtedy, gdy jest to zapytanie dla tego interfejsu. Odrywanie jest usuwane, gdy jej liczba odwołań zmieni się na zero. Zazwyczaj tworzysz interfejs do odrywania dla interfejsu, który jest rzadko używany, ponieważ użycie odrywania powoduje zapisanie wskaźnika tablicy tablicowej we wszystkich wystąpieniach obiektu głównego.

Należy utworzyć klasę implementującą odrywanie od `CComTearOffObjectBase` i z niezależnie od tego, które interfejsy mają być obsługiwane przez obiekt. `CComTearOffObjectBase` jest szablonowana dla klasy Owner i modelu wątku. Klasa Owner jest klasą obiektu, dla którego są implementowane odrywania. Jeśli model wątku nie zostanie określony, używany jest domyślny model wątku.

Należy utworzyć mapę COM dla klasy odrywanej. Gdy ATL tworzy odrywanie, spowoduje utworzenie `CComTearOffObject<CYourTearOffClass>` lub `CComCachedTearOffObject<CYourTearOffClass>` .

Na przykład w próbce sygnału dźwiękowego `CBeeper2` Klasa jest klasą odrywaną, a `CBeeper` Klasa jest klasą będącą właścicielem:

[!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`Base`

`CComTearOffObject`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="ccomtearoffobjectaddref"></a><a name="addref"></a> CComTearOffObject:: AddRef

Zwiększa liczbę odwołań `CComTearOffObject` obiektu o jeden.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Wartość zwracana

Wartość, która może być przydatna w przypadku diagnostyki i testowania.

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="ccomtearoffobject"></a> CComTearOffObject::CComTearOffObject

Konstruktor.

```
CComTearOffObject(void* pv);
```

### <a name="parameters"></a>Parametry

*wa*<br/>
podczas Wskaźnik, który zostanie przekonwertowany na wskaźnik do `CComObject<Owner>` obiektu.

### <a name="remarks"></a>Uwagi

Zwiększa liczbę odwołań właściciela o jeden.

## <a name="ccomtearoffobjectccomtearoffobject"></a><a name="dtor"></a> CComTearOffObject:: ~ CComTearOffObject

Destruktor.

```
~CComTearOffObject();
```

### <a name="remarks"></a>Uwagi

Zwalnia wszystkie przydzieloną zasoby, wywołuje FinalRelease i zmniejsza liczbę blokad modułu.

## <a name="ccomtearoffobjectccomtearoffobjectbase"></a><a name="ccomtearoffobjectbase"></a> CComTearOffObject::CComTearOffObjectBase

Konstruktor.

```
CComTearOffObjectBase();
```

### <a name="remarks"></a>Uwagi

Inicjuje element członkowski [m_pOwner](#m_powner) do wartości null.

## <a name="ccomtearoffobjectm_powner"></a><a name="m_powner"></a> CComTearOffObject:: m_pOwner

Wskaźnik do obiektu [CComObject](../../atl/reference/ccomobject-class.md) pochodzącego od *właściciela*.

```
CComObject<Owner>* m_pOwner;
```

### <a name="parameters"></a>Parametry

*Właściciel*<br/>
podczas Klasa, dla której jest implementowane odrywanie.

### <a name="remarks"></a>Uwagi

Wskaźnik zostanie zainicjowany do wartości NULL podczas konstruowania.

## <a name="ccomtearoffobjectqueryinterface"></a><a name="queryinterface"></a> CComTearOffObject:: QueryInterface

Pobiera wskaźnik do żądanego interfejsu.

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>Parametry

*IID*<br/>
podczas Identyfikator IID żądanego interfejsu.

*ppvObject*<br/>
określoną Wskaźnik do wskaźnika interfejsu identyfikowanego przez *Identyfikator IID* lub wartość null, jeśli nie można odnaleźć interfejsu.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

### <a name="remarks"></a>Uwagi

Najpierw wysyła zapytania dotyczące interfejsów w klasie odrywanej. Jeśli interfejs nie istnieje, kwerendy dla interfejsu w obiekcie Owner. Jeśli żądany interfejs to `IUnknown` , zwraca `IUnknown` właściciela.

## <a name="ccomtearoffobjectrelease"></a><a name="release"></a> CComTearOffObject:: Release

Zmniejsza liczbę odwołań o jeden i, jeśli liczba odwołań wynosi zero, usuwa `CComTearOffObject` .

```
STDMETHOD_ULONG Release();
```

### <a name="return-value"></a>Wartość zwracana

W kompilacjach niedebugowanych zawsze zwraca wartość zero. W kompilacjach debugowania zwraca wartość, która może być przydatna w przypadku diagnostyki lub testowania.

## <a name="see-also"></a>Zobacz też

[Klasa CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
