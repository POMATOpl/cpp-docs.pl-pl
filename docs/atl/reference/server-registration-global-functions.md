---
description: 'Dowiedz się więcej na temat: funkcje globalne rejestracji serwera'
title: Funkcje globalne rejestracji serwera
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
ms.openlocfilehash: 7841c162c2c7c0c93cd8edcd8fd6d78ae4bb2b1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157740"
---
# <a name="server-registration-global-functions"></a>Funkcje globalne rejestracji serwera

Te funkcje zapewniają obsługę rejestrowania i wyrejestrowywania obiektów serwera na mapie obiektów.

> [!IMPORTANT]
> Funkcje wymienione w poniższej tabeli nie mogą być używane w aplikacjach, które są wykonywane w środowisko wykonawcze systemu Windows.

|Nazwa|Opis|
|-|-|
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|Ta funkcja jest wywoływana, aby zarejestrować każdy obiekt na mapie obiektów.|
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|Ta funkcja jest wywoływana, aby wyrejestrować każdy obiekt na mapie obiektów.|
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|Ta funkcja jest wywoływana, aby zarejestrować obiekty klasy.|
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|Ta funkcja jest wywoływana, aby odwołać obiekty klasy z modułu COM.|
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|Ta funkcja jest wywoływana w celu pobrania obiektu klasy.|

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlbase. h

## <a name="atlcommoduleregisterserver"></a><a name="atlcommoduleregisterserver"></a> AtlComModuleRegisterServer

Ta funkcja jest wywoływana, aby zarejestrować każdy obiekt na mapie obiektów.

```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Parametry

*pComModule*<br/>
Wskaźnik do modułu COM.

*bRegTypeLib*<br/>
Ma wartość TRUE, jeśli biblioteka typów ma zostać zarejestrowana.

*pCLSID*<br/>
Wskazuje identyfikator CLSID obiektu, który ma zostać zarejestrowany. Jeśli wartość jest równa NULL, wszystkie obiekty w mapie obiektów zostaną zarejestrowane.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

`AtlComModuleRegisterServer` przegląda mapę obiektu automatycznie wygenerowaną ATL i rejestruje każdy obiekt na mapie. Jeśli *pCLSID* nie ma wartości null, rejestrowany jest tylko obiekt, do którego odwołuje się *pCLSID* ; w przeciwnym razie wszystkie obiekty są zarejestrowane.

Ta funkcja jest wywoływana przez [CAtlComModule:: RegisterServer](catlcommodule-class.md#registerserver).

## <a name="atlcommoduleunregisterserver"></a><a name="atlcommoduleunregisterserver"></a> AtlComModuleUnregisterServer

Ta funkcja jest wywoływana, aby wyrejestrować każdy obiekt na mapie obiektów.

```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>Parametry

*pComModule*<br/>
Wskaźnik do modułu COM.

*bUnRegTypeLib*<br/>
Ma wartość TRUE, jeśli biblioteka typów ma zostać zarejestrowana.

*pCLSID*<br/>
Wskazuje identyfikator CLSID obiektu, który ma zostać wyrejestrowany. Jeśli wartość NULL wszystkie obiekty w mapie obiektów zostaną wyrejestrowane.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

`AtlComModuleUnregisterServer` przegląda mapowanie obiektu ATL i wyrejestrowuje każdy obiekt na mapie. Jeśli *pCLSID* nie ma wartości null, tylko obiekt, do którego odwołuje się *pCLSID* , zostanie wyrejestrowany. w przeciwnym razie wszystkie obiekty są wyrejestrowani.

Ta funkcja jest wywoływana przez [CAtlComModule:: UnregisterServer](catlcommodule-class.md#unregisterserver).

## <a name="atlcommoduleregisterclassobjects"></a><a name="atlcommoduleregisterclassobjects"></a> AtlComModuleRegisterClassObjects

Ta funkcja jest wywoływana, aby zarejestrować obiekty klasy.

```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```

### <a name="parameters"></a>Parametry

*pComModule*<br/>
Wskaźnik do modułu COM.

*dwClsContext*<br/>
Określa kontekst, w którym obiekt klasy ma być uruchamiany. Możliwe wartości to CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER lub CLSCTX_LOCAL_SERVER. Aby uzyskać więcej informacji, zobacz [CLSCTX](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx) .

*flagiDW*<br/>
Określa typy połączeń do obiektu klasy. Możliwe wartości to REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE lub REGCLS_MULTI_SEPARATE. Aby uzyskać więcej informacji, zobacz [REGCLS](/windows/win32/api/combaseapi/ne-combaseapi-regcls) .

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Ta funkcja pomocnika jest wykorzystywana przez [CComModule:: RegisterClassObjects](ccommodule-class.md#registerclassobjects) (przestarzałe w ATL 7,0) i [CAtlExeModuleT:: RegisterClassObjects](catlexemodulet-class.md#registerclassobjects).

## <a name="atlcommodulerevokeclassobjects"></a><a name="atlcommodulerevokeclassobjects"></a> AtlComModuleRevokeClassObjects

Ta funkcja jest wywoływana, aby usunąć fabrykę/fabryki klas z tabeli działających obiektów.

```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```

### <a name="parameters"></a>Parametry

*pComModule*<br/>
Wskaźnik do modułu COM.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Ta funkcja pomocnika jest wykorzystywana przez [CComModule:: RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (przestarzałe w ATL 7,0) i [CAtlExeModuleT:: RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects).

## <a name="atlcommodulegetclassobject"></a><a name="atlcommodulegetclassobject"></a> AtlComModuleGetClassObject

Ta funkcja jest wywoływana, aby zwrócić fabrykę klasy.

```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```

### <a name="parameters"></a>Parametry

*pComModule*<br/>
Wskaźnik do modułu COM.

*rclsid*<br/>
Identyfikator CLSID obiektu, który ma zostać utworzony.

*riid*<br/>
Identyfikator IID żądanego interfejsu.

*ppv*<br/>
Wskaźnik do wskaźnika interfejsu identyfikowanego przez *riid*. Jeśli obiekt nie obsługuje tego interfejsu, *PPV* ma wartość null.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Ta funkcja pomocnika jest wykorzystywana przez [CComModule:: GetClassObject](ccommodule-class.md#getclassobject) (przestarzałe w ATL 7,0) i [CAtlDllModuleT:: GetClassObject](catldllmodulet-class.md#getclassobject).

## <a name="see-also"></a>Zobacz też

[Funkcje](../../atl/reference/atl-functions.md)
