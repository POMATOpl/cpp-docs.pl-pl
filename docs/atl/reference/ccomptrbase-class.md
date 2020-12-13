---
description: 'Dowiedz się więcej na temat: Klasa CComPtrBase'
title: Klasa CComPtrBase
ms.date: 11/04/2016
f1_keywords:
- CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase::Advise
- ATLCOMCLI/ATL::CComPtrBase::Attach
- ATLCOMCLI/ATL::CComPtrBase::CoCreateInstance
- ATLCOMCLI/ATL::CComPtrBase::CopyTo
- ATLCOMCLI/ATL::CComPtrBase::Detach
- ATLCOMCLI/ATL::CComPtrBase::IsEqualObject
- ATLCOMCLI/ATL::CComPtrBase::QueryInterface
- ATLCOMCLI/ATL::CComPtrBase::Release
- ATLCOMCLI/ATL::CComPtrBase::SetSite
- ATLCOMCLI/ATL::CComPtrBase::p
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
ms.openlocfilehash: 34f197904775bc15366f412e629ef81b26dde74e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142392"
---
# <a name="ccomptrbase-class"></a>Klasa CComPtrBase

Ta klasa stanowi podstawę dla klas wskaźników inteligentnych korzystających z procedur pamięci opartych na modelu COM.

