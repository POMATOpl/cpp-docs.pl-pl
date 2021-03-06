---
description: 'Dowiedz się więcej na temat: Klasa CAtlDllModuleT'
title: Klasa CAtlDllModuleT
ms.date: 11/04/2016
f1_keywords:
- CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::CAtlDllModuleT
- ATLBASE/ATL::CAtlDllModuleT::DllCanUnloadNow
- ATLBASE/ATL::CAtlDllModuleT::DllGetClassObject
- ATLBASE/ATL::CAtlDllModuleT::DllMain
- ATLBASE/ATL::CAtlDllModuleT::DllRegisterServer
- ATLBASE/ATL::CAtlDllModuleT::DllUnregisterServer
- ATLBASE/ATL::CAtlDllModuleT::GetClassObject
helpviewer_keywords:
- CAtlDllModuleT class
ms.assetid: 351d5767-8257-4878-94be-45a85e31a72d
ms.openlocfilehash: b6b6f87fc77187b150824fcd67fae254eb6d8f57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147436"
---
# <a name="catldllmodulet-class"></a>Klasa CAtlDllModuleT

Ta klasa reprezentuje moduł biblioteki DLL.

## <a name="syntax"></a>Składnia

```cpp
template <class T>
class ATL_NO_VTABLE CAtlDllModuleT : public CAtlModuleT<T>
```

### <a name="parameters"></a>Parametry

*T*<br/>
Klasa pochodna `CAtlDllModuleT` .

## <a name="members"></a>Elementy członkowskie

