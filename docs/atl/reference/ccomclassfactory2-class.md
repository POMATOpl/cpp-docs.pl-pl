---
description: 'Dowiedz się więcej na temat: Klasa CComClassFactory2'
title: Klasa CComClassFactory2
ms.date: 11/04/2016
f1_keywords:
- CComClassFactory2
- ATLCOM/ATL::CComClassFactory2
- ATLCOM/ATL::CComClassFactory2::CreateInstance
- ATLCOM/ATL::CComClassFactory2::CreateInstanceLic
- ATLCOM/ATL::CComClassFactory2::GetLicInfo
- ATLCOM/ATL::CComClassFactory2::LockServer
- ATLCOM/ATL::CComClassFactory2::RequestLicKey
helpviewer_keywords:
- CComClassFactory2 class
ms.assetid: 19b66fd6-b9ed-47a0-822c-8132184f5a3e
ms.openlocfilehash: 7aebf09616c7fc4e85f6c44aee4db84886033f8b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146890"
---
# <a name="ccomclassfactory2-class"></a>Klasa CComClassFactory2

Ta klasa implementuje interfejs [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) .

## <a name="syntax"></a>Składnia

```
template <class license>
class CComClassFactory2 : public IClassFactory2,
    public CComObjectRootEx<CComGlobalsThreadModel>,
    public license
```

#### <a name="parameters"></a>Parametry

*licencja*<br/>
Klasa, która implementuje następujące funkcje statyczne:

- `static BOOL VerifyLicenseKey( BSTR bstr );`

- `static BOOL GetLicenseKey( DWORD dwReserved, BSTR * pBstr );`

