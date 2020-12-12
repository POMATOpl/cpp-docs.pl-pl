---
description: 'Dowiedz się więcej na temat: Klasa CComCoClass'
title: Klasa CComCoClass
ms.date: 11/04/2016
f1_keywords:
- CComCoClass
- ATLCOM/ATL::CComCoClass
- ATLCOM/ATL::CComCoClass::CreateInstance
- ATLCOM/ATL::CComCoClass::Error
- ATLCOM/ATL::CComCoClass::GetObjectCLSID
- ATLCOM/ATL::CComCoClass::GetObjectDescription
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
ms.openlocfilehash: 31895afa9100159e8ac1a9ef370f6548e2b2e3f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152259"
---
# <a name="ccomcoclass-class"></a>Klasa CComCoClass

Ta klasa dostarcza metody do tworzenia wystąpień klasy i uzyskiwania jej właściwości.

## <a name="syntax"></a>Składnia

```
template <class T, const CLSID* pclsid = &CLSID_NULL>
class CComCoClass
```

#### <a name="parameters"></a>Parametry

*T*<br/>
Klasa, która pochodzi od `CComCoClass` .

*pclsid*<br/>
Wskaźnik do identyfikatora CLSID obiektu.

## <a name="members"></a>Elementy członkowskie

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CComCoClass:: CreateInstance](#createinstance)|Ruchom Tworzy wystąpienie klasy i zapytania dla interfejsu.|
|[CComCoClass:: Error](#error)|Ruchom Zwraca informacje o rozbudowanym błędzie dla klienta.|
|[CComCoClass:: GetObjectCLSID](#getobjectclsid)|Ruchom Zwraca identyfikator klasy obiektu.|
|[CComCoClass:: GetObjectDescription](#getobjectdescription)|Ruchom Zastąpienie w celu zwrócenia opisu obiektu.|

## <a name="remarks"></a>Uwagi

`CComCoClass` zapewnia metody pobierania identyfikatora CLSID obiektu, ustawiania informacji o błędach i tworzenia wystąpień klasy. Każda Klasa zarejestrowana w mapie obiektów powinna pochodzić od `CComCoClass` .

`CComCoClass` definiuje także domyślną fabrykę klas i model agregacji dla obiektu. `CComCoClass` program używa następujących dwóch makr:

- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) Deklaruje fabrykę klas do [CComClassFactory](../../atl/reference/ccomclassfactory-class.md).

- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable) Deklaruje, że obiekt może być zagregowany.

Można zastąpić jedno z tych ustawień domyślnych, określając inne makro w definicji klasy. Na przykład, aby użyć [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) zamiast `CComClassFactory` , określ makro [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) :

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlcom. h

## <a name="ccomcoclasscreateinstance"></a><a name="createinstance"></a> CComCoClass:: CreateInstance

Za pomocą tych `CreateInstance` funkcji można utworzyć wystąpienie obiektu com i pobrać wskaźnik interfejsu bez użycia interfejsu API modelu com.

```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```

### <a name="parameters"></a>Parametry

*Pytania*<br/>
Interfejs COM, który powinien zostać zwrócony przez *PP*.

*punkOuter*<br/>
podczas Nieznana zewnętrzna lub kontrolka nieznana agregacji.

*miesięcznie*<br/>
określoną Adres zmiennej wskaźnika, która odbiera żądany wskaźnik interfejsu, jeśli Tworzenie zakończy się pomyślnie.

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT. Aby uzyskać opis możliwych zwracanych wartości, zobacz Funkcja [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) w Windows SDK.

### <a name="remarks"></a>Uwagi

Użyj pierwszego przeciążenia tej funkcji na potrzeby typowego tworzenia obiektów; Użyj drugiego przeciążenia, gdy zachodzi potrzeba zagregowania tworzonego obiektu.

Klasa ATL implementująca wymagany obiekt COM (czyli Klasa używana jako pierwszy parametr szablonu do [CComCoClass](../../atl/reference/ccomcoclass-class.md)) musi znajdować się w tym samym projekcie co kod wywołujący. Tworzenie obiektu COM jest wykonywane przez fabrykę klasy zarejestrowanej dla tej klasy ATL.

Te funkcje są przydatne do tworzenia obiektów, których nie można utworzyć zewnętrznie przy użyciu makra [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto) . Są one również przydatne w sytuacjach, gdy chcesz uniknąć wydajności interfejsu API modelu COM.

Należy pamiętać, że interfejs *Q* musi mieć skojarzony identyfikator IID, który można pobrać za pomocą operatora [__uuidof](../../cpp/uuidof-operator.md) .

### <a name="example"></a>Przykład

W poniższym przykładzie `CDocument` jest wygenerowaną przez kreatora klasą ATL utworzoną z `CComCoClass` implementującą `IDocument` interfejs. Klasa jest zarejestrowana na mapie obiektu za pomocą makra OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO, więc klienci nie mogą tworzyć wystąpień dokumentu przy użyciu funkcji [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance). `CApplication` jest klasą coclass, która udostępnia metodę na jednym z własnych interfejsów COM do tworzenia wystąpień klasy dokumentu. Poniższy kod pokazuje, jak łatwo utworzyć wystąpienia klasy dokumentu przy użyciu `CreateInstance` składowej dziedziczonej z `CComCoClass` klasy bazowej.

[!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]

## <a name="ccomcoclasserror"></a><a name="error"></a> CComCoClass:: Error

Ta funkcja statyczna konfiguruje `IErrorInfo` interfejs, aby zapewnić klientowi informacje o błędzie.

```
static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance ());

static HRESULT Error(
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```

### <a name="parameters"></a>Parametry

*lpszDesc*<br/>
podczas Ciąg opisujący błąd. Wersja Unicode programu `Error` określa, że *lpszDesc* jest typu LPCOLESTR; wersja ANSI określa typ LPCSTR.

*IID*<br/>
podczas Identyfikator IID interfejsu definiujący błąd lub GUID_NULL (wartość domyślna), jeśli błąd jest zdefiniowany przez system operacyjny.

*hRes*<br/>
podczas Wartość HRESULT, która ma zostać zwrócona do obiektu wywołującego. Wartość domyślna to 0. Aby uzyskać więcej informacji na temat *hRes*, zobacz uwagi.

*nID*<br/>
podczas Identyfikator zasobu, w którym jest przechowywany ciąg opisu błędu. Ta wartość powinna należeć do przedziału od 0x0200 do 0xFFFF włącznie. W kompilacjach debugowania wynikiem **będzie wynik** , jeśli *NID* nie indeksuje poprawnego ciągu. W kompilacjach wydania ciąg opisu błędu zostanie ustawiony na "nieznany błąd".

*dwHelpID*<br/>
podczas Identyfikator kontekstu pomocy dla błędu.

*lpszHelpFile*<br/>
podczas Ścieżka i nazwa pliku pomocy opisującego błąd.

*hInst*<br/>
podczas Dojście do zasobu. Domyślnie ten parametr to `_AtlModule::GetResourceInstance` , gdzie `_AtlModule` jest globalnym wystąpieniem [CAtlModule](../../atl/reference/catlmodule-class.md).

### <a name="return-value"></a>Wartość zwracana

Standardowa wartość HRESULT. Aby uzyskać szczegółowe informacje, zobacz uwagi.

### <a name="remarks"></a>Uwagi

Do wywołania `Error` obiekt musi implementować `ISupportErrorInfo Interface` interfejs.

Jeśli parametr *hRes* jest różny od zera, `Error` zwraca wartość *hRes*. Jeśli *hRes* ma wartość zero, wówczas pierwsze cztery wersje `Error` zwracanych DISP_E_EXCEPTION. Ostatnie dwie wersje zwracają wynik **MAKE_HRESULT makro (1, FACILITY_ITF,** *NID* **)**.

## <a name="ccomcoclassgetobjectclsid"></a><a name="getobjectclsid"></a> CComCoClass:: GetObjectCLSID

Zapewnia spójny sposób pobierania identyfikatora CLSID obiektu.

```
static const CLSID& WINAPI GetObjectCLSID();
```

### <a name="return-value"></a>Wartość zwracana

Identyfikator klasy obiektu.

## <a name="ccomcoclassgetobjectdescription"></a><a name="getobjectdescription"></a> CComCoClass:: GetObjectDescription

Ta funkcja statyczna Pobiera opis tekstu obiektu klasy.

```
static LPCTSTR WINAPI GetObjectDescription();
```

### <a name="return-value"></a>Wartość zwracana

Opis obiektu klasy.

### <a name="remarks"></a>Uwagi

Domyślna implementacja zwraca wartość NULL. Tę metodę można zastąpić za pomocą makra [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description) . Na przykład:

[!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]

`GetObjectDescription` jest wywoływana przez `IComponentRegistrar::GetComponents` . `IComponentRegistrar` jest interfejsem automatyzacji, który umożliwia rejestrowanie i Wyrejestrowywanie poszczególnych składników w bibliotece DLL. Podczas tworzenia obiektu rejestratora składników przy użyciu Kreatora projektu ATL Kreator automatycznie implementuje `IComponentRegistrar` interfejs. `IComponentRegistrar` jest zwykle używany przez program Microsoft Transaction Server.

Aby uzyskać więcej informacji na temat Kreatora projektu ATL, zobacz artykuł [Tworzenie projektu ATL](../../atl/reference/creating-an-atl-project.md).

## <a name="see-also"></a>Zobacz też

[Przegląd klas](../../atl/atl-class-overview.md)