### <a name="public-constructors"></a>Konstruktory publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAtlDllModuleT::CAtlDllModuleT](#catldllmodulet)|Konstruktor.|
|[CAtlDllModuleT:: ~ CAtlDllModuleT](#dtor)|Destruktor.|

### <a name="public-methods"></a>Metody publiczne

|Nazwa|Opis|
|----------|-----------------|
|[CAtlDllModuleT::D llCanUnloadNow](#dllcanunloadnow)|Testuje, czy biblioteka DLL może zostać zwolniona.|
|[CAtlDllModuleT::D llGetClassObject](#dllgetclassobject)|Zwraca fabrykę klas.|
|[CAtlDllModuleT::D llMain](#dllmain)|Opcjonalny punkt wejścia do biblioteki dołączanej dynamicznie (DLL).|
|[CAtlDllModuleT::D llRegisterServer](#dllregisterserver)|Dodaje wpisy do rejestru systemowego dla obiektów w bibliotece DLL.|
|[CAtlDllModuleT::D llUnregisterServer](#dllunregisterserver)|Usuwa wpisy z rejestru systemowego dla obiektów w bibliotece DLL.|
|[CAtlDllModuleT:: GetClassObject](#getclassobject)|Zwraca fabrykę klas. Wywoływane przez [DllGetClassObject](#dllgetclassobject).|

## <a name="remarks"></a>Uwagi

`CAtlDllModuleT` reprezentuje moduł dla biblioteki dołączanej dynamicznie (DLL) i udostępnia funkcje używane przez wszystkie projekty DLL. Ta specjalizacja klasy [CAtlModuleT](../../atl/reference/catlmodulet-class.md) obejmuje obsługę rejestracji.

Aby uzyskać więcej informacji na temat modułów w ATL, zobacz [klasy modułów ATL](../../atl/atl-module-classes.md).

## <a name="inheritance-hierarchy"></a>Hierarchia dziedziczenia

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CAtlDllModuleT`

## <a name="requirements"></a>Wymagania

**Nagłówek:** atlbase. h

## <a name="catldllmoduletcatldllmodulet"></a><a name="catldllmodulet"></a> CAtlDllModuleT::CAtlDllModuleT

Konstruktor.

```cpp
CAtlDllModuleT() throw();
```

## <a name="catldllmoduletcatldllmodulet"></a><a name="dtor"></a> CAtlDllModuleT:: ~ CAtlDllModuleT

Destruktor.

```cpp
~CAtlDllModuleT() throw();
```

## <a name="catldllmoduletdllcanunloadnow"></a><a name="dllcanunloadnow"></a> CAtlDllModuleT::D llCanUnloadNow

Testuje, czy biblioteka DLL może zostać zwolniona.

```cpp
HRESULT DllCanUnloadNow() throw();
```

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK, jeśli biblioteka DLL może zostać zwolniona, lub S_FALSE, jeśli nie może.

## <a name="catldllmoduletdllgetclassobject"></a><a name="dllgetclassobject"></a> CAtlDllModuleT::D llGetClassObject

Zwraca fabrykę klas.

```cpp
HRESULT DllGetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parametry

*rclsid*<br/>
Identyfikator CLSID obiektu, który ma zostać utworzony.

*riid*<br/>
Identyfikator IID żądanego interfejsu.

*ppv*<br/>
Wskaźnik do wskaźnika interfejsu identyfikowanego przez *riid*. Jeśli obiekt nie obsługuje tego interfejsu, *PPV* ma wartość null.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

## <a name="catldllmoduletdllmain"></a><a name="dllmain"></a> CAtlDllModuleT::D llMain

Opcjonalny punkt wejścia do biblioteki dołączanej dynamicznie (DLL).

```cpp
BOOL WINAPI DllMain(DWORD dwReason, LPVOID /* lpReserved*/) throw();
```

### <a name="parameters"></a>Parametry

*Prawidłowych dwreason*<br/>
W przypadku ustawienia wartości DLL_PROCESS_ATTACH wywołania powiadomień DLL_THREAD_ATTACH i DLL_THREAD_DETACH są wyłączone.

*lpReserved*<br/>
Zarezerwowany.

### <a name="return-value"></a>Wartość zwracana

Zawsze zwraca wartość TRUE.

### <a name="remarks"></a>Uwagi

Wyłączenie wywołań powiadomień DLL_THREAD_ATTACH i DLL_THREAD_DETACH może być przydatną optymalizacją dla aplikacji wielowątkowych, które mają wiele bibliotek DLL, które często tworzą i usuwają wątki, a biblioteki DLL nie potrzebują tych powiadomień na poziomie wątku w przypadku załączników/odłączeń.

## <a name="catldllmoduletdllregisterserver"></a><a name="dllregisterserver"></a> CAtlDllModuleT::D llRegisterServer

Dodaje wpisy do rejestru systemowego dla obiektów w bibliotece DLL.

```cpp
HRESULT DllRegisterServer(BOOL bRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parametry

*bRegTypeLib*<br/>
Ma wartość TRUE, jeśli biblioteka typów ma zostać zarejestrowana. Wartość domyślna to TRUE.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

## <a name="catldllmoduletdllunregisterserver"></a><a name="dllunregisterserver"></a> CAtlDllModuleT::D llUnregisterServer

Usuwa wpisy z rejestru systemowego dla obiektów w bibliotece DLL.

```cpp
HRESULT DllUnregisterServer(BOOL bUnRegTypeLib = TRUE) throw();
```

### <a name="parameters"></a>Parametry

*bUnRegTypeLib*<br/>
Ma wartość TRUE, jeśli biblioteka typów ma zostać usunięta z rejestru. Wartość domyślna to TRUE.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

## <a name="catldllmoduletgetclassobject"></a><a name="getclassobject"></a> CAtlDllModuleT:: GetClassObject

Tworzy obiekt o określonym identyfikatorze CLSID.

```cpp
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>Parametry

*rclsid*<br/>
Identyfikator CLSID obiektu, który ma zostać utworzony.

*riid*<br/>
Identyfikator IID żądanego interfejsu.

*ppv*<br/>
Wskaźnik do wskaźnika interfejsu identyfikowanego przez *riid*. Jeśli obiekt nie obsługuje tego interfejsu, *PPV* ma wartość null.

### <a name="return-value"></a>Wartość zwracana

Zwraca S_OK po powodzeniu lub błąd HRESULT w przypadku niepowodzenia.

### <a name="remarks"></a>Uwagi

Ta metoda jest wywoływana przez [CAtlDllModuleT::D llgetclassobject](#dllgetclassobject) i jest dołączana do zgodności z poprzednimi wersjami.

## <a name="see-also"></a>Zobacz też

[Klasa CAtlModuleT](../../atl/reference/catlmodulet-class.md)<br/>
[Klasa CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)<br/>
[Przegląd klas](../../atl/atl-class-overview.md)<br/>
[Klasy modułów](../../atl/atl-module-classes.md)