- `static BOOL IsLicenseValid( );`

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComClassFactory2:: CreateInstance](#createinstance)|Tworzy obiekt o określonym identyfikatorze CLSID.|
|[CComClassFactory2::CreateInstanceLic](#createinstancelic)|Podano klucz licencji, tworzy obiekt o określonym identyfikatorze CLSID.|
|[CComClassFactory2::GetLicInfo](#getlicinfo)|Pobiera informacje opisujące możliwości licencjonowania fabryki klas.|
|[CComClassFactory2:: LockServer —](#lockserver)|Blokuje fabrykę klas w pamięci.|
|[CComClassFactory2::RequestLicKey](#requestlickey)|Tworzy i zwraca klucz licencji.|

## <a name="remarks"></a>Uwagi

`CComClassFactory2` implementuje interfejs [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2) , który jest rozszerzeniem [elementu IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory). `IClassFactory2` steruje tworzeniem obiektów za pomocą licencji. Fabryka klas wykonywana na licencjonowanym komputerze może zapewnić klucz licencji w czasie wykonywania. Ten klucz licencji pozwala aplikacji na tworzenie wystąpień obiektów w przypadku, gdy nie istnieje pełna licencja komputera.

Obiekty ATL zwykle uzyskują fabrykę klasy poprzez wyprowadzanie z [CComCoClass](../../atl/reference/ccomcoclass-class.md). Ta klasa zawiera [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)makro, które deklaruje [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) jako domyślną fabrykę klas. Aby użyć `CComClassFactory2` , określ [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) makro w definicji klasy obiektu. Na przykład:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomclassfactory2-class_1.h)]

`CMyLicense`, parametr szablonu do `CComClassFactory2` , musi implementować funkcje statyczne `VerifyLicenseKey` , `GetLicenseKey` i `IsLicenseValid` . Oto przykład prostej klasy licencji:

[!code-cpp[NVC_ATL_COM#3](../../atl/codesnippet/cpp/ccomclassfactory2-class_2.h)]

`CComClassFactory2` pochodzi od obu `CComClassFactory2Base` *licencji*. `CComClassFactory2Base`z kolei pochodzi od `IClassFactory2` i `CComObjectRootEx< CComGlobalsThreadModel >` .

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

`CComObjectRootBase`

`license`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory2`

`CComClassFactory2`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="ccomclassfactory2createinstance"></a><a name="createinstance"></a> CComClassFactory2:: CreateInstance

Tworzy obiekt o określonym identyfikatorze CLSID i Pobiera wskaźnik interfejsu do tego obiektu.

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>Parametry

*pUnkOuter*<br/>
podczas Jeśli obiekt jest tworzony w ramach agregacji, *pUnkOuter* musi być nieznane zewnętrzne. W przeciwnym razie *pUnkOuter* musi mieć wartość null.

*riid*<br/>
podczas Identyfikator IID żądanego interfejsu. Jeśli *pUnkOuter* ma wartość różną od null, *riid* musi być `IID_IUnknown` .

*ppvObj*<br/>
określoną Wskaźnik do wskaźnika interfejsu identyfikowanego przez *riid*. Jeśli obiekt nie obsługuje tego interfejsu, *ppvObj* ma wartość null.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

### <a name="remarks"></a>Uwagi

Wymaga, aby komputer był w pełni licencjonowany. Jeśli pełna licencja komputera nie istnieje, wywołaj [CreateInstanceLic](#createinstancelic).

## <a name="ccomclassfactory2createinstancelic"></a><a name="createinstancelic"></a> CComClassFactory2::CreateInstanceLic

Podobnie jak w przypadku [wystąpienia](#createinstance), z wyjątkiem tego, że `CreateInstanceLic` wymaga klucza licencji.

```
STDMETHOD(CreateInstanceLic)(
    IUnknown* pUnkOuter,
    IUnknown* /* pUnkReserved
*/,
    REFIID riid,
    BSTR bstrKey,
    void** ppvObject);
```

### <a name="parameters"></a>Parametry

*pUnkOuter*<br/>
podczas Jeśli obiekt jest tworzony w ramach agregacji, *pUnkOuter* musi być nieznane zewnętrzne. W przeciwnym razie *pUnkOuter* musi mieć wartość null.

*pUnkReserved*<br/>
podczas Nieużywane. Musi mieć wartość NULL.

*riid*<br/>
podczas Identyfikator IID żądanego interfejsu. Jeśli *pUnkOuter* ma wartość różną od null, *riid* musi być `IID_IUnknown` .

*bstrKey*<br/>
podczas Klucz licencji czasu wykonywania uzyskany wcześniej z wywołania do `RequestLicKey` . Ten klucz jest wymagany do utworzenia obiektu.

*ppvObject*<br/>
określoną Wskaźnik do wskaźnika interfejsu określonego przez *riid*. Jeśli obiekt nie obsługuje tego interfejsu, *ppvObject* ma wartość null.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

### <a name="remarks"></a>Uwagi

Klucz licencji można uzyskać za pomocą [RequestLicKey](#requestlickey). Aby można było utworzyć obiekt na komputerze bez licencji, należy wywołać polecenie `CreateInstanceLic` .

## <a name="ccomclassfactory2getlicinfo"></a><a name="getlicinfo"></a> CComClassFactory2::GetLicInfo

Wypełnia strukturę [LICINFO](/windows/win32/api/ocidl/ns-ocidl-licinfo) z informacjami opisującymi możliwości licencjonowania klasy fabryki.

```
STDMETHOD(GetLicInfo)(LICINFO* pLicInfo);
```

### <a name="parameters"></a>Parametry

*pLicInfo*<br/>
określoną Wskaźnik do `LICINFO` struktury.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

### <a name="remarks"></a>Uwagi

`fRuntimeKeyAvail`Element członkowski tej struktury wskazuje, czy dany klucz licencji zapewnia, że fabryka klas umożliwia tworzenie obiektów na komputerze bez licencji. Członek *fLicVerified* wskazuje, czy istnieje pełna licencja na komputer.

## <a name="ccomclassfactory2lockserver"></a><a name="lockserver"></a> CComClassFactory2:: LockServer —

Zwiększa i zmniejsza liczbę blokad modułu przez wywoływanie `_Module::Lock` i `_Module::Unlock` , odpowiednio.

```
STDMETHOD(LockServer)(BOOL fLock);
```

### <a name="parameters"></a>Parametry

*Zarodowych*<br/>
podczas W przypadku wartości TRUE liczba blokad jest zwiększana; w przeciwnym razie licznik blokady jest zmniejszany.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

### <a name="remarks"></a>Uwagi

`_Module` odwołuje się do globalnego wystąpienia [CComModule](../../atl/reference/ccommodule-class.md) lub klasy pochodzącej od niej.

Wywołanie `LockServer` umożliwia klientowi przechowywanie w fabryce klasy, dzięki czemu można szybko utworzyć wiele obiektów.

## <a name="ccomclassfactory2requestlickey"></a><a name="requestlickey"></a> CComClassFactory2::RequestLicKey

Tworzy i zwraca klucz licencji, pod warunkiem, że `fRuntimeKeyAvail` element członkowski struktury [LICINFO](/windows/win32/api/ocidl/ns-ocidl-licinfo) ma wartość true.

```
STDMETHOD(RequestLicKey)(DWORD dwReserved, BSTR* pbstrKey);
```

### <a name="parameters"></a>Parametry

*dwReserved*<br/>
podczas Nieużywane. Musi być równa zero.

*pbstrKey*<br/>
określoną Wskaźnik na klucz licencji.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT.

### <a name="remarks"></a>Uwagi

Klucz licencji jest wymagany do wywołania [CreateInstanceLic](#createinstancelic) w celu utworzenia obiektu na komputerze bez licencji. Jeśli `fRuntimeKeyAvail` ma wartość false, obiekty można tworzyć tylko na w pełni licencjonowanym komputerze.

Wywołaj [GetLicInfo](#getlicinfo) , aby pobrać wartość `fRuntimeKeyAvail` .

## <a name="see-also"></a>Zobacz też

[Klasa CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[Klasa CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)<br/>
[Klasa CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)
