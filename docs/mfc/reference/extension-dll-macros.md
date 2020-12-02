---
title: Makra i funkcje do zarządzania bibliotekami DLL
description: Przewodnik referencyjny dotyczący makr i funkcji MFC związanych z zarządzaniem bibliotekami DLL.
ms.date: 11/30/2020
helpviewer_keywords:
- module macros in MFC
ms.openlocfilehash: b70c4506d49f656e1570f2500cfaa39c28053291
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440322"
---
# <a name="macros-and-functions-for-managing-dlls"></a>Makra i funkcje do zarządzania bibliotekami DLL

| Nazwa | Opis |
|--|--|
| [`AFX_EXT_CLASS`](#afx_ext_class)] | Eksportuje klasy. |
| [`AFX_MANAGE_STATE`](#afx_manage_state) | Ochrona wyeksportowanej funkcji w bibliotece DLL. |
| [`AfxOleInitModule`](#afxoleinitmodule) | Zapewnia obsługę OLE przy użyciu zwykłej biblioteki MFC DLL, która jest dynamicznie połączona z MFC. |
| [`AfxNetInitModule`](#afxnetinitmodule) | Zapewnia obsługę funkcji MFC Sockets ze zwykłej biblioteki MFC DLL, która jest dynamicznie połączona z MFC. |
| [`AfxGetAmbientActCtx`](#afxgetambientactctx) | Pobiera bieżący stan flagi stanu dla modułu. |
| [`AfxGetStaticModuleState`](#afxgetstaticmodulestate) | Ustawia stan modułu przed inicjalizacją i przywraca poprzedni stan modułu po oczyszczeniu. |
| [`AfxInitExtensionModule`](#afxinitextensionmodule) | Inicjuje bibliotekę DLL. |
| [`AfxSetAmbientActCtx`](#afxsetambientactctx) | Ustaw flagę stanu dla modułu, która ma wpływ na zachowanie WinSxS MFC. |
| [`AfxTermExtensionModule`](#afxtermextensionmodule) | Umożliwia MFC czyszczenie biblioteki DLL rozszerzenia MFC, gdy każdy proces odłącza się od biblioteki DLL. |

## <a name="afx_ext_class"></a><a name="afx_ext_class"></a> `AFX_EXT_CLASS`

[Biblioteki DLL rozszerzeń MFC](../../build/extension-dlls.md) używają makro `AFX_EXT_CLASS` do eksportowania klas; pliki wykonywalne łączące się z biblioteką DLL rozszerzenia MFC używają makra do importowania klas.

### <a name="remarks"></a>Uwagi

Za pomocą `AFX_EXT_CLASS` makra te same pliki nagłówkowe, które służą do kompilowania biblioteki DLL rozszerzenia MFC mogą być używane z plikami wykonywalnymi, które łączą się z biblioteką DLL.

W pliku nagłówkowym biblioteki DLL Dodaj `AFX_EXT_CLASS` słowo kluczowe do deklaracji klasy w następujący sposób:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Aby uzyskać więcej informacji, zobacz [Eksportowanie i importowanie `AFX_EXT_CLASS` za pomocą ](../../build/exporting-and-importing-using-afx-ext-class.md).

### <a name="requirements"></a>Wymagania

**Nagłówek:**\<afxv_dll.h>

## <a name="afx_manage_state"></a><a name="afx_manage_state"></a> `AFX_MANAGE_STATE`

Wywołaj to makro, aby chronić funkcję eksportowaną w bibliotece DLL.

### <a name="syntax"></a>Składnia

```cpp
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )
```

### <a name="parameters"></a>Parametry

*`pModuleState`*<br/>
Wskaźnik do `AFX_MODULE_STATE` struktury.

### <a name="remarks"></a>Uwagi

Gdy to makro jest wywoływane, *`pModuleState`* jest efektywnym stanem modułu dla reszty zakresu bezpośrednio zawierającego. Po opuszczeniu zakresu poprzedni stan obowiązującego modułu zostanie automatycznie przywrócony.

`AFX_MODULE_STATE`Struktura zawiera dane globalne dla modułu, czyli część stanu modułu, który jest wypychany lub zdjęte.

Domyślnie MFC używa dojścia do zasobów głównej aplikacji do ładowania szablonu zasobu. W przypadku wyeksportowanej funkcji w bibliotece DLL, takiej jak ta, która powoduje uruchomienie okna dialogowego w bibliotece DLL, szablon zasobu jest przechowywany w module DLL. Upewnij się, że stan modułu jest włączony, aby można było użyć prawidłowego uchwytu. Stan można zmienić, dodając następujący kod na początku funkcji:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

To makro zamienia bieżący stan modułu na stan zwrócony z [`AfxGetStaticModuleState`](#afxgetstaticmodulestate) do do końca bieżącego zakresu.

Aby uzyskać więcej informacji na temat stanów modułów i MFC, zobacz [Zarządzanie danymi stanu modułów MFC](../managing-the-state-data-of-mfc-modules.md) i [uwagami technicznymi 58](../tn058-mfc-module-state-implementation.md).

> [!NOTE]
> Gdy MFC tworzy kontekst aktywacji dla zestawu, używa go [`AfxWinInit`](application-information-and-management.md#afxwininit) do utworzenia kontekstu i `AFX_MANAGE_STATE` aktywowania i dezaktywowania go. Należy również pamiętać, że `AFX_MANAGE_STATE` włączono obsługę statycznych BIBLIOTEK MFC, a także BIBLIOTEK MFC DLL, aby umożliwić wykonywanie kodu MFC w odpowiednim kontekście aktywacji wybranym przez użytkownika dll. Aby uzyskać więcej informacji, zobacz [Obsługa kontekstów aktywacji w stanie modułu MFC](../support-for-activation-contexts-in-the-mfc-module-state.md).

### <a name="requirements"></a>Wymagania

**Nagłówek:**\<afxstat_.h>

## <a name="a-nameafxoleinitmodule-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> `AfxOleInitModule`

Aby zapewnić obsługę OLE ze zwykłej biblioteki MFC DLL, która jest dynamicznie połączona z MFC, Wywołaj tę funkcję w funkcji regularnej biblioteki DLL MFC, `CWinApp::InitInstance` Aby zainicjować bibliotekę MFC OLE dll.

### <a name="syntax"></a>Składnia

```cpp
void AFXAPI AfxOleInitModule( );
```

### <a name="remarks"></a>Uwagi

Biblioteka MFC OLE DLL jest biblioteką DLL rozszerzenia MFC; Aby biblioteka DLL rozszerzenia MFC mogła zostać podłączona do `CDynLinkLibrary` łańcucha, musi utworzyć `CDynLinkLibrary` obiekt w kontekście każdego modułu, który będzie go używać. `AfxOleInitModule` tworzy `CDynLinkLibrary` obiekt w kontekście regularnej biblioteki DLL MFC, dzięki czemu będzie on połączony z `CDynLinkLibrary` łańcuchem obiektów zwykłej biblioteki MFC DLL.

Jeśli tworzysz formant OLE i używasz `COleControlModule` , nie należy wywoływać, `AfxOleInitModule` ponieważ `InitInstance` funkcja członkowska dla `COleControlModule` wywołań `AfxOleInitModule` .

### <a name="requirements"></a>Wymagania

**Nagłówek**: \<afxdll_.h>

## <a name="afxnetinitmodule"></a><a name="afxnetinitmodule"></a> `AfxNetInitModule`

W przypadku obsługi usługi MFC Sockets ze zwykłej biblioteki MFC DLL, która jest dynamicznie połączona z MFC, Dodaj wywołanie tej funkcji w funkcji regularnej biblioteki DLL MFC, `CWinApp::InitInstance` Aby zainicjować bibliotekę DLL usługi MFC Sockets.

### <a name="syntax"></a>Składnia

```cpp
void AFXAPI AfxNetInitModule( );
```

### <a name="remarks"></a>Uwagi

Biblioteka DLL Sockets MFC jest biblioteką DLL rozszerzenia MFC; Aby biblioteka DLL rozszerzenia MFC mogła zostać podłączona do `CDynLinkLibrary` łańcucha, musi utworzyć `CDynLinkLibrary` obiekt w kontekście każdego modułu, który będzie go używać. `AfxNetInitModule` tworzy `CDynLinkLibrary` obiekt w kontekście regularnej biblioteki DLL MFC, dzięki czemu będzie on połączony z `CDynLinkLibrary` łańcuchem obiektów zwykłej biblioteki MFC DLL.

### <a name="requirements"></a>Wymagania

**Nagłówek:**\<afxdll_.h>

## <a name="afxgetambientactctx"></a><a name="afxgetambientactctx"></a> `AfxGetAmbientActCtx`

Użyj tej funkcji, aby uzyskać bieżący stan flagi stanu dla modułu, która ma wpływ na zachowanie WinSxS MFC.

### <a name="syntax"></a>Składnia

```cpp
BOOL AFXAPI AfxGetAmbientActCtx();
```

### <a name="return-value"></a>Wartość zwracana

Bieżąca wartość flagi stanu modułu.

### <a name="remarks"></a>Uwagi

Po ustawieniu flagi (co jest ustawieniem domyślnym), a wątek przechodzi do modułu MFC (zobacz [`AFX_MANAGE_STATE`](#afx_manage_state) ), kontekst modułu jest aktywowany.

Jeśli flaga nie jest ustawiona, kontekst modułu nie jest aktywowany przy wpisie.

Kontekst modułu jest określany na podstawie jego manifestu, często osadzony w zasobach modułu.

### <a name="requirements"></a>Wymagania

**Nagłówek:**\<afxcomctl32.h>

## <a name="afxgetstaticmodulestate"></a><a name="afxgetstaticmodulestate"></a> `AfxGetStaticModuleState`

Wywołaj tę funkcję, aby ustawić stan modułu przed inicjalizacją i przywrócić poprzedni stan modułu po oczyszczeniu.

### <a name="syntax"></a>Składnia

```cpp
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );
```

### <a name="return-value"></a>Wartość zwracana

Wskaźnik do `AFX_MODULE_STATE` struktury.

### <a name="remarks"></a>Uwagi

`AFX_MODULE_STATE`Struktura zawiera dane globalne dla modułu, czyli część stanu modułu, który jest wypychany lub zdjęte.

Domyślnie MFC używa dojścia do zasobów głównej aplikacji do ładowania szablonu zasobu. W przypadku wyeksportowanej funkcji w bibliotece DLL, takiej jak ta, która powoduje uruchomienie okna dialogowego w bibliotece DLL, szablon zasobu jest przechowywany w module DLL. Upewnij się, że stan modułu jest włączony, aby można było użyć prawidłowego uchwytu. Stan można zmienić, dodając następujący kod na początku funkcji:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));
```

To makro zamienia bieżący stan modułu na stan zwrócony z `AfxGetStaticModuleState` do do końca bieżącego zakresu.

Aby uzyskać więcej informacji na temat stanów modułów i MFC, zobacz [Zarządzanie danymi stanu modułów MFC](../managing-the-state-data-of-mfc-modules.md) i [uwagami technicznymi 58](../tn058-mfc-module-state-implementation.md).

### <a name="requirements"></a>Wymagania

**Nagłówek:**\<afxstat_.h>

## <a name="afxinitextensionmodule"></a><a name="afxinitextensionmodule"></a> `AfxInitExtensionModule`

Wywołaj tę funkcję w bibliotece DLL rozszerzenia MFC, `DllMain` Aby zainicjować bibliotekę DLL.

### <a name="syntax"></a>Składnia

```cpp
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );
```

### <a name="parameters"></a>Parametry

*`state`*<br/>
Odwołanie do struktury [ `AFX_EXTENSION_MODULE` struktury](afx-extension-module-structure.md) , która będzie zawierać stan modułu biblioteki DLL rozszerzenia MFC po zainicjowaniu. Stan zawiera kopię obiektów klasy środowiska uruchomieniowego, które zostały zainicjowane przez bibliotekę DLL rozszerzenia MFC jako część normalnej konstrukcji obiektu statycznego wykonane przed `DllMain` wprowadzeniem.

*`hModule`*<br/>
Dojście modułu DLL rozszerzenia MFC.

### <a name="return-value"></a>Wartość zwracana

`TRUE` Jeśli biblioteka DLL rozszerzenia MFC została pomyślnie zainicjowana; w przeciwnym razie `FALSE` .

### <a name="remarks"></a>Uwagi

Przykład:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL;
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;
...
```

`AfxInitExtensionModule` tworzy kopię HMODULE biblioteki DLL i przechwytuje klasy środowiska uruchomieniowego biblioteki DLL ( `CRuntimeClass` struktury), a także jego fabryki obiektów `COleObjectFactory` do użycia w przyszłości podczas `CDynLinkLibrary` tworzenia obiektu.
Biblioteki DLL rozszerzenia MFC muszą wykonywać dwie rzeczy w `DllMain` funkcji:

- Wywołaj [`AfxInitExtensionModule`](#afxinitextensionmodule) i sprawdź wartość zwracaną.

- Utwórz `CDynLinkLibrary` obiekt, jeśli biblioteka DLL będzie eksportować obiekty [ `CRuntimeClass` struktury](cruntimeclass-structure.md) lub ma własne zasoby niestandardowe.

Można wywołać `AfxTermExtensionModule` , aby oczyścić bibliotekę DLL rozszerzenia MFC, gdy każdy proces zostanie odłączony od biblioteki DLL rozszerzenia MFC (co się stanie w momencie zakończenia procesu lub gdy biblioteka DLL jest zwolniona przez `AfxFreeLibrary` wywołanie).

### <a name="requirements"></a>Wymagania

**Nagłówek:**\<afxdll_.h>

## <a name="afxsetambientactctx"></a><a name="afxsetambientactctx"></a> `AfxSetAmbientActCtx`

Ta funkcja służy do ustawiania flagi stanu dla modułu, która ma wpływ na zachowanie WinSxS MFC.

### <a name="syntax"></a>Składnia

```cpp
void AFXAPI AfxSetAmbientActCtx(BOOL bSet);
```

### <a name="parameters"></a>Parametry

*`bSet`*<br/>
Nowa wartość flagi stanu modułu.

### <a name="remarks"></a>Uwagi

Po ustawieniu flagi (co jest ustawieniem domyślnym), a wątek przechodzi do modułu MFC (zobacz [`AFX_MANAGE_STATE`](#afx_manage_state) ), kontekst modułu jest aktywowany.
Jeśli flaga nie jest ustawiona, kontekst modułu nie jest aktywowany przy wpisie.
Kontekst modułu jest określany na podstawie jego manifestu, często osadzony w zasobach modułu.

### <a name="example"></a>Przykład

```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
}
```

### <a name="requirements"></a>Wymagania

**Nagłówek:**\<afxcomctl32.h>

## <a name="afxtermextensionmodule"></a><a name="afxtermextensionmodule"></a> `AfxTermExtensionModule`

Wywołaj tę funkcję, aby umożliwić MFC czyszczenie biblioteki DLL rozszerzenia MFC, gdy każdy proces odłącza się od biblioteki DLL (co się stanie po zakończeniu procesu lub gdy biblioteka DLL zostanie zwolniona przez `AfxFreeLibrary` wywołanie).

### <a name="syntax"></a>Składnia

```cpp
void AFXAPI AfxTermExtensionModule( AFX_EXTENSION_MODULE& state, BOOL bAll = FALSE );
```

### <a name="parameters"></a>Parametry

*`state`*<br/>
Odwołanie do [`AFX_EXTENSION_MODULE`](afx-extension-module-structure.md) struktury zawierającej stan modułu DLL rozszerzenia MFC.

*`bAll`*<br/>
W przypadku wartości TRUE Wyczyść wszystkie moduły DLL rozszerzenia MFC. W przeciwnym razie wyczyść tylko bieżący moduł DLL.

### <a name="remarks"></a>Uwagi

`AfxTermExtensionModule` spowoduje usunięcie wszystkich magazynów lokalnych podłączonych do modułu i usunięcie wszelkich wpisów z pamięci podręcznej mapy komunikatów. Przykład:

```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL;
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;

        new CMyDynLinkLibrary(NVC_MFC_DLLDLL);

    }
    else if (dwReason == DLL_PROCESS_DETACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Terminating!\n");

        // Terminate the library before destructors are called
        AfxTermExtensionModule(NVC_MFC_DLLDLL);
    }
    return 1;   // ok
}
```

Jeśli aplikacja ładuje i zwalnia biblioteki DLL rozszerzenia MFC dynamicznie, należy wywołać metodę `AfxTermExtensionModule` . Ponieważ większość bibliotek DLL rozszerzeń MFC nie są ładowane dynamicznie (zwykle są one połączone za pośrednictwem ich bibliotek importu), wywołanie `AfxTermExtensionModule` zazwyczaj nie jest konieczne.

Biblioteki DLL rozszerzenia MFC muszą wywoływać [`AfxInitExtensionModule`](#afxinitextensionmodule) się w ich `DllMain` . Jeśli biblioteka DLL eksportuje [`CRuntimeClass`](cruntimeclass-structure.md) obiekty lub ma własne zasoby niestandardowe, należy również utworzyć `CDynLinkLibrary` obiekt w `DllMain` .

### <a name="requirements"></a>Wymagania

**Nagłówek:**\<afxdll_.h>

## <a name="see-also"></a>Zobacz też

[Makra i Globals](mfc-macros-and-globals.md)<br/>
[`AfxMessageBox`](cstring-formatting-and-message-box-display.md#afxmessagebox)<br/>
[Zarządzanie danymi stanu modułów MFC](../managing-the-state-data-of-mfc-modules.md)<br/>