## <a name="syntax"></a>Składnia

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Typ obiektu, do którego odwołuje się inteligentny wskaźnik.

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComPtrBase:: ~ CComPtrBase](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComPtrBase:: Advise](#advise)|Wywołaj tę metodę, aby utworzyć połączenie między `CComPtrBase` punktem połączenia a ujściam klienta.|
|[CComPtrBase:: Attach](#attach)|Wywołaj tę metodę, aby przejąć na własność istniejący wskaźnik.|
|[CComPtrBase:: CoCreateInstance](#cocreateinstance)|Wywołaj tę metodę, aby utworzyć obiekt klasy skojarzonej z określonym IDENTYFIKATORem klasy lub IDENTYFIKATORem programu.|
|[CComPtrBase:: CopyTo](#copyto)|Wywołaj tę metodę, aby skopiować `CComPtrBase` wskaźnik do innej zmiennej wskaźnika.|
|[CComPtrBase::D etach](#detach)|Wywołaj tę metodę, aby zwolnić własność wskaźnika.|
|[CComPtrBase:: isequalobject](#isequalobject)|Wywołaj tę metodę, aby sprawdzić, czy określone `IUnknown` punkty do tego samego obiektu są skojarzone z `CComPtrBase` obiektem.|
|[CComPtrBase:: QueryInterface](#queryinterface)|Wywołaj tę metodę, aby zwrócić wskaźnik do określonego interfejsu.|
|[CComPtrBase:: Release](#release)|Wywołaj tę metodę, aby zwolnić interfejs.|
|[CComPtrBase:: SetSite](#setsite)|Wywołaj tę metodę, aby ustawić lokację `CComPtrBase` obiektu do `IUnknown` obiektu nadrzędnego.|

### <a name="public-operators"></a>Operatory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComPtrBase:: operator T *](#operator_t_star)|Operator rzutowania.|
|[CComPtrBase:: operator!](#operator_not)|Operator NOT.|
|[CComPtrBase:: operator &](#operator_amp)|Operator &.|
|[CComPtrBase:: operator *](#operator_star)|Operator \*.|
|[CComPtrBase:: operator <](#ccomptrbase__operator lt)|Operator mniejszości.|
|[CComPtrBase:: operator = =](#operator_eq_eq)|Operator równości.|
|[CComPtrBase:: operator->](#operator_ptr)|Operator wskaźnika do elementów członkowskich.|

### <a name="public-data-members"></a>Publiczne elementy członkowskie danych

|Nazwa|Opis|
|----------|-----------------|
|[CComPtrBase::p](#p)|Zmienna elementu członkowskiego danych wskaźnika.|

## <a name="remarks"></a>Uwagi

Ta klasa stanowi podstawę dla innych inteligentnych wskaźników, w których używane są procedury zarządzania pamięcią COM, takie jak [CComQIPtr](../../atl/reference/ccomqiptr-class.md) i [CComPtr](../../atl/reference/ccomptr-class.md). Klasy pochodne dodają własne konstruktory i operatory, ale bazują na metodach dostarczonych przez `CComPtrBase` .

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcomcli. h

## <a name="ccomptrbaseadvise"></a><a name="advise"></a> CComPtrBase:: Advise

Wywołaj tę metodę, aby utworzyć połączenie między `CComPtrBase` punktem połączenia a ujściam klienta.

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>Parametry

*Punkt*<br/>
Wskaźnik do klienta `IUnknown` .

*IID*<br/>
Identyfikator GUID punktu połączenia. Zwykle jest to takie samo, jak interfejs wychodzący zarządzany przez punkt połączenia.

*Kreatora*<br/>
Wskaźnik do pliku cookie, który jednoznacznie identyfikuje połączenie.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [AtlAdvise](connection-point-global-functions.md#atladvise) .

## <a name="ccomptrbaseattach"></a><a name="attach"></a> CComPtrBase:: Attach

Wywołaj tę metodę, aby przejąć na własność istniejący wskaźnik.

```cpp
void Attach(T* p2) throw();
```

### <a name="parameters"></a>Parametry

*P2*<br/>
Obiekt przejdzie na `CComPtrBase` własność tego wskaźnika.

### <a name="remarks"></a>Uwagi

`Attach` wywołuje [CComPtrBase:: Release](#release) w istniejącej zmiennej składowej [CComPtrBase::p](#p) , a następnie przypisuje *P2* do `CComPtrBase::p` . Gdy `CComPtrBase` obiekt przejmuje własność wskaźnika, zostanie automatycznie wywołana `Release` na wskaźniku, który usunie wskaźnik i wszystkie przydzielono dane, jeśli liczba odwołań w obiekcie przejdzie do 0.

## <a name="ccomptrbaseccomptrbase"></a><a name="dtor"></a> CComPtrBase:: ~ CComPtrBase

Destruktor.

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>Uwagi

Zwalnia interfejs wskazywany przez `CComPtrBase` .

## <a name="ccomptrbasecocreateinstance"></a><a name="cocreateinstance"></a> CComPtrBase:: CoCreateInstance

Wywołaj tę metodę, aby utworzyć obiekt klasy skojarzonej z określonym IDENTYFIKATORem klasy lub IDENTYFIKATORem programu.

```
HRESULT CoCreateInstance(
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```

### <a name="parameters"></a>Parametry

*szProgID*<br/>
Wskaźnik do identyfikatora ProgID używany do odzyskania identyfikatora CLSID.

*pUnkOuter*<br/>
Jeśli wartość jest równa NULL, wskazuje, że obiekt nie jest tworzony w ramach agregacji. Jeśli wartość nie jest równa NULL, jest wskaźnikiem do interfejsu obiektu agregacji `IUnknown` (kontrolka `IUnknown` ).

*dwClsContext*<br/>
Kontekst, w którym zostanie uruchomiony kod zarządzający nowo utworzonym obiektem.

*rclsid*<br/>
Identyfikator CLSID skojarzony z danymi i kodem, który zostanie użyty do utworzenia obiektu.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK dla sukcesu lub REGDB_E_CLASSNOTREG, CLASS_E_NOAGGREGATION, CO_E_CLASSSTRING lub E_NOINTERFACE w przypadku niepowodzenia. Opis tych błędów można znaleźć w tematach [CoCreateClassInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) i [CLSIDFromProgID](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) .

### <a name="remarks"></a>Uwagi

Jeśli zostanie wywołana pierwsza forma metody, [CLSIDFromProgID](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) jest używana do odzyskania identyfikatora CLSID. Oba formularze następnie wywołują [CoCreateClassInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

W kompilacjach debugowania wystąpi błąd potwierdzenia, jeśli [CComPtrBase::p](#p) nie jest równa null.

## <a name="ccomptrbasecopyto"></a><a name="copyto"></a> CComPtrBase:: CopyTo

Wywołaj tę metodę, aby skopiować `CComPtrBase` wskaźnik do innej zmiennej wskaźnika.

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>Parametry

*Formacie*<br/>
Adres zmiennej, która będzie odbierać `CComPtrBase` wskaźnik.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu, E_POINTER w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Kopiuje `CComPtrBase` wskaźnik do *PPT*. Liczba odwołań dla zmiennej składowej [CComPtrBase::p](#p) jest zwiększana.

Błąd HRESULT zostanie zwrócony, jeśli wartość *PPT* jest równa null. W kompilacjach debugowania wystąpi błąd potwierdzenia, jeśli *PPT* będzie równa null.

## <a name="ccomptrbasedetach"></a><a name="detach"></a> CComPtrBase::D etach

Wywołaj tę metodę, aby zwolnić własność wskaźnika.

```
T* Detach() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca kopię wskaźnika.

### <a name="remarks"></a>Uwagi

Zwalnia własność wskaźnika, ustawia zmienną składową danych [CComPtrBase::p](#p) na null i zwraca kopię wskaźnika.

## <a name="ccomptrbaseisequalobject"></a><a name="isequalobject"></a> CComPtrBase:: isequalobject

Wywołaj tę metodę, aby sprawdzić, czy określone `IUnknown` punkty do tego samego obiektu są skojarzone z `CComPtrBase` obiektem.

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>Parametry

*pOther*<br/>
`IUnknown *`Do porównania.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli obiekty są identyczne, w przeciwnym razie false.

## <a name="ccomptrbaseoperator-"></a><a name="operator_not"></a> CComPtrBase:: operator!

Operator NOT.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true `CComHeapPtr` , jeśli wskaźnik jest równy null, FAŁSZ w przeciwnym razie.

## <a name="ccomptrbaseoperator-amp"></a><a name="operator_amp"></a> CComPtrBase:: operator &amp;

Operator &.

```
T** operator&() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca adres obiektu wskazywanego przez `CComPtrBase` obiekt.

## <a name="ccomptrbaseoperator-"></a><a name="operator_star"></a> CComPtrBase:: operator \*

Operator \*.

```
T& operator*() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość [CComPtrBase::p](#p); oznacza to wskaźnik do obiektu, do którego odwołuje się `CComPtrBase` obiekt.

W przypadku kompilacji debugowania wystąpi błąd potwierdzenia, jeśli [CComPtrBase::p](#p) nie jest równa null.

## <a name="ccomptrbaseoperator-"></a><a name="operator_eq_eq"></a> CComPtrBase:: operator = =

Operator równości.

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>Parametry

*Zmiennoprzecinkow*<br/>
Wskaźnik do obiektu.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true `CComPtrBase` , jeśli i *pt* wskazuje na ten sam obiekt, w przeciwnym razie false.

## <a name="ccomptrbaseoperator--gt"></a><a name="operator_ptr"></a> CComPtrBase:: operator-&gt;

Operator wskaźnika do składowej.

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość zmiennej składowej danych [CComPtrBase::p](#p) .

### <a name="remarks"></a>Uwagi

Użyj tego operatora, aby wywołać metodę w klasie wskazywanej przez `CComPtrBase` obiekt. W kompilacjach debugowania wystąpi błąd potwierdzenia, jeśli `CComPtrBase` element członkowski danych wskazuje wartość null.

## <a name="ccomptrbaseoperator-lt"></a><a name="operator_lt"></a> CComPtrBase:: operator &lt;

Operator mniejszości.

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>Parametry

*Zmiennoprzecinkow*<br/>
Wskaźnik do obiektu.

### <a name="return-value"></a>Wartość zwracana

Zwraca wartość true, jeśli wskaźnik zarządzany przez bieżący obiekt jest mniejszy niż wskaźnik, do którego jest porównywany.

## <a name="ccomptrbaseoperator-t"></a><a name="operator_t_star"></a> CComPtrBase:: operator T\*

Operator rzutowania.

```
operator T*() const throw();
```

### <a name="remarks"></a>Uwagi

Zwraca wskaźnik do typu danych obiektu zdefiniowanego w szablonie klasy.

## <a name="ccomptrbasep"></a><a name="p"></a> CComPtrBase::p

Zmienna elementu członkowskiego danych wskaźnika.

```
T* p;
```

### <a name="remarks"></a>Uwagi

Ta zmienna członkowska zawiera informacje o wskaźniku.

## <a name="ccomptrbasequeryinterface"></a><a name="queryinterface"></a> CComPtrBase:: QueryInterface

Wywołaj tę metodę, aby zwrócić wskaźnik do określonego interfejsu.

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>Parametry

*Pytania*<br/>
Typ obiektu, którego wskaźnik interfejsu jest wymagany.

*miesięcznie*<br/>
Adres zmiennej wyjściowej, która odbiera żądany wskaźnik interfejsu.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu lub E_NOINTERFACE w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Ta metoda wywołuje [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)).

W kompilacjach debugowania wystąpi błąd potwierdzenia, jeśli *PP* nie jest równy null.

## <a name="ccomptrbaserelease"></a><a name="release"></a> CComPtrBase:: Release

Wywołaj tę metodę, aby zwolnić interfejs.

```cpp
void Release() throw();
```

### <a name="remarks"></a>Uwagi

Interfejs jest wydawany, a [CComPtrBase::p](#p) ma wartość null.

## <a name="ccomptrbasesetsite"></a><a name="setsite"></a> CComPtrBase:: SetSite

Wywołaj tę metodę, aby ustawić lokację `CComPtrBase` obiektu do `IUnknown` obiektu nadrzędnego.

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>Parametry

*punkParent*<br/>
Wskaźnik do `IUnknown` interfejsu elementu nadrzędnego.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Ta metoda wywołuje [AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite).

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
